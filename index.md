**由于ios端微信浏览器内核限制，本教程只适用于微信Android客户端，ios端并没有可替代的相应方法，用iphone和ipad看青年大学习的可以洗洗睡了**

# 敬告

**本作仅供学习与讨论之用，请不要过度传播。牢记社会主义核心价值观：富强 民主 文明 和谐 自由 平等 公正 法治 爱国 敬业 诚信 友善**


![markdown](https://www.mdeditor.cn/images/logos/markdown.png "markdown")


## 这个东西存在的意义

>*学校强制要求青年大学习？*
>*青年大学习时间过长？*

这个东西可以帮助你在获得积分的基础上尽量减少青年大学习的时间（~~想要分还不想看视频~~）

## 基本原理

通过微信Android内置的“QQ浏览器X5内核”的调试功能调出控制台，并将视频播放进度调整至视频末尾，以达到跳过视频的目的。

## 具体实施方案

#### 1. 打开微信X5内核调试模式

在微信里依次打开如下三个网页：

<http://debugmm.qq.com/?forcex5=true>
<http://debugtbs.qq.com>
<http://debugx5.qq.com>

可以分别看到如下的三个页面：

![force use x5](https://fangkehou-team.github.io/qingniandamoyu/imagees/force_use_x5.jpg "force use x5")
![debug tbs](https://fangkehou-team.github.io/qingniandamoyu/imagees/debug_tbs.jpg "debug tbs")
![debug x5](https://fangkehou-team.github.io/qingniandamoyu/imagees/debug_x5.jpg "debug x5")

当三个页面出现的内容与截图一致或基本一致时表示调试模式已经打开

#### 2. 开启vConsole

在最后一个页面的信息标签中打开“vConsole调试功能”如下图：

![debug x5 vconsole](https://fangkehou-team.github.io/qingniandamoyu/imagees/debug_x5_vconsole.jpg "debug x5 vconsole")

#### 3. 按照正常的流程进入学习

在视频页面中，点击网页下方vConsole按钮，如下图：
![daxuexi_1](https://fangkehou-team.github.io/qingniandamoyu/imagees/daxuexi_1.jpg "daxuexi_1")

出现如下页面：
![daxuexi_2](https://fangkehou-team.github.io/qingniandamoyu/imagees/daxuexi_2.jpg "daxuexi_2")

在下方command下粘贴如下代码：

```javascript
document.getElementById("Bvideo").addEventListener("timeupdate",function(){
        var counter = setTimeout(function(){ document.getElementById("Bvideo").currentTime=10000; clearTimeout(counter);}, 1000);
    })
```

并按下OK，出现如下结果：
![daxuexi_3](https://fangkehou-team.github.io/qingniandamoyu/imagees/daxuexi_3.jpg "daxuexi_3")

点击上方空白处退出该页面

过一会你就会发现视频停止了并且出现了课后答题界面（对，只有课后题，没有视频内的题，因为已经跳过了）

回答完课后题退出就会发现积分已经到手了

#### 感谢
本页面参考了
[青年大摸鱼油猴脚本（电脑端）](https://greasyfork.org/zh-CN/scripts/404861-%E9%9D%92%E5%B9%B4%E5%A4%A7%E6%91%B8%E9%B1%BC)，
[微信网页调试之利用vConsole真机调试](https://blog.csdn.net/flysnownet/article/details/93975099)
[青年大学习视频跳过方法](https://www.cnblogs.com/Mayfly-nymph/p/12613510.html)
*没错我就是缝合怪*

### End