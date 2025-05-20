# Retrieval-Augmented Generation (RAG) Chatbot

## Project Description
This project implements a Retrieval-Augmented Generation (RAG) Chatbot using LangChain, HuggingFace language models, and FAISS vector store. The chatbot allows users to ask questions based on a custom knowledge base created from PDF documents. It uses a Streamlit web app interface for interactive chat.

## Assignment Overview and How This Project Addresses It

### Task 1: Data Loading
The project loads PDF documents from the `Data/` directory, processes them into text chunks, and creates vector embeddings using HuggingFace sentence-transformers. These embeddings are stored in a FAISS vector store for efficient retrieval.

### Task 2: Set Up RAG with LangChain
LangChain components are used to set up a Retrieval-Augmented Generation pipeline. The pipeline uses a HuggingFace LLM endpoint combined with a FAISS retriever to answer user queries based on the knowledge base.

### Task 3: Build the Chatbot
A Streamlit-based chatbot app is built that leverages the RAG pipeline to provide accurate, context-aware answers to user questions. The chatbot also displays source documents and page numbers for transparency.

### Requirements and Bonus
- The code is well-documented with clear function descriptions.
- A sample set of questions and chatbot responses is included in `Sample_Questions_and_Chatbot_Responses.pdf`.
- All code and relevant files are organized for easy deployment and sharing on GitHub.
- This README file serves as the bonus documentation.

## Features
- Load and process PDF documents as knowledge base
- Create vector embeddings and store in FAISS
- Retrieval-based question answering using HuggingFace LLM
- Streamlit web interface for interactive chat
- Source referencing with page numbers in responses
- Environment variable support for HuggingFace API token

## Installation

1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd Assignment-GenAI
   ```

2. Ensure you have Python 3.8 or higher installed.

3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

4. Set up environment variables:
   - Create a `.env` file in the root directory.
   - Add your HuggingFace API token:
     ```
     HF_TOKEN=your_huggingface_api_token_here
     ```

## Data Preparation

Before running the chatbot, prepare the vector store by processing the PDF documents:

```bash
python create_memory.py
```

This script loads PDFs from the `Data/` folder, splits them into chunks, creates embeddings, and saves the FAISS vector store locally at `vectorstore/db_faiss`.

## Usage

To launch the chatbot web app, run:

```bash
streamlit run Chat-bot.py
```

This will open a local Streamlit interface where you can interact with the chatbot.

## Dependencies

All required Python packages and versions are listed in `requirements.txt`. Key dependencies include:

- langchain and langchain-community
- huggingface-hub
- faiss-cpu
- streamlit
- PyMuPDF
- python-dotenv
- transformers

## Folder Structure Overview

```
Assignment-GenAI/
│
├── Chat-bot.py               # Streamlit chatbot app
├── create_memory.py          # Script to load PDFs and create vector store
├── requirements.txt          # Python dependencies
├── Sample_Questions_and_Chatbot_Responses.pdf  # Sample Q&A responses
├── Data/                     # Folder containing PDF documents as knowledge base
├── vectorstore/              # FAISS vector store files
│   └── db_faiss/
│       ├── index.faiss
│       └── index.pkl
├── .gitignore
└── .blackboxrules
```

---

## Author

Anshul Katiyar  
Email: itsanshulkatiyar@gmail.com




