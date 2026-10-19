# Video Translate Skill – AI 视频翻译、配音与 SRT 字幕 [![Security: B — Skills Directory](https://www.skillsdirectory.com/api/skills/gravityvortex-souldub-video-translate/badge)](https://www.skillsdirectory.com/skills/gravityvortex-souldub-video-translate)

[English](README.md) | [简体中文](README.zh-CN.md) | [Español](README.es.md) | [ไทย](README.th.md)

<p align="center">
  <img src="cover-readme.png" alt="Video Translate Skill – SoulDub AI 视频翻译 Skill 封面" width="760">
</p>

**Video Translate Skill** 是一个由 AI 驱动的视频翻译工作流：它会把视频中的语音音频翻译成另一种语言，生成带时间轴的 SRT 字幕，通过文本转语音（TTS）创建配音，并将新的音轨合并回视频，全程在一个自动化流水线中完成。

它基于 **[SoulDub](https://souldub.ai) AI** 构建，可对本地 MP4 视频进行**原声配音**翻译，让配音语音保留原说话人的语气。处理完成后，你可以下载：

- 译制后的**视频**
- **目标语言字幕**（SRT）
- **双语 SRT 字幕**

---

## 目录

- [什么是 Video Translate Skill？](#what-is-video-translate-skill)
- [功能](#features)
- [安装](#installation)
- [环境要求](#requirements)
- [使用](#usage)
- [工作原理](#how-it-works)
- [输出文件](#output-files)
- [配置与隐私](#configuration--privacy)
- [使用场景](#use-cases)
- [FAQ](#faq)

---

<a name="what-is-video-translate-skill"></a>
## 什么是 Video Translate Skill？

Video Translate Skill 是一个面向创作者、教育者和团队的全自动化 **AI 视频翻译器**，用于制作多语言视频内容。无需手动转写、翻译、加字幕、录制旁白和剪辑，你只需提供本地 MP4 文件，Skill 便会处理整个工作流：语音识别、翻译、字幕时间轴、TTS 配音和音频合并。

<a name="features"></a>
## 功能

- **AI 视频翻译** – 将语音内容从一种语言翻译成另一种语言。
- **原声配音** – 由 SoulDub AI 提供支持，保留说话人的音色。
- **带时间轴的字幕生成** – 生成与语音同步的精确 SRT 字幕。
- **双语 SRT 字幕** – 源语言与目标语言同时显示，适合语言学习和审校。
- **文本转语音（TTS）配音** – 以目标语言生成自然流畅的语音。
- **自动音频合并** – 用配音音轨替换原始音轨。
- **本地 MP4 支持** – 直接处理你本机上的 MP4 文件。

<a name="installation"></a>
## 安装

只需一条命令即可为你的 AI Agent 安装该 Skill：

```bash
npx skills add jiabaogithub/souldub-skills --skill souldub-video-translate
```

<a name="requirements"></a>
## 环境要求

- Python 3.11 或更高版本
- [`uv`](https://docs.astral.sh/uv/)
- 网络连接
- SoulDub API 密钥
- 源视频的读取权限，以及输出文件夹的写入权限

### 设置你的 API 密钥

两种方式任选其一：

```yaml
# ~/.souldub/souldub.config.yaml
souldub_api_key: "YOUR_API_KEY"
```

```bash
export SOULDUB_API_KEY="YOUR_API_KEY"
```

检查认证状态：

```bash
uv run scripts/video_translation.py auth status
```

<a name="usage"></a>
## 使用

安装后，只需告诉 Agent **视频路径** 和 **目标语言**，例如：

> 将 `/path/to/video.mp4` 翻译成英文并采用原声配音。

Agent 会询问缺失的信息、启动任务、报告进度，并返回输出文件路径。

<a name="how-it-works"></a>
## 工作原理

1. **输入** – 提供本地 MP4 视频并选择目标语言。
2. **翻译** – 识别语音音频并翻译成目标语言。
3. **字幕** – 生成带时间轴的 SRT 字幕，包括双语版本。
4. **配音** – TTS 创建配音语音，通过 SoulDub AI 实现原声配音。
5. **合并** – 将新的音轨合并回视频。
6. **下载** – 获取译制视频和字幕文件。

<a name="output-files"></a>
## 输出文件

| 文件 | 说明 |
| --- | --- |
| 译制视频（MP4） | 带有目标语言配音音轨的视频 |
| 目标语言 SRT | 已翻译语言的带时间轴字幕 |
| 双语 SRT | 同时显示原文和译文的字幕 |

默认情况下，文件会保存为 `result.mp4`、`translated.srt` 和 `bilingual.srt`，存放在源视频旁边的 `souldub_outputs/` 文件夹中。

<a name="configuration--privacy"></a>
## 配置与隐私

- 已安装的 Skill 文件按只读方式处理；运行时状态存储在你的平台用户状态目录中。
- 输出默认写入源视频旁边的 `souldub_outputs/` 文件夹。
- 该 Skill 不会持久化 API 密钥、预签名上传 URL、媒体网关 URL 或临时签名参数。

<a name="use-cases"></a>
## 使用场景

- 全球产品发布和营销的视频本地化
- 在线教育的课程和教程翻译
- 在 YouTube、TikTok 等平台进行跨地区内容分发
- 面向无障碍访问和语言学习的多语言字幕

<a name="faq"></a>
## FAQ

**Video Translate Skill 能做什么？**\
它会把视频中的语音翻译成另一种语言、生成 SRT 字幕、用 TTS 创建 AI 配音，并将新音频合并到视频中。

**支持哪种视频格式？**\
本地 MP4 视频。

**能否保留原说话人的声音？**\
可以。该 Skill 使用 SoulDub AI 进行原声配音。

**我能获得哪些字幕格式？**\
目标语言 SRT 和双语 SRT。

---

如果你觉得 **Video Translate Skill** 有用，请给仓库点个 ⭐，让更多人发现这款 AI 视频翻译工具。
