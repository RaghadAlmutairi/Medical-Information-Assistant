# Medical Information Assistant

A Streamlit app powered by a **ReAct agent** that answers general medical questions using tools, with safety guardrails built into every response. It provides general health information only, never diagnosis or treatment advice.

📸 [View app screenshots (PDF)](MedAgent.pdf)

## What it does
The agent reasons step by step, decides which tool to call, observes the result, and then writes a final answer.

**Tools**
- **Medical info lookup:** searches Wikipedia for conditions and general medical topics
- **Drug info lookup:** queries an internal drug database
- **BMI calculator**
- **Medical disclaimer:** appended to every answer

## Safety guardrails
- **Output filter:** redacts dosage, diagnosis, and directive advice from responses
- **Rate limiter:** caps the number of requests per session
- **Iteration cap:** limits how many tool calls the agent can make per question
- **Mandatory disclaimer:** every answer states it is not a substitute for professional medical advice

## Interface
- **Reasoning trace:** shows each thought, tool call, and observation
- **Final answer:** the filtered response
- **Session stats and history**

## Tech stack
Python · Streamlit · OpenAI GPT-4o-mini · ReAct agent pattern with a tool dispatcher

## Run it locally
```bash
git clone https://github.com/RaghadAlmutairi/Medical-Information-Assistant.git
cd Medical-Information-Assistant
pip install -r requirements.txt
```

Set your OpenAI API key as an environment variable (never commit it to the repo):

```bash
export OPENAI_API_KEY="your-key-here"      # macOS / Linux
setx OPENAI_API_KEY "your-key-here"        # Windows
```

Then start the app:

```bash
streamlit run app.py
```

## Repository contents
| File | Description |
|---|---|
| `app.py` | Streamlit app: agent loop, tools, guardrails |
| `requirements.txt` | Python dependencies |
| `Reference_Agent_System_Walkthrough_Guardrails...` | Walkthrough of the agent system and guardrails |

## Disclaimer
This project is for educational purposes. It provides general information only and is not a medical device or a substitute for professional medical advice.
