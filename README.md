# Deep Learning — Course Implementations & Labs

A personal repository of hands-on implementations, notes, and labs from advanced AI/ML courses offered by [DeepLearning.AI](https://www.deeplearning.ai/) and [LangChain Academy](https://academy.langchain.com/). This repository tracks step-by-step reconstructions and experimental work in building agentic systems, Retrieval-Augmented Generation (RAG) pipelines, knowledge graphs, and fine-tuning configurations.

---

## 📂 Repository Structure

```text
06_deep_learning/
├── 00-short-courses/                      # DeepLearning.AI short course implementations
│   ├── 00-llm-chat-with-your-data/
│   ├── 01-preprocessing-unstructured-data-for-llm-application/
│   ├── 02_vector-databases-from-embeddings-to-applications/
│   ├── 03-knowledge-graphs-for-rag/
│   ├── 04-finetuning-large-language-models/
│   └── 05-pydantic-for-LLM-workflows/
└── 01-langchain-academy-langGraph/        # LangChain Academy - LangGraph specialization
    ├── module-0/ to module-6/             # Reference materials & local studio configurations
    └── local-notebooks/                   # Custom labs and self-built notebooks
```

---

## 📚 DeepLearning.AI Short Courses

### 00 — LLM Chat with Your Data
* **Course:** [LangChain: Chat with Your Data](https://www.deeplearning.ai/short-courses/langchain-chat-with-your-data/)
* **Focus:** Build a RAG (Retrieval-Augmented Generation) pipeline using LangChain to enable conversational Q&A over custom document collections.
* **Notebooks:** Document loaders, splitting, vector stores & embeddings, retrieval strategies, and conversational retrieval chains.

### 01 — Preprocessing Unstructured Data for LLM Applications
* **Course:** [Preprocessing Unstructured Data for LLM Applications](https://www.deeplearning.ai/short-courses/preprocessing-unstructured-data-for-llm-applications/)
* **Focus:** Extracting, cleaning, and preparing raw/unstructured documents (PDFs, images, HTML) for LLM consumption using OCR and chunking strategies.
* **Notebooks:** PDF & image parsing, table extraction, metadata enrichment, content normalization, and RAG integration.

### 02 — Vector Databases: From Embeddings to Applications
* **Course:** [Vector Databases: From Embeddings to Applications](https://www.deeplearning.ai/short-courses/vector-databases-from-embeddings-to-applications/)
* **Focus:** Generating embeddings and querying vector databases with approximate nearest-neighbor (ANN) algorithms.
* **Notebooks:** Generating vector representations, indexing, and evaluating similarity search.

### 03 — Knowledge Graphs for RAG
* **Course:** [Knowledge Graphs for RAG](https://www.deeplearning.ai/short-courses/knowledge-graphs-rag/)
* **Focus:** Building graph-based RAG architectures using Neo4j and LangChain to retrieve structured entities and relational contexts.
* **Notebooks:** Construction of knowledge graphs from text, Cypher query generation, and hybrid search pipelines.

### 04 — Fine-Tuning Large Language Models
* **Course:** [Fine-Tuning Large Language Models](https://www.deeplearning.ai/short-courses/finetuning-large-language-models/)
* **Focus:** Data preparation, instruction tuning, model training loops, and evaluation criteria for tuning open-source models.
* **Notebooks:**
  * `00_where_finetuning_fit.ipynb`: Analyzing fine-tuning vs. prompt engineering.
  * `01_instruction_finetuning.ipynb`: Formatting prompt/response datasets.
  * `02_data_preparation.ipynb`: Tokenization and preprocessing data.
  * `03_training.ipynb`: Model training execution.
  * `04_evaluation.ipynb`: Benchmarking tuned vs. base models.

### 05 — Pydantic for LLM Workflows
* **Course:** [Pydantic for LLM Workflows](https://www.deeplearning.ai/short-courses/pydantic-for-llm-workflows/)
* **Focus:** Defining reliable JSON schemas, structured outputs, validation rules, and error recovery/retry mechanisms for LLM tool calling.
* **Notebooks:**
  * `00_pydantic_basics.ipynb`: Core Pydantic concepts (Fields, Types, Validation).
  * `01_prompting_structure_retry.ipynb`: Self-correction loops on parsing failures.
  * `02_pydantic_for_structured_llm_output.ipynb`: Parsing structured response objects.
  * `03_pydantic_tool_calling.ipynb`: Constructing schemas for dynamic tool calls.

---

## ⚡ Specialized Programs

### LangChain Academy — Introduction to LangGraph
* **Source:** [Introduction to LangGraph](https://academy.langchain.com/courses/intro-to-langgraph)
* **Directory:** [`01-langchain-academy-langGraph/`](file:///home/harry/Desktop/prcx_01/xx_github/06_deep_learning/01-langchain-academy-langGraph)
* **Goal:** Understand stateful, multi-agent cognitive architectures. Includes the official reference notebooks (Modules 0–6) alongside personal experiments and implementations located in the `local-notebooks/` workspace.
* **Topics Covered:** State Reducers, Thread Management, Persistent DB Checkpointing, Breakpoints (Human-in-the-Loop), Map-Reduce flows, Sub-graphs, and local LangGraph Studio hosting.

---

## 🛠️ Technology Stack

| Tool / Library | Category | Purpose |
|---|---|---|
| **Python 3.12+** | Language | Core runtime |
| **uv** | Package Manager | Fast dependency resolution & virtual environment management |
| **LangChain** | Framework | LLM orchestration and agent integrations |
| **LangGraph** | Framework | Stateful, multi-agent orchestrator |
| **Pydantic** | Validation | Data parsing and validation schemas |
| **Neo4j** | Database | Graph database for Knowledge Graphs |
| **ChromaDB** | Database | Local vector store for document indexing |
| **OpenAI / Lamini** | API / Model | LLM endpoints and embedding generators |
| **LangSmith** | Observability | Tracing and debugging agent runs |

---

## 🚀 Getting Started

### Prerequisites
- Python 3.12 or higher.
- [`uv`](https://docs.astral.sh/uv/) (highly recommended) or `pip`.

### Setup
Every project directory contains its own virtual environment settings:
```bash
# Navigate to a specific short course
cd 00-short-courses/03-knowledge-graphs-for-rag

# Or navigate to the LangGraph workspace
cd 01-langchain-academy-langGraph

# Sync dependencies using uv
uv sync

# Start Jupyter Notebook
uv run jupyter notebook
```

*For more details on environment variables and LangGraph Studio configuration, refer to the respective directories.*
