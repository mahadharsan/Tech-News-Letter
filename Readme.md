# 🤖 LLM Driven Tech News Newsletter Generator

An intelligent newsletter generator that automatically curates and summarizes groundbreaking technology news using LLMs. Built with Python, Groq API, and web scraping.

## 🌟 Features

- **Intelligent Link Filtering**: Uses LLM to identify groundbreaking tech news from noise
- **Multi-Source Support**: Scrapes from Ars Technica, TechCrunch, and other tech news sites
- **Automated Summarization**: Generates professional newsletters with structured sections
- **Smart Content Extraction**: Handles both relative and absolute URLs
- **JSON Schema Validation**: Ensures consistent, structured output

## 🛠️ Tech Stack

- **Python 3.12+**
- **Groq API** (LLM inference)
- **BeautifulSoup4** (Web scraping)
- **OpenAI SDK** (API client)
- **python-dotenv** (Environment management)

## 📋 Prerequisites

- Python 3.12 or higher
- Groq API key (free tier available at [console.groq.com](https://console.groq.com))

## 🚀 Installation

1. **Clone the repository**
```bash
git clone https://github.com/mahadharsan/Tech-News-Letter.git
cd Tech-News-Letter
```

2. **Create virtual environment**
```bash
python -m venv .venv
source .venv/bin/activate  # On Windows: .venv\Scripts\activate
```

3. **Install dependencies**
```bash
pip install -r requirements.txt
```

4. **Set up environment variables**
```bash
# Create .env file
echo "GROQ_API_KEY=your_api_key_here" > .env
```

## 💻 Usage

### Basic Usage
```python
from newsletter_generator import create_newsletter

# Generate newsletter from a tech news site
newsletter = create_newsletter(
    title="Today's Tech News",
    url="https://arstechnica.com/"
)

print(newsletter)
```

### Supported News Sources

- Ars Technica: `https://arstechnica.com/`
- Times of India Tech: `https://timesofindia.indiatimes.com/technology`
- Add more sources as needed

## 📁 Project Structure
```
Tech-News-Letter/
├── scraper.py              # Web scraping functions
├── newsletter_generator.py # Main newsletter generation logic
├── .env                    # Environment variables (not committed)
├── .gitignore             # Git ignore file
├── requirements.txt       # Python dependencies
└── README.md             # This file
```

## 🔧 Configuration

### Customize Newsletter Focus

Edit the `link_system_prompt` in `newsletter_generator.py`:
```python
link_system_prompt = """
Focus on:
- AI/ML breakthroughs and research
- Quantum computing advances
- Space technology
- Your custom topics here
"""
```

### Change LLM Model
```python
response = groq.chat.completions.create(
    model='llama-3.3-70b-versatile',  # Change model here
    # Other models: 'llama-3.1-8b-instant', 'mixtral-8x7b-32768'
    ...
)
```

## 📊 Sample Output
```markdown
# Groundbreaking Tech News Letter

## AI/ML Breakthroughs and Research
### OpenAI's GPT-5.1: A New Era in Conversational AI
OpenAI has released GPT-5.1 with improved instruction-following...

## Major Product Launches
### Framework Laptop 16: Upgradeable Design
The Framework Laptop 16 offers a fresh take on modular computing...
```

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 🐛 Known Issues

- Google News requires JavaScript rendering (Selenium recommended)
- Some sites have rate limiting - add delays between requests
- 5,000 character truncation may cut important content

## 🚧 Roadmap

- [ ] Add email delivery functionality
- [ ] Support for RSS feeds
- [ ] Multi-source aggregation in single newsletter
- [ ] Scheduled daily generation
- [ ] Web UI dashboard
- [ ] Docker containerization

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👤 Author

**Your Name**
- GitHub: [@mahadharsan](https://github.com/mahadharsan)
- LinkedIn: [Mahadharsan Ravichandran](https://linkedin.com/in/mahadharsan-ravichandran)

## 🙏 Acknowledgments

- [Groq](https://groq.com/) for fast LLM inference
- [Ars Technica](https://arstechnica.com/) for quality tech journalism
- BeautifulSoup4 for robust web scraping

## ⚠️ Disclaimer

This tool is for educational purposes. Please respect website terms of service and rate limits when scraping content.

---

**Built with ❤️ and 🤖 by Mahadharsan!**