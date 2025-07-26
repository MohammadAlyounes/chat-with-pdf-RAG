Chat with My PDF Book - RAG System

A Retrieval-Augmented Generation (RAG) system that enables intelligent conversations with PDF documents (Books) using vector embeddings and large language models.

Linkedin Post: https://www.linkedin.com/feed/update/urn:li:activity:7354869978690383872/

Project Architecture


<img width="1082" height="896" alt="project_architecture" src="https://github.com/user-attachments/assets/8a68a71e-67fc-4d23-a541-833e2b8cab00" />



(Please see the screenshots in the images directory for more explanation)

 Main query question prompt from our book: "How much data was produced by the assault on an al-Qaeda safe house in Afghanistan in 2017? Give me any realistic approximation response."

🚀 Features

PDF Text Extraction: Automated text processing and chunking (for book structure)

Vector Embeddings: Efficient document indexing using [BAAI/bge-base-en-v1.5]

Semantic Search: Retrieval of relevant document sections

Context-Aware Generation: LLM-powered responses from the book source

🌍 Real-World Applications & Benefits

Privacy-First AI Solutions

This RAG system addresses critical limitations of traditional LLMs:

Data Privacy: Private documents remain local - never sent to external APIs or used for model training

Zero Data Leakage: Local Llama 3.1 deployment ensures no data transmission to external servers

No Training Updates: Model operates in inference-only mode - your data is never used to update or retrain the model

Complete Offline Operation: Internet connection not required for document processing or chat functionality

Knowledge Gaps: Enables AI to access information not present in training data (post-cutoff content, proprietary documents, specialized literature)

Cost Efficiency: Reduces API costs by using local Llama 3.1 deployment


The system consists of two main pipelines:

📚 Indexing Pipeline (indexing_pipeline.ipynb):

* PDF document loading and text extraction

* Semantic text chunking for optimal retrieval

* Vector embedding generation

* Local FAISS database storage

🤖 Generation Pipeline (generation_pipeline.ipynb):

* User query processing and embedding

* Similarity search in FAISS vector database

* Context retrieval and prompt augmentation

* Local Llama 3.1 response generation


🔒 Privacy Guarantee: All processing occurs locally - no data transmission to external servers.


🛠️ Technology Stack Used

Language: Python

Vector Database: FAISS (Facebook AI Similarity Search)

Embeddings: [OpenAI/Sentence-Transformers/BAAI/bge-base-en-v1.5] (local)

LLM: Llama 3.1 (Local deployment)

PDF Processing: [PyMuPDFLoader, Custom cleaning for book structure]

Framework: LangChain with FAISS integration

🚦 Usage

1. Clone the git repo

2. Install dependencies: pip install -r  requirements.txt

3. Set up environment variables: OpenAI key if used, or you should download local LLM as in the project


Step 1: Document Indexing

Run the indexing pipeline from Anaconda prompt

jupyter notebook indexing_pipeline.ipynb

1. Upload your PDF document

2. Configure text chunking parameters

3. Generate embeddings using your chosen model

4. Create and save FAISS index (.faiss + .pkl files

Step 2: Start Chatting

Run the generation pipeline

jupyter notebook generation_pipeline.ipynb

1. Load the pre-built FAISS index (VB)

2. Process user queries and find similar chunks

3. Generate contextual responses using retrieved information


🔄 Future Development Roadmap

* User Interface Enhancement (GUI, Web interface)

* Advanced search: Filters, date ranges, and metadata queries

* Hybrid search: Combine semantic and keyword-based retrieval

* Query optimization: Automatic query expansion and refinement
  
* Model switching: Support for multiple LLM backends
