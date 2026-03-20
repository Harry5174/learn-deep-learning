# Deep Learning — Course Implementations

A personal repository of hands-on implementations and notes from courses offered on [DeepLearning.AI](https://www.deeplearning.ai/). The focus is on practical, notebook-driven exploration of modern AI/ML techniques — particularly in the areas of large language models, retrieval-augmented generation, and vector-based search.

---

## Repository Structure

```
06_deep_learning/
└── 00_short_courses/               # DeepLearning.AI short course implementations
    ├── 00_llm_chat_with_your_data/
    ├── 01_preprocessing_unstructured_data_for_llm_application/
    ├── 02_vector_databases_from_embeddings_to_applications/
    └── 03_knowledge_graphs_for_rag/
```

---

## Short Courses

### 00 — LLM Chat with Your Data

**Course:** [LangChain: Chat with Your Data](https://www.deeplearning.ai/short-courses/langchain-chat-with-your-data/)

Learn how to build a RAG (Retrieval-Augmented Generation) pipeline using LangChain to enable conversational Q&A over custom document collections.

| Lecture | Topic |
|---------|-------|
| lecture_01 | Document Loaders |
| lecture_02 | Document Splitting |
| lecture_03 | Vector Stores and Embeddings |
| lecture_04 | Retrieval |
| lecture_05 | Question Answering |
| lecture_06 | Chat |
| lecture_07 | Conversational Retrieval Chain |

**Key Concepts:** Document loading, text splitting, embedding, vector stores, retrieval chains, conversational memory.

---

### 01 — Preprocessing Unstructured Data for LLM Applications

**Course:** [Preprocessing Unstructured Data for LLM Applications](https://www.deeplearning.ai/short-courses/preprocessing-unstructured-data-for-llm-applications/)

Covers techniques to extract, clean, and prepare unstructured documents (PDFs, images, HTML) for use in LLM pipelines.

| Notebook | Topic |
|----------|-------|
| `preprocessing_pdfs_and_images.ipynb` | Extracting text from PDFs and image-based documents |
| `extracting_tables.ipynb` | Table detection and extraction |
| `normalizing_content.ipynb` | Content normalization and cleaning |
| `meta_data_extraction_and_chunking.ipynb` | Metadata extraction and intelligent chunking |
| `rag.ipynb` | End-to-end RAG pipeline with preprocessed data |

**Key Concepts:** Unstructured data parsing, OCR, table extraction, chunking strategies, metadata-aware retrieval.

**Dependencies:** See `requirements.txt`

---

### 02 — Vector Databases: From Embeddings to Applications

**Course:** [Vector Databases: from Embeddings to Applications](https://www.deeplearning.ai/short-courses/vector-databases-from-embeddings-to-applications/)

Explores how vector embeddings are created, stored, and queried in vector databases, including approximate nearest-neighbor search algorithms.

| Notebook | Topic |
|----------|-------|
| `l1_obtaining_vector_representation_of_data.ipynb` | Generating vector embeddings from raw data |
| `l3_approximating_nearest_neighbors.ipynb` | Approximate nearest-neighbor search (ANN algorithms) |

**Key Concepts:** Vector embeddings, similarity search, approximate nearest neighbors (ANN), HNSW, product quantization.

**Dependencies:** `numpy`, `matplotlib`, `networkx`

---

### 03 — Knowledge Graphs for RAG

**Course:** [Knowledge Graphs for RAG](https://www.deeplearning.ai/short-courses/knowledge-graphs-rag/)

Explores building and querying knowledge graphs to enhance retrieval-augmented generation. Uses Neo4j as the graph database backend integrated with LangChain.

| Notebook | Topic |
|----------|-------|
| `preparing_text_for_rag.ipynb` | Structuring and chunking text for graph-based retrieval |
| `constructing_kg_from_text_document.ipynb` | Extracting entities and relationships to build a knowledge graph |
| `querying_knowldge_graphs.ipynb` | Cypher-based querying and hybrid retrieval with RAG |

**Key Concepts:** Knowledge graph construction, entity and relation extraction, Cypher queries, Neo4j, graph-enhanced RAG, LangChain integration.

**Dependencies:** `neo4j`, `langchain-community`, `python-dotenv`

---

## Technology Stack

| Tool / Library | Purpose |
|----------------|---------|
| Python 3.13+ | Primary language |
| Jupyter Notebooks | Interactive experimentation |
| LangChain | LLM orchestration and RAG pipelines |
| OpenAI API | Embeddings and LLM completions |
| ChromaDB | Local vector store |
| Neo4j | Graph database for knowledge graphs |
| uv | Dependency and virtual environment management |

---

## Getting Started

Each sub-course is self-contained. Navigate into the relevant directory and follow the steps below.

### Prerequisites

- Python 3.13 or higher
- [`uv`](https://docs.astral.sh/uv/) (recommended) or `pip`
- API keys where required (see `.env.example` or `.env` in each course directory)

### Setup (with uv)

```bash
cd 00_short_courses/<course_directory>
uv sync
uv run jupyter notebook
```

### Setup (with pip)

```bash
cd 00_short_courses/<course_directory>
pip install -r requirements.txt   # if requirements.txt is present
jupyter notebook
```

### Environment Variables

Courses that require API keys use a `.env` file in their directory. Copy and populate it before running the notebooks:

```bash
cp .env.example .env
# then fill in your keys
```

> **Note:** `.env` files are excluded from version control via `.gitignore`.

---

## Status

This repository is actively maintained and will grow as more courses are completed. New short courses and potentially full specialization implementations will be added over time.

---

## Source

All courses are from [DeepLearning.AI](https://www.deeplearning.ai/short-courses/) — a platform offering short, practical AI courses developed in collaboration with leading AI companies and researchers.
