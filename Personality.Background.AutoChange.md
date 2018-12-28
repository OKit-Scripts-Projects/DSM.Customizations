# DSM背景自动更新
## 起因
作者lixuy的[抓bing图片设置群晖背景](https://github.com/lixuy/DSM_Login_BingWallpaper)

以及[Mojave的动态壁纸自定义](https://www.sysgeek.cn/macos-mojave-dynamic-wallpaper/)

## 简介
从[lixuy博客](https://03k.org/dsm-bing.html)看到的，利用代码抓取bing的图片，自动更换群晖的登录背景和桌布。
由此想到利用代码根据日照情况或者简单地依靠时间来做动态背景，就像Apple Mojave的动态背景。

图片是有了，我从Jetson家“24 Hour Wallpaper”下载了他家全套24小时全分辨率图片，但是由于版权问题我这里不提供他家的付费图片，有需要的自行购买APP，然后提取和转换。

这里做这套方案时用公开发布的图片， 比如[Jetson](https://www.jetsoncreative.com/mojave)家提供的免费组图

以及[Marcin Czachurski](https://itnext.io/@mczachurski?source=user_popover)提供的[地球组图](https://itnext.io/macos-mojave-dynamic-wallpapers-ii-f8b1e55c82f)，
其实也可以用日本的卫星图片。那这么分析了一下，就有了以下三种方案。

## 方案
0. 从经常换图片的网站抓图回来设成背景
0. 准备一套24小时的固定视角摄影图片，根据时间或太阳高度来更换图片
0. 定时从日本卫星抓取地球图片回来，定时更换


