# 🎙️ AI Voice Agent (Realtime)

[![Python](https://img.shields.io/badge/Python-3.9%2B-blue.svg)](https://www.python.org/)
[![FastAPI](https://img.shields.io/badge/FastAPI-0.95+-009688?logo=fastapi)](https://fastapi.tiangolo.com/)
[![WebSockets](https://img.shields.io/badge/WebSockets-Supported-green)](https://developer.mozilla.org/en-US/docs/Web/API/WebSockets_API)
[![AssemblyAI](https://img.shields.io/badge/AssemblyAI-STT-orange)](https://www.assemblyai.com/)
[![Gemini](https://img.shields.io/badge/Gemini-LLM-blueviolet)](https://deepmind.google/technologies/gemini/)
[![Murf](https://img.shields.io/badge/Murf-TTS-yellow)](https://murf.ai/)
[![License](https://img.shields.io/badge/License-MIT-lightgrey)](LICENSE)

---

## 📌 Project Overview

The **AI Voice Agent (Realtime)** is a full-stack application that enables **real-time speech-to-speech interaction**.  
It records user voice, transcribes it, sends it to an **LLM (Gemini)**, generates a response, and returns audio using **Murf TTS**.  
This project integrates **FastAPI**, **WebSockets**, and multiple AI APIs for smooth conversational AI.

---

## 🚀 Features

- 🎤 **Voice Input** → Records audio in real-time.
- 📝 **Speech-to-Text (STT)** → Uses AssemblyAI for transcription.
- 🧠 **AI Reasoning** → Google Gemini LLM handles queries.
- 🔊 **Text-to-Speech (TTS)** → Murf converts responses to speech.
- 🌍 **Web Search Integration** → Optional query resolution via APIs.
- 📂 **Chat History Storage** → Keeps logs for later analysis.
- ⚡ **FastAPI + WebSockets** → Real-time client-server communication.

---

## 📂 Project Structure

```
AI-Voice-Agent-Realtime/
│── backend/
│   ├── Agent_Output/          # Stores recorded audio responses
│   ├── chat_histories/        # Saved user-agent conversations
│   ├── functions/             # Weather & Web search services
│   ├── Routes/                # API route handlers (Transcriber, etc.)
│   ├── Services/              # Core services: STT, TTS, Gemini LLM
│   ├── uploads/               # Uploaded or processed audio
│   ├── utils/                 # Utility functions (logging, helpers)
│   ├── venv/                  # Python virtual environment (ignored in git)
│   ├── main.py                # FastAPI entry point
│   └── requirements.txt       # Backend dependencies
│
│── frontend/
│   ├── index.html             # Frontend UI
│   └── script.js              # WebSocket & client logic
│
│── .gitignore
```

---

## 🛠️ Setup Instructions

### 1️⃣ Clone the Repository
```bash
git clone https://github.com/FlixonCoder/AI-Voice-Agent-Realtime.git
cd AI-Voice-Agent-Realtime
```

### 2️⃣ Setup Python Backend
```bash
cd backend
python -m venv venv
venv\Scripts\activate   # On Windows
source venv/bin/activate  # On Mac/Linux

pip install --upgrade pip
pip install -r requirements.txt
```

### 3️⃣ Setup API Keys
Create a `.env` file inside the `backend/` directory and add your keys:
```
ASSEMBLYAI_API_KEY=your_key_here
GEMINI_API_KEY=your_key_here
MURF_API_KEY=your_key_here
```

### 4️⃣ Run Backend Server
```bash
cd backend
uvicorn main:app --reload
```

### 5️⃣ Setup Frontend
Just open `frontend/index.html` in your browser.  
The script (`script.js`) will connect to the backend via WebSockets.

---

## ⚠️ Common Issues & Fixes

🔹 **`ModuleNotFoundError`** → Run `pip install -r requirements.txt` inside `backend/`.  
🔹 **CORS Errors** → Update FastAPI CORS middleware in `main.py` to allow frontend URL.  
🔹 **WebSocket Not Connecting** → Ensure backend is running on correct port (`localhost:8000`).  
🔹 **API Key Invalid** → Double-check `.env` file placement and keys.  
🔹 **Audio Not Playing** → Confirm Murf API returns valid base64 audio.

---

## 🤝 Contributing

Pull requests are welcome! Please open an issue first to discuss major changes.

---

## 📜 License

This project is licensed under the **MIT License**.

---

## 👨‍💻 Author

Developed by **FlixonCoder** 🚀  
🔗 [GitHub Profile](https://github.com/FlixonCoder)
