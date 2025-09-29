# 🤖 Multimodal AI Agent

This project demonstrates a **Retrieval-Augmented Generation (RAG) pipeline** that allows you to query structured and unstructured data (PDFs, images, and audio) using a **Local LLM**. The system ingests documents, generates embeddings, stores them in **FAISS**, and answers queries based on the ingested content.  

It includes:

- PDF ingestion and text extraction (`pdfplumber`/PyMuPDF)
- Image ingestion with **BLIP captioning** and **OCR**
- Audio transcription using **OpenAI Whisper**
- Embeddings with `sentence-transformers`
- FAISS vector search for retrieval
- Text generation using **FLAN-T5** (or other Hugging Face seq2seq models)
- Sample content: Climate Change Report 2025

---

## Features

1. **Multi-modal ingestion**  
   - PDFs, images, and audio files can be ingested automatically.

2. **Retrieval-Augmented Generation (RAG)**  
   - Queries are answered based on retrieved document chunks with sources cited.

3. **Embeddings & FAISS**  
   - Efficient semantic search using sentence embeddings.

4. **BLIP + OCR for Images**  
   - Extract captions and text from charts, diagrams, and screenshots.

5. **Audio Transcription**  
   - Converts speech in audio files into searchable text.

---

## Installation

This project is designed for **Google Colab**, but can run locally with Python 3.10+.

```bash
# Upgrade pip
pip install --upgrade pip

# Core libraries
pip install sentence-transformers faiss-cpu pillow pytesseract pdfplumber PyMuPDF transformers accelerate timm

# Optional for audio transcription
pip install openai-whisper faster-whisper

# Optional: local LLM binding
pip install llama-cpp-python

# Optional: Streamlit for UI
pip install streamlit

# TTS support (Google TTS / pyttsx3)
pip install gTTS pyttsx3

# Additional tools
apt-get update -qq && apt-get install -y -qq ffmpeg
