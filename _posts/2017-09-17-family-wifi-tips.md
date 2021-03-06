---
layout: post
title: 家庭wifi组网经验
categories: geek
---

之前这边的房子比较少住，无线路由器放在电信光猫旁边，位于客厅一角，所以几个卧室的信号都不是太好，好在手头有不少电猫、无线路由器，所以自己再稍微组了一下网，下面是一些经验：

1. 大部分无线路由器默认是路由器模式，但是一般可以配置成AP模式，中继器模式、桥接模式、Client模式等，具体的配置方法有些路由器可能有明显的指导，有些需要到网上搜索教程，但基本原理和模式的区别大致如下：
   1. 无线路由器通过LAN有线口接到能上网的路由器，那么就成了AP模式。
   2. 如果通过WIFI接到能上网的路由器，就成了中继模式（配置自己的SSID和上级路由器一致）或桥接模式（配置自己的SSID和上级路由器不一致）
   3. 如果WIFI接到能上网的路由器但是不再发射无线信号，而只在有线口接入设备，则成了Client模式（相当于一个网卡）。
2. 中继模式和桥接模式没什么用，因为正因为信号不好，才需要中继或桥接，那么中继或桥接的这一段始终是瓶颈，导致卧室上网很慢很卡。
3. 强烈推荐使用AP模式，在信号不好的地方（如卧室）放一个路由器，将它的IP改为和上级路由器同网段但是不同的IP，然后通过自己的LAN口接入上级路由器的LAN口，为了使用时无缝切换，将这个路由器的SSID和密码设置为和上级路由器一致。
4. 现在的问题是，找一根线连接两个路由器，如果事先没有布过线，就需要走明线，会很难受，这时候电猫就出场了，电猫可以理解为一根网线，但是中间一段是用电线接通的。高档的电猫可以一拖多（一个主机多个从机），甚至从机自己可以是一个AP。我比较穷而且闲置设备多，所以用了一对普通电猫和一个闲置路由器设置为AP模式搞定了。
5. 如果从头装修房子，还是一间房一个AP比较好，可能的话可以放到吊顶里面。