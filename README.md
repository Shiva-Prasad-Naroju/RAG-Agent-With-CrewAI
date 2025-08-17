# RAG AGENT USING CREWAI

## 🔍 What is this project?
This project is a **RAG Agent (Retrieval-Augmented Generation Agent)** built with [CrewAI](https://docs.crewai.com). It demonstrates how a **RAG agent** can answer queries asked by grounding its responses in a knowledge base (PDF), here in this case "RAG_MAS.pdf" -> "RAG-Multi Agent System"

Instead of relying only on the LLM, the **RAG Agent** uses:
- 🔎 **Retrieve** → Find relevant context from PDFs  
- 🧠 **Augment** → Combine retrieved context with user query  
- ✍️ **Generate** → Produce grounded, factual responses  

👉 In simple words: **This is a RAG Agent that answers only with facts from your PDF, not hallucinations.**

## ⚙️ Tech Stack
- 🤖 **CrewAI** – Agent framework  
- ⚡ **Groq (ChatGroq)** – LLaMA 3.1 8B Instant model  
- 🧩 **HuggingFace** – `all-MiniLM-L6-v2` embeddings for semantic search  
- 📚 **RagTool (CrewAI)** – Retrieval-Augmented tool for document Q&A  
- 🐍 **Python** – Core implementation  
- 🔑 **dotenv** – For API key management  
- 🏦 **Chromadb** - Since we didn't mention vectordb specifically, CrewAI defaults to Chroma.

## 🏗️ System Design:
The project defines **RAG Agent**:

1. **📄 SOW RAG Agent (`sow_agent`)**
   - **Role**: Senior SOW Assistant  
   - **Goal**: Help answer questions about Statements of Work  
   - **Backstory**: Expert in contracts and compliance, designed to retrieve facts from documents  
   - **Tools**: RAG Tool for PDF-based retrieval  

## 📂 Project Workflow:
1. Load your PDF knowledge base (e.g., *Rapid SOW Generation Guide*).  

2. Initialize the **RagTool** with this source.  

3. Define the **SOW RAG Agent** (`sow_agent`) with:
   - Role, Goal, Backstory  
   - Groq LLaMA 3.1 8B Instant as its reasoning model  
   - HuggingFace MiniLM embeddings for retrieval  

4. Create **Tasks** that query the RAG agent, for example:  
   - *“What is the waiting period for rehabilitation?”*  
   - *"What is the standard timeline for completing a Statement of Work draft?"*
   - *"Before final approval, what review steps must the SOW undergo?"*

5. Run the task → The RAG agent retrieves context from the PDF and generates a grounded answer.  

## 🎯 Why this project matters:

- Shows how to build a RAG Agent with CrewAI
- Demonstrates Groq LLMs (LLaMA 3.1 8B Instant) in action
- Uses HuggingFace embeddings for document retrieval
- Grounded in a real-world PDF knowledge base

## 📌 Key Takeaways:

- This is not a chatbot – it’s a RAG Agent
- RAG (Retrieval-Augmented Generation) = making LLMs reliable by grounding them in documents
- Agent = AI worker with a defined role (here: SOW Assistant)
- CrewAI = orchestrates the RAG Agent + tools
