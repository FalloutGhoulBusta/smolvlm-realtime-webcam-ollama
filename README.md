# 📹 SmolVLM Realtime Webcam [![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

> Real-time webcam interaction with vision language models via Ollama

## 🚀 Quick Start

1. **Install Ollama** and pull a vision model:
   ```bash
   ollama pull llava
   # or: ollama pull llava:7b, llava:13b, bakllava
   ```

2. Start Ollama with CORS enabled:
   ```bash
   set OLLAMA_ORIGINS=* && ollama serve
   ```

3. Serve the HTML file:
   ```bash
   python -m http.server 8000
   ```

4. Open [http://localhost:8000](http://localhost:8000) in your browser

## 🎯 Features

- 📸 **Live Webcam Capture** - Real-time video feed
- 🤖 **AI Vision Analysis** - Describe what the camera sees
- ⚡ **Configurable Intervals** - 100ms to 2s between requests
- 🔄 **Continuous Processing** - Start/stop with one click

## ⚙️ Configuration

- **Base API**: `http://localhost:11434` (Ollama default)
- **Model**: Must be a vision-capable model from Ollama library
  - ✅ `llava`, `llava:7b`, `llava:13b`, `bakllava`
  - ❌ Text-only models won't work
- **Instruction**: Customize what you want the AI to analyze

## 🤖 Ollama Models Tested

- [moondream](https://ollama.com/library/moondream) - A vision model optimized for real-time analysis
- [hf.co/mradermacher/SmolLM2-135M-Instruct-GGUF:Q2_K](https://huggingface.co/mradermacher/SmolLM2-135M-Instruct-GGUF) - Lightweight instruct-tuned model for efficient processing

## 🛠️ Requirements

- Modern browser with webcam access
- Ollama with a vision model installed
- Local HTTP server (Python, Node.js, etc.)

## 🔧 Troubleshooting

- **CORS Error?** → Start Ollama with `OLLAMA_ORIGINS=*`
- **Camera blocked?** → Grant permissions and use HTTPS/localhost
- **No response?** → Ensure you're using a vision model, not text-only

---

## 📜 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

Built for real-time AI vision interaction 🎥✨