# LangChain Expression Language (LCEL)

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![LangChain](https://img.shields.io/badge/LangChain-Latest-green)
![OpenAI](https://img.shields.io/badge/OpenAI-Compatible-orange)
![Groq](https://img.shields.io/badge/Groq-Enabled-purple)

**LangChain Expression Language (LCEL)** is a **declarative way** to build, compose, and manage workflows in LangChain.  
Instead of writing long chains in Python, LCEL allows you to describe pipelines more **readably and modularly**, making it easier to **combine components like LLMs, retrievers, prompts, and tools**.

## 📌 Project Overview

This project demonstrates building a simple yet powerful language translation application using LCEL. It showcases:

- 🤖 Integration with multiple LLM providers (OpenAI, Groq)
- 🔄 Use of Gemma-2-9b-It model through Groq
- 🎯 Simple translation chain implementation
- 📝 Custom prompt templates
- 🔗 LCEL component chaining

## Project Structure

```
📦 LCEL-Translation
 ┣ 📜 client.py
 ┣ 📜 requirements.txt
 ┣ 📜 serve.py
 ┗ 📓 simplellmLCEL.ipynb
```

---

## Why LCEL?
- **Readable:** Pipelines are expressed clearly like a data flow.  
- **Composable:** You can plug and play components.  
- **Debuggable:** Each stage of execution is traceable.  
- **Production-ready:** Works seamlessly with LangServe & LangSmith.  

---

## Core Components of LCEL

1. **Input**  
   - Entry point for user query or external data.  
   - Example: User provides a question like *“What is LangChain?”*  

2. **Prompt Templates**  
   - Structures how queries and context are combined before sending to LLM.  
   - Example: `"Answer the question based on the context: {context}"`.  

3. **Retrievers**  
   - Used to fetch relevant information from a **Vector Store** or external DB.  
   - Example: Top-k documents from FAISS or Pinecone.  

4. **LLMs / Chat Models**  
   - The core reasoning engine.  
   - Can be GPT, Claude, LLaMA, or any integrated model.  

5. **Chains**  
   - Sequential workflows combining multiple steps (prompt → retriever → LLM).  
   - Can be simple (linear) or complex (branched).  

6. **Memory**  
   - Stores conversation history or state between steps.  
   - Useful for chatbots that require context retention.  

7. **Output Parsers**  
   - Converts raw LLM output into structured format (JSON, list, table, etc.).  
   - Ensures responses are usable downstream.  

8. **Tools / Agents**  
   - Allows the pipeline to call external APIs, calculators, or code execution tools.  
   - Example: Querying SQL DB or using a web search tool.  

---

## LCEL Flow (Conceptual)

```mermaid
flowchart LR
    I[Input] --> P[Prompt Template]
    P --> R[Retriever]
    R --> L[LLM / Chat Model]
    L --> M[Memory]
    M --> O[Output Parser]
    O --> A[Answer / Tool Call]
````

## Project Implementation Flow

```mermaid
graph LR
    A[Input Text] --> B[Prompt Template]
    B --> C[Chat Model<br/>Gemma-2-9b-It]
    C --> D[String Output Parser]
    D --> E[Translated Text]
    style A fill:#f9f,stroke:#333,stroke-width:2px
    style C fill:#bbf,stroke:#333,stroke-width:2px
    style E fill:#bfb,stroke:#333,stroke-width:2px
```

## Quick Start

1. Set up environment variables:
   ```env
   OPEN_API_KEY=your_openai_key
   GROQ_API_KEY=your_groq_key
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Run the notebook:
   - Open `simplellmLCEL.ipynb`
   - Follow the step-by-step implementation



