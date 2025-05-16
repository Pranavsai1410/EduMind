# 📚 EduMind

**EduMind** is an AI-powered educational platform that helps students automatically generate quizzes from their study materials. It supports document uploads (PDF/Word) or pasted text and provides interactive quiz-taking with immediate feedback.

---

## ✨ Features

- 📄 **Quiz Generation**: Upload PDFs, Word documents, or paste text to generate:
  - Multiple Choice Questions (MCQs)
  - True/False Questions
  - Fill-in-the-Blank Questions
- 🧠 **AI-Chat**: Utilizes the `mistral:7b` model via `langchain_ollama` to chat and solve doubts.
- 🖱️ **Summarization**: Takes pdf/word documents and explain the whole thing in one or two paragraphs.
- ⚙️ **Search**: There are uploaded pdfs which can be referred and downloaded to their own local storage.

---

## 🖼️ Screenshots

### 🔐 Login Page
![Login Page](https://github.com/Pranavsai1410/EduMind/blob/main/assests/Screenshot%202025-04-25%20121731.png)

### 📝 Register Page
![Register Page](https://github.com/Pranavsai1410/EduMind/blob/main/assests/Screenshot%202025-04-25%20121843.png)

### 🏠 Dashboard
![Dashboard](https://github.com/Pranavsai1410/EduMind/blob/main/assests/Screenshot%202025-04-25%20121925.png)

### 🤖 AI Chat
![AI Chat](https://github.com/Pranavsai1410/EduMind/blob/main/assests/Screenshot%202025-04-25%20122011.png)

### 📄 Quiz Page
![Quiz Page](https://github.com/Pranavsai1410/EduMind/blob/main/assests/Screenshot%202025-04-25%20122053.png)
![Quiz Questions](https://github.com/Pranavsai1410/EduMind/blob/main/assests/Screenshot%202025-04-25%20122120.png)

### ✅ Quiz Results
![Quiz Results](https://github.com/Pranavsai1410/EduMind/blob/main/assests/Screenshot%202025-04-25%20140251.png)

### 📚 Summary
![Summary](https://github.com/Pranavsai1410/EduMind/blob/main/assests/Screenshot%202025-04-25%20122217.png)

### 🔍 Search PDFs
![Search](https://github.com/Pranavsai1410/EduMind/blob/main/assests/Screenshot%202025-04-25%20122823.png)

---

## 🏗️ Project Structure

### edumind


## 🏗️ Project Structure

### edumind
─ edumind-fr/ # Frontend (Next.js + Tailwind CSS + TypeScript)
─ edumind-bk/ # Backend (Flask + AI + Document Parsing)

markdown
Copy
Edit

### 📁 edumind-fr (Frontend)

- `app/quiz/display/page.tsx`: Upload material & generate quizzes.
- `app/quiz/page.tsx`: Take quizzes & view results.
- `package.json`: Frontend dependencies and scripts.

### 📁 edumind-bk (Backend)

- `main.py`: Flask app with routes for:
  - Text extraction
  - Quiz generation using Mistral 7B via Ollama
  - Quiz evaluation
- `generated_quizzes/`: Stores generated quiz files (excluded via `.gitignore`)
- `logs/`: Logging data (excluded via `.gitignore`)

---

## ✅ Prerequisites

Make sure you have the following installed:

- [Node.js](https://nodejs.org/) (v20.17.0 or later)
- [Python](https://www.python.org/) (3.8 or later)
- [Git](https://git-scm.com/)
- [Ollama](https://ollama.ai) (for running the Mistral 7B model)


# After installing Ollama
ollama pull mistral:7b
🚀 Getting Started
1. Clone the Repository
bash
Copy
Edit
git clone https://github.com/Pranavsai1410/EduMind.git
cd edumind
Replace YourGitHubUsername with your actual GitHub username.

2. Backend Setup (Flask)
bash
Copy
Edit
cd edumind-bk

# Install Python dependencies
pip install flask langchain_ollama PyPDF2 python-docx flask_cors

# Run the Flask server
python grok.py
The server runs at http://0.0.0.0:5000

Ensure ollama is running with the mistral:7b model.

3. Frontend Setup (Next.js)
bash
Copy
Edit
cd edumind-fr

# Install Node.js dependencies
npm install

# Start the development server
npm run dev
The frontend runs at http://localhost:3003

🧪 Usage
📥 Generate a Quiz
Go to http://localhost:3003/quiz/display

Upload a study document or paste raw text.

Choose:

Number of questions (1–20)

Question type (MCQ, True/False, Fill-in-the-Blank)

Click Generate Quiz

🧾 Take the Quiz
After quiz generation, you will be redirected to the quiz page.

Answer the questions and click Submit Quiz.

Instantly receive your score and feedback.

