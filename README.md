## Installation

1. Clone the repository

git clone https://github.com/yourusername/rag-fastapi-api.git

2. Create a virtual environment

python -m venv venv

3. Activate the environment

Windows:
venv\Scripts\activate

Mac/Linux:
source venv/bin/activate

4. Install dependencies

pip install -r requirements.txt

5. Run the API

uvicorn main:app --reload

# Build a RAG API with FastAPI

**Project Link:** [View Project](http://learn.nextwork.org/projects/ai-devops-api)

**Author:** Josh  
**Email:** joshuafurt@gmail.com

---
## Tech Stack

- Python
- FastAPI
- ChromaDB
- Ollama
- Qwen2.5
- Nomic Embed Text
---

## Introducing Today's Project!

In this project, I'm going to build a RAG pipeline using a FAST API and ChromaDB This will help me understand how RAG works as I'm interested in AI.

### Key tools and concepts

The key tools I used include chromaDB, Fast API, Ollama models. Key concepts I learnt include retrieving embedings.
embeddings are basically vectors, and store similar vectors together in an environment.

### Challenges and wins

This project took me approximately 3 daysThe most challenging part was understanding the concept of RAG.

---

## Performing RAG Manually

In this step, I'm going to learn wahat RAG is with a manual demo, as well as create a venv to install all my python dependencies. RAG stands for Retrieval Augmented generation.

![Image](http://learn.nextwork.org/determined_cyan_radiant_beaver/uploads/ai-devops-api_v3j7x5b9)

### Understanding the three parts of RAG

I performed RAG manually by retrieving the prompt and changing it up so essentially augmenting it, and then generated it with the Ollama model. The three parts are Retrieval, Augmentation and Generation.

## Project Architecture

User Question
     ↓
FastAPI Endpoint (/ask)
     ↓
ChromaDB Vector Search
     ↓
Retrieve Relevant Chunks
     ↓
Augment Prompt
     ↓
Ollama LLM Generation
     ↓
Response

### Comparing the two AI models

The key difference I noticed is that nomic-embed-text converts the prompts to embedded texts for search. qwen2.5:0.5b is for generating responses

---

## Building a Personal Knowledge Base

In this step, I'm going to write a personal profile, Embeddings are vectors in a list, where if they have similar meaning are closer

![Image](http://learn.nextwork.org/determined_cyan_radiant_beaver/uploads/ai-devops-api_g3h7m2r5)

### Creating the profile document

I included information about my interests, my career goals, my experience.

### How semantic search finds relevant chunks

When I ask a question, ChromaDB finds the most relvevant vectors and embeddings from the prompt. so it tries to find the closest meaning from the prompt and then. this is semantic search.

---

## Creating the RAG API with FastAPI

In this step, I'm going to build an API that accepts a question and generates an answer I'll test it using Swagger UI.

![Image](http://learn.nextwork.org/determined_cyan_radiant_beaver/uploads/ai-devops-api_j5m1r8t2)

### How the /ask endpoint works

When a question comes in, my endpoint finds the two most relevant chunks from chromaDB and then it combines and augments the original prompt then, the prompt is sent to Ollama to generate an answer.

### Testing with Swagger UI

I tested my API by asking about my interests The AI answered with all my interests I provided in chroma DB The context used was:
"My career goal is to become a AI engineer.\nI'm especially interested in e.g., automation, infrastructure as code, machine learning.",
    "My name is Joshua.\nI'm currently learning about cloud computing, AI, and DevOps."
  ]

---

## Extending to a Multi-User AI Directory

In this project extension, I'm adding multi-user support because real world RAG systems feature mutliple users. Multi-tenancy means more than one user can ask questions and data is stored according to the client on chromadb.

![Image](http://learn.nextwork.org/determined_cyan_radiant_beaver/uploads/ai-devops-api_d5g9k3n7)

### Adding the POST /documents endpoint

In this project extension, I added a POST endpoint that allows to add users and and their description.

![Image](http://learn.nextwork.org/determined_cyan_radiant_beaver/uploads/ai-devops-api_r8t2w6y1)

### Verifying multi-user filtering

In this project extension, I tested multi-user queries by using a where parameter which checked for the user_name and only returns the data which are from its name.

---

## Wrapping Up

I did this project today to learn how to use RAG with AI models. Another skill I want to learn is to optimize this program with some better program architecture.

---

---

