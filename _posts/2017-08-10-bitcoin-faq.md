---
layout: post
title: 比特币FAQ
mathjax: true
---

这篇比特币FAQ试图以FAQ的形式对比特币做一个简单的介绍。主要参考了[比特币白皮书](https://bitcoin.org/bitcoin.pdf)和普林斯顿大学的教材[《区块链：技术驱动金融》](https://u.jd.com/C2NMOf)，当然不可避免的包含了很多个人理解，欢迎探讨。

【2017-08-10初稿 / 2020-05-01小幅更新】

## 1.什么是比特币？

比特币是一种数字货币，它不依赖于某一个中心机构发行，而是依赖于互联网，基于密码学与分布式计算理论发行，人人都可以参与，它的总量有限，你可以把它想象成数字世界的一种黄金。

## 2.比特币有什么用？

比特币目前来说可以买到的最重要的东西是各国的货币。比特币作为一种数字货币，设计的初衷是想让其部分取代法币的，因此理论上它可以做任何钱可以做的事情，然而目前比特币直接购物仍然处在很早期的试验阶段，只有少量商家支持，其中最著名的是[微软](https://support.microsoft.com/zh-cn/help/13942/microsoft-account-how-to-use-bitcoin-to-add-money-to-your-account)。个人认为，阻碍比特币广泛应用的原因有三点，一是比特币支付目前的手续费偏高，对这个问题解决方案的争议甚至导致了比特币的分叉，即支持大区块的BCH和支持闪电网络的BCC；二是比特币的价格波动依然过于剧烈，更多的人把它当成了投资品或投机品；三是由于货币竞争的关系，大部分政府不太支持。

比特币现在被比喻为数字黄金，强调其储值的价值，然而比特币的支付价值才是其价值的基底，比特币如果最终无法用于普遍交易，其价值是值得怀疑的。

## 3.货币应当有国家信用背书，比特币没有，那么它的信用来自于哪里？

货币不一定要有国家信用背书，比如目前黄金还是可以用作国际通行的货币，货币的信用来自于有多少人相信它是货币，基于国家发行的纸币讲的是一个故事，基于密码学共识发行的比特币讲的是另一个故事，人类正是因为有了相信故事的能力，才能组织起更大规模的合作。（推荐阅读[《人类简史》](https://u.jd.com/oYTXl4)）

比特币的信用来源确实不好理解，它通过一种分布式的方式，对谁有多少钱这个问题达成了共识，只要参与这个系统的人都不可否认。你仍然需要理解的是，任何现代货币都是一个故事，货币的特点就是承认它有货币价值的人越多，它就越有货币价值，所以不可否认这里面有信仰成分。

## 4.这么说比特币就是一种传销或者说庞氏骗局嘛？

比特币和传销或庞氏骗局有一点相同，就是都需要一点点信仰。但是区别主要在于，对比特币的信仰会使得这种货币真正具有价值，它的价值就是作为一种货币存在，而不是其他的。而传销或者庞氏骗局带来的是更多的上当受骗的人。

比特币社区最早聚集的是一帮极客、电子朋克，他们希望的是建立一种新的货币体系，出发点绝不是骗钱。当然现在随着炒作比特币及区块链带来的巨大投机机会，**所谓的币圈可能是骗子密度最高的地方**，我给所有人的建议是不懂不投。

## 5.比特币究竟是怎么发行的？

除了创世区块的50个比特币，其它比特币都是对记账权的奖励，是在比特币网络运行中逐渐产生的。比特币需要定期对所有未确认的交易进行确认记账，而获得这个记账权的人将获得一定的比特币奖励，这些奖励是比特币原始的来源。每完成一批交易的记账，会打包成一个所谓的区块，每个区块都有一个指针指向前一个区块，因此被称为区块链。

## 6.谁有多少比特币是怎么记录的，有一个类似银行的账户么？

并没有类似银行账户的概念，比特币区块链只是记录了比特币的产生，以及它产生后所有的转账记录，当转账到某个地址而暂时没有转出时，则这个地址对这个比特币有所有权。

## 7.地址是什么？

地址可以理解为一种身份的证明，它是公开的，就像人人都能看见你家大门上的门牌号码一样。但是只有你自己有一把钥匙可以打开这扇门，这里用到了密码学中的签名算法，总的来说，你可以通过私钥来证明这个地址（公钥）归你管理。

## 8.比特币真的有一个一个的币吗？

上面我们说了，比特币区块链就是一个大帐本，所以并没有像人民币那样一个一个的币存在，而只是人人都能看到某个地址上有多少数量的比特币还没有花掉，而这个地址上的比特币只有持有私钥的人才能签名确认后花掉。因此，比特币实际上就是私钥，因为知道了私钥的人就能花掉比特币。

## 9.怎么保存比特币？

首先，如前所述，保存比特币首要的就是要保存私钥，这是所谓比特币钱包的主要功能，私钥泄露，则比特币丢失。此外，某个地址上有多少币是由公共的区块链来确定的，人人都可以连上比特币网络验证。

## 10.那么究竟谁来记账呢？我为什么要信任这个记账的人？

这是比特币的最精妙的设计。谁来记账是一个不确定的事情，每个节点都要去花很长的时间的计算（这需要消耗电力）来竞争这个记账的权力，获得记账权力后，如果随便乱记，那么会得不到其他节点的承认，这个生成的区块也将作废，虽然它也指向前一个区块形成了区块链，但是其他的人可以创建一个得到更多人承认的区块，产生一条更长的区块链，使得你这条短的区块链作废，浪费了电力而得不到打包的比特币奖励。这种精妙的设计通过人性是逐利的来达到了可信。

## 11. 挖矿与矿机是怎么一回事？

如上一点所述，争夺记账权的工作，也就是争夺对记账权的产生的比特币的奖励，就叫做挖矿。挖矿需要做一种哈希运算，让产生的哈希值包含一定数量的0，这个数量随着整个比特币网络哈希计算能力的提升而变大，使得区块打包的速度，也就是比特币生成的速度基本保持匀速。因此对计算速度的竞赛几乎是一种军备竞赛，从最早的CPU，GPU，一直到现在专门用来计算哈希值的矿机。

挖矿获得的奖励每隔一段时间会减半，慢慢的挖矿的人也就是矿工获得的奖励会越来越少，但比特币网络还有另一种机制：每个转账的人都要给一点点的转账费，作为矿工打包成功的奖励。

## 12.要怎么获得比特币呢？

由于目前通过竞争记账权也就是挖矿来获得比特币已经很专业很困难了，你必须买专业的矿机，加入所谓的矿池共同分担算力与比特币奖励才行。

最简单的办法还是找持有比特币的人用人民币来买，而买卖的方式，由于目前各国监管日益严格，交易平台大多已经不支持类似股票那种法币和比特币的直接交易，而只支持所谓的场外交易平台，也就是平台只做类似淘宝的担保，甚至连担保都没有只是发布信息，买卖比特币是C2C的。建议还是找一些有知名的有担保交易的大平台来购买，这里就不具体推荐了。

## 13.每个区块都会产生比特币，那么比特币会不会越来越多？

不会，每个区块的奖励每隔一段时间会减半，因此这是一个比例为1/2的等比数列，其总量为2100万个。因此比特币是设计为通缩的。

## 14.通缩的货币会越来越能换到更多的商品，那么理论上人人都会囤积比特币而不会花费比特币，那么它还有货币价值吗？

这确实是个好问题，我的理解是到一定的时候（比特币获得了它应有的地位，价格趋于稳定），比特币的拥有者自然会花比特币，就像现在拥有黄金的人一样。而且比特币可以和其他支持通胀的货币一起构成货币体系，就如同现在的黄金和法币一样。

## 15.我听说比特币是匿名的，所以都被用来买毒品？

比特币是一个公开的大帐本，但是它的地址是一串字符串，确实不能直接和人联系起来，因此有一定的匿名性。但是同时，它的账本是公开的，历史是不可更改可以随时查看的，从这个角度来说，它的匿名性还不如现金，只要把比特币地址和人取得了联系，就会追溯到所有的历史。实际上，用比特币贩毒的丝绸之路就被FBI抓了，所以比特币只是一种工具，并不天然的利于犯罪。

## 16.我听说比特币被用来洗钱？

就像上一问一样，我不认为比特币天然的利于洗钱，像中国政府已经开始监管交易所里用比特币进行洗钱的风险了，我觉得比特币还是应当更多的用于合规合法的应用。

## 17.既然比特币只是一种技术，而不由任何组织发行，那么岂不是随随便便都会产生类似的各种数字货币？那么比特币还有什么特别的价值吗？

确实是可以产生任意多种类似的数字货币，甚至它们的技术可以更优秀，但是有两点需要注意，比特币有先发优势，数字货币的价值需要越多参与者越好，在比特币已经占领高地的情况下其他数字货币很难从头开始取得优势地位，其次比特币自身也是可以进行技术革新而进化的。

## 18.比特币分裂是怎么回事？

比特币的相关规则和软件都是开源的，因此当有人不认同现有理念的时候，可以从某个区块开始，按照一个新的规则来打包交易（挖矿），而不接受原来的规则挖出来的区块，反之原来的规则也不再兼容这个新规则挖出来的区块，因此从这个区块开始，有两条区块链各自为政。在这个分类区块之前的未使用的比特币，可以同时转账到两个区块链分支，因此先当于1个原来的比特币变成了新的两个区块链上的各1个比特币。

## 19.这种分裂不是相当于比特币翻倍了么？

不完全是这样，分裂后的比特币由于参与者用脚投票，会出现价值上的差异，从既定事实的角度来说，只有价值高的那种才算是正宗的比特币。目前比特币的转账手续费较高，如何解决这个问题，产生了两个方案，一个是对区块的大小进行扩容，支持这个观点的人分叉出了被称为BCH的数字货币，而另外更复杂的协议仍暂时保留了BTC的称号。

## 20.比特币和区块链的关系？
区块链技术产生于比特币的研发，目前衍生出更多的技术，但是区块链技术的应用场景还需要进一步着实，目前的热潮泡沫很大，个人认为以比特币为代表的数字货币才是区块链真正落实了的应用场景。很多应用场景根本没必要使用区块链技术，但是数字货币却很可能是很有必要的，这一点在此不能详述，可以参见哈耶克的《货币的非国家化》。

## 21.如何投资比特币？
对大部分人来说，投资比特币唯一可行的方式就是用少量的完全不影响生活的钱购买比特币，长期持有5~10年。由于比特币价格仍在剧烈波动中，任何试图追涨杀跌的行为都将陷入赌徒的境地。**任何投资永远记得不懂不投。**