# Agentic AI for DevOps 

A simple LangChain agent that uses a local LLM (via [Ollama](https://ollama.com)) to answer Kubernetes and Docker questions by calling real `kubectl` and `docker` commands as tools.

Built as part of the **TrainWithShubham** masterclass.

## Project Overview
This project is an Agentic AI based DevOps assistant built using Python, LangChain, and Ollama.

The main purpose of the project is to allow users to interact with Docker and Kubernetes using natural language commands.

For example, instead of manually running commands like `docker ps` or `kubectl get pods`, the user can simply ask questions in plain English, and the AI agent decides which tool or command should be executed.

The project uses:

* Python for backend logic
* LangChain for agent orchestration
* Ollama as the local LLM
* Docker and Kubernetes commands as tools

The agent dynamically selects tools based on the user query and returns the output.




## What it does

The agent is wired up with two tools:

- `get_pods` — runs `kubectl get pods -A` and returns the output
- `get_docker_containers` — runs `docker ps` and returns the output

You ask a question in natural language; the LLM decides which tool to call and answers based on the live cluster / Docker state.

## Prerequisites

- Python 3.10+
- [Ollama](https://ollama.com) running locally with the `qwen3:8b` model pulled:
  ```bash
  ollama pull qwen3:8b
  ```
- `kubectl` configured against a cluster (for pod queries)
- `docker` running locally (for container queries)

## Setup

```bash
git clone git@github.com:LondheShubham153/agentic-ai-for-devops-masterclass.git
cd agentic-ai-for-devops-masterclass

python3 -m venv venv
source venv/bin/activate

pip install -r requirements.txt
```

## Run

```bash
python agent.py
```

Example prompts:

```
Ask your Kubernetes Agent a Question: > show me all pods
Ask your Kubernetes Agent a Question: > what containers are running on docker?
```

## Project layout

```
.
├── agent.py            # LangChain agent + tools + entry point
├── requirements.txt    # Python dependencies
└── README.md
```


## What I Learned

This project helped me understand:

* AI Agents
* Tool Calling
* LLM Integration
* DevOps Automation
* LangChain Workflow
* Docker and Kubernetes basics
