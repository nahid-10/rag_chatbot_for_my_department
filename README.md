⚡ Fast PDF Q&A - CSE Department, Comilla University

A fast and efficient PDF-based Question & Answer system designed for the CSE Department of Comilla University. Users can upload a PDF document (e.g., department syllabus, handbook, or notes) and ask questions in natural language. The system retrieves the relevant information and provides concise, one-sentence answers.

📂 Project Structure
Fast-PDF-QA/
│
├── cse.pdf                  # PDF document containing CSE Department information
├── project.png              # Project illustration/screenshot
├── a_chatbot_using_llm.ipyb # Main Python script with Gradio interface and LangChain pipeline
└── README.md

🛠 Features

PDF Document Loader – Automatically loads and preprocesses the PDF.

Text Chunking – Splits PDF content into smaller chunks for better retrieval.

Embeddings & Vector Store – Uses sentence-transformers with FAISS for semantic search.

LLM-based Q&A – Uses Hugging Face models (e.g., google/flan-t5-small) for natural language answers.

Gradio Interface – User-friendly web interface for asking questions.

Optimized & Cached – LRU caching for faster PDF processing and LLM initialization.

Automatic Port Handling – Finds free ports and terminates conflicting processes automatically.

💻 Installation

Clone the repository

git clone https://github.com/nahid-10/rag_chatbot_for_my_department.git
cd rag_chatbot_for_my_department


Install dependencies

pip install -r requirements.txt


Or manually:

pip install langchain-community langchain pypdf sentence-transformers faiss-cpu gradio transformers huggingface-hub


Hugging Face Authentication

from huggingface_hub import login
login(token="YOUR_HUGGINGFACE_TOKEN")

⚡ How to Run
python main.py


The Gradio interface will launch on a free port automatically (default starts from 7860).

Open the displayed link in your browser.

Ask questions about the CSE Department using the input box.

📝 Usage

Type your question in the text box (e.g., “What courses are offered in the CSE Department?”).

Click Submit.

The system returns a concise answer based on the PDF content.

Example Questions:

“Who is the head of the CSE Department?”

“Vice president of cse society?”



⚙️ Technical Details

PDF Loader: PyPDFLoader from langchain-community

Text Splitter: RecursiveCharacterTextSplitter (chunk_size=400, overlap=50)

Embeddings: sentence-transformers/all-MiniLM-L6-v2

Vector Store: FAISS with cosine similarity

LLM: Hugging Face pipeline google/flan-t5-small

QA Chain: RetrievalQA with stuff chain type

Web Interface: gr.Blocks() from Gradio

🔧 Optimization

LRU Caching: Speeds up PDF processing and LLM pipeline initialization.

GPU Support: Automatically uses CUDA if available.

Port Management: Automatically finds a free port and terminates processes blocking it.

Logging: Built-in logging for debugging and monitoring pipeline execution.

📌 Notes

Ensure your PDF (cse.pdf) is in the project directory.

Adjust chunk_size and chunk_overlap in main.py for longer or shorter answers.

For large PDFs, allow extra memory and GPU resources if available.

💡 Future Improvements

Add PDF upload feature in the Gradio interface.

Enable multi-language support for questions and answers.

Integrate advanced models for more accurate answers.

Add answer highlighting from the original PDF content.

📄 License

This project is open-source and free to use for educational purposes.
