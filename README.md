# VAD(Voice Activity Detection)


## 理论基础

    是在信噪比（SNR）不是很低的情况下，语音片段的STE相对较大，而ZCC相对较小；而非语音片段的STE相对较小，但是ZCC相对较大。因为语音信号能量绝大部分包含在低频带内，而噪音信号通常能量较小且含有较高频段的信息。

    故而可以通过测量语音信号的这两个特征并且与两个门限（阈值）进行对比，从而判断语音信号与非语音信号。

    通常对语音信号分帧时取一帧20ms (因为一般会进行短时傅里叶变换，时域和频域的分辨率需要一个平衡，20ms为平衡点，此处不用考虑)。此处输入信号采样率为8000HZ。因此每一帧长度为160 samples.

    STE的计算方法是 , 即帧内信号的平方和。

    在本文中ZCC的计算方法是，将帧内所有sample平移1，再对应点做乘积，符号为负的则说明此处过零，只需将帧内所有负数乘积数目求出则得到该帧的过零率。

## reference

+ [首先这篇文章总结的很好](https://blog.csdn.net/baienguon/article/details/80539296?utm_medium=distribute.pc_relevant.none-task-blog-BlogCommendFromMachineLearnPai2-1.channel_param&depth_1-utm_source=distribute.pc_relevant.none-task-blog-BlogCommendFromMachineLearnPai2-1.channel_param)
+ [WebRTC之VAD算法(讲解的比较详细，多图对比)](https://blog.csdn.net/shichaog/article/details/52399354?utm_medium=distribute.pc_relevant.none-task-blog-BlogCommendFromMachineLearnPai2-5.channel_param&depth_1-utm_source=distribute.pc_relevant.none-task-blog-BlogCommendFromMachineLearnPai2-5.channel_param)
+ 系列文章(C++版)
+ + [VAD实现 （一） --- 读取语音数据](https://blog.csdn.net/iteye_4185/article/details/82514423)
+ + [VAD实现 （二） --- 数据预处理](https://blog.csdn.net/iteye_4185/article/details/82514445?utm_medium=distribute.pc_relevant.none-task-blog-BlogCommendFromMachineLearnPai2-1.channel_param&depth_1-utm_source=distribute.pc_relevant.none-task-blog-BlogCommendFromMachineLearnPai2-1.channel_param)
+ + [VAD实现 （三） --- 算法计算流程与框架](https://blog.csdn.net/iteye_4185/article/details/82515162?utm_medium=distribute.pc_relevant.none-task-blog-BlogCommendFromMachineLearnPai2-2.channel_param&depth_1-utm_source=distribute.pc_relevant.none-task-blog-BlogCommendFromMachineLearnPai2-2.channel_param)
+ + 后续文章没找到  很奇怪！！！！！！

+ [VAD（Voice Activity Detection）算法详解(Python版)](https://blog.csdn.net/weixin_42788078/article/details/89634363)

+ [语音端点检测（VAD）----webrtcvad (Python版)](https://blog.csdn.net/hexuanji/article/details/89923970?utm_medium=distribute.pc_relevant.none-task-blog-BlogCommendFromMachineLearnPai2-1.channel_param&depth_1-utm_source=distribute.pc_relevant.none-task-blog-BlogCommendFromMachineLearnPai2-1.channel_param)

+ [opus编码器静音检测VAD算法](https://segmentfault.com/a/1190000015432946)

+ [单独抽离的webrtc vad算法 (github)](https://github.com/dreamno23/vad/tree/master/webrtc_vad)

+ [webrtc-vad: Easy voice activity detection(C++版)](https://hackage.haskell.org/package/webrtc-vad)
+ + [webrtc-vad-0.1.0.3.tar.gz](https://hackage.haskell.org/package/webrtc-vad-0.1.0.3/webrtc-vad-0.1.0.3.tar.gz)
+ + [Package description](https://hackage.haskell.org/package/webrtc-vad-0.1.0.3/webrtc-vad.cabal)
+ [JavaVAD(回家试试)](https://github.com/debmalya/JavaVAD)

+ [语音活性检测器py-webrtcvad安装使用](https://www.cnblogs.com/zhenyuyaodidiao/p/9288455.html)

+ [py-webrtcvad](https://github.com/wiseman/py-webrtcvad)

+ [Python--用Java调用Python函数过慢的解决方案](https://www.cnblogs.com/halone/p/12823740.html)

+ [python音频分析（一）绘制wav的时域频域图](https://blog.csdn.net/daiyinger/article/details/48289575?utm_medium=distribute.pc_relevant_t0.none-task-blog-BlogCommendFromMachineLearnPai2-1.channel_param&depth_1-utm_source=distribute.pc_relevant_t0.none-task-blog-BlogCommendFromMachineLearnPai2-1.channel_param)

+ [Python音频处理库 pydub](https://zhuanlan.zhihu.com/p/91257681)