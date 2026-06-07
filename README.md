# 🎯 SmartHire AI Mock Interview Agent

An AI-powered mock interview system that conducts technical interviews, evaluates candidate responses using a Large Language Model (Llama 3), provides personalized feedback, assigns scores, and generates detailed interview reports.

This project demonstrates practical implementation of AI Agents, Prompt Engineering, LLM Integration, Interview Automation, and Report Generation using Python and Ollama.

---

## 🚀 Features

✅ Conducts technical mock interviews

✅ Supports full interview and topic-wise interview modes

✅ Evaluates answers using Llama 3 through Ollama

✅ Generates personalized feedback and improvement suggestions

✅ Automatically extracts and calculates interview scores

✅ Maintains interview history and performance tracking

✅ Generates detailed interview reports

✅ Fully local execution without external API costs

---

## 🛠️ Tech Stack

- 🐍 Python
- 🧠 Llama 3
- 🦙 Ollama
- 🌐 Requests API
- 📄 Automated Report Generation
- 🤖 AI Agents
- ✨ Prompt Engineering

---

## 📂 Project Structure

```text
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
├── requirements.txt
└── README.md
```

---

## ⚙️ How It Works

```text
Candidate Response
        │
        ▼
Prompt Generation
        │
        ▼
Llama 3 Evaluation
        │
        ▼
Score Extraction
        │
        ▼
Performance Analysis
        │
        ▼
Detailed Feedback
        │
        ▼
Interview Report Generation
```

---

## 🧠 AI Workflow

### 1️⃣ Question Selection

The system selects technical interview questions from predefined domains such as:

- Python
- Object-Oriented Programming
- Machine Learning
- Deep Learning
- Transformers
- LLMs
- RAG
- AI Agents

### 2️⃣ Answer Evaluation

Candidate responses are converted into structured prompts and sent to Llama 3 through Ollama.

The model evaluates:

- Technical accuracy
- Concept clarity
- Missing points
- Improvement suggestions

### 3️⃣ Score Generation

The AI evaluator assigns a score out of 10 and provides detailed reasoning.

### 4️⃣ Report Generation

At the end of the interview, a comprehensive report is generated containing:

- Candidate information
- Question-wise performance
- AI-generated feedback
- Average score
- Improvement recommendations

---

## 📋 Sample Evaluation Output

```text
Score: 8/10

Evaluation:
Good understanding of the concept.

Missing Points:
Could explain practical use cases.

Improved Answer:
Provide real-world examples and deeper technical details.

Interview Suggestion:
Practice explaining concepts with industry applications.
```

---

## 🔧 Installation

### Clone Repository

```bash
git clone https://github.com/yourusername/smarthire-ai-interview-agent.git
cd smarthire-ai-interview-agent
```

### Install Dependencies

```bash
pip install -r requirements.txt
```

### Install Llama 3

```bash
ollama pull llama3
```

### Start Ollama

```bash
ollama serve
```

### Run Project

```bash
python main.py
```

---

## 🎓 Concepts Demonstrated

- AI Agents
- Generative AI
- Prompt Engineering
- Large Language Models (LLMs)
- Ollama Integration
- Local AI Deployment
- Interview Automation
- Report Generation
- API Communication
- Performance Evaluation Systems

---

## 🔮 Future Improvements

- 🎤 Voice-based interviews
- 🌐 Streamlit web interface
- 📊 Performance analytics dashboard
- 📝 Resume-based question generation
- 🎯 Adaptive interview difficulty
- 🗄️ Database integration
- 🤖 Multi-agent interview workflows

---

## 💡 Key Learning Outcomes

Through this project, I gained hands-on experience with:

- Building AI-powered applications using local LLMs
- Designing structured prompts for evaluation tasks
- Creating modular AI agent architectures
- Automating assessment and report generation workflows
- Integrating Python applications with LLM APIs

---

## 👨‍💻 Author

**Niraj Nale**

B.Tech Robotics & Automation  
MIT World Peace University, Pune

📌 Passionate about AI, Machine Learning, Generative AI, and Software Development.

---

## ⭐ If you found this project interesting, consider giving it a star!
