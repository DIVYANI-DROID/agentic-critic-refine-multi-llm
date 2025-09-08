# Multi-LLM Evaluation with Agentic Critic + Refine

This script generates a single challenging question, collects answers from multiple LLMs (OpenAI, Anthropic, Gemini via OpenAI-compat, Groq, and Ollama), **critiques** each answer with a critic agent, then **self-refines** each answer, and finally **judges** (ranks) the original / critiqued / refined responses using a separate judge model.  
Agentic patterns used: **Multi-Agent (compete), Critic, Reflection/Self-Refine, Orchestration, Judge/Referee**.

## Setup
```bash
python3 -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt
cp .env.example .env  # fill keys


Start Ollama locally for the local model (e.g., llama3.2):

Install from https://ollama.com, then ollama serve and ollama pull llama3.2.

Run
python main.py # or whatever your python file name is

Keys used: OPENAI_API_KEY, ANTHROPIC_API_KEY, optional GOOGLE_API_KEY, DEEPSEEK_API_KEY, GROQ_API_KEY.