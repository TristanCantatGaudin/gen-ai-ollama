# gen-ai-ollama

### 1_ollama.ipynb  

Use the `ollama` package to interact with a local LLM.

### 2_info_in_prompt.ipynb

Shows the difference between raw questions and longer prompts that include information. When the text gets too long, the LLM fails to read it all properly.

### 3_embedding_facts.ipynb

Sentences and paragraphs can be represented as vectors in a high-dimensional space. We use an embedding model and UMAP to visualise the resulting embedding, and compute semantic similarity to a user question.

### 4_simple_RAG_ollama.ipynb

Builds a simple but real Retrieval-Augmented Generation tool, which retrieves and includes relevant pieces of information to enhance the question asked by the user, and limits hallucinations by asking the model to stick to the provided documentation.

### 5_chromadb.ipynb

A ChromaDB quickstart, showing the creation of a collection and retrieval of documents.

### 6_llamaindex_PDF_RAG.ipynb

Uses LlamaIndex to embed PDF documents into ChromaDB and FAISS vectore stores. Runs RAG on them to answer user questions.
