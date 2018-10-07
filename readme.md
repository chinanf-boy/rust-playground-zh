# integer32llc/rust-playground [![explain]][source] [![translate-svg]][translate-list]

<!-- [![size-img]][size] -->

[explain]: http://llever.com/explain.svg
[source]: https://github.com/chinanf-boy/Source-Explain
[translate-svg]: http://llever.com/translate.svg
[translate-list]: https://github.com/chinanf-boy/chinese-translate-list
[size-img]: https://packagephobia.now.sh/badge?p=Name
[size]: https://packagephobia.now.sh/result?p=Name

「 rust 游乐场 」

---

## 校对 🀄️

<!-- doc-templite START generated -->
<!-- time = '2018-09-23' -->
<!-- repo = 'integer32llc/rust-playground' -->
<!-- commit = 'c54773e3b2112bd9d92297fa5af73ee80f58618b' -->
翻译的原文 | 与日期 | 最新更新 | 更多
---|---|---|---
[commit] | ⏰ 2018-09-23 | ![last] | [中文翻译][translate-list]

[last]: https://img.shields.io/github/last-commit/integer32llc/rust-playground.svg
[commit]: https://github.com/integer32llc/rust-playground/tree/c54773e3b2112bd9d92297fa5af73ee80f58618b

<!-- doc-templite END generated -->

- [ ] [网络页面的翻译]

### 贡献

欢迎 👏 勘误/校对/更新贡献 😊 [具体贡献请看](https://github.com/chinanf-boy/chinese-translate-list#贡献)

## 生活

[help me live , live need money 💰](https://github.com/chinanf-boy/live-need-money)

---

### 目录

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->


- [rust 游乐场](#rust-%E6%B8%B8%E4%B9%90%E5%9C%BA)
  - [它做了什么?](#%E5%AE%83%E5%81%9A%E4%BA%86%E4%BB%80%E4%B9%88)
  - [建筑材料](#%E5%BB%BA%E7%AD%91%E6%9D%90%E6%96%99)
  - [资源限制](#%E8%B5%84%E6%BA%90%E9%99%90%E5%88%B6)
    - [网络](#%E7%BD%91%E7%BB%9C)
    - [内容](#%E5%86%85%E5%AE%B9)
    - [执行时间处理时间](#%E6%89%A7%E8%A1%8C%E6%97%B6%E9%97%B4%E5%A4%84%E7%90%86%E6%97%B6%E9%97%B4)
    - [磁盘](#%E7%A3%81%E7%9B%98)
  - [安全名人堂](#%E5%AE%89%E5%85%A8%E5%90%8D%E4%BA%BA%E5%A0%82)
  - [发展](#%E5%8F%91%E5%B1%95)
    - [构建 UI](#%E6%9E%84%E5%BB%BA-ui)
    - [构建并运行服务器](#%E6%9E%84%E5%BB%BA%E5%B9%B6%E8%BF%90%E8%A1%8C%E6%9C%8D%E5%8A%A1%E5%99%A8)
    - [构建或下载容器](#%E6%9E%84%E5%BB%BA%E6%88%96%E4%B8%8B%E8%BD%BD%E5%AE%B9%E5%99%A8)
  - [部署](#%E9%83%A8%E7%BD%B2)
  - [执照](#%E6%89%A7%E7%85%A7)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# rust 游乐场

这是[rust 游乐场][real]的家,也[由 Integer 32 托管][us].

[real]: https://play.rust-lang.org/
[us]: https://play.integer32.com/

## 它做了什么?

游乐允许您在本地安装之前,尝试 Rust,或者在您可能没有编译器的任何其他情况下.

它具有许多功能,包括:

1.  一个漂亮,不显眼的编辑器,带有语法高亮.
2.  能够在调试或发布模式下,针对当前的稳定版,测试版或夜间版本的 Rust 进行编译.
3.  前 100 名受欢迎的crate(按历史下载量排名),板条箱是[Rust Cookbook][]的一部分,并且所有依赖项都可以使用.只需添加`extern foo`使用它们!
4.  能够快速加载代码,并将代码保存到 GitHub[gist][gist]并与您的朋友分享.
5.  [rustfmt][]和[clippy][clippy]可以针对源代码格式.
6.  能够查看源代码的 LLVM IR,assembly 或 Rust MIR.

[rust cookbook]: https://rust-lang-nursery.github.io/rust-cookbook/
[gist]: https://gist.github.com/
[rustfmt]: https://github.com/rust-lang-nursery/rustfmt
[clippy]: https://github.com/Manishearth/rust-clippy

## 建筑材料

一个[React][react]前端与一个[铁][iron]后端链接.[Docker][docker]容器用于提供各种编译器和工具以及帮助隔离它们.

我们希望这个前端和后端堆栈对于潜在的贡献者来说是舒适的! 如果您对贡献感兴趣,请随时提出问题,我们甚至可以指出一些有用的资源.

[react]: https://facebook.github.io/react/
[iron]: http://ironframework.io/
[docker]: https://www.docker.com/

## 资源限制

### 网络

编译器容器与外部世界之间没有网络连接.

### 内容

编译器和生成的可执行文件使用的内存量受容器限制.

### 执行时间处理时间

总编译和执行时间受容器限制.

### 磁盘

这个沙箱 **并没有** 任何磁盘的空间限制.其中运行服务器,临时目录空间是有限的.一个坏的演员可能会填满这个共享空间,但是当该请求结束时，应该就会清理掉它.

## 安全名人堂

感谢那些通过向 Playground 报告安全漏洞或其他攻击媒介而帮助过的人.每份报告都有助于我们改善游乐场!

- Stefan O'Rear 初步沙盒测试(PID 限制).

如果您想执行您认为可能会破坏 Playground 服务的测试,请联系我们,我们可以创建一个独立的克隆来执行测试! 修复后,您可以选择在此处记入.

## 发展

### 构建 UI

```
cd ui/frontend
yarn
yarn run watch # 观察变化并重构
```

如果您不需要后端运行,因为您只是进行基本的 HTML/CSS/JS 更改,请直接在浏览器中打开`ui/frontend/build/index.html`.

### 构建并运行服务器

配置你的`.env`文件如[ui README](./ui/README.md)中所述.

```
cd ui
cargo run
```

### 构建或下载容器

```
cd compiler
./build.sh # 如果你想测试 容器的变化
./fetch.sh # 如果你只想获得 当前的游乐场
```

## 部署

- [亚马逊 EC2(Ubuntu)](deployment/ubuntu.md)

## 执照

任何一种许可自由

- Apache 许可证,2.0 版([许可证 APACHE](LICENSE-APACHE)要么<http://www.apache.org/licenses/LICENSE-2.0>)
- MIT 许可证([LICENSE-MIT](LICENSE-MIT)要么<http://opensource.org/licenses/MIT>)根据你的选择.
