# TruthGuard AI - Advanced Fake News Detection

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![Node.js 18+](https://img.shields.io/badge/node.js-18+-green.svg)](https://nodejs.org/)

TruthGuard AI is an advanced AI-powered tool designed to detect misinformation, analyze bias, sentiment, and readability in text, URLs, and documents. Built with cutting-edge machine learning models and a modern web interface, it provides real-time analysis with high accuracy.

## 🚀 Features

- **AI-Powered Detection**: RoBERTa transformer model trained on 40,000+ news articles
- **Real-Time Processing**: Analysis completes in under 100ms using optimized inference
- **Multi-Dimensional NLP Analysis**: Sentiment, readability, and bias scoring included
- **Multiple Input Methods**: Analyze text, URLs, PDFs, Word files, and more
- **98% Accuracy**: Tested on benchmark Fake News datasets
- **Privacy First**: No content stored. All analysis is temporary
- **Multi-Language Support**: Support for English, Spanish, French — more coming soon
- **Learning & Education**: Explainable results designed to improve media literacy

## 🏗️ Architecture

This project consists of two main components:

### Backend (FastAPI)
- **Framework**: FastAPI with automatic API documentation
- **ML Model**: RoBERTa transformer for fake news classification
- **Caching**: Redis for performance optimization
- **Rate Limiting**: Built-in rate limiting to prevent abuse
- **File Processing**: Support for PDF, DOCX, and text files
- **URL Scraping**: Asynchronous web content extraction

### Frontend (Next.js)
- **Framework**: Next.js 14 with App Router
- **UI Library**: Tailwind CSS with custom components
- **State Management**: Zustand for global state
- **Data Fetching**: TanStack Query for server state management
- **Charts**: Recharts for data visualization
- **Theme Support**: Dark/Light mode with next-themes

## 📋 Prerequisites

- Python 3.8 or higher
- Node.js 18 or higher
- Redis server (for caching and rate limiting)
- Git

## 🛠️ Installation

### Backend Setup

1. **Clone the repository**
   ```bash
   git clone https://github.com/scout6774-66667/Fake-News-Detection-.git
   cd Fake-News-Detection-/backend-fastapi
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

4. **Start Redis server**
   ```bash
   # Install Redis if not already installed
   # On Ubuntu/Debian:
   sudo apt-get install redis-server
   redis-server

   # On macOS:
   brew install redis
   brew services start redis

   # On Windows: Download from https://redis.io/download
   ```

5. **Run the backend**
   ```bash
   uvicorn app:app --host 0.0.0.0 --port 8000 --reload
   ```

The API will be available at `http://localhost:8000` with automatic documentation at `http://localhost:8000/docs`.

### Frontend Setup

1. **Navigate to frontend directory**
   ```bash
   cd ../frontend-nextjs
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Configure environment variables**
   Create a `.env.local` file:
   ```env
   NEXT_PUBLIC_API_URL=http://localhost:8000
   ```

4. **Run the development server**
   ```bash
   npm run dev
   ```

The application will be available at `http://localhost:3000`.

## 📖 Usage

### Web Interface

1. Open your browser and navigate to `http://localhost:3000`
2. Choose your input method:
   - **Text Analysis**: Paste or type the text you want to analyze
   - **URL Analysis**: Enter a URL to analyze web content
   - **File Analysis**: Upload PDF or DOCX files
3. Click "Analyze" to get results
4. View detailed analysis including:
   - Fake/Real prediction with confidence score
   - Sentiment analysis
   - Bias detection
   - Readability metrics

### API Usage

#### Analyze Text
```bash
curl -X POST "http://localhost:8000/analyze/text" \
     -H "Content-Type: application/json" \
     -d '{
       "text": "Your news article text here",
       "include_sentiment": true,
       "include_bias": true,
       "include_readability": true
     }'
```

#### Analyze URL
```bash
curl -X POST "http://localhost:8000/analyze/url" \
     -H "Content-Type: application/json" \
     -d '{
       "url": "https://example.com/news-article",
       "include_sentiment": true,
       "include_bias": true,
       "include_readability": true
     }'
```

#### File Analysis
```bash
curl -X POST "http://localhost:8000/analyze/file" \
     -F "file=@/path/to/your/document.pdf"
```

## 🔧 API Endpoints

| Endpoint | Method | Description |
|----------|--------|-------------|
| `/health` | GET | Health check |
| `/analyze/text` | POST | Analyze text content |
| `/analyze/url` | POST | Analyze URL content |
| `/analyze/file` | POST | Analyze uploaded file |
| `/predict` | POST | Simple prediction (text only) |

## 🧪 Testing

### Backend Tests
```bash
cd backend-fastapi
python -m pytest
```

### Frontend Tests
```bash
cd frontend-nextjs
npm test
```

## 🤝 Contributing

We welcome contributions! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

### Development Guidelines

- Follow PEP 8 for Python code
- Use TypeScript for frontend development
- Write tests for new features
- Update documentation as needed
- Ensure all tests pass before submitting PR

## 📊 Model Information

- **Model**: RoBERTa-base (trained on Fake News datasets)
- **Training Data**: 40,000+ labeled news articles
- **Accuracy**: 98% on test set
- **Inference Time**: <100ms per request
- **Supported Languages**: English, Spanish, French

## 🔒 Privacy & Security

- **No Data Storage**: Content is not stored on servers
- **Temporary Processing**: All analysis is performed in memory
- **Rate Limiting**: Prevents abuse with configurable limits
- **HTTPS**: Recommended for production deployments

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- RoBERTa model by Facebook AI
- FastAPI framework
- Next.js framework
- Hugging Face Transformers library

## 📞 Support

For questions or support, please open an issue on GitHub or contact the maintainers.

---

**TruthGuard AI** - Fighting misinformation with AI-powered analysis.
