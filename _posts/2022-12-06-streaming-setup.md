---
layout: post
title: 如何通过 Audient iD4 MKII 与 FL Studio 处理唱歌直播的声音
excerpt_separator: <!--more-->
---

这篇文章简单分享我直播唱歌时使用的设备，软件，以及声音经过了哪些处理。（[我的直播间](https://live.bilibili.com/23711453)）

我使用的工具包括：麦克风 Shure SM58，声卡（音频界面/接口）Audient iD4 MKII，DAW FL Studio 20，推流软件 OBS。下面对此一一介绍，重点介绍 Audient iD4 MKII，FL Studio 20 的部分。

<!--more-->

# 前言

声音的传输链路是 Shure SM58 -> Audient iD4 MKII -> FL Studio 20 -> OBS。

# 麦克风

我使用麦克风的方式是怼着嘴唱，主要是为了保持音量稳定。对于 Shure SM58，以及其它为舞台表演设计的麦克风来说，无需使用额外的防喷网/罩，人声经过 EQ 处理后就可以消除绝大部分喷麦声，见下文。

# 声卡（音频界面/接口）

声卡是很重要的，如果没有声卡的话，我不知道要怎么才能让声音进到 FL Studio 20 经过处理后再到 OBS，而且一个好的声卡可以很大地降低声音的延迟。Audient iD4 MKII 有一个 Loop-back 功能，基本上就是一个虚拟的输入输出设备，允许任何应用程序输出声音到这个虚拟设备中，或者把它作为麦克风输入到任何应用程序中。有了这个功能，才能实现 FL Studio 20 -> OBS 的过程。

需要注意的是，声卡的麦克风增益不能开太大，以防在大声的时候破 0dB，一般我是设置正常讲话时的音量在 -20dB 左右，可以在 iD4 MKII 的 Loop-back Mixer 里看见输入的音量是多少，前面说的 -20dB 指的是在 Loop-back Mixer 里看见的值，这里的值比实际输入到其它应用程序时的值要大，大概大 10dB，原因未知，但如果在 Mixer 里爆了 0dB 那就会失真。

我们需要把除了「LOOP-BACK 1/2」以外的所有输入音量都关闭，我们会在 DAW 中把经过处理后的人声送进「LOOP-BACK 1/2」。

![streaming-setup-loop-back-mixer]({{ 'images/streaming-setup-loop-back-mixer.png' | relative_url }})

# 声音处理（混音）软件（DAW）

我们在这里进行声音的处理。我一般是把伴奏也放进 FL Studio 一起控制，这样如果想的话可以顺便录上人声，方便后期处理。把 FL Studio 的音频设备设置成声卡的驱动，即「Audient USB Audio ASIO Driver」。

## 伴奏

伴奏送到 mixer 里一个单独的 insert，然后这个 insert 输出到你的音响/耳机（Analogue 1 - Analogue 2）实现监听（见下图），再 send 到 master。伴奏基本只需要做拉低音量的处理，据悉伴奏音量在 -3dB 以下，和人声混在一起的总音量才不会爆 0dB，具体拉低多少视歌曲而定。

![streaming-setup-output]({{ 'images/streaming-setup-output.png' | relative_url }})

## 人声

同样，人声送到一个单独的 insert，输出到「Analogue 1 - Analogue 2」，再 send 到 master。但是人声要做的处理就多了，下图是经过的所有效果器：

![streaming-setup-mixer-slots]({{ 'images/streaming-setup-mixer-slots.png' | relative_url }})

1. TDR Nova：这是一个 De-esser，减少 s 等声母造成的嘶嘶声，这个插件是免费的，使用的时候选 De-esser 预设便可

2. EQ：处理音色，让人声听起来更自然

   ![streaming-setup-eq]({{ 'images/streaming-setup-eq.png' | relative_url }})
   
   * Band 1 类型是 high pass，频率在 80Hz，去除不需要的低频，最重要的是能去除绝大部分的喷麦声，这对于我这种怼嘴唱的人来说尤为关键
   * Band 2 在 160Hz 左右，-7dB，因为我是怼着嘴唱，所以这部分的低频很重，声音听起来很浑浊，降低一些会让声音干净很多
   * Band 5 在 1100Hz 左右，2.5dB，据悉这附近的频率增加一点的话可以让人声更突出
   * Band 6 在 3200Hz 左右，-2.5dB，主要是感觉声音经过 De-esser 后还是有一些嘶嘶声，我就在这再降低了一点对应的频率，不过我也不知道这么做是否更好，也不知道这是否是正确的频率
   * Band 7 类型是 high shelf，在 5500Hz 左右，5dB，据悉增加这后面的频率可以增加人声的「空气感」
   
   这些参数除了 1 和 2，其它纯纯仅供参考，我是乱来的（
   
3. Fruity Limiter：这是 compressor，保证我在大声的时候音量变化不会太大，同时通过 gain 让声音大声点

   ![streaming-setup-compressor]({{ 'images/streaming-setup-compressor.png' | relative_url }})

   * Gain: 9dB
   * Threshold: -30dB
   * Ratio: 3:1
   * Attack: 15ms
   * Release: 120ms

   我的 Threshold 设置思路是，和自己说话/温柔唱歌时候的声音差不多大，或者稍微大一点，就可以了。这里的参数设置肯定还不是最好的，我对 compressor 的调整还没有什么经验，仅供参考

4. Reverb：没什么好说的，就是混响，有些歌曲加上混响会好听很多的时候，就开开

5. Distructor：Overdrive，最轻微的失真效果，目的是让音色更亮，我偶然发现的，加上一点 Overdrive 会让声音亮很多。这里用的是 FL Studio 自带的 Blood Overdriver，直接用的预设，没有额外调参数

6. Fruity Balance：另一个 gain，3dB，要说为什么不加在 compressor 里的话，大概是不要加得太满，给 compressor 后面的效果器留一点空间吧（心虚

7. Wave Candy：单纯一个 dB meter，让我能更方便地监控经过处理后的人声的音量大小

最后，master 输出到「Loop-back 1 - Loop-back 2」。

# OBS

在 OBS 中选择一个麦克风，把输入设备设置成「Loop-back 1/2」，再把这个麦克风的「单声道」选项关闭，否则伴奏会变成单声道：

![streaming-setup-obs-mic]({{ 'images/streaming-setup-obs-mic.png' | relative_url }})