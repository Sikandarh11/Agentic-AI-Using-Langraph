# Agentic AI Using LangGraph

A hands-on learning repository for building agentic AI workflows with [LangGraph](https://github.com/langchain-ai/langgraph). This repo will grow over time to include comprehensive notes, examples, and mini-projects covering LangGraph concepts from the ground up.

---

## 📚 Table of Contents

- [About](#about)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Notebooks](#notebooks)
  - [0 – Test Installation](#0--test-installation)
  - [1 – Simple LLM Workflow](#1--simple-llm-workflow)
  - [2 – Prompt Chaining](#2--prompt-chaining)
- [Future Notes](#future-notes)
- [Contributing](#contributing)

---

## About

LangGraph is a library built on top of [LangChain](https://github.com/langchain-ai/langchain) that lets you model your AI application as a **stateful graph**. Each node in the graph is a Python function that reads from and writes to a shared state object, and edges define the order in which those functions are called.

This repository contains progressive examples that demonstrate how to:

- Define typed state with `TypedDict`
- Build and compile `StateGraph` workflows
- Integrate Large Language Models (LLMs) as graph nodes
- Chain multiple LLM calls together (prompt chaining)

---

## Prerequisites

- Python 3.9 or higher
- An [OpenAI API key](https://platform.openai.com/api-keys) (required for LLM notebooks)

---

## Installation

1. **Clone the repo**

   ```bash
   git clone https://github.com/Sikandarh11/Agentic-AI-Using-Langraph.git
   cd Agentic-AI-Using-Langraph
   ```

2. **Install dependencies**

   ```bash
   pip install -r requirements.txt
   ```

3. **Set your OpenAI API key**

   Create a `.env` file in the project root:

   ```env
   OPENAI_API_KEY=your_openai_api_key_here
   ```

4. **Launch Jupyter**

   ```bash
   jupyter notebook
   ```

---

## Notebooks

### 0 – Test Installation

**File:** `0_test_installation.ipynb`

Verifies that LangGraph is installed correctly by building a simple **BMI calculator** graph.

- **State:** `weight_kg`, `height_m`, `bmi`, `category`
- **Nodes:**
  - `calculate_bmi` – computes BMI from weight and height
  - `label_bmi` – classifies the result (Underweight / Normal weight / Overweight / Obese)
- **Concepts covered:** `StateGraph`, `TypedDict` state, `START` / `END` edges, graph compilation, and Mermaid graph visualisation

---

### 1 – Simple LLM Workflow

**File:** `simple_llm_workflow.ipynb`

Demonstrates the simplest possible LLM-powered graph: a single question-answering node.

- **State:** `question`, `answer`
- **Nodes:**
  - `llm_qa` – sends the question to `ChatOpenAI` and stores the answer in state
- **Concepts covered:** integrating LangChain LLMs as graph nodes, `load_dotenv` for API key management

---

### 2 – Prompt Chaining

**File:** `prompt_chaining.ipynb`

Shows how to **chain multiple LLM calls** by passing outputs from one node as inputs to the next.

- **State:** `title`, `outline`, `content`, `score`
- **Nodes:**
  - `create_outline` – generates a blog outline from a title
  - `create_blog` – writes a full blog post given the outline
  - `evaluate_blog` – scores the finished post
- **Concepts covered:** multi-step LLM pipelines, reading and updating shared state across nodes, sequential edges

---

## Future Notes

This repository will be updated with additional LangGraph concepts and examples, including (but not limited to):

- [ ] Conditional edges and branching logic
- [ ] Cycles and loops in graphs
- [ ] Human-in-the-loop patterns
- [ ] Parallel node execution
- [ ] Persistence and checkpointing
- [ ] Tool-calling agents
- [ ] Multi-agent architectures
- [ ] LangGraph Studio integration

---

## Contributing

Feel free to open an issue or submit a pull request if you spot a bug, have a question, or want to add your own LangGraph examples.

---

> **Author:** [Sikandar Hussain](https://github.com/Sikandarh11)
