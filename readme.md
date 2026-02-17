#  Turning Shopify RAG Answers into Voice for Indian Customers

A voice-enabled customer support and product discovery system built on top of Shopify store data.  
The project uses **Retrieval-Augmented Generation (RAG)** to answer customer questions accurately and converts those answers into **spoken responses**, creating a natural, low-effort shopping experience—especially suited for Indian users.

---

##  Features

-  Voice-based customer interaction
-  RAG-powered answers from real Shopify data
-  Text-to-Speech responses (hands-free support)
-  Answers questions about:
  - product price
  - available sizes
  - fabric/material
  - shipping timelines
  - return & refund policies
- Handles natural, imperfect customer queries
- Supports multi-turn conversations

---

## Project Architecture

```
User Voice
   ↓
Speech-to-Text (SpeechRecognition)
   ↓
Intent & Product Detection
   ↓
RAG (FAISS + Sentence Transformers)
   ↓
Text Answer
   ↓
Text-to-Speech (pyttsx3)
   ↓
Spoken Response
```

---

##  Tech Stack

### Core
- Python
- Shopify Store Data (Products & Policies)

### RAG
- sentence-transformers (`all-MiniLM-L6-v2`)
- FAISS (vector similarity search)

### Voice
- **Speech-to-Text (STT)**  
  - `SpeechRecognition` (Google Speech backend)
- **Text-to-Speech (TTS)**  
  - `pyttsx3` (offline, local)

---

##  Project Structure

```
.
├── shopify_fetch.py      # Fetches and cleans Shopify store data
├── chunk_data.py         # Splits data into chunks
├── build_faiss.py        # Builds FAISS vector index
├── rag_query.py          # Main voice-enabled RAG application
├── hf_stt.py             # Speech-to-Text module
├── hf_tts.py             # Text-to-Speech module
├── shopify_data.json     # Cleaned Shopify data
├── faiss.index           # Vector index
└── README.md
```

---

## ⚙️ Setup Instructions

### 1️⃣ Clone the repository
```bash
git clone <your-repo-link>
cd <repo-name>
```

### 2️⃣ Create and activate a virtual environment (recommended)
```bash
python -m venv venv
venv\Scripts\activate
```

### 3️⃣ Install dependencies
```bash
pip install -r requirements.txt
```

---

##  How to Run the Project

### Step 1: Fetch Shopify data
```bash
python shopify_fetch.py
```

### Step 2: Build the FAISS index
```bash
python build_faiss.py
```

### Step 3: Start the voice assistant
```bash
python rag_query.py
```

---

##  Example Voice Queries

- “What products do you sell?”
- “What is the price of cotton kurta?”
- “What sizes are available in cotton kurta?”
- “What is the fabric of the kurta?”
- “What is your return policy?”
- “Exit”

---

## 🇮🇳 Why This Project Matters

Many Indian customers prefer **speaking and listening** over reading long text.  
This project demonstrates how combining **RAG with voice interfaces** can reduce friction, improve clarity, and create a more natural shopping experience for D2C and Shopify sellers.




