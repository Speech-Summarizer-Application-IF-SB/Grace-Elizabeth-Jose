# Milestone 1: Whisper STT Pipeline

## Overview
This repository contains Milestone 1 of the Meeting Summarizer Application project. 
The purpose of this module is to capture audio and transcribe it into text using the 
Hugging Face Whisper model. The script was developed and tested in Google Colab.

## Files
- `speechsummarizer_application.py` : Python script for audio transcription using Whisper
- `sample_audio.wav` : Optional small test audio file for transcription

## How to Run in Colab
1. Upload `speechsummarizer_application.py` and your audio file to Colab.
2. Install required packages in a cell:
```python
!pip install transformers torch soundfile librosa
