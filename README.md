# Deep_Research - Multi-Agent Research System

A comprehensive AI-powered research workflow that integrates user clarification, research brief generation, multi-agent coordination, and final report generation.

## 🎯 Overview

Deep_Research is an advanced research automation system that orchestrates a complete research workflow from initial user input through final report delivery. The system uses multiple AI agents working together to conduct thorough research and generate comprehensive reports.

## 🏗️ Architecture

The system consists of several key components:

### Core Modules

- **`app.py`** - Main orchestration module that integrates all system components
- **`scope.py`** - User clarification and research brief generation
- **`multiagent.py`** - Multi-agent research coordination
- **`research_agent.py`** - Individual research agent implementation
- **`utils.py`** - Utility functions and helpers
- **`prompts.py`** - System prompts and templates

### Schema Definitions

- **`app_schemas.py`** - Main application state schemas
- **`scope_schemas.py`** - Scoping workflow schemas  
- **`multiagent_state.py`** - Multi-agent state management
- **`research_state.py`** - Research agent state definitions

### Configuration Files

- **`.gitignore`** - Git ignore rules for security and cleanliness
- **`.env.example`** - Environment variables template
- **`.env`** - Your actual environment variables (not tracked by git)

## 🚀 Features

### 1. User Clarification and Scoping
- Interactive user input clarification
- Research scope definition
- Brief generation based on user requirements

### 2. Multi-Agent Research Coordination
- Supervisor agent managing research workflow
- Multiple specialized research agents
- Coordinated research execution

### 3. Comprehensive Report Generation
- Synthesis of all research findings
- Final report generation with structured output
- Date-stamped deliverables

## 🛠️ Technology Stack

- **LangChain** - LLM orchestration and chaining
- **LangGraph** - Graph-based workflow management
- **OpenAI GPT-4** - Primary language model (configurable)
- **Anthropic Claude** - Alternative model support
- **Google Search API** - Web search capabilities
- **Tavily API** - Advanced web search and research
- **Python** - Core implementation language

## 📋 Prerequisites

- Python 3.8+
- API Keys:
  - OpenAI API key
  - Anthropic API key (optional)
  - Google API key
  - Tavily API key
  - LangSmith API key (optional, for tracing)

## ⚙️ Installation

1. Clone the repository:
```bash
git clone https://github.com/MehmetCelik53/Deep_Research.git
cd Deep_Research
```

2. Install dependencies:
```bash
pip install langchain langgraph openai anthropic google-search-results tavily-python rich
```

3. Set up environment variables:
```bash
# Copy the example environment file
cp .env.example .env

# Edit .env with your actual API keys
# GOOGLE_API_KEY=your_google_api_key_here
# TAVILY_API_KEY=your_tavily_api_key_here
# ANTHROPIC_API_KEY=your_anthropic_api_key_here
# OPENAI_API_KEY=your_openai_api_key_here
# LANGSMITH_API_KEY=your_langsmith_api_key_here
```

## 🚀 Usage

### Basic Usage

```python
from app import agent
from app_schemas import AgentInputState
from langchain_core.messages import HumanMessage

# Define your research request
input_state = {
    "messages": [HumanMessage(content="Research the latest developments in AI safety")]
}

# Run the complete research workflow
result = await agent.ainvoke(input_state)

# Access the final report
print(result["final_report"])
```

### Environment Setup

Make sure your `.env` file contains all required API keys:

```bash
GOOGLE_API_KEY="your_google_api_key_here"
TAVILY_API_KEY="your_tavily_api_key_here"
ANTHROPIC_API_KEY="your_anthropic_api_key_here"
OPENAI_API_KEY="your_openai_api_key_here"
LANGSMITH_TRACING="true"
LANGSMITH_API_KEY="your_langsmith_api_key_here"
LANGSMITH_PROJECT="Deep_Research"
```

## 📊 Workflow

1. **User Input** → Clarification and scoping
2. **Research Brief** → Generated based on clarified requirements  
3. **Multi-Agent Research** → Coordinated research execution
4. **Report Generation** → Comprehensive final report

## 🔧 Configuration

The system supports multiple LLM providers:

```python
# OpenAI GPT-4
writer_model = init_chat_model(
    model="openai:gpt-4.1", max_tokens=32000
)

# Anthropic Claude
writer_model = init_chat_model(
    model="anthropic:claude-sonnet-4-20250514", max_tokens=64000
)
```

## 📁 Project Structure

```
Deep_Research/
├── app.py                 # Main application orchestrator
├── scope.py              # User clarification & brief generation
├── multiagent.py         # Multi-agent coordination
├── research_agent.py     # Individual research agent
├── utils.py              # Utility functions
├── prompts.py            # System prompts
├── app_schemas.py        # Application schemas
├── scope_schemas.py      # Scoping schemas
├── multiagent_state.py   # Multi-agent state
├── research_state.py     # Research state
├── .gitignore           # Git ignore rules
├── .env.example         # Environment template
├── .env                 # Your environment variables (not tracked)
└── README.md            # This file
```

## 🔒 Security Notes

- **Never commit `.env` files** - They contain sensitive API keys
- **Use `.env.example`** as a template for required environment variables
- **Keep API keys secure** - Don't share them in public repositories
- **Regular key rotation** - Update API keys periodically for security

## 📝 Development

### Jupyter Notebooks (Not Tracked)

The project includes development notebooks that are excluded from git:
- `appJ.ipynb` - Main application development and testing
- `researchagent.ipynb` - Research agent development

These files contain development code and potentially sensitive information, so they're not tracked in the repository.

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

### Contributing Guidelines

- Never commit `.env` files or API keys
- Follow the existing code style
- Add tests for new features
- Update documentation as needed

## 📜 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 👨‍💻 Author

**Mehmet Celik** - [@MehmetCelik53](https://github.com/MehmetCelik53)

## 🙏 Acknowledgments

- LangChain team for the excellent framework
- OpenAI and Anthropic for powerful language models
- Google and Tavily for search capabilities
- The open-source community for inspiration and tools

---

## 🇹🇷 Türkçe Özet

Deep_Research, kapsamlı AI destekli araştırma iş akışları için geliştirilmiş gelişmiş bir otomasyon sistemidir. Kullanıcı girdisinden final raporuna kadar tüm araştırma sürecini yönetir.

### 🎯 Ana Özellikler

**1. Çoklu Ajan Sistemı**
- **Koordinatör Ajan**: Araştırma sürecini yöneten ana ajan
- **Uzman Ajanlar**: Her biri farklı alanlarda uzmanlaşmış araştırma ajanları
- **İş Birliği**: Ajanlar birlikte çalışarak kapsamlı araştırma yapar

**2. Akıllı Araştırma Süreci**
- **Kullanıcı Netleştirme**: Belirsiz sorular otomatik olarak netleştirilir
- **Kapsam Belirleme**: Araştırma alanı ve derinliği tanımlanır
- **Özet Oluşturma**: Kullanıcı ihtiyaçlarına göre araştırma özeti hazırlanır

**3. Profesyonel Rapor Üretimi**
- **Veri Sentezi**: Tüm araştırma bulgularını birleştirir
- **Yapılandırılmış Çıktı**: Profesyonel format ile rapor oluşturur
- **Tarihli Teslimat**: Zaman damgalı sonuçlar verir

### 🛠️ Teknoloji Altyapısı

- **LangChain & LangGraph**: Modern AI ajan mimarisi
- **OpenAI GPT-4 / Anthropic Claude**: En güncel dil modelleri
- **Google & Tavily API**: Güçlü web araştırma yetenekleri
- **Python Tabanlı**: Sağlam ve ölçeklenebilir kodlama

### 💡 Kullanım Alanları

- **Akademik Araştırma**: Literatür tarama ve analiz
- **Pazar Araştırması**: Rekabet analizi ve trend takibi
- **Teknik Dokümantasyon**: Kompleks konularda detaylı raporlama
- **Stratejik Planlama**: Kapsamlı sektör analizleri
- **İçerik Üretimi**: Derinlemesine araştırma gerektiren yazılar

### 🚀 Nasıl Çalışır?

1. **Soru Sorma**: "AI güvenliği konusundaki son gelişmeleri araştır"
2. **Otomatik Netleştirme**: Sistem soruyu detaylandırır ve kapsamını belirler
3. **Çoklu Ajan Araştırması**: Farklı ajanlar paralel olarak araştırma yapar
4. **Kapsamlı Rapor**: Tüm bulgular birleştirilerek profesyonel rapor oluşturulur

### 🔧 Kurulum ve Kullanım

Proje Python 3.8+ gerektirir ve LangChain ekosistemini kullanır. API anahtarları (.env dosyası) ile konfigüre edilir ve basit Python komutları ile çalıştırılır.

Bu sistem, araştırma sürecinizi otomatikleştirerek zamanınızı önemli ölçüde kazandırır ve profesyonel kalitede sonuçlar üretir.

---

*Son güncelleme: 11 Eylül 2025*