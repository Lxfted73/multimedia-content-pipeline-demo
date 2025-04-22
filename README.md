# HistoryReels

![Python](https://img.shields.io/badge/Python-3.9+-blue.svg) ![APIs](https://img.shields.io/badge/APIs-xAI%20|%20ElevenLabs%20|%20Leonardo-orange.svg) ![Cloud](https://img.shields.io/badge/Cloud-Google%20Drive%20|%20YouTube-green.svg)

A scalable Python-based pipeline to automate the creation, processing, and deployment of educational YouTube Shorts for novice investors. This project integrates multiple AI APIs (xAI Grok, ElevenLabs, Leonardo AI) and cloud services (Google Drive, YouTube Data API) to transform historical narratives into narrated, visually rich videos.

**[Watch a Sample Short](https://www.youtube.com/@TheHistoryOfGains)**
---

## Features

- **Script Generation**: Generates two 130-word historical scripts (e.g., Ottoman Empire trade shifts) with causal analysis and 3-4 puns using xAI Grok API, saved as `grok_scripts.json`.
- **Scene Segmentation**: Splits scripts into 10 scenes each for narration, stored in `grok_scenes.json`.
- **Audio Creation**: Converts text to speech with ElevenLabs API (Adam voice), outputting MP3 files.

- **Image Generation**: Produces 20 scene-specific images (720x1280) via Leonardo AI, uploaded to timestamped Google Drive folders.
- **Video Deployment**: Uploads final videos to YouTube with AI-generated descriptions, including hashtags and calls-to-action.
- **Scalability**: Modular design supports additional scripts/scenes with parallel processing potential.
- **Error Handling**: Robust validation, fallbacks, and logging for API failures, file issues, and authentication.

---

## Project Structure
```
multimedia-content-pipeline/
├── audio_output/             # Generated audio files
├── Script_YYYY-MM-DD_HH-MM-SS/ # Timestamped image downloads
├── grok_scripts.json         # Generated scripts
├── grok_scenes.json          # Scene breakdowns
├── grok_image_prompts.json   # Image prompts and URLs
├── .env                      # Environment variables (not tracked)
├── requirements.txt          # Python dependencies
├── script_generator.py       # Script generation script
├── scene_generator.py        # Scene segmentation script
├── audio_generator.py        # Audio creation script
├── image_generator.py        # Image generation/upload script
├── youtube_uploader.py       # YouTube upload script
└── README.md                 # This file
```

## Usage

- **Generate Scripts**: Run `script_generator.py` to create two historical scripts based on the Ottoman Empire idea.
- **Segment Scenes**: Use `scene_generator.py` to break scripts into 10 scenes each.
- **Create Audio**: Execute `audio_generator.py` to produce MP3 files in `audio_output/`.
- **Generate Images**: Run `image_generator.py` to create and upload images to Google Drive.
- **Upload Videos**: Combine assets manually (e.g., via `moviepy`) or use `youtube_uploader.py` with pre-made MP4s.

*Note*: For full automation, stitch audio/images into videos using a tool like `moviepy` before uploading.

## Future Enhancements

- Add custom ML models (e.g., fine-tuned GPT for scripts, GAN for image refinement).
- Implement parallel processing with `asyncio` for faster scene/image generation.
- Build a Streamlit UI for inputting ideas and viewing outputs.
- Deploy 5+ Shorts and track engagement (e.g., 500+ views).

## Tech Stack

- **Languages**: Python
- **Libraries**: `openai`, `requests`, `google-auth-oauthlib`, `googleapiclient`, `dotenv`, `re`
- **APIs**: xAI Grok, ElevenLabs, Leonardo AI, Google Drive, YouTube Data API
- **Concepts**: API integration, OAuth 2.0, JSON parsing, cloud storage, error handling
