# Speech Summarizer Application - Milestone 1

## Project Overview
The objective of this project is to develop a **real-time Meeting Summarizer** that transcribes audio recordings and generates concise summaries using Hugging Face models.

**Milestone 1:** Audio Transcription (Speech-to-Text) using OpenAI Whisper.

---

## Features Implemented in Milestone 1
- Upload a WAV audio file (short meeting clip recommended).
- Optional noise reduction and resampling for better transcription quality.
- Transcription of audio using **Whisper (openai/whisper-small)**.
- Summarization of the transcription using **BART (facebook/bart-large-cnn)**.
- Saved output files: `transcription.txt` and `summary.txt` (manually downloadable from Colab).

---

## How to Run
1. Open the Colab notebook.  
2. Upload a WAV audio file when prompted.  
3. The notebook will:
   - Play the uploaded audio.
   - Apply noise reduction (optional).
   - Transcribe the audio into text.
   - Generate a summary of the transcription.
   - Save `transcription.txt` and `summary.txt` in the Colab environment.

4. Download the output files manually from the **Files sidebar** in Colab.

---

## Colab Notebook
You can open and run the Milestone 1 notebook here:  
[Open Milestone 1 Notebook in Colab](https://colab.research.google.com/drive/1VbdIEZP83VKNja8c9pOUVELQLWMse2f5?usp=sharing)

---

## Next Steps
- Integrate speaker diarization for multi-speaker meetings.
- Real-time audio streaming and summarization.
- Build a Streamlit interface for interactive usage.
