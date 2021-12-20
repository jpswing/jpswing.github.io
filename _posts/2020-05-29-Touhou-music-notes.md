---
layout: post
title: 东方音乐笔记
excerpt_separator: <!--more-->
---

<iframe width="560" height="315" src="https://www.youtube.com/embed/-i3Otdvu9ao" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

这篇文章是对油管频道 8-bit Music Theory 的一个东方音乐的分析视频的总结，建议配合视频进行阅读，否则大概会看不懂。

视频一开头总结了一些大家都懂的东方曲子的共同点：

1. 快速、急促的鼓点
2. 合成器音色的旋律，并配合着戏剧性的和声（讲道理不是很懂这个戏剧性是什么意思）
3. 在旋律之下的快速琶音
4. 稳定的和弦进行（原文是 reliable stable of chord progressions，讲道理不太看得懂这个 reliable 是什么意思）
5. （ZUNpet）

但是除了这些，还有一个不太容易被人注意到的特点，就是在同一个曲子中，key 通常会频繁地改变。key 的变更在塑造曲子的情感框架上起了很大的作用。接下来视频用两首曲子作为例子进行了说明。
<!--more-->

第一首曲子是东方地灵殿里的《ハルトマンの妖怪少女》。

<iframe frameborder="no" border="0" marginwidth="0" marginheight="0" width="380" height="86" src="//music.163.com/outchain/player?type=2&id=22636634&auto=0&height=66"></iframe>

曲子以 7/8 拍开头，和声上围绕着主和弦 Ebm 进行半音距离的和弦移动（Ebm -> E、Ebm -> D，很酷，我没见过这种配法，当然我见的也不多就是了），配合着切分的节奏，营造了一种诡异的氛围：

![touhou-yokai-girl-section-1]({{ 'images/touhou-yokai-girl-section-1.png' | relative_url }})

而曲子的后半部分却是更为柔和的基于 A minor key 的片段：

![touhou-yokai-girl-section-3]({{ 'images/touhou-yokai-girl-section-3.png' | relative_url }})

Eb minor 和 A minor 的差距很大，这是因为这两个 key 所共有的音符是最少的。既然如此，那 ZUN 是怎么进行过渡的呢？在过渡桥段中，首先拍子转为了 4/4 拍，然后他扩展了曲子开头的半音移动的想法，将 Ebm -> E 中的 E 和弦变为 Edim 和弦，重复两小节后再升高半音，形成 Fm -> F#dim 的进行，再与原进行交替出现，最后一小节再升高到 Gm -> G#dim，过渡桥段便结束在最后的 G#dim 和弦。由于 G#dim 有着解决到比它高半音的和弦的倾向[1]，而它的高半音正好就是 A，所以接到下一段的 A minor 就是很自然而然的事了：

![touhou-yokai-girl-section-2]({{ 'images/touhou-yokai-girl-section-2.png' | relative_url }})

之前的桥段积累了不少的 tension，而这些 tension 在接到新段落时都得到了释放，得到的就是巨大的满足感。这还没完，虽然我们现在已经在 A minor 的段落中了，但是第一个和弦却不是 Am，而是 F，即小调的降六级和弦，再顺阶往上走，到 G，最后在第二个小节才真正解决到 Am，形成了 `bVI - bVII - i` 的和弦进行，这加强了这段的情绪感染力。这个 `bVI - bVII - i` 的和弦进行在东方的曲子中非常常见，以至于在视频中，作者认为这就是 ZUN 默认的 emotional sounding chord progression（不知道该怎么翻）：

![touhou-yokai-girl-section-4]({{ 'images/touhou-yokai-girl-section-4.png' | relative_url }})

这个段落之后，便会接回开头。这次转变并不像之前一样那么突然，相反，ZUN 通过将乐器的增加、鼓点的变化、快速琶音以及升半个 key 的这些技巧配合使用，来逐渐增加音乐的能量，当能量积攒得差不多时，直接接回开头，也不会显得突兀。

第二首曲子是来自东方妖妖梦的《ネクロファンタジア》。

<iframe frameborder="no" border="0" marginwidth="0" marginheight="0" width="380" height="86" src="//music.163.com/outchain/player?type=2&id=22636708&auto=0&height=66"></iframe>

由于想摸了，所以我就简单总结一下这部分内容：作者讲了级进上行或下行的这种和弦进行在东方音乐中很常见；然后讲了一下 ZUN 所用的一些包括 pivot chord 在内的转调技巧；然后提到了 ZUN 很爱用「皮卡第三度」[2] 这个终止式。

[1] 减和弦与属七和弦（在 Eb minor 中是 E7）有着同样的三全音，这就是减和弦与属和弦一样，都想接到主和弦的原因，这里的减和弦也可以换成 Bb7，它也有着同样的三全音，这就是「[三全音代理](https://www.youtube.com/watch?v=Wdn1acmup5g)」。

[2] 皮卡第三度是我个人很喜欢的一种终止式，真的怎么用都好听，具体可看 [好和弦的介绍影片](https://www.youtube.com/watch?v=9uFS7NBdAMA)。
