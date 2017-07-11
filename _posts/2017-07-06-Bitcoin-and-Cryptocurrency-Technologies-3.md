---
layout: post
title: 《比特币与加密货币技术3》：比特币的运行机制
categories: geek
mathjax: true
---

### 3.1 比特币的交易

比特币的交易过程就是不停的创造区块的过程。比特币并不是以账户为核心的系统，而是以交易为核心的系统，那些在交易输出中没有再作为输入的数额，是控制这个输出地址的人可以支配的，而每一次交易，一定要把所有输入的比特币花光。

如果不是恰好能花光，则会出现自己转账给自己的情况，但是这里的地址并不是同一个地址，而只是被同一个人控制而已。这种情况叫地址转换。

再核查交易的有效性时，只需要核查至该交易的输入引用的输出即可，所以核查很快。

可以使用一个新的地址合并自己的比特币，可以两个人共同支付到同一个地址（这两者其实是一样的）。

**交易语法** 一个比特币的交易分为三部分：

* 元数据：包括交易的规模，输入输出的数量，交易的哈希值，以及锁定时间。
* 输入：每个输入包括之前那笔交易的哈希值，输出索引以及签名（实际上也是脚本）。
* 输出：每个输出包括金额以及比特币脚本。输出总和小于等于输入总和。


### 3.2 比特币的脚本

最常见的比特币交易，就是通过某人的签名去取得他在前一笔交易中获得的资金。

交易的输入包括了脚本，为了确认一笔交易正确的获取了上一笔交易所输出的资金，我们把交易的输入脚本和上一笔交易的输出脚本串联起来。

```
<sig>
<pubKey>
---------------
OP_DUP
OP_HASH160
<pubKeyHash?>
OP_EQUALVERIFY
OP_CHECKSIG
```

比特币脚本语言时堆栈式语言，线性不能循环，执行要么完全成功要么完全无效。

一些常见的指令：

| 指令名称            | 功能                                  |
| --------------- | ----------------------------------- |
| OP_DUP          | 复制堆栈顶端数据                            |
| OP_HASH160      | 计算哈希函数两次：第一次用SHA-256，第二次用RIPEMD-160 |
| OP_EQUALVERIFY  | 如果输入是相同的，返回真；如果输入时不同的，返回假，整个交易作废    |
| OP_CHECKSIG     | 检查输入的签名是否有效                         |
| OP_CHECKMULTSIG | 检查再交易中t个公钥（地址）对应的t个签名是否有效           |

上述常见脚本执行的堆栈变化情况：

```
----------执行<sig>
<sig>
----------执行<pubKey>
<pubKey>
<sig>
----------执行OP_DUP
<pubKey>
<pubKey>
<sig>
----------执行OP_HASH160
<pubKeyHash>
<pubKey>
<sig>
----------执行<pubKeyHash?>
<pubKeyHash?>
<pubKeyHash>
<pubKey>
<sig>
----------执行OP_EQUALVERIFY
<pubKey>
<sig>
----------执行OP_CHECKSIG
true
```

实际中绝大部分脚本都是如此，每个节点都有支持的指令的白名单。

使用OP_RETURN指令可以进行销毁证明，它以抛出错误的形式借书脚本，其后的指令都不会执行，但是可以往脚本中植入任意信息。（据此可以发起一笔极小额的比特币交易，将信息永久存储再区块链上。）

支付到脚本 (P2SH)：收款方要求付款方支付比特币到某个脚本地址（哈希值），取款的时候，收款方提供对应的脚本并提供数据通过脚本的验证。P2SH脚本只是对堆栈最顶层的数据进行哈希计算，校验一致后将堆栈最顶层的数据重新解读为一系列指令运行。P2SH简化了输出脚本，复杂性都由输入脚本提供。

### 3.3 比特币脚本的应用

**第三方支付交易** 使用多重签名，付款方、收款方、仲裁方三者间有两者签名才能成功交易。

**绿色地址** 中心机构（银行）记账保证零确认支付。这种信任是有风险的。

**高效小额支付** 付款方生成一系列重复交易，逐渐增加支付额，收款方确认最后一个交易。为了防止收款方恶意不确认，交易将设定锁定时间，超时后将取消。

**智能合约** 比特币系统里可以用技术手段来强制执行的合约。

### 3.4 比特币的区块

区块链由俩个基于哈希值的数据结构结合而成：第一个数据结构是区块的哈希链，第二个数据结构交易构成的梅克尔树。

区块头部有指向上一个区域的指针，包含了挖矿谜题的相关信息，区块头部的哈希函数必须以一大堆零开头，包含矿工可以修改的临时随机数、一个时间戳和一个表示难度的点数，要验证一个区块的链。只要检查头部即可。

每个区块的梅克尔树上有一个特殊的交易——币基交易，输出代表挖矿收入，由区块奖励与交易费构成，此外，矿工还可在币基参数中放入任何值。

比特币的区块结构可以参考blockchain.info查看。

### 3.5 比特币网络

比特币网络运行在TCP网络上，每个节点与其他的随机节点相连，一个新节点加入网络，只需要知道网络中的其中一个节点即可，它会重复询问自己的邻居知道哪些邻居。

交易通过flooding协议完成传播，节点会进行四种校验：验证交易在当前的区块链中是有效的，检查是否双重支付，检查节点是否接收过该交易信息，检查脚本是否在白名单上。竞态条件通过区块的打包来打破。

区块的传播与交易的传播类似。

校验区块需要确认区块头部的哈希值在可以接受的范围内，还要确认区块里的每一个交易。

比特币网络的节点并不多（因为很多节点都是临时在线），完整的交易信息量为几十个GB。

SPV节点只存储它们所关心的、需要进行校核的部分交易，只需要几十MB即可。

### 3.6 限制与优化

比特币的总体数量和记账奖励对现有框架影响太大，社区基本达成共识不会去更改。

比特币现有的交易吞吐量太低：每个区块限定1MB，最多容纳4000个交易，平均10分钟产生一个区块，所以每秒钟只能处理7个交易。

此外比特币使用的密码算法不一定会一直安全。

修订协议带来的后果可以分为**硬分叉**和**软分叉**。硬分叉使得前一版的协议失效，老节点不再接受新的区块，从而出现了分叉。软分叉加入新的特征，使得现有的校验规则更加严格。老节点会接受新的节点。（P2SH就是通过软分叉实现的）。
