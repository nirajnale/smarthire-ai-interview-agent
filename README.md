# SmartHire AI Interview Agent

> A modular Python-based AI interview evaluation system that conducts technical mock interviews through a command-line interface, evaluates candidate responses using a locally hosted Llama 3 model via Ollama, and generates detailed interview reports.

---

# Overview

SmartHire AI Interview Agent is a modular Python application designed to simulate technical interviews and automate answer evaluation using a locally deployed Large Language Model (LLM).

Instead of relying on external AI APIs, the application communicates with a locally running Ollama instance hosting Llama 3, enabling offline inference while demonstrating prompt engineering, modular software design, AI integration, and automated report generation.

The project focuses on software engineering principles including separation of concerns, reusable modules, configurable workflows, and clean application organization.

---

# Problem Statement

Preparing for technical interviews often requires consistent feedback that is difficult to obtain without an interviewer.

This project demonstrates how an AI-assisted evaluation workflow can automate interview assessment by:

- Asking technical interview questions
- Sending responses to an LLM
- Receiving structured evaluations
- Extracting interview scores
- Tracking interview history
- Generating detailed interview reports

---

# Objectives

- Demonstrate LLM integration using Ollama
- Apply prompt engineering for structured evaluations
- Build a modular Python application
- Automate interview assessment
- Generate reusable interview reports
- Showcase clean software organization

---

# Features

- Technical mock interviews
- Topic-wise interview mode
- Full interview mode
- Llama 3 evaluation through Ollama
- Prompt-based answer assessment
- Automatic score extraction
- Interview history tracking
- Overall performance calculation
- Report generation
- Local execution without cloud APIs

---

# High-Level Architecture

```
+-------------------+
|      User         |
+---------+---------+
          |
          v
+-------------------+
|     main.py       |
| CLI Application   |
+---------+---------+
          |
          v
+----------------------------+
| MockInterviewAgent         |
| interview_agent.py         |
+---------+------------------+
          |
          v
+----------------------------+
| Prompt Construction        |
+---------+------------------+
          |
          v
+----------------------------+
| llm_engine.py              |
| Ollama REST API Client     |
+---------+------------------+
          |
          v
+----------------------------+
| Local Llama 3 Model        |
+---------+------------------+
          |
          v
Evaluation Response
          |
          v
+----------------------------+
| Score Extraction           |
| Interview History          |
| Report Generation          |
+---------+------------------+
          |
          v
reports/
```

---

# System Workflow

1. User starts interview.
2. Candidate selects interview mode.
3. Questions are loaded from the question bank.
4. Candidate submits an answer.
5. A structured evaluation prompt is generated.
6. Prompt is sent to Ollama.
7. Llama 3 returns structured feedback.
8. Score is extracted.
9. Interview history is updated.
10. Final report is generated and saved.

---

# Application Modules

## main.py

Application entry point.

Responsible for:

- CLI interaction
- Menu handling
- Interview flow
- User input
- Session orchestration

---

## interview_agent.py

Core business logic.

Responsibilities:

- Prompt construction
- LLM evaluation
- Score extraction
- History management
- Performance aggregation

---

## llm_engine.py

Dedicated LLM communication layer.

Responsibilities:

- HTTP communication
- Ollama integration
- Response handling
- Connection error handling

Separating the LLM client from interview logic improves maintainability and allows the inference backend to be replaced independently.

---

## questions.py

Static question repository.

Provides topic-wise interview questions independent of application logic.

---

## report_generator.py

Responsible for:

- Report formatting
- Report persistence
- Timestamp generation
- Reports directory management

---

# AI Integration

The application integrates with a locally hosted Llama 3 model using the Ollama REST API.

Workflow:

Candidate Answer

↓

Structured Prompt

↓

HTTP Request

↓

Ollama

↓

Llama 3

↓

Structured Evaluation

↓

Score Extraction

↓

Report Generation

The prompt requests a consistent response format containing:

- Score
- Evaluation
- Missing points
- Improved answer
- Interview suggestion

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
├── reports/
└── README.md
```

---

# Technologies Used

- Python
- Ollama
- Llama 3
- Requests
- File I/O
- Modular Programming

---

# Engineering Concepts Demonstrated

- Modular architecture
- Separation of concerns
- Prompt engineering
- AI integration
- HTTP client implementation
- CLI application design
- File management
- Basic exception handling
- Report generation
- State management through interview history

---

# Design Decisions

### Dedicated LLM Layer

Encapsulating model communication inside `llm_engine.py` isolates AI integration from business logic.

### Business Logic Separation

Interview orchestration resides inside `MockInterviewAgent`, keeping UI logic separate.

### Static Question Repository

Question management is isolated from application flow.

### Independent Report Module

Report generation is decoupled from interview execution.

---

# Screenshots

(Add screenshots)

- Home screen
- Interview session
- LLM evaluation
- Generated report

---

# Installation

```bash
git clone <repository-url>

cd smarthire-ai-interview-agent
```

Install dependencies

```bash
pip install requests
```

Install Ollama

```bash
ollama pull llama3
```

Start Ollama

```bash
ollama serve
```

Run

```bash
python main.py
```

---

# Configuration

Current configuration includes:

- Local Ollama endpoint
- Llama 3 model
- Static question bank

---

# Future Improvements

- Web frontend
- REST API backend
- Database persistence
- User authentication
- Resume parsing
- Adaptive questioning
- Conversation memory
- Multiple interview domains
- Admin dashboard
- Analytics
- Docker support
- Automated testing

---

# License

MIT License
