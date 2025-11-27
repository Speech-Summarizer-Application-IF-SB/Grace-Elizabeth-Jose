# 🎙️ AI Live Meeting Summarizer

Convert meeting audio → transcript → clean summary using Whisper + BART, all inside a simple UI.

---

## 📌 Overview

This project is a **Meeting Summarizer Application** that converts speech from audio files into text and generates a concise summary using NLP models.
It was built across **four milestones**, each adding a key feature such as STT, diarization logic, summarization, and finally a working UI.

The final application is a **Gradio-based web app** that allows users to upload an audio file and get:
✔️ Full transcript
✔️ AI-generated summary

---

## 🚀 Features

### 🎤 **Speech-to-Text (Whisper)**

* Accurate transcription using OpenAI Whisper model
* Works with WAV / MP3 files

### 🧠 **Summarization (BART Model)**

* Uses Facebook BART CNN model
* Generates clean, meaningful summaries

### 🧩 **Basic Diarization Logic (Milestone 2)**

* Simple VAD-based speaker change detection
* Tags segments as Speaker 1 / Speaker 2

### 💻 **User Interface (Milestone 4)**

* Built using **Gradio**
* Upload audio → get transcript + summary
* Lightweight, fully local, no API keys required

### 📁 **Output Files**

* Transcript saved as `transcript_mX.txt`
* Summary saved as `summary_mX.txt`

---

## 🏗️ **Milestones Completed**

### 🔹 **Milestone 1 – Speech-to-Text**

* Implemented Whisper transcription
* Noise handling & preprocessing
* Generated transcript + summary (BART)
* Saved outputs (`transcription.txt`, `summary.txt`)

### 🔹 **Milestone 2 – Diarization + Summarization**

* Added basic voice-activity-based diarization
* Assigned Speaker 1 / Speaker 2
* Chunked long text before summarization
* Generated structured summary

### 🔹 **Milestone 3 – Integration Pipeline**

* Combined: STT → Diarization → Summary
* Cleaned code & created a full working pipeline
* Exported outputs successfully

### 🔹 **Milestone 4 – Final UI**

* Built a fully working **Gradio interface**
* Upload audio → process → display transcript & summary
* Final working app stored as `app.py`

---

## 🛠️ **Tech Stack**

| Component      | Tools Used                     |
| -------------- | ------------------------------ |
| Speech-to-Text | Whisper Small                  |
| Summarization  | BART (facebook/bart-large-cnn) |
| Diarization    | Basic VAD-based segmentation   |
| UI             | Gradio                         |
| Backend        | Python                         |

---

## 📦 Project Structure

```
📁 Milestone_1
📁 Milestone_2
📁 Milestone_3
📁 Milestone_4
   └── app.py   ← Final working UI app
README.md
```

---

# ▶️ **How to Run the Final App**

### 1️⃣ Install dependencies

```bash
pip install gradio openai-whisper transformers torch
```

### 2️⃣ Run the application

```bash
python app.py
```

### 3️⃣ Use the UI

* Browser will open automatically
* Upload WAV/MP3 file
* Get transcript + summary

---

# 📄 **Final App Code (app.py)**

*(already included in Milestone 4 folder)*

```python
import gradio as gr
import whisper
from transformers import pipeline
import tempfile

# Load models
model = whisper.load_model("small")
summarizer = pipeline("summarization", model="facebook/bart-large-cnn")

def process_audio(audio):
    if audio is None:
        return "No audio uploaded", "No summary available"

    # Save uploaded audio to temp file
    with tempfile.NamedTemporaryFile(delete=False, suffix=".wav") as temp:
        temp.write(audio)
        temp.flush()
        file_path = temp.name

    # Transcription
    result = model.transcribe(file_path)
    transcript = result["text"]

    # Summarization
    summary = summarizer(transcript, max_length=200, min_length=60)[0]["summary_text"]

    return transcript, summary

# Gradio UI
ui = gr.Interface(
    fn=process_audio,
    inputs=gr.Audio(type="filepath", label="🎤 Upload Audio"),
    outputs=[
        gr.Textbox(label="📝 Transcript"),
        gr.Textbox(label="📘 Summary")
    ],
    title="AI Meeting Summarizer",
    description="Upload an audio file to generate transcript and summary."
)

ui.launch()
```

---

# ✨ Conclusion

This project delivers a complete pipeline that transforms any meeting audio into a structured transcript and summary using speech recognition and NLP.
The Gradio UI makes the system easy to use, lightweight, and accessible without complex setup.

---
