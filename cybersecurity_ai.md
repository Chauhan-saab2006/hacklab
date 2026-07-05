# Cybersecurity Local AI Assistant (RAG-Based)

## Overview
This project describes how to build a fully local, private AI assistant trained on cybersecurity books using Retrieval-Augmented Generation (RAG).

Instead of training a model from scratch, this system:
- Stores documents locally
- Retrieves relevant content
- Uses a local LLM to generate answers

---

## Architecture

### Components
1. Local LLM (Ollama - Llama3, Mistral, etc.)
2. Embedding model (sentence-transformers)
3. Vector Database (FAISS)
4. Framework (LlamaIndex / LangChain)

---

## Setup Steps

### 1. Install Ollama
```bash
curl -fsSL https://ollama.com/install.sh | sh
ollama pull llama3
ollama run llama3
```

### 2. Install Dependencies
```bash
pip install llama-index faiss-cpu sentence-transformers pymupdf
```

### 3. Prepare Data
- Download books from Google Drive
- Store in: /data/cyber_books/

---

## Example Code

```python
from llama_index.core import VectorStoreIndex, SimpleDirectoryReader
from llama_index.embeddings.huggingface import HuggingFaceEmbedding
from llama_index.llms.ollama import Ollama

documents = SimpleDirectoryReader("data/cyber_books").load_data()

embed_model = HuggingFaceEmbedding(
    model_name="sentence-transformers/all-MiniLM-L6-v2"
)

llm = Ollama(model="llama3")

index = VectorStoreIndex.from_documents(
    documents,
    embed_model=embed_model
)

query_engine = index.as_query_engine(llm=llm)

response = query_engine.query(
    "Explain privilege escalation techniques in Linux"
)

print(response)
```

---

## Persistence

```python
index.storage_context.persist(persist_dir="./storage")
```

Load later:
```python
from llama_index.core import load_index_from_storage, StorageContext

storage_context = StorageContext.from_defaults(persist_dir="./storage")
index = load_index_from_storage(storage_context)
```

---

## Best Practices

- Chunk size: 400–700 tokens
- Overlap: ~100 tokens
- Use better embeddings: BAAI/bge-base-en
- Enable source tracking

---

## System Prompt

You are a specialized cybersecurity research assistant operating in a fully local environment.

Your knowledge comes ONLY from the provided document context.

Rules:
- Do NOT hallucinate
- If answer not found, say so clearly

Behavior:
- Provide deep technical explanations
- Assume professional-level user
- Break down attacks step-by-step

Output:
- Direct answer
- Structured explanation
- Technical depth

---

## Query Template

Context:
{retrieved_chunks}

Question:
{user_query}

Instructions:
Answer using ONLY the context.

---

## Enhancements

When explaining attacks, include:
- Preconditions
- Exploitation steps
- Impact
- Detection
- Mitigation

---

## Notes

- Fully offline system
- No cloud/API required
- Suitable for sensitive research

---

## Future Improvements

- CLI tool
- Web UI
- Multi-model setup
- Code-aware parsing

