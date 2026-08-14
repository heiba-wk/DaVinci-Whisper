<div align="center">

# DaVinci Whisper

Transcribe audio and create timeline subtitles directly in DaVinci Resolve.

**English** | [简体中文](README_CN.md)

[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![DaVinci Resolve](https://img.shields.io/badge/DaVinci%20Resolve-Utility%20Script-orange)](https://www.blackmagicdesign.com/products/davinciresolve)

</div>

## Features

- Transcribe with local `faster-whisper` models or an OpenAI-compatible API.
- Use `tiny`, `base`, `small`, `medium`, and `large-v3` local models.
- Render audio from the current timeline or selected media, generate an SRT file, and import it into a subtitle track.
- Configure automatic language detection, hotwords, maximum subtitle length, punctuation trimming, and gap removal.
- Optionally refine transcription text with an AI correction workflow.
- Switch the script interface between English and Chinese.
- Install on macOS or Windows with the included setup scripts.

## Requirements

- DaVinci Resolve with Utility Scripts support
- Python 3.9–3.12
- macOS or Windows
- A separately downloaded Whisper model for local transcription
- A valid OpenAI-compatible API configuration for cloud transcription

## Installation

### 1. Get the project

```bash
git clone https://github.com/heiba-wk/DaVinci-Whisper.git
cd DaVinci-Whisper
```

You can also download a ZIP archive from the GitHub **Code** menu.

### 2. Install the script and dependencies

- **macOS:** Double-click `Mac_Install.command` and enter the administrator password when prompted.
- **Windows:** Run `Windows_Install.bat` and allow administrator access when prompted.

The installer copies the `DaVinci Whisper` script into Resolve's Utility Scripts directory and installs the required Python dependencies. Fully quit and reopen DaVinci Resolve after installation.

### 3. Install a local model

Whisper model weights are too large for this Git repository, so all `model.bin` files are distributed separately. Download the complete folder for each model you want to use:

- [Google Drive](https://drive.google.com/drive/folders/16FLicjnstLhrl3yKgCHOvle5-3_mLii5?usp=sharing)
- [Baidu Netdisk](https://pan.baidu.com/s/1kthNbHJAggTUT2cv9nKaUg?pwd=8888) (access code: `8888`)

Place the downloaded model files in the matching directories:

```text
DaVinci Whisper/
└── model/
    ├── tiny/model.bin
    ├── base/model.bin
    ├── small/model.bin
    ├── medium/model.bin
    └── large-v3/model.bin
```

You only need to download the models you plan to use. Keep each model's configuration, tokenizer, vocabulary, and `model.bin` files together in the same directory.

## Usage

1. Open DaVinci Resolve.
2. Go to `Workspace > Scripts > Utility`.
3. Click `DaVinci Whisper`.
4. Select a local model or cloud API mode.
5. Configure the language, hotwords, and subtitle options.
6. Prepare the content on the timeline or in the Media Pool, then start transcription.

For a more detailed bilingual guide, open [Installation-Usage-Guide.html](Installation-Usage-Guide.html).

## Privacy and network access

- Local `faster-whisper` transcription runs on your computer.
- Cloud transcription sends the selected audio to the API service you configure.
- Update checks and some managed features may connect to HEIBA backend services.
- API keys and runtime sessions must not be committed to Git. Runtime session files are excluded by this repository's `.gitignore`.

## Support

- [More HEIBA plugins](https://www.heibagen.com/plugins)
- [Support development on Ko-fi](https://ko-fi.com/G2G31A6SQU)

## License

DaVinci Whisper is released under the [MIT License](LICENSE). Third-party models, services, and dependencies remain subject to their own licenses and terms.
