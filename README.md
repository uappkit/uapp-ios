## uapp iOS 离线工程

**工程目录结构**

```
.
├── Main
│   ├── App-Prefix.pch
│   ├── AppDelegate.h
│   ├── AppDelegate.m
│   ├── Pandora
│   ├── Resources
│   ├── ViewController.h
│   ├── ViewController.m
│   └── main.m
├── README.md
├── SDKs  # gitignore, 存放官方发布离线打包的SDK，或其他依赖的SDK, Libs等
├── config
├── manifest.json  # 指向 HBuilderX 工程里 manifest.json 的软连接
├── modules        # 存放第三方插件工程
│   └── README.md
├── out            # gitignore, `uapp publish debug` 生成打包基座，并同步给 HBuilderX
│   └── uapp_debug.xcarchive
├── project.yml
└── uapp.xcodeproj
```

### XcodeGen

xcodegen 是用来生成 xcode 工程文件的，使用 xcodegen 便于维护，自动化集成。

**通过 brew 安装**

`brew install xcodegen`

**通过 Make 安装**

```
git clone https://github.com/yonaskolb/XcodeGen.git
cd XcodeGen
make install
```

uapp 工程配置通过 [xcodegen](https://github.com/yonaskolb/XcodeGen) 来维护，配置文件结构如下：

```
.
├── project.yml # xcodegen 配置文件入口
└── config
   ├── base.yml # 基础配置，不建议修改
   ├── custom.yml # 自定义配置，可以添加修改
   ├── uapp_dev.yml # 用于 uapp-dev 开发阶段的配置
   └── uapp_release.yml # 用于 uapp-release 正式发布的配置
```

## 重点说明

第一次使用，或者修改 xcodegen 配置后，一定要执行:

`xcodegen`

会重新生成 xcode 的工程文件 `uapp.xcodeproj`

命令行可通过 `open uapp.xcodeproj` 打开 xcode 工程:
