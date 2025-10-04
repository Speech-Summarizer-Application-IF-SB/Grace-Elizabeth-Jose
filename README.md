# Milestone 1: Whisper STT Pipeline

## Overview
This repository contains Milestone 1 of the Meeting Summarizer Application project. 
The purpose of this module is to capture audio and transcribe it into text using the 
Hugging Face Whisper model. The script was developed and tested in Google Colab.

## Files
- `milestone1_stt.py` : Python script for audio transcription using Whisper
- `requirements.txt` : Python packages required to run the script
- `sample_audio.wav` : Optional small test audio file for transcription

## How to Run

### Option 1: Locally
1. Install required packages:
   ```bash
   pip install transformers torch soundfile librosa
