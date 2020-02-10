# Typecho Theme VOID Δ (Delta)

> Typecho VOID主题的个人修改版。

Δ：~~（用奇怪的方式）~~ 探索VOID的更多可能性。

## 版本详情

### 主题

基于VOID 3.4.0(2020-2-10 nightly)修改

### 配套插件

依赖 1.20 及以上版本插件（本主题不包含VOID插件，需要自行下载）

## 相比于VOID 3.40的拓展功能

* 实现WebP图片格式兼容。（需要启用图片懒加载）（不适用于友链页面）

* 将灯箱从[fancybox](https://github.com/fancyapps/fancybox)更换为[lightbox2](https://github.com/lokesh/lightbox2)，并重写部分代码以实现WebP格式兼容。新的灯箱仅支持上下翻看同一个照片集内图片，以保证文章阅读体验的统一。

## 如何启用WebP兼容功能？
  
1. 请先确保VOID的图片懒加载设置已启用

2. 在Typecho的编辑器中插入一张所有浏览器都支持的图片（如jpg、png等）（以下称其为「图片A」）

3. 确保图片A的存储目录下存在一张与「图片A」同名的WebP格式的图片（以下称其为「图片B」）。（也就是说，「图片A」与「图片B」的链接除了后缀名外都相同。并且「图片B」不需插入到Typecho的编辑器中）。

4. 在文章发布后，主题将会对支持WebP格式的浏览器启用「图片B」。如果主题找不到这张与「图片A」对应的WebP格式图片、或浏览器不兼容WebP格式（如Safari、IE等），主题则会自动启用「图片A」。

## VOID Δ是如何实现WebP兼容的？

1. 后端通过`HTTP Accept`头来判断判断访客的浏览器是否支持WebP格式（参考资料：[又拍云的WebP兼容方案](https://www.upyun.com/tech/article/156/2.html)）

2. 在图片懒加载时，若访客的浏览器兼容WebP，则浏览器将尝试向WebP链接发送请求；若请求成功，则进行加载；反之，则加载备用图片。

3. 灯箱的加载方案同上。但由于灯箱支持上一张/下一张图片的预加载，因此我还为灯箱中的每个图片对象增加了一个判断其WebP链接是否可用的标记，以缩短二次请求所需的处理时间（若浏览器没有缓存）。

## 下载链接

前往[发布页面](https://github.com/Reedo0910/Typecho-Theme-VOID/releases)，下载**VOID-Delta-xxx.zip**发布包文件。

**该发布包文件仅包含主题包，主题的配套插件请安装该版本VOID的对应插件版本**。

主题安装方式和配套插件下载以[Typecho Theme VOID的仓库](https://github.com/AlanDecode/Typecho-Theme-VOID)上的介绍为准。

## 演示站点

[初之音](https://www.himiku.com/) **（注意：这不是我本人的网站，请勿在该站点提任何关于本主题的反馈。）**

## 更多介绍

请参考[原版Typecho Theme VOID的仓库](https://github.com/AlanDecode/Typecho-Theme-VOID)，因为其他功能与原版一致。

## 声明

因为本人没有Typecho的博客，该主题仅在本地的测试环境和[初之音](https://www.himiku.com/)的生产环境（感谢Mikusa）进行了测试。即便如此，仍有可能存在某些未知的情况。

该主题仅供学习交流使用。如要确保稳定，请使用原版主题。

当然，你也可以尝试向我提Issue (Nice try!)  ~~能不能修好就是另一回事了~~

## 感谢

### 开源项目

- [Typecho Theme VOID](https://github.com/AlanDecode/Typecho-Theme-VOID) [MIT] © [AlanDecode](https://github.com/AlanDecode)

- [lightbox2](https://github.com/lokesh/lightbox2) [MIT] © [Lokesh Dhakar](https://github.com/lokesh)
