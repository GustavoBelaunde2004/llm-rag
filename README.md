# LLM RAG: Local Search Engine for Course Notes

A **Retrieval-Augmented Generation (RAG) pipeline** designed to answer queries using course notes and academic materials.  
This project integrates **dense retrieval (FAISS)** with **sparse retrieval (BM25)** for hybrid document search, optimized to run locally with **Ollama + LLaMA 3.2** embeddings.  

## 🚀 Features
- Hybrid retrieval: Combines **FAISS (dense embeddings)** and **BM25 (sparse search)**.  
- Latency optimized: Reduced query response time from **10 minutes → 30 seconds** using serialized caching (95% speedup).  
- High factual grounding: Achieves **80%+ grounding accuracy** by injecting top-ranked retrieved chunks into dynamic prompts.  
- Local-first: Runs entirely on your machine with **Ollama** and Python (no external APIs required).  
- Utilities included:
  - `benchmark_retriever.py` → evaluate retrieval performance.  
  - `visualize_chunks.py` → inspect document splits and chunk relevance.  

## 🛠 Tech Stack
- **Python 3.10+**  
- **LLaMA 3.2 via Ollama**  
- **LangChain**  
- **FAISS + BM25**  
- **PyTorch / TensorFlow (for embeddings)**  

## 📂 Project Structure
├── main.py # Entry point for the RAG pipeline\
├── rag.py # Core RAG logic (retrieval + generation)\
├── data_prep.py # Preprocess and split documents\
├── benchmark_retriever.py # Evaluate retriever performance\
├── visualize_chunks.py # Visualize text chunks for debugging\
├── requirements.txt # Python dependencies\
├── data/ # Source course notes (PDF + processed markdown)

## ⚡ Installation
Clone the repository:

    git clone https://github.com/yourusername/LLM-RAG.git
    cd LLM-RAG

Install dependencies:

    pip install -r requirements.txt

Install Ollama and pull the LLaMA 3.2 model:

    ollama pull llama3.2

## ▶️ Usage
Run the pipeline with:

    python main.py

Enter a query (e.g., "Explain A search"*)

The system retrieves relevant course notes, injects them into a dynamic prompt, and generates an answer using LLaMA 3.2.