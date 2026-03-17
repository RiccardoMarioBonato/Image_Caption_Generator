# Image Caption Generator

A Flask web application that uses the **Salesforce BLIP** model to automatically generate captions for uploaded images.

Built for **01219462 Software Engineering for AI-Enabled Systems**  
Activity 2.5 — Web-Based AI-Enabled Application

---

## Features

- Drag-and-drop or click-to-upload image interface
- AI-generated captions using `Salesforce/blip-image-captioning-base`
- Supports PNG, JPG, JPEG, GIF, BMP, WEBP (up to 16 MB)
- Runs entirely locally — no API key required
- GPU acceleration if available (falls back to CPU)

---

## Setup

**1. Clone the repository**
```bash
git clone https://github.com/your-username/your-repo.git
cd your-repo
```

**2. Create a virtual environment (optional but recommended)**
```bash
python -m venv .venv

# Windows
.\.venv\Scripts\Activate.ps1

# Mac/Linux
source .venv/bin/activate
```

**3. Install dependencies**
```bash
pip install -r requirements.txt
```

> Note: `torch` is ~2 GB. The BLIP model weights (~900 MB) are downloaded automatically on first run and cached locally.

---

## Run

```bash
python app.py
```

Then open **http://localhost:5000** in your browser.

---

## How It Works

1. User uploads an image via the web interface
2. Flask receives the image and saves it temporarily
3. BLIP processes the image and generates a descriptive caption
4. The caption and image are returned to the browser
5. The temporary file is deleted from the server

---

## Tech Stack

| Layer | Technology |
|---|---|
| Web framework | Flask |
| ML model | Salesforce/blip-image-captioning-base |
| ML library | Hugging Face Transformers |
| Image processing | Pillow |
| Deep learning | PyTorch |

---

## Project Structure

```
gallery_app/
├── app.py              # Main application (single file)
├── requirements.txt    # Python dependencies
├── README.md           # This file
└── uploads/            # Temporary upload folder (auto-created, not tracked)
```
