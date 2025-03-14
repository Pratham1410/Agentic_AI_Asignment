# SupportBot: AI-Powered Customer Support Chatbot: https://huggingface.co/spaces/thamesh24/Agentic_Bot_GUI

## 🚀 Overview
SupportBot is an intelligent customer support chatbot designed to answer queries by retrieving relevant information from a given document. It leverages a **hybrid retrieval-augmented generation (RAG) approach**, combining **semantic search** with **generative question answering** to provide accurate and conversational responses.

## ✨ Features
✅ **Hybrid Search Mechanism**: Uses **TF-IDF** for keyword-based retrieval and **SentenceTransformer embeddings** for semantic search.  
✅ **Generative Answering**: Employs **FLAN-T5** to generate natural, context-aware responses.  
✅ **Adaptive Learning**: Implements a feedback loop to refine responses based on simulated feedback.  
✅ **Logging Mechanism**: Maintains logs of all interactions for debugging and analysis.  
✅ **Error Handling**: Gracefully handles out-of-scope queries and document loading issues.

## 🧠 Why These Models Were Chosen?
I have used **SentenceTransformer ('all-MiniLM-L6-v2')** for semantic embeddings and **FLAN-T5 ('google/flan-t5-base')** for generative answering due to their efficiency, accuracy, and suitability for real-time applications. **SentenceTransformer ('all-MiniLM-L6-v2')** is lightweight, fast, and effective for document retrieval, ensuring rapid similarity matching without excessive computational costs. It balances semantic understanding and performance, making it ideal for real-time chatbot interactions. **FLAN-T5 ('google/flan-t5-base')** generates natural, context-aware responses, handles open-ended queries, and adapts well to various question-answering tasks. Unlike extractive models such as **BERT or RoBERTa**, which just extract answers from the text, FLAN-T5 provides more human-like responses. This hybrid approach—combining **TF-IDF + embeddings for retrieval** with **FLAN-T5 for answering**—ensures **both efficiency and a superior user experience** with fluent, human-like responses.

## 🚀 Deployment Steps
### 1️⃣ Install Dependencies
```bash
pip install transformers sentence-transformers PyPDF2 nltk torch numpy scikit-learn
```

### 2️⃣ Prepare Your Document
- Upload a `.pdf` or `.txt` document containing the support information.

### 3️⃣ Run the Bot
```python
bot = SupportBotAgent(document_path="path/to/document.txt")
response = bot.answer_query("How do I reset my password?")
print(response)
```

### 4️⃣ Deploy as a Web App
- Use **Flask** or **FastAPI** to expose an API endpoint.
- Deploy on **Heroku, AWS Lambda, or a simple EC2 instance**.

## 🔧 Known Issues & Future Improvements
🔹 **Limited Context Window**: FLAN-T5 may struggle with very long responses; consider using a larger model for enhanced performance.  
🔹 **Better Feedback Integration**: Future versions can incorporate real user feedback instead of simulated feedback loops.  
🔹 **Multilingual Support**: Expand to handle queries in multiple languages.  
🔹 **Fine-Tuning for Specific Domains**: Adapt FLAN-T5 and the SentenceTransformer model for domain-specific needs.  
🔹 **Enhanced RAG with LLMs**: Improve response quality by integrating **larger language models** and **better retrieval-augmented generation (RAG) techniques**.  

