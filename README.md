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

### 7_agent_query_dataframes.ipynb

Asks the LLM to generate Python code that answers a user question about a Pandas dataframe, executes this code, and returns the answer. The LlamaIndex version doesn't natively work with `deepseek-1:7b`, but our hand-made agent does!

------

Ollama is a wrapper around [Llama.cpp](https://github.com/ggml-org/llama.cpp), which reads models stored in the [GGUF format](https://huggingface.co/docs/hub/en/gguf), including anything (LLM or embedding models) stored at HuggingFace. The examples in this repository use the LLM `deepseek-r1:7b`:

       ~ $ ollama show deepseek-r1:7b
        Model
          architecture        qwen2     
          parameters          7.6B      
          context length      131072    
          embedding length    3584      
          quantization        Q4_K_M    
       
        Capabilities
          completion    
       
        Parameters
          stop    "<｜begin▁of▁sentence｜>"    
          stop    "<｜end▁of▁sentence｜>"      
          stop    "<｜User｜>"                 
          stop    "<｜Assistant｜>"            
       
        License
          MIT License                    
          Copyright (c) 2023 DeepSeek  

On HuggingFace this model is available under `DeepSeek-R1-Distill-Qwen-7B`, which makes it more obvious that it is a distillated version of the open-source model Qwen (specifically, Qwen2.5-Math-7B), fine-tuned using DeepSeek-R1 data. It is a reasoning model, which means it provides its full chain of thoughts. 
