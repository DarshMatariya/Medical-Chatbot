# Medibot – AI Medical Assistant


> **Medibot** is a RAG‑powered medical chatbot that retrieves trusted PDF content, embeds it with Sentence‑Transformers, and serves real‑time answers via Groq’s Llama‑4 Scout LLM – all wrapped in a Streamlit UI.

---

## Features
- **Hybrid RAG pipeline** – FAISS + LangChain for context‑aware answers  
- **Groq Llama‑4 Scout 17B** – low‑latency, high‑quality generation  
- **MMR retrieval** – diverse, relevant passages (`k=7`)  
- **PDF loader** – just drop new guidelines in `/data`, re‑index, and go  
- **Chat history** – persists per session for smoother follow‑ups  

---

## Live Demo
Hit the button –> **https://medical-assistance.streamlit.app/**  
No signup needed; ask away about symptoms, treatments, or anatomy.  
(Out‑of‑scope questions politely bounce.)

---

## Project Structure

Medical-Chatbot/
├─ app.py                # Streamlit entrypoint
├─ requirements.txt
├─ .streamlit/
│   └─ config.toml       
├─ data/                 # Source PDFs
├─ vectorstore/
│   └─ db_faiss/         # Pre‑built FAISS index (.faiss + .pkl)
└─ README.md            


## Tech Stack

UI : Streamlit
Embeddings : sentence-transformers/all-MiniLM-L6-v2
Vector DB : FAISS (saved locally)
LLM	 : Groq (meta‑llama/llama‑4‑scout‑17b)
Orchestration : LangChain

## Environment Variables
GROQ_API_KEY = your-groq-api-key

## Quick Start (Local)

```bash
git clone https://github.com/DarshMatariya/Medical-Chatbot.git
cd Medical-Chatbot

# create venv (optional but recommended)
python -m venv .venv
source .venv/bin/activate  # Windows: .venv\Scripts\activate

pip install -r requirements.txt

# set your Groq key (or export in shell startup)
export GROQ_API_KEY="sk-xxxxxxxxxxx"

streamlit run app.py
