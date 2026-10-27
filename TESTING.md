# Gotta Do! 0.5.0 测试指南 / Testing guide

这是 Windows 桌面开发预览版。推荐 Windows 11 x64；Windows 10 x64 尚未完成完整兼容性验证。macOS、Linux、ARM64 未提供测试包。

## 下载与运行 / Download and run

1. 打开 [Releases](https://github.com/mikeywu913/gotta-do/releases)，选择标记为 Pre-release 的 v0.5.0。
2. 下载 **Gotta-Do-0.5.0-Windows-Portable.zip**；7z 是同一内容的更小压缩格式，需要相应解压工具。
3. 把压缩包完整解压到一个可写目录，再打开里面的 **Gotta Do!.exe**。不要在压缩包内直接运行，不要只复制 EXE。
4. 运行软件不需要安装 Node.js、npm 或 Git。当前包未签名，Windows 可能显示来源警告；请核对发布地址和随包 SHA256 校验值。组织策略阻止时应联系管理员。
5. 更新前从旧版右下角托盘菜单选择退出，再运行新目录中的版本。

**GitHub 自动提供的 Source code (zip/tar.gz) 不是 Windows 运行包。** 请下载上面指定名称的 Portable 压缩包。

Download the named Windows Portable archive from Releases, extract the **whole folder**, then run **Gotta Do!.exe**. Node.js is not required. The automatic GitHub “Source code” archives are not runnable Windows packages. The app is unsigned.

## 建议测试流程

- 新建任务，编辑详情、标签、时间段；开始、完成、收藏、放弃与还原。
- 拖动窗口并调整大小，修改主题、字号、不透明度与磨砂。
- 完全退出后重开，检查任务和设置是否保留；再检查托盘恢复、Win+D、桌面固定和置顶。
- 在设置中切换 English，确认任务原文没有被改写。
- 打开 ✦ AI，输入“明天下午六点半学习英语；完成项目报告”，先使用本机规则提取；检查草稿、批量添加和撤销。
- AI 云端、云端语音需要自行配置服务商账号与密钥。基础任务与本机规则提取无需 AI 账号。
- Windows 本机语音识别需要安装对应中/英文语音包；语音方式和配置详见 [AI 使用说明](AI-SETUP.md)。

## 数据、已知限制与反馈

- 任务、偏好和窗口位置保存在当前 Windows 用户的应用数据目录；通常为 %APPDATA%/gotta-do-desktop。分发包不带开发者任务或密钥。
- 更新前可在完全退出软件后手动备份该目录。不同版本应避免同时运行。
- 云端 AI 请求按用户选择的服务商计费；默认不附带任务上下文，勾选后才发送。密钥由 Windows 加密保存；不要把个人数据目录上传到 Issues。
- 云端接口用模拟服务验证过，尚未对所有服务商与真实麦克风环境完成验证。AI 输出必须确认后才添加任务。
- 当前无云同步、托管账号、支付或 MCP 连接器；Electron 运行时升级与签名安装包列为后续发行工作。
- 出错时请提交 [Issue](https://github.com/mikeywu913/gotta-do/issues/new/choose)，包含系统版本、操作步骤、预期与实际结果。截图应遮盖个人内容，日志请移除姓名、任务和账号信息；不要提交 API Key。

## 校验下载

发布附件附带 SHA256SUMS.txt。PowerShell 示例：

~~~powershell
Get-FileHash -Algorithm SHA256 -LiteralPath '.\Gotta-Do-0.5.0-Windows-Portable.zip'
~~~

将 Hash 与校验文件对应条目比较。校验能发现传输损坏，不能代替发布者身份验证。
