# MetaNovel-Engine

![Version](https://img.shields.io/badge/version-v0.0.22-blue.svg)
![Python](https://img.shields.io/badge/python-3.8+-green.svg)
![License](https://img.shields.io/badge/license-MIT-yellow.svg)

> **AI-Assisted Novel Creation Engine** – A structured, step-by-step tool for long-form novel writing

## 💡 Why Choose MetaNovel-Engine?

- **🎯 Cost-efficient & high performance**: A structured creative workflow avoids redundant generation and significantly reduces AI costs
- **📚 Multi-project management**: Create multiple novels simultaneously with completely isolated data
- **🎨 Personalized configuration**: Independent AI prompts per project; sci-fi, romance, and mystery each have their own style
- **🔄 Progressive creation**: From a single-sentence idea to a complete novel through 7 clear steps
- **🌍 Complete world-building**: Unified management of characters, locations, and items ensures narrative consistency
- **🤖 Intelligent experience**: AI automatically analyzes themes, recommends genres, and generates multiple versions to choose from

## 🚀 5-Minute Quick Start

### 1. Installation
```bash
git clone https://github.com/hahagood/MetaNovel-Engine.git
cd MetaNovel-Engine
pip install -r requirements.txt
```

### 2. API Configuration (First-time Use)
Copy `.env.example` to `.env` and enter your OpenRouter API key:
```bash
cp .env.example .env
# Edit .env and add: OPENROUTER_API_KEY=your_api_key_here
```

### 3. Run the Program
```bash
python meta_novel_cli.py
```

### 4. Start Creating
After launching, choose “Create New Project” and follow the 7-step workflow to begin your novel!

## 🧭 Runtime Environment

- Python 3.8 or higher (Python 3.11+ recommended for better httpx/asyncio performance)
- Virtual environment recommended:
  `python -m venv venv && source venv/bin/activate` or `. bin/activate`
- Dependencies installed via `pip install -r requirements.txt`, including `openai`, `httpx`, and `rich`
- Communicates with the OpenRouter API; ensure access to `https://openrouter.ai`
- Console-based UI only; no browser or GUI required

## 📝 Creation Workflow: 7 Steps

| Step | Feature | Purpose |
|-----|--------|--------|
| 1️⃣ | **Set Theme** | Define the core one-sentence idea |
| 2️⃣ | **Intelligent Theme Expansion** | AI analyzes and recommends genres, generating multiple versions |
| 3️⃣ | **World Building** | Create characters, locations, and items |
| 4️⃣ | **Story Outline** | Write a 500–800 word story framework |
| 5️⃣ | **Chapter Breakdown** | Divide into 5–10 chapter outlines |
| 6️⃣ | **Chapter Summaries** | 300–500 word detailed summary per chapter |
| 7️⃣ | **Generate Main Text** | Generate 2,000–4,000 words per chapter |

*Each step supports viewing, editing, and regeneration to ensure quality.*

## ⚙️ Core Features

### 📁 Project Management
- Unlimited novel projects with complete data isolation
- Quickly switch between projects and continue writing
- Automatic backups to prevent data loss

### 🎨 Personalized AI
- Independent prompt configuration per project
- Adjustable AI writing styles for different genres
- Support for custom AI models and parameters

### 🤖 Intelligent Creation Experience
- **Smart theme analysis**: AI recommends the most suitable genre
- **Multi-version generation**: Generates three different story concepts at once
- **Forced user participation**: Requires user intent to align AI output with expectations
- **Modular architecture**: Independent service modules for easy extension and maintenance

### 📤 Export Features
- Export single chapters, chapter ranges, or full novels
- Standardized metadata including title, export time, chapter info, and word count
- Flexible range input formats (e.g., 1-3, 1,3, 1 3)
- Accurate word counts with automatic cleanup of AI metadata
- Clean output containing only story content
- Clear, user-friendly interface

### 🔧 System Settings
- AI model switching
- Network proxy configuration
- Intelligent retry settings

## 🏗️ Project Structure Overview

- `meta_novel_cli.py`: CLI entry point and main navigation
- `workflow_ui.py`: Business logic and UI for the 7-step workflow
- `project_manager.py` / `project_data_manager.py`: Multi-project management and persistence
- `data_manager.py`: Unified JSON read/write and caching layer
- `llm_service.py`: OpenRouter API interaction and retry logic
- `entity_manager.py`, `theme_paragraph_service.py`: Entity management and theme enhancement

## 📂 Configuration & Data Storage

- `.env`: Stores API key, proxy, and default model settings
- Global config stored in system app data directory
- Project data stored in `<project>/meta/` with backups in `meta_backup/`
- `prompts.json` supports per-project overrides
- Exports written to `exports/` by default

## 🛡️ Robustness & Fault Tolerance

- Unified retry logic with exponential backoff and jitter
- Multi-layer JSON fallback parsing
- Automatic fallback when Canon Bible generation fails
- Auto-completion of required config fields
- Entity name consistency enforcement

## 🧪 Testing & Development

- Activate virtual environment: `. bin/activate`
- Run single test:
  `python -m pytest tests/test_entity_manager.py`
- Run full test suite:
  `python -m pytest tests`

## 🆘 FAQ

**Q: What API key do I need?**  
A: An OpenRouter API key. Register at OpenRouter and add it to `.env`.

**Q: How do I switch AI models?**  
A: Main menu → System Settings → AI Model Management.

**Q: How do I configure a proxy?**  
A: Edit `.env` and set `HTTP_PROXY` and `HTTPS_PROXY`.

**Q: Can I customize AI prompts?**  
A: Yes, via Prompts Template Management in system settings.

**Q: How do I export my novel?**  
A: Use Export Novel in the content generation menu.

## 📄 License

This project is released under the **MIT License**.

---

**Let AI become your best creative partner!** ✨
