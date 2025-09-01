# A Chatbot For My Department (CSE Department, Comilla University)

![Dashboard Screenshot](project.png)

This project demonstrates how to build a **PDF-based Question & Answer chatbot** using Python, LangChain, Hugging Face models, and Gradio. The system allows users to upload a PDF (like department handbooks or notes) and ask questions in natural language, retrieving concise answers directly from the document.

---

## 📌 Project Overview

The goal of this project is to:  

- Load and preprocess PDF documents for efficient information retrieval  
- Split text into manageable chunks for embedding and similarity search  
- Create a vector store using FAISS for semantic search  
- Use a Hugging Face LLM (`google/flan-t5-small`) to answer questions based on retrieved context  
- Provide a web interface using Gradio for interactive Q&A  

---

## 🧰 Tools & Technologies

| Tool                 | Purpose                                       |
|---------------------|-----------------------------------------------|
| `PyPDFLoader`       | Load and read PDF documents                   |
| `LangChain`         | Manage document retrieval & LLM pipelines    |
| `sentence-transformers` | Create embeddings for text chunks          |
| `FAISS`             | Vector store for semantic search             |
| `Hugging Face Transformers` | Language model for generating answers |
| `Gradio`            | Web interface for interacting with the chatbot |
| `torch`             | GPU/CPU support for LLM                       |
| `psutil` & `socket` | Port management and process handling        |

---

## 📂 Files Included

- `a_chatbot_using_llm.ipynb` – Main Python script containing PDF processing, LLM pipeline, and Gradio interface  
- `cse.pdf` – PDF document used for Q&A (CSE Department info)  
- `project.png` – Screenshot or illustration of the project   
- `README.md` – Project documentation 

---

## 📊 Sample Usage

Some example questions you can ask:

- “Who is the head of the CSE Department?”  
- “What courses are offered in the CSE program?”  
- “How many semesters are in the CSE curriculum?”  
- “What lab facilities are available?”  

The chatbot provides **concise, one-sentence answers** extracted from the PDF content.

---

## ⚙️ Technical Details

- **PDF Loader:** `PyPDFLoader` from `langchain-community`  
- **Text Splitter:** `RecursiveCharacterTextSplitter` (chunk_size=400, overlap=50)  
- **Embeddings:** `sentence-transformers/all-MiniLM-L6-v2`  
- **Vector Store:** FAISS with cosine similarity  
- **LLM:** Hugging Face pipeline (`google/flan-t5-small`)  
- **QA Chain:** `RetrievalQA` with `stuff` chain type  
- **Interface:** `gr.Blocks()` from Gradio  

---

## 🔧 Optimization Features

- **LRU Caching:** Speeds up PDF processing and LLM pipeline initialization  
- **GPU Support:** Automatically uses CUDA if available  
- **Port Management:** Finds free ports and terminates processes blocking them  
- **Logging:** Built-in logging for debugging and monitoring  

---

## 💡 Future Improvements

- Add **PDF upload feature** in the Gradio interface  
- Support **multiple PDFs** simultaneously  
- Use **larger or more advanced LLMs** for more accurate answers  
- Highlight the exact part of the PDF where the answer is found  

---

## 📄 License

This project is **open-source** and free to use for educational purposes.
