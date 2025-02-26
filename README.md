# Assignment_Tasks_3

# RAG-Based Chatbot for PDF Documents

## Project Overview
This project implements a **Retrieval-Augmented Generation (RAG) Chatbot** using an **open-source Language Model (LLM)** to answer questions based on uploaded **PDF documents**. The chatbot extracts text, stores it in a **vector database (FAISS)**, retrieves relevant content, and generates responses using a **Mistral 7B or Falcon 7B model**.

## Key Features
- **Uploads and processes PDF documents**  
- **Uses FAISS for fast similarity searches**  
- **Retrieves relevant text before answering (RAG)**  
- **Utilizes an open-source LLM (Mistral 7B / Falcon 7B)**  
- **Runs in Google Colab for easy deployment**  

---

## Tech Stack
- **Python** (Primary Language)
- **LangChain** (RAG & Retrieval)
- **FAISS** (Vector Database)
- **Transformers** (LLM & Hugging Face)
- **PyMuPDF** (Extract text from PDFs)
- **Google Colab** (Runtime environment)

---

## Installation & Setup
### **Install Dependencies**
Run the following command in Google Colab:
```python
!pip install langchain faiss-cpu transformers accelerate torch pymupdf sentence-transformers chromadb bitsandbytes
```

### **Authenticate Hugging Face (For Mistral 7B Users)**
If using Mistral 7B, you must log in:
```python
from huggingface_hub import login
login()
```
- **Get your Hugging Face token:** [Create a Token](https://huggingface.co/settings/tokens)

### **Run the Chatbot**
```python
from scripts.chatbot import start_chatbot
start_chatbot()
```

---

## How It Works
### **Step 1: Upload & Process PDFs**
- Extracts text from PDF using **PyMuPDF**.
- Splits text into smaller chunks for efficient retrieval.

### **Step 2: Store Embeddings in FAISS**
- Converts text chunks into numerical embeddings using **sentence-transformers**.
- Stores them in **FAISS**, a vector search database.

### **Step 3: Chat with the Document (RAG-Based Responses)**
- Retrieves the most relevant content from FAISS.
- Uses **Mistral 7B / Falcon 7B** to generate context-aware answers.

---

##  Example Queries
- **"What is this document about?"**  
- **"Summarize the key points in 3 bullet points."**  
- **"Explain this in simple terms."**  

---

## Model Options
This chatbot supports **two open-source LLMs**:
### **Option 1: Mistral 7B Instruct v0.3**
```python
model_name = "mistralai/Mistral-7B-Instruct-v0.3"
```
- Requires **Hugging Face authentication** (Gated access).  
- **Best for high-quality responses.**

### **Option 2: Falcon 7B Instruct** (Recommended for Google Colab)
```python
model_name = "tiiuae/falcon-7b-instruct"
```
- **No authentication required** (Fully open-source).  
- **Faster inference & lower memory usage.**

---

## Troubleshooting
** Out of Memory Error (OOM)?**  
- Use **Falcon 7B** instead of **Mistral 7B**.  
- Try **4-bit quantization** to reduce model size.

** Model Loading Issues?**  
- Ensure you **requested access** to Mistral 7B on Hugging Face.

---

##  Future Improvements
- Add **Gradio UI** for a user-friendly chatbot interface.  
- Optimize FAISS retrieval to improve response relevance.  
- Fine-tune the model on domain-specific documents.  

---

## Citations:
Document used for chatbot:
Goleman, D. (2017). Leadership that gets results. Harvard Business Review March April 2000 - Leadership Perspectives, 85–96. https://doi.org/10.4324/9781315250601-9 

---

##  License
This project is **open-source** Feel free to contribute and improve! 

