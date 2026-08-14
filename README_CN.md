<div align="center">

# DaVinci Whisper

在 DaVinci Resolve 中使用 Whisper 自动转录并生成时间线字幕。

[English](README.md) | **简体中文**

[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![DaVinci Resolve](https://img.shields.io/badge/DaVinci%20Resolve-Utility%20Script-orange)](https://www.blackmagicdesign.com/products/davinciresolve)

</div>

## 功能

- 支持本地 `faster-whisper` 模型和 OpenAI 兼容 API 转录。
- 支持 `tiny`、`base`、`small`、`medium`、`large-v3` 本地模型。
- 可从当前时间线或所选媒体渲染音频、生成 SRT，并导入字幕轨道。
- 支持自动语言检测、热词、单条字幕最大字符数、标点清理和去除字幕间隙等设置。
- 支持可选的 AI 文本修正流程。
- 脚本界面可以在英文和中文之间切换。
- 提供 macOS 和 Windows 安装脚本。

## 环境要求

- 支持 Utility Scripts 的 DaVinci Resolve
- Python 3.9–3.12
- macOS 或 Windows
- 本地转录需要单独下载 Whisper 模型
- 云端转录需要有效的 OpenAI 兼容 API 配置

## 安装

### 1. 获取项目

```bash
git clone https://github.com/heiba-wk/DaVinci-Whisper.git
cd DaVinci-Whisper
```

也可以通过 GitHub 的 **Code** 菜单下载 ZIP 压缩包。

### 2. 安装脚本和依赖

- **macOS：** 双击 `Mac_Install.command`，按提示输入管理员密码。
- **Windows：** 运行 `Windows_Install.bat`，并按提示允许管理员权限。

安装器会把 `DaVinci Whisper` 脚本复制到 Resolve 的 Utility Scripts 目录，并安装所需 Python 依赖。安装完成后，请完全退出并重新打开 DaVinci Resolve。

### 3. 安装本地模型

Whisper 模型权重文件过大，因此所有 `model.bin` 均不包含在 Git 仓库中。请下载需要使用的完整模型文件夹：

- [Google Drive](https://drive.google.com/drive/folders/16FLicjnstLhrl3yKgCHOvle5-3_mLii5?usp=sharing)
- [百度网盘](https://pan.baidu.com/s/1kthNbHJAggTUT2cv9nKaUg?pwd=8888)（提取码：`8888`）

把下载后的模型文件放入对应目录：

```text
DaVinci Whisper/
└── model/
    ├── tiny/model.bin
    ├── base/model.bin
    ├── small/model.bin
    ├── medium/model.bin
    └── large-v3/model.bin
```

只需下载你实际使用的模型。请将每个模型的配置、tokenizer、vocabulary 和 `model.bin` 文件完整保留在同一目录中。

## 使用

1. 打开 DaVinci Resolve。
2. 进入 `工作区（Workspace） > 脚本（Scripts） > Utility`。
3. 点击 `DaVinci Whisper`。
4. 选择本地模型或云端 API 模式。
5. 设置语言、热词和字幕选项。
6. 在时间线或媒体池中准备好需要转录的内容，然后开始转录。

更完整的中英文说明请查看 [Installation-Usage-Guide.html](Installation-Usage-Guide.html)。

## 隐私与网络请求

- 本地 `faster-whisper` 转录在你的电脑上执行。
- 云端转录会把所选音频发送到你配置的 API 服务。
- 更新检查和部分托管功能可能连接 HEIBA 后端服务。
- API 密钥和运行时会话不应提交到 Git；本仓库已通过 `.gitignore` 排除运行时会话文件。

## 支持项目

- [更多 HEIBA 插件](https://www.heibagen.com/plugins)
- [通过 Ko-fi 支持开发](https://ko-fi.com/G2G31A6SQU)

## 许可证

DaVinci Whisper 使用 [MIT License](LICENSE) 开源。第三方模型、服务和依赖仍受各自许可证及服务条款约束。
