<div align="center">

# DaVinci Whisper

在 DaVinci Resolve 中使用 Whisper 自动转录并生成时间线字幕。

Transcribe audio and create timeline subtitles directly in DaVinci Resolve.

[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![DaVinci Resolve](https://img.shields.io/badge/DaVinci%20Resolve-Utility%20Script-orange)](https://www.blackmagicdesign.com/products/davinciresolve)

</div>

## 功能

- 支持本地 `faster-whisper` 转录和 OpenAI 兼容 API 转录。
- 支持 `tiny`、`base`、`small`、`medium`、`large-v3` 本地模型。
- 可从当前时间线或所选媒体渲染音频、生成 SRT，并导入字幕轨道。
- 支持自动语言检测、中英文界面、热词、单条字幕最大字符数、去除字幕间隙等设置。
- 支持可选的 AI 文本修正流程。
- 支持 macOS 与 Windows 安装脚本。

## 环境要求

- DaVinci Resolve（需要支持 Utility Scripts）
- Python 3.9–3.12
- macOS 或 Windows
- 本地转录需要单独下载 Whisper 模型
- 云端转录需要可用的 OpenAI 兼容 API 配置

## 安装

### 1. 获取项目

```bash
git clone https://github.com/heiba-wk/DaVinci-Whisper.git
cd DaVinci-Whisper
```

也可以在 GitHub 的 Releases 或 Code 菜单中下载 ZIP。

### 2. 安装脚本和依赖

- macOS：双击 `Mac_Install.command`，按提示输入管理员密码。
- Windows：右键或双击运行 `Windows_Install.bat`，并允许管理员权限。

安装器会把 `DaVinci Whisper` 脚本复制到 Resolve 的 Utility Scripts 目录，并安装所需 Python 依赖。安装完成后，请完全退出并重新打开 DaVinci Resolve。

### 3. 安装本地模型

由于模型文件很大，`model.bin` 不包含在 Git 仓库中。请下载需要的完整模型文件夹：

- [Google Drive（国际）](https://drive.google.com/drive/folders/16FLicjnstLhrl3yKgCHOvle5-3_mLii5?usp=sharing)
- [百度网盘（中国大陆，提取码：8888）](https://pan.baidu.com/s/1kthNbHJAggTUT2cv9nKaUg?pwd=8888)

把下载后的模型文件放入对应目录，并确保至少存在如下文件：

```text
DaVinci Whisper/
└── model/
    ├── tiny/model.bin
    ├── base/model.bin
    ├── small/model.bin
    ├── medium/model.bin
    └── large-v3/model.bin
```

只需下载你实际使用的模型。请保留下载包内与 `model.bin` 同目录的配置、tokenizer 和 vocabulary 文件。

## 使用

1. 打开 DaVinci Resolve。
2. 进入 `工作区（Workspace） > 脚本（Scripts） > Utility`。
3. 点击 `DaVinci Whisper`。
4. 选择本地模型或云端 API 模式，设置语言、热词和字幕参数。
5. 在时间线或媒体池中准备好需要转录的内容，然后开始转录。

更完整的中英文图文说明请查看 [Installation-Usage-Guide.html](Installation-Usage-Guide.html)。

## 隐私与网络请求

- 本地 `faster-whisper` 模式在本机执行语音识别。
- 云端模式会把待转录音频发送到你选择的 API 服务。
- 更新检查和部分托管功能可能访问 HEIBA 的后端服务。
- API 密钥和运行时会话不应提交到 Git；本仓库已通过 `.gitignore` 排除运行时会话文件。

## English

DaVinci Whisper is a bilingual Utility script for DaVinci Resolve. It can render audio from a timeline or selected media, transcribe it with local `faster-whisper` models or an OpenAI-compatible API, generate an SRT file, and import subtitles into Resolve.

### Quick start

1. Clone or download this repository.
2. Run `Mac_Install.command` on macOS or `Windows_Install.bat` on Windows.
3. Download the required local model from [Google Drive](https://drive.google.com/drive/folders/16FLicjnstLhrl3yKgCHOvle5-3_mLii5?usp=sharing) or [Baidu Netdisk](https://pan.baidu.com/s/1kthNbHJAggTUT2cv9nKaUg?pwd=8888) (code: `8888`).
4. Put the complete model files under `DaVinci Whisper/model/<model-name>/`.
5. Restart Resolve and open `Workspace > Scripts > Utility > DaVinci Whisper`.

Model weights (`model.bin`) are intentionally excluded from this repository because of their size. Download only the models you need and keep all accompanying configuration and tokenizer files together.

## 支持项目 / Support

- [更多 HEIBA 插件](https://www.heibagen.com/plugins)
- [Ko-fi](https://ko-fi.com/G2G31A6SQU)

## 许可证

本项目使用 [MIT License](LICENSE) 开源。第三方模型、服务和依赖仍受各自许可证及服务条款约束。

