echo # EduMind > README.md
echo. >> README.md
echo EduMind is an educational platform designed to help students generate quizzes from study materials, take quizzes, and evaluate their performance. It consists of a **Next.js frontend** and a **Flask backend**, leveraging AI to create dynamic quizzes from uploaded documents (PDF/Word) or pasted text. >> README.md
echo. >> README.md
echo ## Features >> README.md
echo. >> README.md
echo - **Quiz Generation**: Upload a PDF/Word document or paste text to generate quizzes with multiple-choice, true/false, or fill-in-the-blank questions. >> README.md
echo - **Interactive Quiz-Taking**: Take quizzes with a user-friendly interface and get immediate feedback on your performance. >> README.md
echo - **AI-Powered**: Uses the `mistral:7b` model (via `langchain_ollama`) to generate quiz questions based on the provided material. >> README.md
echo - **Flexible Deployment**: Separate frontend and backend for easy scaling and maintenance. >> README.md
echo. >> README.md
echo ## Project Structure >> README.md
echo. >> README.md
echo The repository contains two main directories: >> README.md
echo. >> README.md
echo - **`edumind-fr`**: The frontend, built with Next.js, TypeScript, and Tailwind CSS. >> README.md
echo   - Handles the user interface for uploading materials, generating quizzes, and taking quizzes. >> README.md
echo - **`edumind-bk`**: The backend, built with Flask (Python). >> README.md
echo   - Manages text extraction from documents, quiz generation using AI, and quiz evaluation. >> README.md
echo. >> README.md
echo ### Directory Breakdown >> README.md
echo. >> README.md
echo - `edumind-fr/` >> README.md
echo   - `app/quiz/display/page.tsx`: Page for uploading study materials and generating quizzes. >> README.md
echo   - `app/quiz/page.tsx`: Page for taking quizzes and viewing results. >> README.md
echo   - `package.json`: Frontend dependencies and scripts. >> README.md
echo - `edumind-bk/` >> README.md
echo   - `grok.py`: Main Flask application with endpoints for text extraction, quiz generation, and evaluation. >> README.md
echo   - `generated_quizzes/`: Stores generated quizzes (excluded from Git via `.gitignore`). >> README.md
echo   - `logs/`: Stores logs (excluded from Git via `.gitignore`). >> README.md
echo. >> README.md
echo ## Prerequisites >> README.md
echo. >> README.md
echo Before setting up the project, ensure you have the following installed: >> README.md
echo. >> README.md
echo - **Node.js** (v20.17.0 or later): For the frontend. >> README.md
echo - **Python** (3.8 or later): For the backend. >> README.md
echo - **Git**: To clone and manage the repository. >> README.md
echo - **Ollama**: To run the `mistral:7b` model locally for quiz generation. >> README.md
echo   - Install Ollama from [ollama.ai](https://ollama.ai/). >> README.md
echo   - Pull the model: `ollama pull mistral:7b`. >> README.md
echo. >> README.md
echo ## Setup Instructions >> README.md
echo. >> README.md
echo ### 1. Clone the Repository >> README.md
echo. >> README.md
echo Clone the EduMind repository to your local machine: >> README.md
echo. >> README.md
echo ```bash >> README.md
echo git clone https://github.com/YourGitHubUsername/edumind.git >> README.md
echo cd edumind >> README.md
echo ``` >> README.md
echo. >> README.md
echo Replace `YourGitHubUsername` with your actual GitHub username. >> README.md
echo. >> README.md
echo ### 2. Set Up the Backend (`edumind-bk`) >> README.md
echo. >> README.md
echo 1. Navigate to the backend directory: >> README.md
echo    ```bash >> README.md
echo    cd edumind-bk >> README.md
echo    ``` >> README.md
echo. >> README.md
echo 2. Install Python dependencies: >> README.md
echo    ```bash >> README.md
echo    pip install flask langchain_ollama PyPDF2 python-docx flask_cors >> README.md
echo    ``` >> README.md
echo. >> README.md
echo 3. Start the Flask server: >> README.md
echo    ```bash >> README.md
echo    python grok.py >> README.md
echo    ``` >> README.md
echo    - The server will run on `http://0.0.0.0:5000`. >> README.md
echo    - Ensure Ollama is running and the `mistral:7b` model is available. >> README.md
echo. >> README.md
echo ### 3. Set Up the Frontend (`edumind-fr`) >> README.md
echo. >> README.md
echo 1. Open a new terminal and navigate to the frontend directory: >> README.md
echo    ```bash >> README.md
echo    cd edumind-fr >> README.md
echo    ``` >> README.md
echo. >> README.md
echo 2. Install Node.js dependencies: >> README.md
echo    ```bash >> README.md
echo    npm install >> README.md
echo    ``` >> README.md
echo. >> README.md
echo 3. Start the Next.js development server: >> README.md
echo    ```bash >> README.md
echo    npm run dev >> README.md
echo    ``` >> README.md
echo    - The frontend will run on `http://localhost:3003`. >> README.md
echo. >> README.md
echo ### 4. Test the Application >> README.md
echo. >> README.md
echo - Open your browser and go to `http://localhost:3003/quiz/display`. >> README.md
echo - Upload a PDF/Word document or paste text (e.g., "Unit-2\n\nFederal\n\nSystem:\n\nGovernments\n\nhav..."). >> README.md
echo - Select the number of questions and question type (e.g., multiple-choice). >> README.md
echo - Click "Generate Quiz" to create a quiz. >> README.md
echo - Take the quiz and view your results. >> README.md
echo. >> README.md
echo ## Usage >> README.md
echo. >> README.md
echo 1. **Generate a Quiz**: >> README.md
echo    - Navigate to `/quiz/display`. >> README.md
echo    - Upload a document or paste study material. >> README.md
echo    - Choose the number of questions (1–20) and question type (multiple-choice, true/false, fill-in-the-blank). >> README.md
echo    - Click "Generate Quiz" to create a quiz. >> README.md
echo. >> README.md
echo 2. **Take a Quiz**: >> README.md
echo    - After generating a quiz, you’ll be redirected to the quiz page. >> README.md
echo    - Answer the questions and click "Submit Quiz" to see your score and feedback. >> README.md
echo. >> README.md
echo 3. **View Results**: >> README.md
echo    - Review your score, correct answers, and explanations after submitting the quiz. >> README.md
echo. >> README.md
echo ## Troubleshooting >> README.md
echo. >> README.md
echo - **Flask Server Fails**: >> README.md
echo   - Ensure port `5000` is free: `netstat -aon | findstr :5000`. >> README.md
echo   - Terminate conflicting processes: `taskkill /PID <PID> /F`. >> README.md
echo   - Verify Ollama is running: `ollama list` should show `mistral:7b`. >> README.md
echo. >> README.md
echo - **Next.js Fails to Start**: >> README.md
echo   - Delete the `.next` folder: `rm -rf .next`. >> README.md
echo   - Clear `node_modules`: `rm -rf node_modules package-lock.json`, then `npm install`. >> README.md
echo   - Run as Administrator if you encounter `EPERM` errors. >> README.md
echo. >> README.md
echo - **Frontend Can’t Connect to Backend**: >> README.md
echo   - Ensure the backend is running on `http://0.0.0.0:5000`. >> README.md
echo   - Verify CORS settings in `grok.py` match the frontend port (`http://localhost:3003`). >> README.md
echo. >> README.md
echo ## Contributing >> README.md
echo. >> README.md
echo Contributions are welcome! To contribute: >> README.md
echo. >> README.md
echo 1. Fork the repository. >> README.md
echo 2. Create a new branch: `git checkout -b feature/your-feature`. >> README.md
echo 3. Make your changes and commit: `git commit -m "Add your feature"`. >> README.md
echo 4. Push to your fork: `git push origin feature/your-feature`. >> README.md
echo 5. Open a pull request on GitHub. >> README.md
echo. >> README.md
echo ## License >> README.md
echo. >> README.md
echo This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details. >> README.md
echo. >> README.md
echo ## Contact >> README.md
echo. >> README.md
echo For questions or feedback, please open an issue on GitHub or reach out to the maintainers. >> README.md
