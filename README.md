<p align="center"><img src="assets/logo.png" width="104" alt="Gotta Do!"></p>

<h1 align="center">Gotta Do!</h1>

<p align="center">常驻 Windows 桌面的待办、日历与随手记。</p>
<p align="center"><strong>简体中文</strong> · <a href="README.en.md">English</a></p>
<p align="center"><a href="https://github.com/mikeywu913/gotta-do/releases/download/v0.8.2/Gotta-Do-0.8.2-Windows-Portable.zip"><strong>下载 Windows 便携版</strong></a> · <a href="https://github.com/mikeywu913/gotta-do/releases/tag/v0.8.2">v0.8.2 更新说明</a> · <a href="https://github.com/mikeywu913/gotta-do/issues/new/choose">反馈问题</a></p>

## 下载与运行

| 系统 | 下载 | 版本 |
| --- | --- | --- |
| 推荐 Windows 11 x64 | [Portable ZIP](https://github.com/mikeywu913/gotta-do/releases/download/v0.8.2/Gotta-Do-0.8.2-Windows-Portable.zip) | 0.8.2 公开测试版 |

1. 将 ZIP **完整解压**到有写入权限的文件夹。
2. 打开解压后的 **Gotta Do!.exe**。运行无需 Node.js。
3. GitHub 自动生成的 Source code 压缩包不可直接运行。

应用当前未签名。可在发布页下载 `SHA256SUMS.txt`，核对文件摘要。

## 使用指南

| 想做什么 | 操作 |
| --- | --- |
| 快速添加任务 | 点黄色「添加任务」。可以填标签、日期和时段，随后在日历里查看。 |
| 在桌面随时看到任务 | 在设置中开启「固定到桌面」。Win+D 回到桌面时可继续查看。 |
| 录音与离线转写 | 点麦克风开始录音，停止后在音频条目的菜单中点「转文字」。内置 Whisper 模型，无需 API Key。 |
| 记笔记与回顾 | 顶栏打开随手记、日志或周报。随手记支持 Markdown 编辑和预览。 |
| 设置语言与窗口 | 设置中可切换中文或 English，也可调整窗口外观和滑出行为。 |

## 从旧版升级

先从托盘彻底退出旧版，再把新版解压到新文件夹。任务和设置沿用本机用户目录。请将旧程序旁的 **Notes** 整个复制到新程序旁，包含 `.index.json`。

[详细测试指南](TESTING.md) · [AI 配置](AI-SETUP.md) · [本机数据说明](PRIVACY.md) · [版权](COPYRIGHT.md)
