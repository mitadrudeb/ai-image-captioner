# 🖼️ AI Image Captioner — Multi-Model, Multi-Source

An AI-powered image captioning tool that uses **open-source models** to describe images. Upload a photo or paste a webpage URL — the AI will generate captions for every image it finds.

![Python](https://img.shields.io/badge/Python-3.9+-blue?logo=python&logoColor=white)
![Hugging Face](https://img.shields.io/badge/🤗_Hugging_Face-Transformers-orange)
![Gradio](https://img.shields.io/badge/Gradio-UI-brightgreen)
![License](https://img.shields.io/badge/License-MIT-yellow)

## ✨ Features

| Feature | Description |
|---------|-------------|
| **Image Upload** | Upload any image from your device and get an AI-generated caption |
| **URL Scraping** | Paste a webpage URL → auto-scrape and caption all images on the page |
| **Model Switching** | Switch between BLIP and Florence-2 models to compare results |
| **Cross-Platform** | Runs on Windows, Linux, macOS, and Google Colab |
| **Zero API Cost** | 100% open-source, no API keys needed |

## 🤖 Models Used

| Model | Params | Type | Link |
|-------|--------|------|------|
| Salesforce/blip-image-captioning-base | ~0.25B | Image-to-text | [Hugging Face](https://huggingface.co/Salesforce/blip-image-captioning-base) |
| microsoft/Florence-2-base | ~0.23B | Vision foundation model | [Hugging Face](https://huggingface.co/microsoft/Florence-2-base) |

Both models run comfortably on **CPU** (a GPU will make inference faster).

## 🚀 Quick Start

### Option 1: Google Colab (Easiest)

[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/mitadrudeb/ai-image-captioner/blob/main/AI_Image_Captioner.ipynb)

> Replace `YOUR_USERNAME` with your GitHub username after pushing the repo.

### Option 2: Run Locally

```bash
# 1. Clone the repo
git clone https://github.com/mitadrudeb/ai-image-captioner.git
cd ai-image-captioner

# 2. Create a virtual environment (recommended)
python -m venv venv
source venv/bin/activate        # Linux/macOS
# venv\Scripts\activate          # Windows

# 3. Install dependencies
pip install -r requirements.txt

# 4. Run the notebook
jupyter notebook AI_Image_Captioner.ipynb
```

The Gradio app will launch at `http://127.0.0.1:7860`.

## 📸 How It Works

```
┌─────────────┐     ┌──────────────┐     ┌─────────────┐     ┌──────────┐
│  Image       │ ──► │  Processor    │ ──► │  AI Model    │ ──► │  Caption  │
│  (upload/url)│     │  (resize,     │     │  (BLIP or    │     │  (text)   │
│              │     │   normalize)  │     │   Florence)  │     │           │
└─────────────┘     └──────────────┘     └─────────────┘     └──────────┘
```

### Upload Mode
1. User uploads an image through the Gradio interface
2. The image is processed and passed to the selected model
3. The model generates a text caption

### URL Mode
1. User pastes a webpage URL
2. BeautifulSoup scrapes all `<img>` tags from the HTML
3. Each image is downloaded, filtered (skip SVGs, tiny icons)
4. The selected model captions each valid image
5. All captions are displayed in a formatted output

## 🛠️ Tech Stack

- **[Transformers](https://huggingface.co/docs/transformers)** — Load and run AI models
- **[PyTorch](https://pytorch.org/)** — Deep learning backend
- **[Gradio](https://gradio.app/)** — Interactive web UI
- **[BeautifulSoup](https://www.crummy.com/software/BeautifulSoup/)** — HTML parsing / web scraping
- **[Pillow](https://pillow.readthedocs.io/)** — Image processing

## 📂 Project Structure

```
ai-image-captioner/
├── AI_Image_Captioner.ipynb   # Main notebook (run this!)
├── requirements.txt           # Python dependencies
├── README.md                  # This file
├── LICENSE                    # MIT License
└── .gitignore                 # Git ignore rules
```

## 📝 What I Learned

This is a beginner-level AI/ML project I built while learning LLM engineering. Key takeaways:

- How to load and run pre-trained models from Hugging Face
- The image captioning pipeline: image → processor → model → text
- Web scraping with BeautifulSoup to collect images from any webpage
- Building interactive demos with Gradio
- Writing device-agnostic code that runs on both CPU and GPU

## 🔮 Future Improvements

- [ ] Batch processing for multiple uploaded images
- [ ] Video frame captioning
- [ ] Fine-tuning on a custom dataset
- [ ] Object detection with Florence-2's `<OD>` prompt
- [ ] Deploy to Hugging Face Spaces

## 📄 License

This project is licensed under the MIT License — see [LICENSE](LICENSE) for details.

---

*Built with ❤️ using open-source AI models. No API keys, no costs, just learning.*
