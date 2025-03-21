# Realtime Screen Sharing AI using Qwen Model

A powerful multimodal AI assistant that analyzes your screen in real-time, listens to your voice queries, and responds with synthesized speech. This project combines screen sharing, speech recognition, visual analysis, and text-to-speech into a seamless interactive experience.

## Features

* **Real-time Screen Sharing:** Share your screen with the AI assistant
* **Speech Recognition:** Automatically detects and transcribes speech using Whisper
* **Visual Analysis:** Processes screen content using Qwen2.5-VL-3B-Instruct model
* **Voice Responses:** Generates natural-sounding responses using Kokoro TTS
* **WebSocket Communication:** Enables real-time bidirectional data flow
* **Responsive UI:** Clean interface with audio level visualization

## System Architecture

The project consists of two main components:

### Frontend (React)
* Screen capture and audio input processing
* WebSocket client for real-time communication
* Audio visualization and playback
* User interface for interaction

### Backend (Python)
* Speech detection and transcription (Whisper)
* Visual content analysis (Qwen2.5-VL)
* Text-to-speech synthesis (Kokoro TTS)
* WebSocket server for bidirectional communication

## Requirements

### Frontend
* Node.js (v16 or higher)
* npm or yarn
* Modern web browser with screen sharing support

### Backend
* Python 3.8+
* CUDA-compatible GPU (minimum 8GB VRAM recommended)
* Required Python packages:
   * torch
   * transformers
   * websockets
   * numpy
   * Pillow
   * kokoro (for TTS)

## Installation

### Backend Setup
1. Clone the repository:
```bash
git clone https://github.com/dushyantzz/Realtime-Screen-Sharing-AI-using-Qwen-Model.git
cd Realtime-Screen-Sharing-AI-using-Qwen-Model/AI\ MODEL/Pythonbackend
```

2. Create and activate a virtual environment:
```bash
python -m venv .venv
source .venv/bin/activate  # On Windows: .venv\Scripts\activate
```

3. Install dependencies:
```bash
pip install torch transformers websockets numpy Pillow kokoro
```

4. Run the backend server:
```bash
python main.py
```

### Frontend Setup
1. Navigate to the frontend directory:
```bash
cd ../Frontend-multimodal
```

2. Install dependencies:
```bash
npm install
```

3. Update the WebSocket server URL in `src/App.tsx`:
```jsx
<WebSocketProvider url="ws://localhost:9074">
```

4. Start the development server:
```bash
npm run dev
```

5. Open your browser and navigate to http://localhost:5173

## Usage

1. Launch both the backend and frontend applications
2. Allow screen sharing and microphone access when prompted
3. The system will automatically:
   * Capture your screen
   * Listen for your voice
   * Process visual content
   * Respond to your queries with synthesized speech

## How It Works

1. **Speech Detection:** The system continuously analyzes audio input to detect speech segments
2. **Transcription:** Detected speech is transcribed using the Whisper model
3. **Visual Analysis:** The Qwen multimodal model processes both the transcribed text and current screen content
4. **Response Generation:** The system generates a contextual response based on what it sees and hears
5. **Speech Synthesis:** The text response is converted to speech using Kokoro TTS
6. **Playback:** The synthesized speech is played back to the user

## Performance Considerations

* The system requires significant GPU resources for optimal performance
* Minimum recommended GPU: NVIDIA GTX 1660 or better (8GB+ VRAM)
* For smoother performance, consider:
   * Reducing image resolution
   * Using smaller AI models
   * Limiting the maximum speech duration

## License

MIT License

## Acknowledgments

* This project uses the Qwen2.5-VL-3B-Instruct model from Alibaba
* Speech recognition powered by OpenAI's Whisper model
* Text-to-speech synthesis using Kokoro TTS
