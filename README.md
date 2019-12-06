#  🌪ghurri-net


中文 | [English](https://github.com/shaojintian/ghurri-net/blob/master/README-en.md)

<!-- PROJECT SHIELDS -->

[![Contributors][contributors-shield]][contributors-url]
[![Forks][forks-shield]][forks-url]
[![Stargazers][stars-shield]][stars-url]
[![Issues][issues-shield]][issues-url]
[![MIT License][license-shield]][license-url]
[![LinkedIn][linkedin-shield]][linkedin-url]
<a title="Build Status" target="_blank" href="https://travis-ci.com/shaojintian/ghurri-net"><img src="https://img.shields.io/travis/com/shaojintian/ghurri-net?style=flat-square&logo=appveyor"></a>
<a title="Codecov" target="_blank" href="https://codecov.io/gh/shaojintian/ghurri-net"><img src="https://img.shields.io/codecov/c/github/shaojintian/ghurri-net?style=flat-square&logo=appveyor"></a>
<a title="Supported Platforms" target="_blank" href="https://github.com/shaojintian/ghurri-net"><img src="https://img.shields.io/badge/platform-Linux%20%7C%20macOS%20%7C%20Windows-549688?style=flat-square&logo=appveyor"></a>
<a title="Require Go Version" target="_blank" href="https://github.com/shaojintian/ghurri-net"><img src="https://img.shields.io/badge/go-%3E%3D1.12-30dff3?style=flat-square&logo=appveyor"></a>
<a title="Release" target="_blank" href="https://github.com/shaojintian/ghurri-net/releases"><img src="https://img.shields.io/github/release/shaojintian/ghurri-net.svg?color=161823&style=flat-square&logo=appveyor"></a>
<br/>
<a title="" target="_blank" href="https://golangci.com/r/github.com/shaojintian/ghurri-net"><img src="https://golangci.com/badges/github.com/shaojintian/ghurri-net.svg"></a>
<a title="Doc for gnet" target="_blank" href="https://gowalker.org/github.com/shaojintian/ghurri-net?lang=zh-CN"><img src="https://img.shields.io/badge/api-reference-8d4bbb.svg?style=flat-square&logo=appveyor"></a>
<a title="gnet on Sourcegraph" target="_blank" href="https://sourcegraph.com/github.com/shaojintian/ghurri-net?badge"><img src="https://sourcegraph.com/github.com/shaojintian/ghurri-net/-/badge.svg?style=flat-square"></a>


<!-- PROJECT LOGO -->
<br />

<p align="center">
  <a href="https://github.com/shaojintian/ghurri-net/">
    <img src="docs/images/logo.png" alt="Logo" width="80" height="80">
  </a>

  <h3 align="center">🌪ghurri-net</h3>
  <p align="center">
    使用此网络框架快速启动网络应用程序，灵感来源于<a href="https://github.com/panjf2000/gnet">gnet</a>
    <br />
    <a href="https://github.com/shaojintian/ghurri-net"><strong>Explore the docs »</strong></a>
    <br />
    <br />
    <a href="https://github.com/shaojintian/ghurri-net"> View Demo</a>
    ·
    <a href="https://github.com/shaojintian/ghurri-net/issues">Report Bug</a>
    ·
    <a href="https://github.com/shaojintian/ghurri-net/issues">Request Feature</a>
  </p>

</p>

 本篇README.md面向开发者 

# 🚀 功能

- [x] [高性能](#性能测试) 的基于多线程/Go程网络模型的 event-loop 事件驱动
- [x] 支持Reactor 和 Proactor 两种架构模式
- [x] 内置 Round-Robin 轮询负载均衡算法,由开源库 [gclover](https://github.com/shaojintian/gclover) 提供支持
- [x] 内置 goroutine 池，由开源库 [gsweat](https://github.com/shaojintian/gsweat) 提供支持
- [x] 内置 bytes 内存池，由开源库 [pool](https://github.com/gobwas/pool/) 提供支持
- [x] 简洁的 APIs
- [x] 基于 Ring-Buffer 的高效内存利用
- [x] 支持多种网络协议：TCP、UDP、Unix Sockets
- [x] 支持两种事件驱动机制：Linux 里的 epoll 以及 MacOS X/FreeBSD 里的 kqueue
- [x] 支持异步写操作
- [x] 灵活的事件定时器
- [x] SO_REUSEPORT 端口重用
- [x] 内置多种编解码器，支持对 TCP 数据流分包：LineBasedFrameCodec, DelimiterBasedFrameCodec, FixedLengthFrameCodec 和 LengthFieldBasedFrameCodec，参考自 [netty codec](https://github.com/netty/netty/tree/netty-4.1.43.Final/codec/src/main/java/io/netty/handler/codec)，而且支持自定制编解码器
- [x] 支持 Windows 平台，基于IOCP 事件驱动机制
- [ ] 加入更多的负载均衡算法：随机、最少连接、一致性哈希等等
- [ ] 支持 TLS
- [ ] 实现 `ghurri-net` 客户端








## 目录

- [上手指南](#上手指南)
  - [开发前的配置要求](#开发前的配置要求)
  - [安装步骤](#安装步骤)
- [文件目录说明](#文件目录说明)
- [开发的架构](#开发的架构)
- [部署](#部署)
- [使用到的框架](#使用到的框架)
- [核心设计💡](#核心设计)
- [性能测试📊](#性能测试)
- [贡献者](#贡献者)
  - [如何参与开源项目](#如何参与开源项目)
- [版本控制](#版本控制)
- [作者](#作者)
- [赞助❤](#赞助)
- [鸣谢](#鸣谢)

### 上手指南

请将所有链接中的“shaojintian/ghurri-net”改为“your_github_name/your_repository”



###### 开发前的配置要求

1. xxxxx x.x.x
2. xxxxx x.x.x

###### **安装步骤**

1. Get a free API Key at [https://example.com](https://example.com)
2. Clone the repo

```sh
git clone https://github.com/shaojintian/ghurri-net.git
```

### 文件目录说明

eg:

```
filetree 
├── ARCHITECTURE.md
├── LICENSE.txt
├── README.md
├── /account/
├── /bbs/
├── /docs/
│  ├── /rules/
│  │  ├── backend.txt
│  │  └── frontend.txt
├── manage.py
├── /oa/
├── /static/
├── /templates/
├── useless.md
└── /util/

```





### 开发的架构 

请阅读[ARCHITECTURE.md](https://github.com/shaojintian/ghurri-net/blob/master/ARCHITECTURE.md) 查阅为该项目的架构。

### 部署

暂无

### 使用到的框架

- [xxxxxxx](https://getbootstrap.com)
- [xxxxxxx](https://jquery.com)
- [xxxxxxx](https://laravel.com)


## 💡核心设计

1. xxxxx
2. xxxxx
3. xxxxx

## 📊性能测试

 1. xxxxx
 2. xxxxx


### 贡献者

请阅读**CONTRIBUTING.md** 查阅为该项目做出贡献的开发者。

#### 如何参与开源项目

贡献使开源社区成为一个学习、激励和创造的绝佳场所。你所作的任何贡献都是**非常感谢**的。

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request



### 版本控制

该项目使用Git进行版本管理。您可以在repository参看当前可用版本。

### 作者

E-mail: sjt@hnu.edu.cn

知乎:[笃行er](https://www.zhihu.com/people/sjt_ai/activities)  &ensp; qq:1075803623    

 *您也可以在贡献者名单中参看所有参与该项目的开发者。*

### 版权说明

该项目签署了MIT 授权许可，详情请参阅 [LICENSE.txt](https://github.com/shaojintian/ghurri-net/blob/master/LICENSE.txt)

### 鸣谢

- [gnet](https://github.com/panjf2000/gnet)
- [Img Shields](https://shields.io)
- [Choose an Open Source License](https://choosealicense.com)
- [GitHub Pages](https://pages.github.com)
- [Animate.css](https://daneden.github.io/animate.css)
- [xxxxxxxxxxxxxx](https://connoratherton.com/loaders)

### 赞助

If you like this project and want to sponsor the author, you can reward the author using Wechat or Alipay by scanning the following QR code.

<figure class="half">
  <img src="docs/images/reward_wechat.png" width="200" height="260"/>
  <img src="docs/images/reward_alipay.png" width="200" height="260"/>
</figure>
<!-- links -->

[your-project-path]: shaojintian/ghurri-net
[contributors-shield]: https://img.shields.io/github/contributors/shaojintian/ghurri-net.svg?style=flat-square
[contributors-url]: https://github.com/shaojintian/ghurri-net/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/shaojintian/ghurri-net.svg?style=flat-square
[forks-url]: https://github.com/shaojintian/ghurri-net/network/members
[stars-shield]: https://img.shields.io/github/stars/shaojintian/ghurri-net.svg?style=flat-square
[stars-url]: https://github.com/shaojintian/ghurri-net/stargazers
[issues-shield]: https://img.shields.io/github/issues/shaojintian/ghurri-net.svg?style=flat-square
[issues-url]: https://img.shields.io/github/issues/shaojintian/ghurri-net.svg
[license-shield]: https://img.shields.io/github/license/shaojintian/ghurri-net.svg?style=flat-square
[license-url]: https://github.com/shaojintian/ghurri-net/blob/master/LICENSE.txt
[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=flat-square&logo=linkedin&colorB=555
[linkedin-url]: https://linkedin.com/in/shaojintian