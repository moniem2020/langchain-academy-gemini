# LangChain Academy – Gemini Edition ?

![LangChain Academy](https://cdn.prod.website-files.com/65b8cd72835ceeacd4449a53/66e9eba1020525eea7873f96_LCA-big-green%20(2).svg)
[![Google Gemini logo](https://upload.wikimedia.org/wikipedia/commons/thumb/d/d9/Google_Gemini_logo_2025.svg/300px-Google_Gemini_logo_2025.svg.png)](https://ai.google.dev/)

---

## ?? Introduction

Welcome to **LangChain Academy (Gemini Edition)** — a Gemini-ready fork of the official LangChain Academy tailored for the *Introduction to LangGraph* course. Everything is preconfigured to use the Gemini API, so you can focus on building graphs instead of swapping SDKs.

Module 0 covers setup, Modules 1–4 focus on LangGraph with progressively advanced themes, Module 5 explores memory-rich workflows, and Module 6 shows you how to deploy and productionize your agents.

Each module directory includes:
- ?? Jupyter notebooks that walk through the concepts
- ?? A `studio/` folder with LangGraph Studio graphs for interactive exploration

---

## ?? Modules Overview

| Module | Focus Area                                             |
| ------ | ------------------------------------------------------ |
| 0      | Environment setup, dependencies, and project structure |
| 1      | Introduction to LangGraph basics                       |
| 2      | Building and running simple agents                     |
| 3      | Managing memory and state with LangGraph               |
| 4      | Retrieval workflows and Tavily-powered search          |
| 5      | Memory-driven workflows and multi-agent patterns       |
| 6      | Advanced orchestration and deployment                  |

---

## ?? Setup & Installation

### Python version
Ensure you have **Python 3.11+** for full compatibility with LangGraph:
```bash
python3 --version
```

### Clone repo
```bash
git clone https://github.com/moniem2020/langchain-academy-gemini.git
cd langchain-academy-gemini
```

### Create an environment and install dependencies

**Mac/Linux/WSL**
```bash
python3 -m venv lc-academy-env
source lc-academy-env/bin/activate
pip install -r requirements.txt
```

**Windows PowerShell**
```powershell
python3 -m venv lc-academy-env
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope Process
lc-academy-env\scripts\activate
pip install -r requirements.txt
```

### Running notebooks
If you need Jupyter, follow the [official installation guide](https://jupyter.org/install), then launch:
```bash
jupyter notebook
```

---

## ?? Environment Variables

Create a `.env` file or export the variables in your shell. We ship `.env.example` files in every `studio/` folder to make this easy.

### Set Gemini API key
- Generate an API key in [Google AI Studio](https://aistudio.google.com/app/apikey)
- Set `GOOGLE_API_KEY` in your environment (LangChain also respects `GEMINI_API_KEY`; keep them synchronized if you use both)

Example `.env`:
```env
GOOGLE_API_KEY="your-gemini-api-key"
LANGSMITH_API_KEY="your-langsmith-key"
LANGSMITH_TRACING_V2=true
LANGSMITH_PROJECT="langchain-academy-gemini"
TAVILY_API_KEY="your-tavily-key"  # Needed for Module 4 examples
```

---

## ?? LangGraph Studio

LangGraph Studio is the IDE we use to inspect and test graphs.

From each module’s `studio/` directory, start the local dev server:
```bash
langgraph dev
```

Expected output:
```
- ?? API: http://127.0.0.1:2024
- ?? Studio UI: https://smith.langchain.com/studio/?baseUrl=http://127.0.0.1:2024
- ?? API Docs: http://127.0.0.1:2024/docs
```

Open the UI in your browser: [LangGraph Studio](https://smith.langchain.com/studio/?baseUrl=http://127.0.0.1:2024).

To generate `.env` files for modules 1–6:
```bash
for i in {1..6}; do
  cp module-$i/studio/.env.example module-$i/studio/.env
  echo "GOOGLE_API_KEY=\"$GOOGLE_API_KEY\"" > module-$i/studio/.env
done
echo "TAVILY_API_KEY=\"$TAVILY_API_KEY\"" >> module-4/studio/.env
```

---

## ?? Notes

- This repository is a Gemini-optimized variant of the original LangChain Academy.
- No manual OpenAI ? Gemini replacements required — everything is ready to run with Gemini from the start.
- Contributions are welcome! If you spot a gap or have an idea, feel free to open a PR.

Happy building! ??
