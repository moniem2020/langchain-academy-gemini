# LangChain Academy – Gemini Edition 🚀

![LangChain Academy](https://cdn.prod.website-files.com/65b8cd72835ceeacd4449a53/66e9eba1020525eea7873f96_LCA-big-green%20\(2\).svg)


![Gemini](https://upload.wikimedia.org/wikipedia/commons/8/8a/Google_Gemini_logo.svg)

---

## 🌟 Introduction

Welcome to **LangChain Academy (Gemini Edition)**!
This repo is a **Gemini-customized fork** of the official LangChain Academy.

It is specifically designed for the **Introduction to LangGraph** course.

### 📌 Structure

* **Module 0 →** Basic setup
* **Modules 1–6 →** LangGraph (progressively adding advanced themes)

Each module includes:

* 📓 Jupyter notebooks for hands-on learning
* 🖥️ `studio/` folder with LangGraph Studio graphs

👉 You can follow the same learning flow as the original LangChain Academy, but with **Gemini API support out of the box** (no manual OpenAI → Gemini replacements).

---

## 📚 Modules Overview

| Module | Focus Area                                             |
| ------ | ------------------------------------------------------ |
| 0      | Environment setup, dependencies, and project structure |
| 1      | Introduction to LangGraph basics                       |
| 2      | Building and running simple agents                     |
| 3      | Managing memory and state with LangGraph               |
| 4      | RAG and web search with Tavily + LangGraph             |
| 5      | Multi-agent systems and workflows                      |
| 6      | Advanced orchestration and deployment                  |

---

## 📂 Setup & Installation

### Clone repo

```bash
git clone https://github.com/moniem2020/langchain-academy-gemini.git
cd langchain-academy-gemini
```

### Create an environment and install dependencies

#### Mac/Linux/WSL

```bash
python3 -m venv lc-academy-env
source lc-academy-env/bin/activate
pip install -r requirements.txt
```

#### Windows Powershell

```powershell
python3 -m venv lc-academy-env
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope Process
lc-academy-env\scripts\activate
pip install -r requirements.txt
```

### Running notebooks

If you don't have Jupyter set up, follow installation instructions [here](https://jupyter.org/install).

```bash
jupyter notebook
```

---

## 🔑 Environment Variables

We use a `.env` file with `python-dotenv`.

### Set Gemini API key

* Sign up for Gemini API [here](https://ai.google.dev/)
* Set `GOOGLE_API_KEY` in your `.env` file

Example `.env`:

```env
GOOGLE_API_KEY="your-gemini-api-key"
LANGSMITH_API_KEY="your-langsmith-key"
LANGSMITH_TRACING_V2=true
LANGSMITH_PROJECT="langchain-academy-gemini"
TAVILY_API_KEY="your-tavily-key"   # used in Module 4
```

---

## 🎨 Set up LangGraph Studio

LangGraph Studio is a custom IDE for viewing and testing agents.

To start the local development server (from the `/studio` directory inside each module):

```bash
langgraph dev
```

Expected output:

```
- 🚀 API: http://127.0.0.1:2024
- 🎨 Studio UI: https://smith.langchain.com/studio/?baseUrl=http://127.0.0.1:2024
- 📚 API Docs: http://127.0.0.1:2024/docs
```

Open your browser → Studio UI: [Studio](https://smith.langchain.com/studio/?baseUrl=http://127.0.0.1:2024)

* To use Studio, create a `.env` file with the relevant API keys.
* Run this from the command line to create these files for modules 1–6:

```bash
for i in {1..6}; do
  cp module-$i/studio/.env.example module-$i/studio/.env
  echo "GOOGLE_API_KEY=\"$GOOGLE_API_KEY\"" > module-$i/studio/.env
done
echo "TAVILY_API_KEY=\"$TAVILY_API_KEY\"" >> module-4/studio/.env
```

---

## ⚠️ Note

This repository is **not** the official LangChain Academy repo.
It’s a **Gemini-customized fork**, so you don’t need to manually edit OpenAI → Gemini — everything is ready to go 🚀.

---

## ❤️ Made with love

Made with ❤️ by the community — contributors welcome!
