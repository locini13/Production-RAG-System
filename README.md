# SmartRAG – Retrieval-Augmented Generation Knowledge Assistant

## Overview

SmartRAG is an AI-powered knowledge assistant built using a Retrieval-Augmented Generation (RAG) architecture. It automatically ingests documents, converts them into vector embeddings, stores them in Pinecone, and enables semantic search to generate accurate, context-aware responses through a Telegram interface.

This project demonstrates modern AI system design by combining workflow automation, vector databases, reranking, and large language models to reduce hallucinations and improve response reliability.

## Architecture

### Ingestion Pipeline

Google Drive → Document Processing → Text Splitting → OpenAI Embeddings → Pinecone Vector Database

### Retrieval Pipeline

Telegram → Semantic Search → Reranking → OpenAI LLM → Context-Aware Response

## Key Features

* Retrieval-Augmented Generation (RAG) for grounded AI responses
* Automated document ingestion from Google Drive
* Semantic vector search powered by Pinecone
* Reranking for improved answer relevance
* Reduced hallucinations through contextual retrieval
* End-to-end automated workflow using n8n
* Real-time conversational interface via Telegram

## Tech Stack

* **n8n** – Workflow automation
* **OpenAI** – Embeddings and language model
* **Pinecone** – Vector database for semantic retrieval
* **Cohere** – Reranking model
* **Telegram API** – Chat interface
* **Google Drive API** – Document source

## Repository Structure

```
smart-rag-assistant/
│
├── workflows/
│   ├── rag.json
│  
│
├── architecture.png
└── README.md
```
## How It Works

### Automated Knowledge Ingestion

When documents are added to Google Drive, the ingestion workflow:

1. Downloads the file
2. Splits text into optimized chunks
3. Generates embeddings
4. Stores vectors in Pinecone

This ensures the knowledge base stays continuously updated.### Intelligent Retrieval

When a user sends a query via Telegram:

1. The query is converted into a vector embedding
2. Pinecone performs semantic similarity search
3. Results are reranked for relevance
4. The LLM generates a grounded response using retrieved context

This pipeline improves factual accuracy and minimizes unsupported answers.

## Setup Instructions

### 1. Import the Workflows

Download the JSON files from the `/workflows` directory and import them into your n8n instance.

### 2. Configure Credentials

Provide your own credentials inside n8n:

* OpenAI API Key
* Pinecone API Key
* Cohere API Key
* Telegram Bot Token
* Google Drive Authentication

### 3. Activate the Workflows

Enable both workflows after configuration:

* Document ingestion workflow
* Telegram assistant workflow

Your AI knowledge assistant will then be ready to use.

## Example Use Cases

* Customer support automation
* Internal knowledge assistants
* FAQ systems
* Documentation search
* AI helpdesks
* Business knowledge retrieval

## Security Note

Credentials and API keys are not included in this repository.
Users must supply their own keys when configuring the workflows.

## Usage Notice

This repository is shared for portfolio and educational viewing purposes only.
No permission is granted to copy, modify, distribute, or use this project commercially without explicit consent from the author.

## Future Improvements

* Hybrid search (keyword + vector)
* Metadata filtering
* Retrieval evaluation pipeline
* Containerized deployment
* Multi-source document ingestion (Notion, Slack, Confluence)
* Streaming responses
* Access control for private knowledge bases

## Author

Developed as a practical implementation of a modern RAG-based AI system, showcasing workflow automation, vector search, and production-style architecture.
