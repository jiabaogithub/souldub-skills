# Video Translate Skill – AI Video Translation, Dubbing & SRT Subtitles [![Security: B — Skills Directory](https://www.skillsdirectory.com/api/skills/gravityvortex-souldub-video-translate/badge)](https://www.skillsdirectory.com/skills/gravityvortex-souldub-video-translate)

[English](README.md) | [简体中文](README.zh-CN.md) | [Español](README.es.md) | [ไทย](README.th.md)

<p align="center">
  <img src="cover-readme.png" alt="Video Translate Skill – SoulDub AI video translation skill cover" width="760">
</p>

**Video Translate Skill** is an AI-powered video translation workflow that translates the spoken audio in your videos into another language, generates timed SRT subtitles, creates dubbed speech with text-to-speech (TTS), and merges the new audio track back into the video, all in one automated pipeline.

Built on **[SoulDub](https://souldub.ai) AI**, it translates local MP4 videos with **original-voice dubbing**, so the dubbed speech keeps the feel of the original speaker. When processing is finished, you can download:

- the **translated video**
- **target-language subtitles** (SRT)
- **bilingual SRT subtitles**

---

## Table of Contents

- [What is Video Translate Skill?](#what-is-video-translate-skill)
- [Features](#features)
- [Installation](#installation)
- [Requirements](#requirements)
- [Usage](#usage)
- [How It Works](#how-it-works)
- [Output Files](#output-files)
- [Configuration & Privacy](#configuration--privacy)
- [Use Cases](#use-cases)
- [FAQ](#faq)

---

## What is Video Translate Skill?

Video Translate Skill is an automated **AI video translator** for creators, educators, and teams who need multilingual video content. Instead of transcribing, translating, subtitling, recording voice-overs, and editing by hand, you provide a local MP4 file and the skill handles the whole workflow: speech recognition, translation, subtitle timing, TTS dubbing, and audio merging.

## Features

- **AI video translation** – translates spoken content from one language into another.
- **Original-voice dubbing** – powered by SoulDub AI to keep the speaker's vocal character.
- **Timed subtitle generation** – produces accurate SRT subtitles synced to the speech.
- **Bilingual SRT subtitles** – source and target language displayed together, ideal for language learning and review.
- **Text-to-speech (TTS) dubbing** – generates natural-sounding speech in the target language.
- **Automatic audio merging** – replaces the original audio track with the dubbed one.
- **Local MP4 support** – works directly with MP4 files on your machine.

## Installation

Install the skill for your AI agent with one command:

```bash
npx skills add jiabaogithub/souldub-skills --skill souldub-video-translate
```

## Requirements

- Python 3.11 or later
- [`uv`](https://docs.astral.sh/uv/)
- Internet connection
- A SoulDub API key
- Read access to the source video and write access to the output folder

### Set your API key

Use either method:

```yaml
# ~/.souldub/souldub.config.yaml
souldub_api_key: "YOUR_API_KEY"
```

```bash
export SOULDUB_API_KEY="YOUR_API_KEY"
```

Check authentication:

```bash
uv run scripts/video_translation.py auth status
```

## Usage

After installation, just tell your agent the **video path** and the **target language**, for example:

> Translate `/path/to/video.mp4` into English with original-voice dubbing.

The agent will ask for any missing information, start the task, report progress, and return the output paths.

## How It Works

1. **Input** – provide a local MP4 video and choose the target language.
2. **Translate** – the spoken audio is recognized and translated into the target language.
3. **Subtitle** – timed SRT subtitles are generated, including a bilingual version.
4. **Dub** – TTS creates the dubbed speech, with original-voice dubbing via SoulDub AI.
5. **Merge** – the new audio track is merged back into the video.
6. **Download** – get the translated video and subtitle files.

## Output Files

| File | Description |
| --- | --- |
| Translated video (MP4) | Video with the dubbed audio track in the target language |
| Target-language SRT | Timed subtitles in the translated language |
| Bilingual SRT | Subtitles showing both original and translated text |

By default, files are saved as `result.mp4`, `translated.srt`, and `bilingual.srt` in a `souldub_outputs/` folder next to the source video.

## Configuration & Privacy

- Installed skill files are treated as read-only; runtime state is stored in your platform's user state directory.
- Outputs are written to `souldub_outputs/` beside the source video by default.
- The skill does not persist API keys, pre-signed upload URLs, media gateway URLs, or temporary signed parameters.

## Use Cases

- **Video localization** for global product launches and marketing
- **Course and tutorial translation** for online education
- **Cross-border content distribution** on YouTube, TikTok, and more
- **Multilingual subtitles** for accessibility and language learning

## FAQ

**What does Video Translate Skill do?**\
It translates the speech in a video into another language, generates SRT subtitles, creates AI dubbing with TTS, and merges the new audio into the video.

**Which video format is supported?**\
Local MP4 videos.

**Can I keep the original speaker's voice?**\
Yes. The skill uses SoulDub AI for original-voice dubbing.

**What subtitle formats do I get?**\
Target-language SRT and bilingual SRT.

---

If you find **Video Translate Skill** useful, please give the repository a ⭐ so more people can discover this AI video translation tool.
