<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:1e1b4b,50:312e81,100:1e1b4b&height=200&section=header&text=FREE%20API%20KEYS%20MODELS&fontSize=44&fontColor=ffffff&animation=fadeIn&fontAlignY=38&desc=One%20Notebook%20%E2%80%A2%20Five%20Free-Tier%20LLM%20Providers%20%E2%80%A2%20LangChain%20Ready&descAlignY=58&descSize=16&descColor=c7d2fe" width="100%"/>

<p>
  <img src="https://img.shields.io/badge/Python-3.10+-3776AB?style=for-the-badge&logo=python&logoColor=white" />
  <img src="https://img.shields.io/badge/LangChain-Ready-1C3C3C?style=for-the-badge&logo=langchain&logoColor=white" />
  <img src="https://img.shields.io/badge/Jupyter-Notebook-F37626?style=for-the-badge&logo=jupyter&logoColor=white" />
  <img src="https://img.shields.io/badge/Providers-5-6366F1?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Cost-%240.00-22c55e?style=for-the-badge" />
</p>

<p>
  <img src="https://komarev.com/ghpvc/?username=SalikAhmad702-freeapikeys&label=Repo+Views&color=6366f1&style=flat-square" />
</p>

</div>

<br/>

## 📌 Overview

**Free API Keys Models** is a single reference notebook (`models.ipynb`) that shows the *exact, minimal* LangChain initialization code for five LLM providers that offer genuinely usable **free API tiers**. No SDK-hunting, no half-finished quickstarts, no marketing filler — just the import, the class, and the model string for each provider, ready to copy and run.

Every provider initializes the same `model` object shape, so once you pick one, everything downstream — chains, agents, RAG pipelines — stays identical.

<br/>

## 🧭 How It Works

```mermaid
flowchart LR
    A["📓 Open models.ipynb"] --> B["🔍 Pick a provider section"]
    B --> C["📋 Copy the init cell"]
    C --> D["🔑 Paste your free API key in .env"]
    D --> E["🚀 model.invoke(...)"]
```

<br/>

## ⚡ Providers Covered

<table>
<tr>
<td width="50%" valign="top">

### 🌬️ Mistral AI
`mistral-medium-latest`
via `langchain-mistralai`
Native key auth

### ⚡ Groq
`llama-3.3-70b-versatile`
via `langchain-groq`
Native key auth — blazing inference speed

</td>
<td width="50%" valign="top">

### 🔀 OpenRouter
`google/gemma-4-31b-it:free`
via `langchain-openrouter`
Native key auth — free-tagged models

### 🌐 Qwen (Alibaba DashScope Intl)
`qwen-turbo`
via `langchain-openai` (OpenAI-compatible)

</td>
</tr>
</table>

<div align="center">

### 🦙 Ollama Cloud
`gpt-oss:20b` · via `langchain-openai` (OpenAI-compatible)

</div>

<br/>

## 🛠️ Tech Stack

<p>
  <img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white" />
  <img src="https://img.shields.io/badge/LangChain-1C3C3C?style=flat-square&logo=langchain&logoColor=white" />
  <img src="https://img.shields.io/badge/Mistral%20AI-FA520F?style=flat-square&logo=mistralai&logoColor=white" />
  <img src="https://img.shields.io/badge/Groq-F55036?style=flat-square" />
  <img src="https://img.shields.io/badge/OpenRouter-6366F1?style=flat-square" />
  <img src="https://img.shields.io/badge/Qwen-615CED?style=flat-square" />
  <img src="https://img.shields.io/badge/Ollama-000000?style=flat-square&logo=ollama&logoColor=white" />
  <img src="https://img.shields.io/badge/dotenv-ECD53F?style=flat-square&logo=dotenv&logoColor=black" />
</p>

<br/>

## 🚀 Quick Start

**1. Clone the repo**
```bash
git clone https://github.com/SalikAhmad702/Free-API-Keys-Models.git
cd Free-API-Keys-Models
```

**2. Create a virtual environment**
```bash
python -m venv venv

# Windows
venv\Scripts\activate
# macOS/Linux
source venv/bin/activate
```

**3. Install dependencies**

Using `pip`:
```bash
pip install -r requirements.txt
```

Or using `uv` (faster):
```bash
uv pip install -r requirements.txt
```

Each provider cell in the notebook also has its own `uv pip install` line commented above it, if you only want to install one provider's package:
```bash
uv pip install langchain-mistralai
uv pip install langchain-groq
uv pip install langchain-openrouter
uv pip install langchain-openai
```

**4. Set up your keys**
```bash
cp .env.example .env
```
Open `.env` and paste in your real API keys — you only need the ones you plan to use.

**5. Launch the notebook**
```bash
jupyter notebook models.ipynb
```
Run the cell under whichever provider heading you want. Each block is fully self-contained.

<br/>

## 🧩 The Pattern

Every provider reduces to the same three lines:

```python
from langchain_groq import ChatGroq

model = ChatGroq(model="llama-3.3-70b-versatile")
response = model.invoke("Explain RAG in one sentence.")
print(response.content)
```

For OpenAI-compatible providers (Qwen, Ollama Cloud), the only difference is a `base_url`:

```python
from langchain_openai import ChatOpenAI
import os

model = ChatOpenAI(
    model="qwen-turbo",
    api_key=os.getenv("QWEN_API_KEY"),
    base_url="https://dashscope-intl.aliyuncs.com/compatible-mode/v1",
)
```

Swap the class, swap the provider — your chains, prompts, and agents never need to change.

<br/>

## 🔐 Where to Get Free API Keys

| Provider | Console |
|---|---|
| 🌬️ Mistral AI | [console.mistral.ai](https://console.mistral.ai/) |
| ⚡ Groq | [console.groq.com/keys](https://console.groq.com/keys) |
| 🔀 OpenRouter | [openrouter.ai/keys](https://openrouter.ai/keys) |
| 🌐 Qwen (DashScope Intl) | [dashscope-intl.console.aliyun.com](https://dashscope-intl.console.aliyun.com/) |
| 🦙 Ollama Cloud | [ollama.com](https://ollama.com/) |

<br/>

## 📁 Repository Structure

```
Free-API-Keys-Models/
├── models.ipynb         # One markdown header + one code cell per provider
├── .env.example          # Key template — copy to .env and fill in
├── requirements.txt       # Everything needed to run every cell
└── README.md
```

<br/>

## 🗺️ Roadmap

- [x] Mistral, Groq, OpenRouter, Qwen, Ollama Cloud
- [ ] Google Gemini free tier
- [ ] Streaming response examples per provider
- [ ] Latency + quality benchmark script across all five

<br/>

## 🤝 Contributing

Found another provider with a real free tier? Add it in the same format — one markdown header, one self-contained code cell — and open a PR.

```bash
git checkout -b add/provider-name
git commit -m "feat: add <provider> setup"
git push origin add/provider-name
```

<br/>

---

<div align="center">

## 👤 Author

### **Salik Ahmad**
**AI/ML Engineer**

*Building agentic AI systems, RAG pipelines, and LLM-powered tools — one free API key at a time.*

<p>
  <a href="https://salikahmad.vercel.app/" target="_blank">
    <img src="https://img.shields.io/badge/Portfolio-salikahmad.vercel.app-6366F1?style=for-the-badge&logo=vercel&logoColor=white&labelColor=0d0d0d" />
  </a>
  <a href="https://www.linkedin.com/in/salik-ahmad-programmer/" target="_blank">
    <img src="https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white&labelColor=0d0d0d" />
  </a>
  <a href="https://github.com/SalikAhmad702" target="_blank">
    <img src="https://img.shields.io/badge/GitHub-Follow-181717?style=for-the-badge&logo=github&logoColor=white&labelColor=0d0d0d" />
  </a>
  <a href="https://www.kaggle.com/salikahmad702" target="_blank">
    <img src="https://img.shields.io/badge/Kaggle-Explore-20BEFF?style=for-the-badge&logo=kaggle&logoColor=white&labelColor=0d0d0d" />
  </a>
</p>

<br/>

<sub>⭐ If this saved you an hour of digging through provider docs, consider starring the repo.</sub>

<br/><br/>

---

<sub>© 2026 Salik Ahmad · AI/ML Engineer</sub>

</div>
