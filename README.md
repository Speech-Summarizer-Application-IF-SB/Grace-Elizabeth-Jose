# 🎙️ **AI Meeting Summarizer – Milestone 1 to 4 (Final Project)**

*A complete pipeline for Speech-to-Text, Diarization, and Automatic Summarization*

---

## ✅ **Overview**

This project converts meeting audio into a clean, structured summary using:

* **Whisper** (Speech-to-Text)
* **Rule-based diarization (VAD + speaker switching)**
* **BART** (Summarization)
* **Simple UI using Gradio**
* **Outputs saved as `.txt`**

The system is lightweight, works locally, and does NOT require paid APIs.

---

## 📁 **Project Structure**

```
Milestone-1/
│── transcribe.py
│── output_m1.txt

Milestone-2/
│── diarization.py
│── diarized_m2.txt

Milestone-3/
│── summary.py
│── summary_m3.txt

Milestone-4/
│── app.py        ← Final application (Gradio)
│── summary_m4.txt
│── README.md
```

---

# 🚀 **Milestone Breakdown**

---

## **🟩 Milestone 1 – Speech-to-Text (Whisper)**

**Goal:** Convert audio (.wav / .mp3) into text.

✔ Whisper small model
✔ FP32 CPU mode
✔ Generates transcript `.txt` file

**Output example:**
`transcript_m1.txt`

---

## **🟩 Milestone 2 – Speaker Diarization (Simple VAD)**

**Goal:** Detect speech segments and assign alternating speaker labels.

✔ Implemented using `webrtcvad`
✔ Window-based frame detection
✔ Alternates between Speaker 1 & 2
✔ Produces diarized transcript

**Output example:**
`diarized_m2.txt`

---

## **🟩 Milestone 3 – Summarization (BART)**

**Goal:** Generate a clean summary from long diarized text.

✔ Uses `facebook/bart-large-cnn`
✔ Automatic chunking to avoid token overflow
✔ Final merged summary saved as a file

**Output example:**
`summary_m3.txt`

---

## **🟩 Milestone 4 – Final Gradio Application**

**Goal:** Interactive UI for uploading audio → transcript → summary.

✔ Upload audio file
✔ Whisper transcription
✔ BART summarization
✔ Results shown in UI
✔ Downloadable summary

**File:** `app.py`

---

# 🧪 **How to Run the Final App**

### **1. Install dependencies**

```bash
pip install gradio transformers git+https://github.com/openai/whisper.git
pip install webrtcvad
```

### **2. Run the app**

```bash
python app.py
```

### **3. Open UI**

A browser will automatically open with a clean Gradio interface where you can:

* Upload audio
* View transcript
* View summary
* Download summary

---

# 📝 **Features Completed**

| Feature                      | Status      |
| ---------------------------- | ----------- |
| Whisper Speech-to-Text       | ✅ Completed |
| Diarization (Rule-based VAD) | ✅ Completed |
| Chunk-based Summarization    | ✅ Completed |
| BART summarizer              | ✅ Completed |
| Gradio UI                    | ✅ Completed |
| Export summary               | ✅ Completed |

---

# 📦 **Outputs Generated**

* **Transcript:** `transcript_m1.txt`
* **Diarized Transcript:** `diarized_m2.txt`
* **Milestone 3 Summary:** `summary_m3.txt`
* **Final Summary (UI):** `summary_m4.txt`

---

# 🔚 **Conclusion**

This project delivers a complete meeting summarization pipeline with:

* STT
* Speaker segmentation
* High-quality abstractive summary
* Simple UI for end-users

You now have a **clean and working final Milestone system**.

---

