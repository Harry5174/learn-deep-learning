# LangChain Academy — Introduction to LangGraph

A structured workspace for implementing and experimenting with the official **LangChain Academy: Introduction to LangGraph** course. This directory serves as a personal laboratory for exploring multi-agent systems, state management, persistent memory, human-in-the-loop interactions, and deployment architectures.

---

## 📂 Workspace Structure

To balance study materials with hands-on practice, this directory is split into reference materials and personal implementations:

- **`module-0` to `module-6/` (Course Materials):** The original, official course notebooks and local LangGraph Studio configurations (`/studio` subfolders) downloaded from LangChain.
- **`local-notebooks/` (Active Learning & Experiments):** Personal, step-by-step reconstructions and customized notebooks where the actual coding, debugging, and experimentation take place.
  - **`01-module/`:** Simple graphs, routing, basic chains, and foundational LangGraph mechanics.
    - `00_simple_graph.ipynb`: Hand-coded state graph implementation.
    - `01_chain.ipynb`: Custom LLM chain invocation and flow control.
  - **`02-module/`:** (In Progress) State reducers, schemas, and database memory integration.

---

## 🛠️ Course Syllabus

| Module | Core Focus | Key Concepts & Exercises |
|---|---|---|
| **Module 0** | **Setup** | Environment configuration, API key setup, and package verification. |
| **Module 1** | **Build a Graph** | State graphs, nodes, edges, conditional routing, basic agents, memory, and Studio. |
| **Module 2** | **State and Memory** | Custom state schemas, state reducers, thread-based memory, and token trimming/filtering. |
| **Module 3** | **Human-in-the-Loop** | Breakpoints, manual state updates, user input queues, time travel, and streaming. |
| **Module 4** | **Specialized Workflows** | Parallel node execution, Map-Reduce map/reduce architectures, sub-graphs, and agent routers. |
| **Module 5** | **Memory & Cognitive Architecture** | Long-term memory stores, user profiles, collections, and personalized agent behaviors. |
| **Module 6** | **Deployment** | LangGraph Cloud, local API server hosting, containerization, and handling double-texting. |

---

## 🚀 Setup & Installation

This project is managed using [`uv`](https://docs.astral.sh/uv/) for fast, reproducible dependency resolution. Make sure you have Python **3.11, 3.12, or 3.13** installed.

### Option A: Using `uv` (Recommended)

1. Sync dependencies and create a virtual environment:
   ```bash
   uv sync
   ```
2. Activate the environment:
   ```bash
   source .venv/bin/activate
   ```
3. Start the Jupyter server:
   ```bash
   uv run jupyter notebook
   ```

### Option B: Using standard `pip`

1. Create and activate a standard virtual environment:
   ```bash
   python3 -m venv lc-academy-env
   source lc-academy-env/bin/activate
   ```
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Run Jupyter:
   ```bash
   jupyter notebook
   ```

---

## 🔑 Environment Variables

Create a `.env` file in the root of this folder (excluded from Git) and populate it with your credentials:

```ini
# Core LLM provider
OPENAI_API_KEY="your-openai-key"

# Observability and Tracing
LANGSMITH_API_KEY="your-langsmith-key"
LANGSMITH_TRACING_V2="true"
LANGSMITH_PROJECT="langchain-academy"
# LANGSMITH_ENDPOINT="https://eu.api.smith.langchain.com" # Uncomment if using EU instance

# Search Tool (used in Module 4)
TAVILY_API_KEY="your-tavily-key"
```

---

## 🎨 Local LangGraph Studio

LangGraph Studio offers a custom IDE for visualizing, editing, and running state graphs.

### Starting the Studio Server
To run the local Studio server, navigate to the `/studio` directory of the active module and run the LangGraph CLI:

```bash
cd module-1/studio  # Example for Module 1
langgraph dev
```

Your terminal will display access endpoints:
```text
🚀 API: http://127.0.0.1:2024
🎨 Studio UI: https://smith.langchain.com/studio/?baseUrl=http://127.0.0.1:2024
📚 API Docs: http://127.0.0.1:2024/docs
```

Open your browser and navigate to the **Studio UI** link.

### Distributing environment keys to Studio folders
To make sure the local Studio container has access to your credentials, copy your `.env` configuration to the target module's studio folder:

```bash
# Helper loop to copy and configure envs for Modules 1-5
for i in {1..5}; do
  cp module-$i/studio/.env.example module-$i/studio/.env
  echo "OPENAI_API_KEY=\"$OPENAI_API_KEY\"" > module-$i/studio/.env
done
echo "TAVILY_API_KEY=\"$TAVILY_API_KEY\"" >> module-4/studio/.env
```
