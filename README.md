# SmartHire AI Interview Agent

> A modular Python-based AI interview evaluation system that simulates technical mock interviews using a locally hosted **Llama 3 Large Language Model** through **Ollama**, providing intelligent answer evaluation, structured feedback, interview history tracking, and automated report generation.

---

## Overview

SmartHire AI Interview Agent is a command-line application designed to automate technical interview practice using Generative AI.

The application conducts mock interviews by presenting technical questions, collecting candidate responses, evaluating answers through a locally running Llama 3 model, extracting interview scores, maintaining interview history, and generating a detailed interview report.

Rather than functioning as a simple chatbot, the project demonstrates how Large Language Models can be integrated into a modular software application to automate an interview evaluation workflow while maintaining clean software organization and separation of responsibilities.

The project emphasizes practical software engineering concepts such as modular architecture, prompt engineering, AI integration, reusable components, and report generation.

---

# Problem Statement

Preparing for technical interviews often requires experienced interviewers who can provide timely and structured feedback.

This project explores how a locally deployed Large Language Model can automate parts of the interview process by:

- asking technical interview questions
- evaluating candidate responses
- providing constructive feedback
- assigning interview scores
- maintaining interview history
- generating performance reports

The project serves as both a software engineering exercise and a practical introduction to AI-assisted interview automation.

---

# Objectives

The primary objectives of the project are to demonstrate:

- Modular Python application development
- Large Language Model (LLM) integration
- AI Agent workflow concepts
- Prompt engineering
- Interview automation
- Automated answer evaluation
- Interview history management
- Report generation
- Clean software engineering practices

---

# Features

- Full technical interview mode
- Topic-wise interview mode
- Question bank organized by domain
- AI-powered answer evaluation using Llama 3
- Prompt-based response analysis
- Automatic score extraction
- Interview history tracking
- Performance summary generation
- Timestamped report generation
- Local execution using Ollama (no cloud AI dependency)

---

# High-Level Architecture

```text
                    Candidate
                        │
                        ▼
                 Command Line UI
                    (main.py)
                        │
                        ▼
            MockInterviewAgent
             (Business Logic)
                        │
      ┌─────────────────┼──────────────────┐
      │                 │                  │
      ▼                 ▼                  ▼
Prompt Builder   Interview History   Score Extraction
      │
      ▼
      llm_engine.py
      │
HTTP POST Request
      │
      ▼
 Ollama REST API
      │
      ▼
 Local Llama 3
      │
      ▼
Structured Evaluation
      │
      ▼
report_generator.py
      │
      ▼
 Interview Report (.txt)
```

---

# System Workflow

```
Student starts interview
        │
        ▼
main.py initializes application
        │
        ▼
Student selects interview mode
        │
        ▼
Questions loaded from questions.py
        │
        ▼
Candidate submits answer
        │
        ▼
MockInterviewAgent constructs prompt
        │
        ▼
Prompt sent to Ollama
        │
        ▼
Llama 3 evaluates answer
        │
        ▼
Structured feedback returned
        │
        ▼
Score extracted
        │
        ▼
Interview history updated
        │
        ▼
Final report generated
        │
        ▼
Report saved locally
```

---

# AI Evaluation Workflow

The AI evaluation process consists of the following stages:

1. Candidate answers a technical interview question.
2. The application creates a structured evaluation prompt.
3. The prompt is sent to the locally running Llama 3 model through Ollama.
4. The model returns structured feedback including:

- Score
- Evaluation
- Missing Points
- Improved Answer
- Interview Suggestions

5. The application extracts the interview score.
6. Interview history is updated.
7. The final interview report is generated.

---

# AI Agent Concepts Demonstrated

Although lightweight, the project illustrates the core building blocks of an AI Agent.

| AI Agent Component | Implementation |
|-------------------|----------------|
| User Input | Candidate interview response |
| Goal | Evaluate technical interview answers |
| LLM Brain | Llama 3 |
| Tool | Ollama REST API |
| Memory | Interview history (`self.history`) |
| Decision | Structured evaluation & scoring |
| Output | Interview report |

---

# Application Modules

## main.py

Application entry point.

Responsibilities:

- Display application menu
- Accept candidate information
- Start interview sessions
- Coordinate interview workflow
- Save final reports

---

## interview_agent.py

Core business logic.

Responsibilities:

- Prompt construction
- LLM interaction
- Answer evaluation
- Score extraction
- Interview history management
- Overall score calculation
- Final report preparation

This module encapsulates the application's interview orchestration logic while keeping AI communication separate.

---

## llm_engine.py

Dedicated AI communication layer.

Responsibilities:

- Build Ollama requests
- Send HTTP requests
- Receive LLM responses
- Handle connection failures
- Isolate LLM communication

Separating this functionality improves maintainability and allows future replacement of the inference backend without affecting interview logic.

---

## questions.py

Question repository.

Responsibilities:

- Store technical interview questions
- Organize questions by topic
- Provide an extensible question bank

Current topics include:

- Python
- OOP
- Machine Learning
- Deep Learning
- Transformers
- LLMs
- RAG
- AI Agents

---

## report_generator.py

Responsible for report persistence.

Responsibilities:

- Create reports directory
- Generate timestamped filenames
- Save interview reports
- Manage report output

---

# Project Structure

```
smarthire-ai-interview-agent/
│
├── main.py
├── interview_agent.py
├── llm_engine.py
├── questions.py
├── report_generator.py
│
├── reports/
│
└── README.md
```

---

# Technologies Used

### Programming Language

- Python

### AI

- Ollama
- Llama 3
- Prompt Engineering

### Libraries

- requests
- os
- datetime

### Concepts

- AI Agents
- Generative AI
- Modular Programming
- File Handling
- HTTP Communication

---

# Engineering Concepts Demonstrated

- Modular software architecture
- Separation of concerns
- Prompt engineering
- Local LLM integration
- HTTP client implementation
- AI-assisted workflow automation
- CLI application design
- Interview history management
- Report generation
- Basic exception handling
- Reusable components

---

# Design Decisions

### Modular Architecture

Each major responsibility is isolated into its own module, reducing coupling and improving maintainability.

### Dedicated LLM Layer

AI communication is encapsulated inside `llm_engine.py`, preventing interview logic from depending directly on HTTP requests.

### Structured Prompt Engineering

The application requests responses in a consistent format, simplifying score extraction and report generation.

### Local LLM Deployment

Using Ollama enables offline execution while avoiding dependency on third-party AI services.

### Extensible Question Bank

Interview questions are maintained separately from application logic, making it straightforward to add new domains.

---

# Screenshots

Add screenshots for:

- Main Menu
- Topic Selection
- Interview Session
- AI Evaluation Output
- Generated Interview Report

---

# Installation

Clone the repository

```bash
git clone https://github.com/yourusername/smarthire-ai-interview-agent.git

cd smarthire-ai-interview-agent
```

Install dependencies

```bash
pip install requests
```

Install Llama 3

```bash
ollama pull llama3
```

Start Ollama

```bash
ollama serve
```

Run the application

```bash
python main.py
```

---

# Configuration

The application currently uses:

- Local Ollama endpoint (`http://localhost:11434`)
- Llama 3 model
- Static question repository
- Local report storage

---

# Future Improvements

Potential enhancements include:

- Web interface
- REST API backend
- Persistent database
- User authentication
- Adaptive interview difficulty
- Resume-based question generation
- Multi-user support
- Conversation memory improvements
- Structured JSON LLM responses
- Docker containerization
- Automated testing
- CI/CD pipeline

---

# License

This project is licensed under the MIT License.
