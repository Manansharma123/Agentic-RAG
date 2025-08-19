# AgenticRAG - Using LangGraph

A powerful **Agentic RAG (Retrieval-Augmented Generation)** system that combines **document retrieval, LLM reasoning, and agent-like decision-making** to provide accurate and context-aware responses.  

Developed by: **Manan Sharma - Gen AI Data Scientist**  

---

## 🌟 Features
- 📄 **RAG-based QA**: Query PDF or text documents using embeddings and vector search  
- 🧠 **Agentic Flow**: Uses decision edges (grade, rewrite, generate) for intelligent control flow  
- 🔍 **Search Integration**: Extend responses with web search for real-time knowledge  
- 💬 **Conversational Memory**: Maintains session history for contextual answers  
- ⚡ **LLM Orchestration**: Powered by **LangGraph**, **Groq LLMs**, and **HuggingFace embeddings**  

---

## 📦 Installation

### 1. Clone the repository
```bash
git clone https://github.com/your-username/AgenticRAG.git
cd AgenticRAG
```

### 2. Create Conda environment
```bash
conda create -n agenticrag python=3.10 -y
conda activate agenticrag
```

### 3. Install dependencies
```bash
pip install -r requirements.txt
```

---

## 🔑 Configuration

1. **Groq API Key**  
   Get your API key from [Groq Console](https://console.groq.com/).  
   Export it as an environment variable:
   ```bash
   export GROQ_API_KEY=your_api_key_here   # Mac/Linux
   setx GROQ_API_KEY "your_api_key_here"   # Windows
   ```

2. **Embeddings**  
   By default, uses **HuggingFace `all-MiniLM-L6-v2`**.  

3. (Optional) Create `.env` file for config:
   ```
   GROQ_API_KEY=your_api_key_here
   CHUNK_SIZE=600
   CHUNK_OVERLAP=150
   ```

---

## ▶️ Usage

Run the notebook or convert to Python:

```bash
jupyter notebook AgenticRAG.ipynb
```

OR if you export it as a `.py` file:
```bash
python main.py
```

---

## 📂 Project Structure

```
AgenticRAG/
├── AgenticRAG.ipynb        # Main Agentic RAG notebook
├── requirements.txt        # Dependencies
├── README.md               # Project documentation
└── data/                   # (Optional) Place your documents here
```

---

## ⚙️ Modes

### 🔹 RAG Mode
- Upload a document
- Split into chunks (`RecursiveCharacterTextSplitter`)
- Store in FAISS vector DB
- Retrieve relevant chunks for query

### 🔹 Agentic Flow
- **Grade step** → Check if retrieved docs are relevant  
- **Rewrite step** → Reformulate question if needed  
- **Generate step** → Produce final answer with context  

---

## 🔬 Technical Details
- **LLM**: Groq models (e.g. `mixtral-8x7b`, `gemma2-9b-it`)  
- **Embeddings**: HuggingFace `all-MiniLM-L6-v2`  
- **Vector Store**: FAISS  
- **Document Processing**: Recursive splitting (chunk size 600, overlap 150)  
- **Framework**: LangChain + LangGraph  

---


### Troubleshooting
- **Model Decommissioned**: Use supported Groq models → see [Groq Docs](https://console.groq.com/docs/models)  
- **API Key Error**: Check `GROQ_API_KEY` is set correctly  
- **Large PDFs**: Keep under 50MB for smooth processing  

---

## 🙏 Acknowledgments
- [LangChain](https://www.langchain.com/)  
- [LangGraph](https://github.com/langchain-ai/langgraph)  
- [Groq](https://groq.com/)  
- [HuggingFace](https://huggingface.co/)  
