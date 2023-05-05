# bili-video-merger
此工具用于将B站缓存视频的video.m4s和audio.m4s整合为一个文件，使用FFmpeg.wasm开发
### 简介
BiliBili（以下简称B站）为了防止通过缓存的方式盗取视频，是将视频画面文件（video.m4s）和视频音轨文件（audio.m4s）分开传输的。<br>
而现如今，更多的人在移动端上使用B站，有在B站软件外观看B站离线视频的需求，却没有一个便捷的方式整合两个文件，FFmpeg上手门槛又相对较高，故而有了本项目。<br><br>
示例页面：[https://bilitool.klee.love](https://bilitool.klee.love)
### 依赖
此项目基于FFmpeg.wasm开发，已适配绝大多数现代浏览器。
### 使用方法
仅需部署本项目后，根据提示操作即可，就算是菜鸟小白亦可轻易使用。
### 一些说明
本项目使用 Vercel* 搭建，您可以Fork本仓库后访问 [Vercel](https://vercel.com) 使用GitHub登录并导入您的Fork仓库在根目录创建Project。
#### 为什么要使用Vercel？
@ffmpeg/core在编译FFmpeg时，配置了pthreads，导致产生的js胶水代码中使用了SharedArrayBuffer。<br>
ShardArrayBuffer由于安全问题，仅可用在cross-origin isolated环境下，故需要配置以下响应头：
```
Cross-Origin-Embedder-Policy: require-corp
Cross-Origin-Opener-Policy: same-origin
```
但，Vercel不是必须的。在本项目中，使用了Python脚本为其添加以上响应头，同时为了利（bai）用（piao）Serverless服务，综合考虑下使用了Vercel。<br>
若您需要自行部署，也可以在您自己的服务器上利用诸如Nginx、Apache、Caddy等Web服务器软件添加响应头。（您可能需要将main.html重命名为index.html）<br>
Have Fun!

---

Made with ♡ by [魂归梓里(ZiAzusa)](https://about.sukimoe.cn/)
