# 语音与 AI 提供商说明

## 录音与离线转写

点击麦克风直接开始录音。使用暂停／继续控制，停止后保存到本机；录音条目右侧三个点可重命名、转文字、在文件夹中定位。播放按钮旁可拖动进度。

首次使用 whisper.cpp：设置 → 输入与录音 → 安装离线转写。会下载 Windows CPU 引擎约 8.2 MB 和中英文 base 模型 147,951,465 字节（约 141 MiB，按十进制为 148 MB）。安装后转写不需要 API Key、订阅或网络；录音不会因为离线转写而上传。

引擎固定为官方 v1.9.2 Windows x64，SHA256：49dcc16de826f20bd53d44f947a1ae49dfa81f86cad67a64d80820cb192d674a。
模型来源 ggerganov/whisper.cpp，ggml-base.bin SHA256：60ed5bc3dd14eea856493d334349b405782ddcaf0028d4b5df4088345fba2efe。

依用户选择采用 https://github.com/ggml-org/whisper.cpp 。此前比较的备选为 https://github.com/k2-fsa/sherpa-onnx （便于后续实时识别）和 https://github.com/SYSTRAN/faster-whisper （更适合服务端与独立显卡部署）。这些适用方向是工程选型判断，不保证在所有电脑上有相同速度或准确率。

识别结果留在录音条目下，点击“整理为任务”进入可编辑草稿。识别可能出错，请确认时间与内容后再添加。需要云端识别时，选择“已配置的云端语音服务”；只有点击转文字才上传录音至所配置的服务。

## 本机 AI 提供商

AI → 提供商：检测程序、设置路径、启用／停用、选择模型。先在对应原生工具完成安装和登录，Gotta Do! 不读取或显示其令牌文件。已检测程序不等同于已登录。

| 通道 | 调用方式 | 模型 |
| --- | --- | --- |
| Claude Code | `claude -p` 的 JSON 输出 | 原生默认或用户填写 ID |
| Codex | `codex exec --json`，任务目录只读 | App Server `model/list` 真实目录 |
| DeepSeek Harness | `dsh --profile headless` | 跟随 DSH 原生配置 |
| Grok Build | headless JSON，关闭工具 | 原生默认或 `grok models` |
| OpenCode | `run --format json`，plan agent | 原生默认或 `opencode models` |
| Pi | `--mode json --no-tools` | 原生默认或 `--list-models` |
| API | 原有兼容接口 | 在连接中配置 |

此轮定位为任务提取与草稿生成，不提供完整编程工作台、MCP 客户端或任意文件自动写入。用户确认添加后才改变任务。工作目录为应用专用目录；各 CLI 仍可能加载其自身的用户配置与插件，原生工具的行为由其版本和设置决定。

## Skill

AI → 技能，可保存、导入、导出文本 Skill；“同步本机技能”让用户选择文件夹，读取其中的 SKILL.md。自动同步最多补充到 30 项，跳过同名项目；不执行目录中的脚本，不自动跟随符号链接或读取其他文件。技能模板会随请求发送给用户选中的提供商。

## 已测试范围

录音媒体链路：测试设备；真实语音转写：官方 jfk.wav 示例。未采集用户本人的音频，未评估其麦克风硬件和中文口音准确率。Codex 真实检测与模型目录已验证；其余未安装工具的响应解析使用格式样本验证，实际登录／计费与模型可用性需在安装后确认。
