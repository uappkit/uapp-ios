SDKs 目录存放离线打包所需的 SDK, 第三方依赖的插件工程等
如果依赖第三方的工程比较庞大，可以通过软连接创建(`ln -sfn source target`)，或者通过 `git submodule` 维护.

例如：

```
SDKs
├── DouyinPlugin
├── FFMpegPlugin
├── README.md
├── SDK -> $HOME/.uappsdk/ios/SDK
└── ijkplayer -> $HOME/.uappsdk/ios/ijkplayer
```