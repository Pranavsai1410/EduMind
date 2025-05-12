EduMind
EduMind is an educational platform designed to help students generate quizzes from study materials, take quizzes, and evaluate their performance. It consists of a Next.js frontend and a Flask backend, leveraging AI to create dynamic quizzes from uploaded documents (PDF/Word) or pasted text.
Features

Quiz Generation: Upload a PDF/Word document or paste text to generate quizzes with multiple-choice, true/false, or fill-in-the-blank questions.
Interactive Quiz-Taking: Take quizzes with a user-friendly interface and get immediate feedback on your performance.
AI-Powered: Uses the mistral:7b model (via langchain_ollama) to generate quiz questions based on the provided material.
Flexible Deployment: Separate frontend and backend for easy scaling and maintenance.

Project Structure
The repository contains two main directories:

edumind-fr: The frontend, built with Next.js, TypeScript, and Tailwind CSS.
Handles the user interface for uploading materials, generating quizzes, and taking quizzes.


edumind-bk: The backend, built with Flask (Python).
Manages text extraction from documents, quiz generation using AI, and quiz evaluation.



Directory Breakdown

edumind-fr/
app/quiz/display/page.tsx: Page for uploading study materials and generating quizzes.
app/quiz/page.tsx: Page for taking quizzes and viewing results.
package.json: Frontend dependencies and scripts.


edumind-bk/
grok.py: Main Flask application with endpoints for text extraction, quiz generation, and evaluation.
generated_quizzes/: Stores generated quizzes (excluded from Git via .gitignore).
logs/: Stores logs (excluded from Git via .gitignore).



Prerequisites
Before setting up the project, ensure you have the following installed:

Node.js (v20.17.0 or later): For the frontend.
Python (3.8 or later): For the backend.
Git: To clone and manage the repository.
Ollama: To run the mistral:7b model locally for quiz generation.
Install Ollama from ollama.ai.
Pull the model: ollama pull mistral:7b.



Setup Instructions
1. Clone the Repository
Clone the EduMind repository to your local machine:
git clone https://github.com/YourGitHubUsername/edumind.git
cd edumind

Replace YourGitHubUsername with your actual GitHub username.
2. Set Up the Backend (edumind-bk)

Navigate to the backend directory:
cd edumind-bk


Install Python dependencies:
pip install flask langchain_ollama PyPDF2 python-docx flask_cors


Start the Flask server:
python grok.py


The server will run on http://0.0.0.0:5000.
Ensure Ollama is running and the mistral:7b model is available.



3. Set Up the Frontend (edumind-fr)

Open a new terminal and navigate to the frontend directory:
cd edumind-fr


Install Node.js dependencies:
npm install


Start the Next.js development server:
npm run dev


The frontend will run on http://localhost:3003.



4. Test the Application

Open your browser and go to http://localhost:3003/quiz/display.
Upload a PDF/Word document or paste text (e.g., "Unit-2\n\nFederal\n\nSystem:\n\nGovernments\n\nhav...").
Select the number of questions and question type (e.g., multiple-choice).
Click "Generate Quiz" to create a quiz.
Take the quiz and view your results.

Usage

Generate a Quiz:

Navigate to /quiz/display.
Upload a document or paste study material.
Choose the number of questions (1–20) and question type (multiple-choice, true/false, fill-in-the-blank).
Click "Generate Quiz" to create a quiz.


Take a Quiz:

After generating a quiz, you’ll be redirected to the quiz page.
Answer the questions and click "Submit Quiz" to see your score and feedback.


View Results:

Review your score, correct answers, and explanations after submitting the quiz.



Troubleshooting

Flask Server Fails:

Ensure port 5000 is free: netstat -aon | findstr :5000.
Terminate conflicting processes: taskkill /PID <PID> /F.
Verify Ollama is running: ollama list should show mistral:7b.


Next.js Fails to Start:

Delete the .next folder: rm -rf .next.
Clear node_modules: rm -rf node_modules package-lock.json, then npm install.
Run as Administrator if you encounter EPERM errors.


Frontend Can’t Connect to Backend:

Ensure the backend is running on http://0.0.0.0:5000.
Verify CORS settings in grok.py match the frontend port (http://localhost:3003).




