# 🤖 AI Developer Assistant — Ollama + Streamlit

A **ChatGPT-style local AI developer assistant** built with **Python, Streamlit, and Ollama**.

It runs a local LLM through Ollama, keeps conversation history, supports multiple working modes, lets you switch between installed models, and provides a clean chat interface designed as a portfolio project.

---

## ✨ Features

- 💬 ChatGPT-style chat interface
- 🧠 Local LLM using Ollama
- 🔄 Switch between installed Ollama models
- ✅ Test Ollama connection from the sidebar
- 🗂️ Previous chats shown in the sidebar
- ➕ Create a new chat
- 🌙 Dark / Light mode toggle
- 🧾 Persistent conversation history using JSONL
- ⚡ Streaming AI responses
- 🔁 Regenerate the last response
- 📋 Copy assistant responses
- ⬇️ Download the current conversation
- 🗑️ Clear the current chat
- 📝 Application logging
- 🧩 Multiple assistant modes
- 💻 Runs locally on your computer

---

## 🧩 Assistant Modes

| Mode | Purpose |
|---|---|
| 💬 **Answer Questions** | Ask general questions and get clear answers |
| 💻 **Explain Code** | Paste code and get a beginner-friendly explanation |
| ⚙️ **Generate Code** | Describe what you want to build and generate code |
| 📝 **Summarize Text** | Paste long text and receive a concise summary |

---

## 🖥️ Interface

The application is designed to feel similar to ChatGPT.

```text
┌──────────────────────────┬──────────────────────────────────────────┐
│ 🤖 AI Developer Assistant│ AI Developer Assistant                   │
│ Local AI • Ollama        │ Local Ollama • llama3.2:3b              │
│                          │                                          │
│ ＋ New chat              │ Answer | Explain | Generate | Summarize │
│                          │                                          │
│ Dark mode        ON      │          How can I help you today?       │
│                          │                                          │
│ MODEL SELECTION          │                                          │
│ llama3.2:3b ▼            │                                          │
│                          │                                          │
│ 🟢 Connected             │                                          │
│ [ Test Ollama ]          │                                          │
│                          │                                          │
│ PREVIOUS CHATS           │                                          │
│ What is AI?              │                                          │
│ Explain Python code      │                                          │
│ Generate calculator      │                                          │
│                          │      Message AI Developer Assistant...   │
│ CHAT TOOLS               │                                          │
│ Clear Current History    │                                          │
│ Download Chat            │                                          │
└──────────────────────────┴──────────────────────────────────────────┘
```

---

## 🛠️ Tech Stack

- Python
- Streamlit
- Ollama
- Local Large Language Models
- JSON / JSONL
- Python Logging
- HTML / CSS
- JavaScript

---

## 🧠 Default Model

The project currently uses:

```text
llama3.2:3b
```

The application also reads the models installed in Ollama and displays them in the model selection dropdown.

Check installed models with:

```bash
ollama list
```

Example:

```text
NAME            SIZE
llama3.2:3b     2.0 GB
```

---

## 📂 Project Structure

```text
AI-Developer-Assistant-Ollama-Streamlit/
│
├── ai_developer_assistant_chatgpt_ui.py
├── history.jsonl
├── app.log
├── requirements.txt
├── .gitignore
└── README.md
```

| File | Description |
|---|---|
| `ai_developer_assistant_chatgpt_ui.py` | Main Streamlit application |
| `history.jsonl` | Stores chat history |
| `app.log` | Stores application logs |
| `requirements.txt` | Python dependencies |
| `.gitignore` | Files Git should ignore |
| `README.md` | Project documentation |

---

## 🚀 Installation

### 1. Clone the Repository

```bash
git clone https://github.com/Karanveer05/AI-Developer-Assistant-Ollama-Streamlit.git
```

Then move into the project folder:

```bash
cd AI-Developer-Assistant-Ollama-Streamlit
```

---

### 2. Install Ollama

Install Ollama on your computer.

Check installation:

```bash
ollama --version
```

---

### 3. Download a Model

Example:

```bash
ollama pull llama3.2:3b
```

Check installed models:

```bash
ollama list
```

---

### 4. Install Python Packages

```bash
python -m pip install streamlit ollama
```

Or:

```bash
python -m pip install -r requirements.txt
```

---

## ▶️ Run the Application

Open the terminal inside the project folder and run:

```bash
python -m streamlit run ai_developer_assistant_chatgpt_ui.py
```

Then open:

```text
http://localhost:8501
```

---

## ⌨️ Useful Keyboard Shortcuts

| Action | Shortcut |
|---|---|
| Open VS Code terminal | `Ctrl + `` |
| Save file | `Ctrl + S` |
| Stop Streamlit server | `Ctrl + C` |
| Open browser address bar | `Ctrl + L` |
| Refresh browser | `Ctrl + R` |
| Take screenshot | `Windows + Shift + S` |

---

## 🔌 Ollama Connection Test

The application checks whether Ollama and the selected model are working.

If connected:

```text
🟢 Connected • llama3.2:3b
```

If connection fails:

```text
🔴 Ollama not connected
```

You can also click:

```text
🔌 Test Ollama
```

from the sidebar.

---

## 🔄 Model Selection

The application automatically reads installed Ollama models.

For example, install another model:

```bash
ollama pull gemma3:4b
```

Then the model selector can show:

```text
llama3.2:3b
gemma3:4b
```

Select any installed model from the sidebar.

---

## 💾 Conversation History

Conversations are stored in:

```text
history.jsonl
```

Example:

```json
{
  "chat_id": "example-chat-id",
  "role": "user",
  "content": "Explain Python decorators",
  "mode": "Answer Questions",
  "created_at": "2026-09-01T12:15:00"
}
```

The `chat_id` allows the application to maintain separate conversations similar to ChatGPT.

---

## 🗂️ Previous Chats

Previous conversations are displayed in the sidebar.

Example:

```text
Previous Chats

What is machine learning?
Explain Python decorators
Generate a calculator
Summarize an article
```

Clicking a previous chat opens that conversation.

---

## ➕ New Chat

Click:

```text
＋ New chat
```

to create a new conversation.

Previous conversations remain saved.

---

## 🗑️ Clear Current History

The **Clear Current History** option removes only the currently selected conversation instead of deleting all saved chats.

---

## ⚡ Streaming Responses

Ollama responses are streamed into the interface while the model is generating them.

```text
User Prompt
    ↓
Selected Mode
    ↓
System Instruction
    ↓
Previous Chat Context
    ↓
Ollama
    ↓
Selected Local Model
    ↓
Streaming Response
    ↓
Save to history.jsonl
```

---

## 🔁 Regenerate Response

The application can regenerate the latest assistant response while keeping the previous conversation context.

---

## 📋 Copy Response

Assistant responses can be copied using the copy button.

---

## ⬇️ Download Chat

The current conversation can be downloaded as a text file from the sidebar.

---

## 📝 Logging

Application activity and errors are stored in:

```text
app.log
```

Logging helps diagnose:

- Ollama connection problems
- Model loading errors
- History file errors
- Response generation failures

---

## 🔐 Privacy

This project is designed to use **local Ollama models**.

For local models, prompts are processed through the Ollama service running on your computer.

No Gemini or OpenAI API key is required.

---

## 🛡️ Recommended `.gitignore`

```gitignore
.venv/
venv/
__pycache__/
*.pyc
app.log
.env
history.jsonl
```

Ignoring `history.jsonl` is recommended because it may contain personal conversation history.

---

## 📦 requirements.txt

```text
streamlit
ollama
```

---

## 🧱 Application Architecture

```text
                         USER
                           │
                           ▼
                 Streamlit Chat Interface
                           │
              ┌────────────┴────────────┐
              │                         │
              ▼                         ▼
        Mode Selection            Model Selection
              │                         │
              └────────────┬────────────┘
                           ▼
                 System Instructions
                           │
                           ▼
                  Conversation History
                    (history.jsonl)
                           │
                           ▼
                      Ollama
                           │
                           ▼
                  Selected Local LLM
                           │
                           ▼
                  Streaming Response
                           │
                           ▼
                   Streamlit Chat UI
                           │
                           ▼
                  Save Conversation
```

---

## 💡 What This Project Demonstrates

This project demonstrates practical concepts used in modern Generative AI applications:

- Local LLM integration
- Prompt engineering
- System instructions
- Conversation memory
- Multiple AI modes
- Streaming responses
- Model switching
- Session management
- Persistent chat history
- Error handling
- Logging
- Streamlit UI development
- Chat-style application design

---

## 🔮 Future Improvements

- Gemini + Ollama provider switching
- RAG with PDF documents
- File upload and analysis
- Image understanding
- Voice input
- Database-backed chat history
- User authentication
- Rename and delete chats
- Export chats as Markdown or PDF
- Agent tools
- Web search
- GitHub integration

---

## 👨‍💻 Author

**Karanveer Singh**

Built as a portfolio project while learning and exploring:

- Generative AI
- Large Language Models
- Ollama
- Streamlit
- Python
- AI Application Development

---

## ⭐ Support

If you find this project useful, consider giving the repository a **star ⭐**.

---

## 📄 License

This project is currently intended for educational and portfolio purposes.

You can add an **MIT License** if you want others to freely use, modify, and distribute the project.
