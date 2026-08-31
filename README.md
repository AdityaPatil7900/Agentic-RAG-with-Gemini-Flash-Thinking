# 🤖 Agentic RAG with Gemini Flash Thinking

> **An intelligent, agentic Retrieval-Augmented Generation (RAG) system that combines document retrieval, query rewriting, vector search, web search, and Gemini-powered reasoning to produce context-aware, source-grounded answers.**

<p align="center">

**🧠 Gemini Flash Thinking** • **🔎 Agentic Retrieval** • **🗄️ Qdrant** • **🌐 Web Search** • **⚡ Streamlit**

</p>

---

## 🌟 Overview

Traditional RAG systems typically follow a simple pipeline:

```text
User Query
    ↓
Retrieve Documents
    ↓
Generate Answer
```

This project goes a step further by introducing an **agentic retrieval workflow**.

The system can:

- 📄 Process uploaded PDF documents
- 🌐 Extract content from web pages
- ✂️ Automatically chunk and embed content
- 🗄️ Store embeddings in Qdrant Cloud
- 🔄 Rewrite user queries to improve retrieval
- 🔎 Perform similarity-based document retrieval
- 🎯 Filter retrieved context using similarity thresholds
- 🌍 Fall back to web search when local knowledge is insufficient
- 🧠 Generate context-aware responses using Gemini
- 📚 Provide source attribution
- 💬 Maintain conversation history
- ⚙️ Orchestrate the workflow using Agno
- 🖥️ Provide an interactive Streamlit interface

The goal is to make the RAG pipeline **more adaptive, context-aware, and useful for real-world question answering.**

---

# 🏗️ System Architecture

```text
                         ┌─────────────────────┐
                         │      User Query     │
                         └──────────┬──────────┘
                                    │
                                    ▼
                         ┌─────────────────────┐
                         │   Query Reformulator│
                         │   / Query Rewriter  │
                         └──────────┬──────────┘
                                    │
                                    ▼
                         ┌─────────────────────┐
                         │   Retrieval Agent   │
                         └──────────┬──────────┘
                                    │
                     ┌──────────────┴──────────────┐
                     │                             │
                     ▼                             ▼
            ┌─────────────────┐          ┌─────────────────┐
            │ Qdrant Vector   │          │  Web Search     │
            │ Search          │          │  (Exa AI)      │
            └────────┬────────┘          └────────┬────────┘
                     │                             │
                     └──────────────┬──────────────┘
                                    │
                                    ▼
                         ┌─────────────────────┐
                         │ Context Aggregation │
                         └──────────┬──────────┘
                                    │
                                    ▼
                         ┌─────────────────────┐
                         │ Gemini Flash        │
                         │ Thinking            │
                         └──────────┬──────────┘
                                    │
                                    ▼
                         ┌─────────────────────┐
                         │ Grounded Response   │
                         │ + Source Attribution│
                         └─────────────────────┘
```

---

# ✨ Key Features

## 📄 Intelligent Document Processing

- Upload and process PDF documents
- Extract content from web pages
- Automatically chunk textual content
- Generate vector embeddings
- Store embeddings in Qdrant Cloud

## 🔎 Intelligent Retrieval

- Query rewriting for improved retrieval
- Semantic similarity search
- Similarity threshold filtering
- Context-aware document retrieval
- Source attribution for generated responses

## 🌐 Web Search Fallback

When relevant information is not available in the indexed documents, the system can use web search as an additional information source.

### Web search capabilities

- 🔍 Exa AI integration
- 🎯 Domain filtering
- 🌐 External web content retrieval
- 🔄 Retrieval fallback mechanism

## 🧠 Agentic Reasoning

The application uses an agent-based architecture to make the retrieval process more adaptive.

The query reformulation workflow can transform an initial user question into a retrieval-friendly query before searching the available knowledge sources.

## 💬 Conversational Interface

The Streamlit interface provides:

- Interactive chat
- Document upload
- Web URL input
- Query visibility
- Source visibility
- Chat history management
- Configurable web search domains

---

# 🧩 Technology Stack

| Technology | Purpose |
|---|---|
| 🐍 **Python** | Core application development |
| 🧠 **Gemini Flash Thinking** | Reasoning and response generation |
| 🔤 **Gemini Embeddings** | Vector representation of documents |
| 🗄️ **Qdrant Cloud** | Vector database and similarity search |
| 🤖 **Agno** | Agent orchestration |
| 🌐 **Exa AI** | Optional web search |
| 🖥️ **Streamlit** | Interactive user interface |
| 📄 **PDF Processing** | Document ingestion |
| 🔎 **Semantic Search** | Context retrieval |

---

# 🔄 End-to-End Workflow

### 1️⃣ Document Ingestion

```text
PDF / Web Page
      ↓
Content Extraction
      ↓
Text Chunking
      ↓
Embedding Generation
      ↓
Qdrant Vector Database
```

### 2️⃣ Query Processing

```text
User Question
      ↓
Query Reformulation
      ↓
Improved Search Query
```

### 3️⃣ Retrieval

```text
Rewritten Query
      ↓
Qdrant Similarity Search
      ↓
Similarity Threshold
      ↓
Relevant Context
```

### 4️⃣ Web Fallback

```text
Insufficient Local Context
            ↓
       Exa Web Search
            ↓
     External Information
```

### 5️⃣ Generation

```text
Retrieved Context
       +
Conversation History
       +
User Query
       ↓
Gemini Flash Thinking
       ↓
Context-Aware Answer
       +
Source Attribution
```

---

# 🚀 Getting Started

## 📋 Prerequisites

Before running the project, you will need:

- Python 3.x
- Google AI API key
- Qdrant Cloud account
- Qdrant API key
- Qdrant cluster URL
- Exa AI API key *(optional)*

---

## 🔑 1. Configure Google AI

Create a Google AI API key through Google AI Studio.

The application uses Gemini for:

- 🧠 Response generation
- 🔤 Embedding generation
- 🤖 Reasoning

---

## 🗄️ 2. Configure Qdrant Cloud

Create a Qdrant Cloud cluster and obtain:

```text
QDRANT_API_KEY
QDRANT_URL
```

The Qdrant instance is used for storing and retrieving vector embeddings.

---

## 🌐 3. Configure Exa AI

Exa AI is optional.

It enables the application to perform web searches when the local document knowledge base does not provide sufficient context.

---

# ⚙️ Installation

### Clone the repository

```bash
git clone <YOUR_GITHUB_REPOSITORY_URL>
cd <YOUR_PROJECT_DIRECTORY>
```

### Install dependencies

```bash
pip install -r requirements.txt
```

---

# ▶️ Run the Application

Start the Streamlit application:

```bash
streamlit run agentic_rag_gemini.py
```

The application will launch an interactive browser-based interface.

---

# 🖥️ How to Use

## Step 1 — Configure API Keys 🔐

Enter your credentials through the application interface:

- Google API key
- Qdrant API key
- Qdrant URL
- Exa AI API key *(optional)*

---

## Step 2 — Add Knowledge 📚

Upload:

```text
📄 PDF Documents
```

or provide:

```text
🌐 Web Page URLs
```

The system processes the content and creates vector embeddings for retrieval.

---

## Step 3 — Ask Questions 💬

Enter a natural-language question.

The system can:

```text
Question
   ↓
Rewrite Query
   ↓
Search Knowledge Base
   ↓
Evaluate Retrieved Context
   ↓
Web Search if Necessary
   ↓
Generate Answer
   ↓
Show Sources
```

---

## Step 4 — Explore the Response 🔍

The interface can expose:

- Rewritten query
- Retrieved information
- Generated answer
- Sources
- Web search results when used

---

# 🧠 What Makes This Project Different?

A conventional RAG pipeline can struggle when a user's query does not closely match the wording of the stored documents.

This project introduces an **agentic retrieval layer** that can reformulate the user's question before retrieval.

### Traditional RAG

```text
Query
 ↓
Vector Search
 ↓
Context
 ↓
LLM
 ↓
Answer
```

### This System

```text
Query
 ↓
Query Reformulation
 ↓
Vector Retrieval
 ↓
Similarity Filtering
 ↓
 ┌────────────────────────┐
 │ Relevant Local Context?│
 └────────────┬───────────┘
              │
        ┌─────┴─────┐
       YES           NO
        │             │
        ▼             ▼
   Local Context   Web Search
        │             │
        └──────┬──────┘
               ▼
        Context Aggregation
               ↓
        Gemini Reasoning
               ↓
       Grounded Response
               ↓
        Source Attribution
```

---

# 📊 Engineering Concepts Demonstrated

This project demonstrates practical experience with:

- Retrieval-Augmented Generation (RAG)
- Agentic AI workflows
- Natural Language Processing
- Query reformulation
- Semantic search
- Vector databases
- Embeddings
- Similarity search
- Document processing
- Context management
- LLM-based reasoning
- Web search integration
- Source attribution
- Conversational AI
- AI application development

---

# 🧪 Example Use Cases

### 📚 Research Assistant

Upload research papers and ask questions about their contents.

### 📑 Document Q&A

Upload organizational documents and retrieve context-aware answers.

### 🌐 Knowledge Exploration

Combine private document knowledge with external web information.

### 🧠 AI Research Workflow

Use query reformulation and semantic retrieval to improve information discovery.

### 💬 Conversational Knowledge Base

Maintain a conversation while grounding responses in indexed documents.

---

# 🔐 Security Notes

API keys should **never be committed to GitHub**.

Do not place credentials directly inside source code.

Recommended approach:

```text
API Keys
   ↓
Environment Variables / Secure Configuration
   ↓
Application
```

Make sure sensitive files are included in `.gitignore`.

Example:

```gitignore
.env
__pycache__/
*.pyc
.venv/
venv/
```

---

# 📸 Screenshots

> Add screenshots of your working application here.

Recommended screenshots:

### 🖥️ Main Interface

```text
![Application Interface](screenshots/main-interface.png)
```

### 📄 Document Upload

```text
![Document Upload](screenshots/document-upload.png)
```

### 💬 RAG Conversation

```text
![RAG Response](screenshots/rag-response.png)
```

### 🔎 Retrieved Sources

```text
![Retrieved Sources](screenshots/sources.png)
```

**Tip:** Screenshots make a GitHub README significantly more compelling to recruiters. Add 2–4 high-quality screenshots after you verify the actual UI.

---

# 🛣️ Roadmap

Potential future improvements include:

- [ ] Add automated RAG evaluation
- [ ] Add retrieval precision/recall evaluation
- [ ] Add answer faithfulness evaluation
- [ ] Add document-level metadata filtering
- [ ] Add advanced reranking
- [ ] Add persistent conversation memory
- [ ] Add authentication
- [ ] Add API endpoint using FastAPI
- [ ] Add Docker deployment
- [ ] Add automated testing
- [ ] Add observability and logging
- [ ] Add cloud deployment
- [ ] Add performance benchmarking

---

# 📈 Future Architecture

The long-term goal is to evolve the application toward a production-oriented AI system:

```text
                 ┌──────────────────┐
                 │   User / Client  │
                 └────────┬─────────┘
                          ↓
                 ┌──────────────────┐
                 │   FastAPI API    │
                 └────────┬─────────┘
                          ↓
                 ┌──────────────────┐
                 │ Agent Orchestrator│
                 └────────┬─────────┘
                          ↓
            ┌─────────────┴─────────────┐
            ↓                           ↓
      Vector Retrieval             Web Search
            ↓                           ↓
            └─────────────┬─────────────┘
                          ↓
                   Context Reranking
                          ↓
                   LLM Generation
                          ↓
                   Evaluation Layer
                          ↓
                  Grounded Response
```

---

# 🎯 Learning Outcomes

Through this project, the following concepts are explored:

### Artificial Intelligence
- Agent-based workflows
- LLM reasoning
- Generative AI

### Machine Learning
- Embeddings
- Vector representations
- Similarity-based retrieval

### Natural Language Processing
- Query reformulation
- Semantic retrieval
- Context processing

### AI Engineering
- API integration
- Vector database integration
- Application orchestration
- Interactive AI interfaces

---

# 💡 Key Takeaway

> **The objective is not simply to connect an LLM to documents.**

The project explores how an AI system can **reason about a user's information need, improve the query, retrieve relevant context, supplement missing information through web search, and produce a source-aware response.**

---

# 🤝 Contributions

Contributions, ideas, and improvements are welcome.

If you find an issue or have an idea for improving the retrieval pipeline, feel free to open an issue or submit a pull request.

---

# ⭐ Support

If you find this project useful or interesting, consider giving the repository a ⭐.

It helps others discover the project and motivates further development.

---

# 👨‍💻 Author

**Aditya Patil**

🎓 MS Artificial Intelligence — Worcester Polytechnic Institute

🔬 Interests:

`Artificial Intelligence` • `Machine Learning` • `Generative AI` • `NLP` • `Deep Learning` • `Data Science` • `Information Retrieval`

🔗 GitHub: `AdityaPatil7900`

---

## 📌 Project Keywords

```text
Artificial Intelligence
Machine Learning
Generative AI
Large Language Models
LLM
RAG
Agentic RAG
Retrieval-Augmented Generation
NLP
Natural Language Processing
Information Retrieval
Semantic Search
Vector Database
Qdrant
Gemini
Gemini Flash Thinking
Embeddings
Query Rewriting
Query Reformulation
Agno
Exa AI
Streamlit
Python
Conversational AI
Document Intelligence
AI Agents
```

---

<p align="center">

### 🚀 Building toward more reliable, intelligent, and context-aware AI systems.

</p>
