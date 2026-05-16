# 🤖 CodeAlpha AI Internship Projects

![CodeAlpha](https://img.shields.io/badge/CodeAlpha-AI%20Internship-blue?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Completed-success?style=for-the-badge)
![Tasks](https://img.shields.io/badge/Tasks%20Completed-4%20%2F%204-brightgreen?style=for-the-badge)

> A collection of four Artificial Intelligence projects completed as part of the **CodeAlpha AI Internship Programme**. Each project explores a distinct domain of applied AI — from Natural Language Processing and Generative Deep Learning to Computer Vision — all built as fully functional, browser-based applications.

---

## 📋 Table of Contents

- [Overview](#overview)
- [Task 1 — Language Translation Tool](#task-1--language-translation-tool)
- [Task 2 — Chatbot for FAQs](#task-2--chatbot-for-faqs)
- [Task 3 — Music Generation with AI](#task-3--music-generation-with-ai)
- [Task 4 — Object Detection and Tracking](#task-4--object-detection-and-tracking)
- [Tech Stack](#tech-stack)
- [How to Run](#how-to-run)
- [Project Structure](#project-structure)
- [Internship Details](#internship-details)

---

## Overview

| # | Task | Domain | Core Technology |
|---|------|--------|----------------|
| 1 | Language Translation Tool | NLP | MyMemory API · Web Speech API |
| 2 | Chatbot for FAQs | Conversational AI | TF-IDF · Cosine Similarity · Claude AI |
| 3 | Music Generation with AI | Generative Deep Learning | LSTM · Web Audio API · MIDI |
| 4 | Object Detection & Tracking | Computer Vision | TensorFlow.js · COCO-SSD · SORT |

All four projects are self-contained single-file HTML applications — no installation or build step required. Simply open in any modern browser.

---

## Task 1 — Language Translation Tool

**`task1_translation_tool.html`**

A real-time language translation web app that lets users type text, select source and target languages, and instantly receive a translated result.

### Features
- 🌍 Supports **50+ language pairs** (Arabic, Chinese, French, German, Hindi, Japanese, Korean, Spanish, Urdu, and more)
- 🔊 **Text-to-speech** playback of translated output using the Web Speech API
- 📋 **One-click copy** to clipboard with animated confirmation
- 🔁 **Language swap** button with rotation animation
- 📊 Real-time character counter (500-character limit)
- 📱 Fully responsive — works on desktop and mobile

### How It Works
```
User Input → Language Selection → Fetch API → MyMemory REST API → Translated Text → Display
```

### API Used
- [MyMemory Translation API](https://mymemory.translated.net/) — free, no key required

---

## Task 2 — Chatbot for FAQs

**`task2_faq_chatbot.html`**

An intelligent FAQ chatbot that uses NLP preprocessing and TF-IDF cosine similarity to match user questions to the most relevant answer from a knowledge base.

### Features
- 🧠 **NLP Pipeline** — tokenisation, stop-word removal, Porter stemming
- 📐 **TF-IDF vectorisation** with cosine similarity ranking (built from scratch in JS)
- 📊 **Confidence score** displayed as a visual bar beneath each response
- 🤖 **Claude AI fallback** for questions outside the FAQ corpus
- 🎤 **Voice input** via Web Speech Recognition API
- 💬 Suggested follow-up question chips after each response

### NLP Pipeline
```
Raw Input → Lowercase → Punctuation Removal → Tokenisation → Stop-Word Filtering → Stemming → TF-IDF Vector → Cosine Similarity → Best Match
```

### Confidence Threshold
Answers with a similarity score below **0.15** are automatically routed to the Claude AI API for a generative response.

---

## Task 3 — Music Generation with AI

**`task3_music_generation.html`**

An AI-powered music composer that generates original melodies using an LSTM-based sequence model and plays them back in real time via the Web Audio API.

### Features
- 🎵 **LSTM neural network** for autoregressive note sequence generation
- 🎛️ **Temperature control** — adjust creativity from deterministic (0.1) to highly random (2.0)
- 🎼 **4 genre modes** — Classical, Jazz, Ambient, Custom
- 🎹 **Live piano roll** visualisation on HTML5 Canvas
- ⏱️ **BPM control** — 60 to 180 beats per minute
- 💾 **MIDI export** — download generated sequence as a `.mid` file
- 🔊 Web Audio API synthesis with ADSR envelope shaping

### Model Architecture
```
Embedding (64d) → LSTM (256) → Dropout (0.3) → LSTM (256) → Dropout (0.3) → Dense Softmax (89 classes)
```

### Generation Formula
```
Frequency (Hz) = 440 × 2^((midi_note − 69) / 12)
```

---

## Task 4 — Object Detection and Tracking

**`task4_object_detection.html`**

A real-time object detection and tracking system powered by TensorFlow.js that identifies and tracks multiple objects in a live webcam feed with persistent tracking IDs.

### Features
- 📷 **Live webcam feed** via `getUserMedia` API
- 🎯 **COCO-SSD detection** — identifies 80 object classes in real time
- 🔢 **SORT tracking algorithm** — Kalman filter + Hungarian algorithm for persistent IDs
- 🎨 **Colour-coded bounding boxes** per tracking ID
- 📊 Live FPS counter, inference time, and detection log
- 📸 **Snapshot export** — saves annotated frame as PNG
- 🎚️ Adjustable confidence threshold slider

### Detection Pipeline
```
Webcam Frame → TensorFlow.js Inference → COCO-SSD Detections → SORT Tracker → Canvas Overlay Render → Display
```

### Trackable Object Classes
Person, car, bicycle, cat, dog, chair, laptop, mobile phone, bottle, and 71 more COCO classes.

---

## Tech Stack

| Technology | Used In |
|-----------|---------|
| HTML5 / CSS3 / Vanilla JavaScript | All tasks |
| MyMemory Translation REST API | Task 1 |
| Web Speech API (TTS + STT) | Task 1, Task 2 |
| TF-IDF / Cosine Similarity (custom JS) | Task 2 |
| Anthropic Claude AI API | Task 2 |
| LSTM Sequence Model (JS simulation) | Task 3 |
| Web Audio API | Task 3 |
| MIDI Binary Encoder (custom JS) | Task 3 |
| TensorFlow.js v4.11.0 | Task 4 |
| COCO-SSD v2.2.3 | Task 4 |
| SORT Tracking Algorithm (custom JS) | Task 4 |
| HTML5 Canvas 2D API | Task 3, Task 4 |

---

## How to Run

No installation or build step is required. Each task is a self-contained HTML file.

```bash
# Clone the repository
git clone https://github.com/MuhammadHamza1605/CodeAlpha.git

# Navigate into the folder
cd CodeAlpha_AI_Projects

# Open any task directly in your browser
open task1_translation_tool.html
open task2_faq_chatbot.html
open task3_music_generation.html
open task4_object_detection.html
```

> **Note for Task 4:** Camera access requires the page to be served over HTTPS or `localhost`. Use a local server if opening directly in the browser doesn't prompt for camera permission:
> ```bash
> python -m http.server 8000
> # Then visit http://localhost:8000/task4_object_detection.html
> ```

---

## Project Structure

```
CodeAlpha_AI_Projects/
│
├── task1_translation_tool.html       # Language Translation Tool
├── task2_faq_chatbot.html            # FAQ Chatbot with NLP
├── task3_music_generation.html       # AI Music Generator
├── task4_object_detection.html       # Object Detection & Tracking
│
├── AI_Internship_Tasks_Documentation.docx   # Full technical documentation
└── README.md                         # This file
```

---

## Internship Details

| | |
|---|---|
| **Organisation** | CodeAlpha |
| **Programme** | Artificial Intelligence Internship |
| **Website** | [www.codealpha.tech](https://www.codealpha.tech) |
| **Tasks Completed** | 4 out of 4 |
| **Deliverable** | Fully functional browser-based AI applications |

---

## 📄 License

This project was built for educational purposes as part of the CodeAlpha internship programme.

---

<div align="center">
  <strong>Built with ❤️ during the CodeAlpha AI Internship</strong><br/>
  <a href="https://www.codealpha.tech">www.codealpha.tech</a>
</div>
