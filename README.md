# Wikipedia Knowledge Graph RAG System

[![Python](https://img.shields.io/badge/Python-3.8+-blue?logo=python&logoColor=white)](https://www.python.org/)
[![Neo4j](https://img.shields.io/badge/Neo4j-Latest-008CC1?logo=neo4j&logoColor=white)](https://neo4j.com/)
[![OpenAI](https://img.shields.io/badge/OpenAI-API-412991?logo=openai&logoColor=white)](https://openai.com/)
[![Wikipedia](https://img.shields.io/badge/Wikipedia-API-000000?logo=wikipedia&logoColor=white)](https://www.wikipedia.org/)

An intelligent question-answering system powered by knowledge graphs, combining Neo4j database and Wikipedia data for efficient Retrieval-Augmented Generation (RAG).

## Core Features

- 🔍 Smart Retrieval - Hybrid vector and graph-based search
- 📚 Knowledge Construction - Automated Wikipedia entity relationship extraction
- 🧠 Context Aware - Multi-turn conversation memory
- 🔄 Real-time Updates - Dynamic Wikipedia data synchronization

## Prerequisites

- Python 3.8+
- Neo4j Database
- OpenAI API access

## Environment Variables

Create a `.env` file with:

```env
AURA_INSTANCENAME=your_instance
NEO4J_URI=your_uri
NEO4J_USERNAME=your_username
NEO4J_PASSWORD=your_password
NEO4J_DATABASE=your_database
OPENAI_API_KEY=your_key
OPENAI_ENDPOINT=your_endpoint
```

## Installation

```bash
pip install -r requirements.txt
```

## Usage

```python
python wikipedia_kg_rag.py

```

Example queries:

```python
# Simple query
"How did the Roman empire fall?"

# Query with chat history
"When did he become the first emperor?"
```

## Architecture

```mermaid
graph TD
    A[Wikipedia Data] -->|Extract| B[Data Processor]
    B -->|Store| C[Neo4j Graph]
    B -->|Embed| D[Vector Store]
    E[User Query] -->|Input| F[Query Engine]
    F -->|Search| C
    F -->|Match| D
    C -->|Context| G[Response Generator]
    D -->|Similar Docs| G
    G -->|Generate| H[Final Answer]
```
