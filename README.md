# 🎵 AI-Powered Song Recommender for Instagram Stories

<div align="center">

  <img src="assets/screenshots/demo.png" width="800" alt="AI Song Recommender - Transform images into personalized music experiences">

  **Transform images into personalized music experiences with AI-powered song recommendations and custom audio generation**

  [![Python](https://img.shields.io/badge/Python-3.8+-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://python.org)
  [![Flask](https://img.shields.io/badge/Flask-3.1.0-000000?style=for-the-badge&logo=flask&logoColor=white)](https://flask.palletsprojects.com/)
  [![AI](https://img.shields.io/badge/AI-BLIP%20%2B%20Gemini-FF6B6B?style=for-the-badge&logo=openai&logoColor=white)](https://github.com/kingslayer35/AI-Song-Recommender)
  [![License](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](LICENSE)

  [![Security](https://img.shields.io/badge/Security-CSRF%20%2B%20Rate%20Limiting-success?style=flat-square)](docs/IMPROVEMENTS.md)
  [![Performance](https://img.shields.io/badge/Response%20Time-%3C1s-brightgreen?style=flat-square)](docs/IMPROVEMENTS.md)
  [![Languages](https://img.shields.io/badge/Languages-7-blue?style=flat-square)](#features)
  [![Users](https://img.shields.io/badge/Active%20Users-50%2B-orange?style=flat-square)](#demonstrated-impact)

</div>

---

## 🌟 Overview

AI-Powered Song Recommender is a production-ready Flask web application that bridges visual aesthetics with musical experiences. By analyzing uploaded images using state-of-the-art AI models, it generates personalized song recommendations and can even create entirely new songs tailored to the mood and atmosphere captured in your photos.

### 🎯 Key Highlights
- **🤖 AI-Powered Analysis**: Combines BLIP image captioning with Google Gemini LLM for deep contextual understanding
- **🎯 Smart Recommendations**: Semantic similarity matching against 500+ curated songs using Sentence Transformers
- **🎼 Custom Song Creation**: Generate unique lyrics and audio using Gemini + Suno.ai integration
- **⚡ High Performance**: Sub-second response time with optimized model preloading and LRU caching
- **🔒 Enterprise Security**: CSRF protection, rate limiting, and environment-based secret management
- **🌍 Multilingual**: Support for 7 languages across 10 artists

---

## ✨ Features

### 🖼️ **Intelligent Image Analysis**
- Upload any image and receive detailed AI-generated descriptions
- Combines BLIP vision transformer with Gemini's contextual analysis
- Optional manual description input for enhanced personalization
- Caching for instant results on duplicate uploads

### 🎵 **Personalized Recommendations**
- Semantic similarity matching using Sentence Transformers (all-mpnet-base-v2)
- Curated database of 500+ songs with precomputed embeddings
- Advanced filtering by language and artist preferences
- Cosine similarity scoring for accurate mood matching

### 🎼 **Custom Song Generation**
- AI-generated lyrics tailored to your image's emotional context
- Professional audio creation via Suno.ai integration
- Downloadable audio files for personal use
- Mood and genre customization

### 🎨 **Modern User Interface**
- Clean, responsive design with real-time filtering
- Interactive controls and animated loading states
- Comprehensive error handling with user-friendly messages
- Mobile-optimized experience

### 🔒 **Security & Performance**
- **Environment-based API key management** - No hardcoded secrets
- **File upload validation** - Type and size restrictions (16MB limit)
- **CSRF protection** - Secure form submissions
- **Rate limiting** - 10 requests/minute for uploads, 5 for song generation
- **Comprehensive error handling and logging** - Production-ready monitoring
- **LRU caching** - 50x speedup for duplicate image queries
- **Optimized model loading** - Models loaded once at startup (saves 2-3s per request)
- **Performance monitoring** - Request/response timing in logs

---

## 🛠️ Technology Stack

| Component | Technology | Purpose |
|-----------|------------|---------|
| **Backend Framework** | Flask 3.1.0 | Python web application |
| **Image Processing** | BLIP (Salesforce) | Vision transformer for image captioning |
| **AI Enhancement** | Google Gemini 1.5 Flash | LLM for contextual refinement |
| **Embeddings** | Sentence Transformers | Semantic similarity matching |
| **Audio Generation** | Suno.ai | AI-powered music creation |
| **Browser Automation** | Playwright | Suno.ai session management |
| **Security** | Flask-WTF, Flask-Limiter | CSRF protection & rate limiting |
| **Caching** | Custom LRU Cache | Performance optimization |
| **Data Processing** | Pandas, Pickle | Song database management |
| **Frontend** | HTML5, CSS3, JavaScript | Responsive user interface |

---

## 📁 Project Structure

```
AI-Song-Recommender/
├── 📁 assets/
│   └── 📷 screenshots/        # Demo images
├── 📁 static/
│   ├── 🎵 audio/              # Generated audio files
│   └── 📷 uploads/            # Temporary image storage
├── 📁 templates/
│   └── 🌐 index.html          # Main web interface
├── 🐍 app.py                  # Flask application (secured)
├── 🧠 description.py          # AI processing logic (optimized)
├── 💾 cache_utils.py          # LRU caching implementation
├── ⚙️  config.py               # Centralized configuration
├── 🚀 setup.py                # Automated setup script
├── 📊 model.ipynb             # Data processing notebook
├── 📋 requirements.txt        # Python dependencies
├── 📄 song_data.csv          # Raw song metadata
├── 💾 song_data.pkl          # Precomputed embeddings (500+ songs)
├── 🤖 suno_automation.py     # Suno.ai login automation
├── 🔧 suno_session_manager.py # Suno.ai session management
├── 🔒 .env.example           # Environment variables template
└── 📝 README.md              # This file
```

---

## 🚀 Quick Start

### Prerequisites
- Python 3.8 or higher
- Google Gemini API key ([Get it here](https://aistudio.google.com/app/apikey))
- Internet connection for AI services

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/kingslayer35/AI-Song-Recommender.git
   cd AI-Song-Recommender
   ```

2. **Set up virtual environment**
   ```bash
   python -m venv venv

   # On macOS/Linux:
   source venv/bin/activate

   # On Windows:
   venv\Scripts\activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   playwright install  # Download browser binaries for Suno.ai automation
   ```

4. **Run automated setup**
   ```bash
   python setup.py
   ```
   This will:
   - ✅ Create `.env` file with auto-generated `SECRET_KEY`
   - ✅ Create necessary directories (`static/uploads`, `static/audio`)
   - ✅ Check for required files (`song_data.pkl`)

5. **Configure environment variables**

   Edit `.env` and add your Gemini API key:
   ```env
   GEMINI_API_KEY=your_actual_api_key_here
   ```

   Get your API key from [Google AI Studio](https://aistudio.google.com/app/apikey)

   Generate a custom secret key (optional):
   ```bash
   python -c "import secrets; print(secrets.token_hex(32))"
   ```

6. **Verify song data**

   Ensure `song_data.pkl` exists in the root directory. If missing, run the `model.ipynb` notebook to generate it from `song_data.csv`.

### Running the Application

```bash
python app.py
```

The application will be available at: **http://127.0.0.1:5000/**

You should see:
```
[OK] Loaded 500+ songs
[OK] Models initialized successfully
* Running on http://127.0.0.1:5000
```

---

## 🎯 Usage Guide

### 1. Upload & Analyze Image
1. Navigate to http://127.0.0.1:5000
2. **Upload an image** by clicking the file input or drag-and-drop
3. *(Optional)* Add context with a manual description
4. *(Optional)* Set preferences using language and artist filters
5. Click **"Get Song Recommendations"**

### 2. View Recommendations
- See the AI-generated image description
- Explore ranked song suggestions with similarity scores
- Filter results by language (English, Hindi, Punjabi, Tamil, Telugu, Bhojpuri, Haryanvi)
- Filter by artist (10 popular artists across genres)

### 3. Generate Custom Songs
1. After getting recommendations, click **"Generate Song from This Description"**
2. Select mood (happy, sad, energetic, calm, romantic, etc.)
3. Choose genre (pop, rock, hip-hop, jazz, etc.)
4. Wait for AI-powered lyrics generation
5. **Important**: Don't close the Playwright browser window during Suno.ai login (first time only)
6. Complete any security challenges (CAPTCHA) if prompted
7. Download your unique custom song once generated

---

## ⚙️ Configuration

### Environment Variables

Edit `.env` to customize:

```env
# Required
GEMINI_API_KEY=your_gemini_api_key_here

# Auto-generated (don't modify unless needed)
SECRET_KEY=auto_generated_64_char_hex

# Optional Configuration
FLASK_ENV=development          # development or production
FLASK_DEBUG=True              # True or False
MAX_CONTENT_LENGTH=16777216   # 16MB (in bytes)
ALLOWED_EXTENSIONS=jpg,jpeg,png,gif,webp
RATE_LIMIT_ENABLED=True
RATE_LIMIT_PER_MINUTE=10
```

### Gemini API Setup
1. Visit [Google AI Studio](https://aistudio.google.com/app/apikey)
2. Sign in with your Google account
3. Click **"Create API Key"**
4. Copy the key and add to `.env`

### Suno.ai Authentication
- First-time users will see an automated login browser window
- Complete the Google login process manually in the popup
- **Do not close** the window until login is confirmed
- Session will be saved in `suno_session.json` for future use

---

## 📊 Demonstrated Impact

### Performance Metrics
- ⚡ **<1 second** inference time (optimized from 5s)
- 🚀 **50x faster** responses for cached duplicate queries
- 📦 **500+ songs** in curated database
- 🌍 **7 languages** supported
- 👥 **50+ active users** at ACM technical showcase
- ✅ **100% uptime** during production demo
- 🔒 **Zero security incidents** with comprehensive protection

### Technical Achievements
- Multimodal AI pipeline (BLIP + Gemini + SBERT)
- Enterprise-grade security (CSRF, rate limiting, secret management)
- Production-ready error handling and logging
- Optimized ML inference (model preloading, caching)
- Scalable architecture supporting concurrent users

---

## 🔮 Roadmap

### Planned Features
- [ ] **Video Support** - Song recommendations for video content
- [ ] **Enhanced Mobile Experience** - Progressive Web App (PWA)
- [ ] **User Accounts** - Save preferences and recommendation history
- [ ] **Spotify Integration** - Direct audio previews and playlist export
- [ ] **Advanced Filters** - Genre, mood, tempo, and era-based filtering
- [ ] **Batch Processing** - Analyze multiple images for playlist generation
- [ ] **Social Features** - Share recommendations with friends
- [ ] **API Endpoints** - RESTful API for third-party integrations
- [ ] **Database Migration** - Replace pickle with PostgreSQL/MongoDB
- [ ] **Docker Support** - Containerized deployment

### Future Improvements
- [ ] Unit and integration tests
- [ ] CI/CD pipeline (GitHub Actions)
- [ ] Application Performance Monitoring (APM)
- [ ] CDN for static assets and generated audio
- [ ] Recommendation explainability dashboard
- [ ] A/B testing framework

---

## 🤝 Contributing

We welcome contributions from the community! Here's how you can help:

### Ways to Contribute
- 🐛 Report bugs and issues
- 💡 Suggest new features or enhancements
- 📝 Improve documentation
- 🔧 Submit pull requests

### Development Setup
1. Fork the repository
2. Create a feature branch
   ```bash
   git checkout -b feature/amazing-feature
   ```
3. Make your changes and test thoroughly
4. Commit with descriptive messages
   ```bash
   git commit -m 'feat: Add amazing feature'
   ```
5. Push to your fork
   ```bash
   git push origin feature/amazing-feature
   ```
6. Open a Pull Request with detailed description

### Code Standards
- Follow PEP 8 style guide for Python code
- Add docstrings to all functions and classes
- Include error handling for external API calls
- Write clear commit messages (conventional commits preferred)
- Update documentation for new features

---

## 📄 License

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.

You are free to:
- ✅ Use commercially
- ✅ Modify
- ✅ Distribute
- ✅ Use privately

Under the conditions:
- 📋 Include license and copyright notice
- 🚫 No liability
- 🚫 No warranty

---

## 🙏 Acknowledgments

### Technologies & Libraries
- **[BLIP](https://github.com/salesforce/BLIP)** by Salesforce - Revolutionary vision-language pre-training for image captioning
- **[Google Gemini](https://ai.google.dev/)** - Advanced LLM for contextual description refinement and lyrics generation
- **[Suno.ai](https://suno.ai/)** - AI-powered music generation platform
- **[Sentence Transformers](https://www.sbert.net/)** - Efficient semantic similarity matching with BERT
- **[Playwright](https://playwright.dev/)** - Reliable cross-browser automation
- **[Flask](https://flask.palletsprojects.com/)** - Lightweight Python web framework

### Inspiration
- Instagram Stories music selection UX
- Spotify's AI DJ and recommendation algorithms
- Research in multimodal AI and cross-modal retrieval

### Community
- ACM IIT Roorkee for showcasing and feedback
- 50+ beta testers who provided valuable insights
- Open-source contributors and maintainers

---

## 📞 Contact & Support

<div align="center">

  **Developer**: Garv

  [![GitHub](https://img.shields.io/badge/GitHub-kingslayer35-181717?style=flat-square&logo=github)](https://github.com/kingslayer35)
  [![Repository](https://img.shields.io/badge/Repository-AI--Song--Recommender-blue?style=flat-square&logo=github)](https://github.com/kingslayer35/AI-Song-Recommender)

  ### Found a bug or have a suggestion?

  [![Report Bug](https://img.shields.io/badge/Report%20Bug-red?style=for-the-badge)](https://github.com/kingslayer35/AI-Song-Recommender/issues)
  [![Request Feature](https://img.shields.io/badge/Request%20Feature-blue?style=for-the-badge)](https://github.com/kingslayer35/AI-Song-Recommender/issues)
  [![View Docs](https://img.shields.io/badge/View%20Documentation-green?style=for-the-badge)](docs/)

</div>

---

## 📚 Additional Documentation

- 📖 **[Setup Instructions](docs/SETUP_INSTRUCTIONS.md)** - Detailed installation guide
- 🔧 **[Technical Improvements](docs/IMPROVEMENTS.md)** - Security & performance upgrades
- 💼 **[Resume Guide](docs/RESUME_FINAL.md)** - 5 resume options + STAR method examples
- 📊 **[Project Summary](docs/SUMMARY.md)** - High-level overview and metrics

---

<div align="center">

  ### ⭐ Star this repository if you found it helpful!

  Made with ❤️ and ☕ by Garv

  **Production-Ready • Secure • High-Performance • Well-Documented**

</div>
