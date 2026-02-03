# 🎭 Emotion Analyzer

A multimodal emotion analysis system that processes **video and audio inputs** to detect and analyze human emotions in real-time using Google's Gemini API.

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/)
[![Flask](https://img.shields.io/badge/Flask-2.0+-green.svg)](https://flask.palletsprojects.com/)
[![Docker](https://img.shields.io/badge/Docker-Ready-blue.svg)](https://www.docker.com/)
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

## 📋 Table of Contents
- [Overview](#overview)
- [Features](#features)
- [Tech Stack](#tech-stack)
- [Architecture](#architecture)
- [Installation](#installation)
- [Usage](#usage)
- [API Documentation](#api-documentation)
- [Docker Deployment](#docker-deployment)
- [Project Structure](#project-structure)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)

## 🎯 Overview

This Emotion Analyzer is an AI-powered application that leverages Google's Gemini API to perform sophisticated emotion detection from both video frames and audio streams. The system provides real-time analysis with an intuitive web interface, making emotion recognition accessible and easy to use.

**Key Capabilities:**
- Multimodal emotion detection (video + audio)
- Real-time processing and analysis
- Interactive web-based user interface
- Containerized deployment with Docker
- RESTful API for easy integration

## ✨ Features

- **🎥 Video Emotion Analysis**: Detects emotions from facial expressions in video streams
- **🎤 Audio Emotion Analysis**: Analyzes emotional tone from voice and speech patterns
- **🔄 Multimodal Processing**: Combines video and audio inputs for more accurate emotion detection
- **🌐 Web Interface**: User-friendly HTML interface for easy interaction
- **🚀 Scalable Deployment**: Docker containerization for consistent deployment across environments
- **⚡ Real-time Processing**: Fast emotion analysis using Google Gemini API
- **📊 Detailed Results**: Comprehensive emotion classification with confidence scores

## 🛠️ Tech Stack

### Backend
- **Python 3.8+**: Core programming language
- **Flask**: Lightweight web framework for API and web server
- **Google Gemini API**: State-of-the-art AI model for emotion analysis
- **OpenCV**: Video processing and frame extraction (likely)

### Frontend
- **HTML5**: Structure and markup
- **CSS3**: Styling and responsive design
- **JavaScript**: Interactive features and API communication

### DevOps
- **Docker**: Containerization for scalable deployment
- **Git**: Version control

## 🏗️ Architecture

```
┌─────────────────┐
│   Web Browser   │
└────────┬────────┘
         │ HTTP
         ▼
┌─────────────────┐
│  Flask Server   │
│   (server.py)   │
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│ Chat Functions  │
│(chat_functions) │
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│  Gemini API     │
│ (Emotion Model) │
└─────────────────┘
```

## 📦 Installation

### Prerequisites
- Python 3.8 or higher
- Google Gemini API key
- Docker (optional, for containerized deployment)
- Webcam/microphone (for real-time analysis)

### Local Setup

1. **Clone the repository**
```bash
git clone https://github.com/Subhhankar/Emotion-Analyzer.git
cd Emotion-Analyzer
```

2. **Create a virtual environment**
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. **Install dependencies**
```bash
pip install -r requirements.txt
```

4. **Set up environment variables**
```bash
# Create a .env file
echo "GEMINI_API_KEY=your_api_key_here" > .env
```

5. **Run the application**
```bash
python server.py
```

6. **Access the application**
Open your browser and navigate to: `http://localhost:5000`

## 🚀 Usage

### Web Interface

1. Navigate to the application URL
2. Upload a video file or enable webcam access
3. (Optional) Enable microphone for audio analysis
4. Click "Analyze Emotion"
5. View the detected emotions with confidence scores

### API Endpoints

#### Analyze Emotion
```bash
POST /analyze
Content-Type: multipart/form-data

Parameters:
- video: Video file (optional)
- audio: Audio file (optional)

Response:
{
  "emotions": {
    "primary": "happy",
    "confidence": 0.87,
    "all_detected": ["happy", "excited", "content"]
  },
  "timestamp": "2024-02-03T10:30:00Z"
}
```

## 🐳 Docker Deployment

### Build the Docker image
```bash
docker build -t emotion-analyzer .
```

### Run the container
```bash
docker run -p 5000:5000 \
  -e GEMINI_API_KEY=your_api_key \
  emotion-analyzer
```

### Using Docker Compose
```bash
docker-compose up -d
```

## 📁 Project Structure

```
Emotion-Analyzer/
├── __pycache__/           # Python cache files
├── static/                # Static files (CSS, JS, images)
│   ├── css/
│   ├── js/
│   └── images/
├── templates/             # HTML templates
│   └── index.html
├── chat_functions.py      # Core emotion analysis logic
├── server.py              # Flask application server
├── requirements.txt       # Python dependencies
├── .gitignore            # Git ignore rules
├── Dockerfile            # Docker configuration
└── README.md             # This file
```

## 🔧 Configuration

### Environment Variables

| Variable | Description | Required |
|----------|-------------|----------|
| `GEMINI_API_KEY` | Google Gemini API authentication key | Yes |
| `FLASK_ENV` | Flask environment (development/production) | No |
| `PORT` | Application port (default: 5000) | No |

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👤 Contact

**Subhankar Saha**

- Email: subhankar.datascience@gmail.com
- LinkedIn: [linkedin.com/in/subhankar-saha-87577a246](https://www.linkedin.com/in/subhankar-saha-87577a246/)
- GitHub: [@Subhhankar](https://github.com/Subhhankar)

## 🙏 Acknowledgments

- Google Gemini API for powerful emotion analysis capabilities
- Flask framework for lightweight web development
- The open-source community for various tools and libraries

## 🔮 Future Enhancements

- [ ] Support for batch video processing
- [ ] Advanced emotion tracking over time
- [ ] Integration with multiple AI models for comparison
- [ ] Mobile application support
- [ ] Real-time emotion analytics dashboard
- [ ] Export emotion analysis reports (PDF/CSV)
- [ ] Multi-language support

---

**⭐ If you find this project useful, please consider giving it a star!**
