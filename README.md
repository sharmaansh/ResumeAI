# 🤖 ResumeAI

> An interactive AI-powered resume assistant that lets recruiters, hiring managers, and visitors explore my professional profile through natural language.

Instead of reading through a static resume, visitors can simply **ask questions about my skills, experience, projects, education, and technical background** and get concise, resume-based answers.

## ✨ Overview

**ResumeAI** combines a **FastAPI backend**, **Groq AI**, and a lightweight web interface to turn a traditional resume into an interactive AI experience.

The application reads my resume from a PDF, converts it into structured information, and uses that information to answer questions about my professional background.

### Example

Instead of searching through a resume for:

> "What technologies does Ansh have experience with?"

You can simply ask ResumeAI and get a relevant answer based on the information in the resume.

## 🚀 Features

* 🤖 **AI-Powered Resume Assistant**
* 📄 **PDF Resume Parsing**
* 💬 **Natural Language Questions**
* 🧠 **Conversation History**
* 🎯 **Job Role Suitability Analysis**
* 📋 **Structured Resume Information**
* ⚡ **FastAPI REST API**
* 🎨 **Responsive Chat Interface**
* 🔒 **Resume-Grounded Responses**
* 📱 **Mobile-Friendly UI**

## 🛠️ Tech Stack

| Technology     | Purpose                             |
| -------------- | ----------------------------------- |
| **Python**     | Backend development                 |
| **FastAPI**    | REST API                            |
| **Groq API**   | AI-powered resume analysis          |
| **Pydantic**   | Data validation and structured data |
| **PyPDF**      | PDF text extraction                 |
| **HTML/CSS**   | Frontend interface                  |
| **JavaScript** | Chat functionality                  |
| **Marked.js**  | Markdown rendering                  |

## 🏗️ Architecture

```text
                    ┌──────────────────┐
                    │   Resume PDF     │
                    └────────┬─────────┘
                             │
                             ▼
                    ┌──────────────────┐
                    │  PyPDF Extraction│
                    └────────┬─────────┘
                             │
                             ▼
                    ┌──────────────────┐
                    │   Groq AI Model  │
                    │ Resume Structuring│
                    └────────┬─────────┘
                             │
                             ▼
                    ┌──────────────────┐
                    │ Structured Resume│
                    │      Data        │
                    └────────┬─────────┘
                             │
                             ▼
┌───────────────┐    ┌──────────────────┐
│ Portfolio User│───▶│  FastAPI Backend │
└───────────────┘    └────────┬─────────┘
                              │
                              ▼
                     ┌─────────────────┐
                     │   Groq AI Chat  │
                     └────────┬────────┘
                              │
                              ▼
                     ┌─────────────────┐
                     │ AI Response     │
                     └─────────────────┘
```

## 💡 What Can You Ask?

Visitors can ask questions such as:

* **Give me a brief overview of the candidate.**
* **What are his strongest skills?**
* **Tell me about his work experience.**
* **What projects has he worked on?**
* **What technologies does he use?**
* **Does he have experience with Python?**
* **Tell me about his internship.**
* **What is his educational background?**
* **Would he be suitable for a software developer role?**

You can also provide a **job description** to get resume-based suitability insights.

## 📂 Project Structure

```text
ResumeAI/
│
├── main.py
├── index.html
├── my_resume.pdf
└── README.md
```

## ⚙️ How It Works

### 1. Resume Extraction

The application reads the resume PDF using **PyPDF** and extracts its text.

### 2. Resume Structuring

The extracted resume text is sent to the AI model, which converts it into structured information such as:

* Personal information
* Current role
* Experience
* Skills
* Projects
* Education
* Certifications
* Achievements
* Languages

### 3. AI Assistant

When a visitor asks a question, the structured resume information is supplied to the AI assistant.

The assistant is instructed to:

* Use only information supported by the resume.
* Avoid inventing qualifications.
* Avoid guessing missing information.
* Keep responses concise and easy to read.
* Use conversation history for follow-up questions.

## 🔑 Environment Setup

Create a `.env` file in the project directory:

```env
GROQ_API_KEY=your_groq_api_key_here
```

### Important

**Never commit your ****`.env`**** file or API key to GitHub.**

Add the following to `.gitignore`:

```gitignore
.env
__pycache__/
*.pyc
venv/
.venv/
```

## 📦 Installation

Clone the repository:

```bash
git clone https://github.com/sharmaansh/ResumeAI.git
cd ResumeAI
```

Create a virtual environment:

```bash
python -m venv venv
```

Activate it on Windows:

```bash
venv\Scripts\activate
```

Install the dependencies:

```bash
pip install fastapi uvicorn groq python-dotenv pydantic pypdf
```

## ▶️ Run the Application

Start the FastAPI server:

```bash
uvicorn main:app --reload
```

The API will be available at:

```text
http://127.0.0.1:8000
```

Open `index.html` in your browser to use the ResumeAI interface.

## 🔌 API Endpoints

### `GET /`

Returns basic application information.

### `GET /health`

Checks the application and resume loading status.

### `GET /profile`

Returns a basic candidate profile containing information such as role, experience, and skills.

### `POST /chat`

Accepts a question and returns an AI-generated response based on the resume.

Example request:

```json
{
  "question": "What are the candidate's strongest skills?",
  "history": []
}
```

## 🎯 Why I Built This

Traditional resumes are static.

I wanted to experiment with turning a resume into an **interactive professional profile** where visitors can ask questions instead of manually searching through multiple sections of a resume.

This project also demonstrates practical use of:

* Generative AI
* Prompt engineering
* Structured data extraction
* PDF processing
* REST APIs
* FastAPI
* Frontend/backend integration
* Conversational AI

## 🔮 Future Improvements

* [ ] Deploy the application publicly
* [ ] Integrate it directly into my portfolio website
* [ ] Add resume upload functionality
* [ ] Support multiple resumes
* [ ] Add streaming AI responses
* [ ] Add voice-based questions
* [ ] Improve job-description matching
* [ ] Add automated resume scoring
* [ ] Add authentication
* [ ] Add database support
* [ ] Add analytics for visitor questions

## 🔐 Privacy

The application is designed to provide information based on the candidate's resume.

If you fork or reuse this project, make sure you understand what personal information is contained in the resume PDF before making your repository public.

Also, **never expose your Groq API key**.

## 📸 Project

This project is part of my personal developer portfolio and demonstrates how AI can be used to create a more interactive way of presenting professional experience.

---

### 👨‍💻 Author

**Himanshu Sharma**

GitHub: [@sharmaansh](https://github.com/sharmaansh)

---

⭐ If you find this project interesting, feel free to star the repository!
