# TradeSage: Unraveling Markets with AI

> Transforming complex trade data into clear, queryable insights using Large Language Models.

TradeSage is an LLM-powered trade intelligence system that converts raw structured 
trade data into natural language narratives. Built as a Bachelor's thesis project in 
collaboration with a stock analysis company (deployed in their production environment), 
it enables analysts, businesses, and non-experts alike to query complex international 
trade data through a conversational interface.

The system combines Retrieval-Augmented Generation (RAG), supervised fine-tuning on 
domain-specific trade data, and a lightweight Flask interface demonstrating that 
open-source LLMs can match proprietary solutions in specialised domains at a fraction 
of the cost.

---

## How It Works
```
Raw Trade Data (SQL)
       ↓
Data Engineering Layer      — parsing, cleaning, prompt-completion generation
       ↓
LLM + RAG Layer             — LlamaIndex, fine-tuned Llama 3, vector retrieval
       ↓
Flask Chat Interface        — natural language queries, narrative responses
```

The pipeline has four stages:
1. **Data Retrieval:** financial news, structured SQL trade databases, market signals
2. **Data Engineering:** NLP preprocessing, conversion of tabular data into 
                          1,500+ prompt-completion pairs
3. **LLM Reasoning:** RAG via LlamaIndex + fine-tuned Llama 3 with quantization
4. **User Interface:** Flask web app with conversational query interface

---

## Tech Stack

| Layer | Tools |
|---|---|
| LLM & Reasoning | Llama 2/3, LangChain, LlamaIndex, Groq |
| Vector Search | Pinecone |
| Data Engineering | Python, Pandas, SQL |
| Model Training | Hugging Face, PyTorch, Model Quantization |
| Web App | Flask |
| Embeddings | Hugging Face Transformers |

---

## Getting Started

### Prerequisites
- Python 3.9+
- A [Groq API key](https://console.groq.com/keys)
- A [Hugging Face token](https://huggingface.co/settings/tokens)

### Installation

**1. Clone the repository**
```bash
git clone https://github.com/fahad0071/TradeSage
cd TradeSage
```

**2. Create and activate a virtual environment**
```bash
# Create
python -m venv .venv

# Activate (Windows CMD)
.venv\Scripts\activate

# Activate (Windows PowerShell)
.\.venv\Scripts\Activate

# Activate (Mac/Linux)
source .venv/bin/activate
```

**3. Set up environment variables**
```bash
# Mac/Linux
cp .env.example .env

# Windows
copy .env.example .env
```

Open `.env` and add your keys:
```
GROQ_API_KEY=your_groq_key_here
HUGGINGFACE_TOKEN=your_hf_token_here
```

**4. Install dependencies**
```bash
pip install -r requirements.txt
```

**5. Run the app**
```bash
python app.py
```

Visit `http://localhost:5000` in your browser.

---

## Project Structure
```
TradeSage/
│
├── app.py                  # Flask application entry point
│
├── templates/              # HTML templates for the chat interface
├── static/                 # Images and static assets
│
├── Notebooks/              # Experimentation and training notebooks
│   ├── rag_pipeline.ipynb
│   ├── fine_tuning.ipynb
│   └── ...
│
├── Paper/              # Research Paper
│   ├── Thesis_TradeSage-Unraveling Markets with AI
│
├── Data Engineering/       # Scripts used to parse and process raw trade data
│
├── parsed_data.csv         # Final cleaned dataset used for RAG and fine-tuning
│
├── .env.example            # Environment variable template
└── requirements.txt
```

---

## Notebooks

The `Notebooks/` directory contains the full experimentation pipeline:
- Data parsing and prompt-completion generation
- RAG implementation with LangChain and LlamaIndex
- Llama 3 fine-tuning with quantization
- Model evaluation and comparison

---

## Key Findings

- RAG with open-source LLMs (Llama 2/3) can effectively match GPT-3 based solutions 
  for domain-specific tasks at significantly lower cost
- Fine-tuning on 1,500 instances yielded measurable improvement but showed signs of 
  overfitting, pointing to the need for larger domain-specific datasets
- Model quantization was essential for practical deployment without A100-class GPUs

---

## Research Context

This project was developed as a Bachelor's thesis at the National University of 
Computer and Emerging Sciences (FAST), Karachi. The system is currently deployed 
in production at a stock analysis company (name withheld under NDA).

**Authors:** Fahad Zahid, Nashit Budhwani, Lohit Ashwa
**Supervisor:** Dr. Muhammad Rafi

---

## Notes

- The `Notebooks/` directory contains all experimentation and training code
- Additional data sources can be added by updating the data directory path in the 
  relevant notebook
- Ngrok integration (used during Colab development) has been removed from the 
  production version
