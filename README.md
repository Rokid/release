Rokid Release
====================================
[![Build Status](https://travis-ci.org/Rokid/release.svg?branch=master)](https://travis-ci.org/Rokid/release)

Rokid 用于提供发布镜像的 GitHub 仓库，目前支持 Linux/Android 的官方镜像发布。

### 名词解释

Rokid Release 中定义了如下角色以及定义，在使用前请先了解。

#### 什么是发布（Release）

我们定义一次发布（Release）为一个使用 Markdown 编写的文件，主要分为两个部署：配置与文本内容。一个简单的例子如下：

```md
<!--upgrade_image_uri=https://foobar.loop/path/to/your/upgrade-img-->
<!--flush_image_uri=https://foobar.loop/path/to/your/flush-img-->

本次更新：
- 增加了对多激活词的支持；
- 修复了播放器的内存泄漏问题；

```

如上，配置部分使用注释书写，需要包含：

- `upgrade_image_uri` 升级镜像地址；
- `flush_image_uri` 刷机镜像地址；

文本内容为通用 Markdown 内容，是本次镜像更新的内容，以及任何你想跟镜像用户告知的事项、通告以及声明。

#### 提交者

每次发布都由一个[提交者](#提交者)发起，一般为镜像的开发及维护人员。目前已知的镜像维护人员为：

- 官方 Linux 镜像由 [@yorkie](https://github.com/yorkie) 维护；
- 官方安卓镜像由 [@siokagami](https://github.com/siokagami) 维护；

#### 发布者

[提交者](#提交者)每次发起一个发布后，需要[发布者](#发布者)的审阅方可发布，一般为我们 Rokid Team 的运营人员。

- [@zhangyamei43](https://github.com/zhangyamei43)

### 如何提交

- 创建一个分支，并且在对应目录下提交一个使用 Markdown 编写的文件，命名格式为`{version}-{date}-{buildId}.md`；
- Markdown 文件中，编写好你的更新日志；
- 在一起准备就绪后，创建一个到 `master` 的 Pull Request；
- 在 Pull Request 中，需要明确你的镜像地址，方便维护人员审阅以及发布；

### 如何发布

- 每收到一个镜像 Pull Request 后，首先需要检查更新日志中是否有格式问题、语法问题以及表达是否清晰；
- 确认更新日志没有问题后，要求提交者提供镜像地址包含升级镜像和刷机镜像，以及 CI 报告；
- 确认镜像地址无误后，即可对镜像进行发布
  - 如果对 git 比较熟悉，可以直接在提交分支中，增加 `upgrade_image_uri` 和 `flush_image_uri`；
  - 如果对 git 不熟悉，可以将发布镜像地址在 Pull Request 告知提交者，并要求更新到对应的 Markdown 文件中；
- 最后审阅 Markdown 中的镜像地址及文本内容，确认无误后，合并分支到 `master`；
- 等待发布成功，将本地内容同步至[开发者论坛](https://forum.rokid.com)中；

### 在线API

- 查看 RokidOS 镜像列表：https://rokid.github.io/release/rokidos.json

### License

Rokid Copy Right.
