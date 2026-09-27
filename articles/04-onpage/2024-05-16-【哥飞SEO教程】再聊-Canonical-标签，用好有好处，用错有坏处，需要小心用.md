# 【哥飞SEO教程】再聊 Canonical 标签，用好有好处，用错有坏处，需要小心用

> 发布于 2024-05-16 · [公众号原文](https://mp.weixin.qq.com/s/C4Q_h6gYOp_fohELvAfQMQ)

最近哥飞发现还是有很多朋友没有理解 Canonical 标签的正确用法，所以今天单独写一篇文章来详细讲讲。

哥飞在以前的文章也讲过这个标签，感兴趣可以点进去看：
1\. [如何给一个已经上线的网站出SEO改造建议](https://mp.weixin.qq.com/s/9uuenB2Cg15wyaCQc0o1kg)

2\. [【5800字长文】从网站站内优化到部署上线再到推广运营一篇文章让你学明白](https://mp.weixin.qq.com/s/eM1vquYr87hYfgM5JYY6HA)

3\. [【哥飞带你读】你需要了解的10个重要SEO元标签（下）](https://mp.weixin.qq.com/s/pgRb7By2EVLMDYZ1E2JG5Q)

4\. [推荐一款好用且免费的SEO插件，哥飞天天都在用](https://mp.weixin.qq.com/s/BGNEsu-cmxMwy-IGKnNHAA)

5\. [【哥飞评站】AI贴纸生成网站 StickerBaker 的SEO评测报告和改进建议（4000字）](https://mp.weixin.qq.com/s/aCNzWnu09jQxPcPHMcswMA)

关于 Canonical 的教程文章，也可以看看下面这些：
1\. 什么是规范化
https://developers.google.com/search/docs/crawling-
indexing/canonicalization?hl=zh-cn

2\. 如何使用 canonical 及其他方法指定规范网址
https://developers.google.com/search/docs/crawling-indexing/consolidate-
duplicate-urls?hl=zh-cn

3\. Semrush 的 Canonical 教程
https://www.semrush.com/blog/canonical-url-guide/

4\. Ahrefs 的 Canonical 教程
https://ahrefs.com/blog/zh/canonical-tags/

下面，哥飞会基于自己的理解，给大家介绍 Canoni cal 。

**一、为什么要有 Canonical **

先说结论，Canonical 目的是为了解决 重复网址 问题，注意，哥飞说的是重复网址，而不是 重复网页 哦。

同一个网页，有可能多个域名都可以访问，最典型的就是 www 域名和裸域名都能够访问，这就导致一个网页有多个网址。

如果是子目录，有可能 /abc/ 和 /abc/index.html 或者 /abc/index.php 都能够访问，于是一个网页有更多网址。

这还不算完，这些网址后面又可以加各种各样的参数，还会导致更多的网址出现。

哥飞举例例子给大家更好理解。

假设域名是 gefei.vip ，同时解析了 www.gefei.vip 和 gefei.vip 。

注意，这里哥飞只是用来举例，实际更规范的做法是选定一个域名作为主域名，然后把另一个域名通过3 01跳转到这个主域名。
如哥飞习惯选择 gefei.vip 为主域名，然后把 www.gefei.vip 301 跳转到 gefei.vip 。
注意，如果是大网站，为了防止 cookie 泄漏，一般是把 www.gefei.vip 作为主域名，然后把 gefei.vip 用 301 跳转到
www.gefei.vip 。

假设目录是 /shequn/ ，后端用的 php 写的， 也就是 /shequn/ 和 /shequn/index.php 都能够访问。

假设张三和李四都在自己网站上推荐了哥飞社群，都带了来源参数，参数名称还不一样，一个是 ref=zs ，一个是 via=ls 。

那么总共可能会有以下这么多个网址被使用：

https://gefei.vip/shequn/

---
https://www.gefei.vip /shequn/
https://gefei.vip /shequn/index.php
https://www.gefei.vip /shequn/index.php
https://gefei.vip /shequn/index.php? ref=zs
https://www.gefei.vip /shequn/? v ia =ls
还可能有更多……

上面哥飞只列出了部分情况，实际可能会有更多。

而这些看起来不一样的网址，其实都是社群首页，返回的 html 是一样的。

那么在搜索引擎的眼里就会很奇怪，为什么会有这么多的 重复网页 。

注意，哥飞这里用了“ 重复网页 ”，而在前文用了“ 重复网址 ”，其实是视角不同。

在我们自己眼里，知道这些网址其实是同一个网页的不同网址，所以是“ 重复网址 ”，而在搜索引擎眼里，这就是一些“ 重复网页 ”。

哥飞这里再展开一下，除了上面这个原因会造成重复网页，如果你的代码是前端渲染的，也会造成重复网页，具体可以看这篇文章《 [
【哥飞SEO教程】如果不想要谷歌给的免费流量，你就用前端渲染吧
](https://mp.weixin.qq.com/s/ibWT766ftLAq2LrH4wMUWw)
》。

为了让站长把最规范的一个网址告诉搜索引擎，谷歌等搜索引擎就开始使用 Canonical 标签。

** 二、 Canonical 是什么，有什么用 **

还是拿上面哥飞举的这个例子来说，我想用的规范且唯一网址是：
https://gefei.vip /shequn/

那么就可以在网页 html 的 head 中增加如下一行代码：

*
```html
<link rel="canonical" href="https://gefei.vip/shequn/">
```
这样不管别人用哪个网址访问社群首页，Canonical 都不变，都是：
https://gefei.vip /shequn/

所以 Canonical 的正确用法就是用来指定每一个网页的规范化URL到底是哪个。

** 三、多语言时 Canonical 怎么写 ** ** **

假设你的网站有多种语言，如同时支持中文和英文，网址分别是：

中文
| https://gefei.vip /shequn/
---|---
英文
| https://gefei.vip /en/shequn/


这个时候就要注意了，在英文页面的 html 里， Canonical 就要这样写：

*
```html
<link rel="canonical" href="https://gefei.vip/en/shequn/">
```
看到了吗？

Canonical 需要如实反映当前网页的真实网址。

千万千万不要不管什么语言都写死成同一个网址。

哥飞还看见过有些人全站任何网址的 Canonical 都写成了首页，这也是不对的，是对 Canonical 没有理解到位才会导致的错误。

** 四、Canonical 有什么好处？ **

还是拿上面的例子来说，张三和李四都给了外链，虽然给出的链接地址不一样，但是如果我们在页面里设置了正确的 Canonical
，那么搜索引擎就能够把这些不同网址的权重都汇聚到 Canonical 指定的网址里去。
