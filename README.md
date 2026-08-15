# 🤖 ResumeAI

> **An AI-powered interactive resume assistant that turns a traditional resume into a conversational professional profile.**

ResumeAI allows recruiters, hiring managers, and visitors to interact with a resume using natural-language questions.

Instead of manually reading through a static PDF, users can ask questions such as:

* "What are the candidate's strongest skills?"
* "Tell me about their work experience."
* "What projects have they worked on?"
* "Does the candidate have Python experience?"
* "Would they be suitable for a software developer role?"

ResumeAI processes the resume, structures the information using AI, and uses that structured data to provide concise, resume-grounded answers.

---

## ✨ Features

* 🤖 **AI-Powered Resume Assistant**
* 📄 **PDF Resume Parsing**
* 💬 **Natural Language Conversations**
* 🧠 **Conversation History**
* 🎯 **Job Role Suitability Analysis**
* 📋 **Structured Resume Information**
* ⚡ **FastAPI REST API**
* 🎨 **Responsive Chat Interface**
* 🔒 **Resume-Grounded Responses**
* 📱 **Mobile-Friendly UI**
* 📝 **Markdown Response Rendering**
* 🐳 **Docker Support**

---

## 🛠️ Tech Stack

| Technology    | Purpose                             |
| ------------- | ----------------------------------- |
| 🐍 Python     | Backend development                 |
| ⚡ FastAPI     | REST API and application server     |
| 🧠 Groq API   | AI-powered resume analysis          |
| 📦 Pydantic   | Data validation and structured data |
| 📄 PyPDF      | PDF text extraction                 |
| 🌐 HTML/CSS   | Frontend interface                  |
| ⚙️ JavaScript | Chat functionality                  |
| 📝 Marked.js  | Markdown rendering                  |
| 🐳 Docker     | Containerization                    |

---

## 🏗️ Architecture

```text
                    ┌──────────────────┐
                    │    Resume PDF    │
                    └────────┬─────────┘
                             │
                             ▼
                    ┌──────────────────┐
                    │  PyPDF Extraction│
                    └────────┬─────────┘
                             │
                             ▼
                    ┌──────────────────┐
                    │     Groq AI      │
                    │ Resume Structuring│
                    └────────┬─────────┘
                             │
                             ▼
                    ┌──────────────────┐
                    │ Structured Resume│
                    │       Data       │
                    └────────┬─────────┘
                             │
                             ▼
┌───────────────┐    ┌──────────────────┐
│    Visitor    │───▶│  FastAPI Backend │
└───────────────┘    └────────┬─────────┘
                              │
                              ▼
                     ┌─────────────────┐
                     │    Groq AI Chat │
                     └────────┬────────┘
                              │
                              ▼
                     ┌─────────────────┐
                     │   AI Response   │
                     └─────────────────┘
```

---

## 🔄 How It Works

### 1. Resume Extraction

ResumeAI reads the candidate's PDF resume using **PyPDF** and extracts its text.

### 2. Resume Structuring

The extracted information is processed using the Groq AI API and converted into structured information such as:

* Personal information
* Current role
* Work experience
* Technical skills
* Projects
* Education
* Certifications
* Achievements
* Languages

### 3. AI Assistant

When a visitor asks a question, the structured resume information is provided to the AI assistant.

The assistant is instructed to:

* Use information supported by the resume
* Avoid inventing qualifications or experience
* Avoid guessing missing information
* Provide concise and useful responses
* Maintain context through conversation history

---

## 💬 Example Questions

ResumeAI can answer questions such as:

```text
Give me a brief overview of the candidate.
```

```text
What are the candidate's strongest technical skills?
```

```text
Tell me about their work experience.
```

```text
What projects has the candidate worked on?
```

```text
Does the candidate have experience with Python?
```

```text
What is their educational background?
```

```text
Would this candidate be suitable for a software developer role?
```

You can also provide a **job description** and use ResumeAI to get resume-based suitability insights.

---

## 📂 Project Structure

```text
ResumeAI/
│
├── Docker/
│   ├── Dockerfile
│   ├── .dockerignore
│   ├── main.py
│   ├── index.html
│   ├── my_resume.pdf
│   └── requirements.txt
│
├── main.py
├── index.html
├── my_resume.pdf
├── requirements.txt
└── README.md
```

---

# ⚙️ Local Installation

## 1. Clone the Repository

```bash
git clone https://github.com/sharmaansh/ResumeAI.git
cd ResumeAI
```

## 2. Create a Virtual Environment

```bash
python -m venv venv
```

### Windows

```bash
venv\Scripts\activate
```

### macOS / Linux

```bash
source venv/bin/activate
```

## 3. Install Dependencies

```bash
pip install -r requirements.txt
```

---

## 🔑 Environment Variables

Create a `.env` file in the project root:

```env
GROQ_API_KEY=your_groq_api_key_here
```

### ⚠️ Security

**Never commit your API key to GitHub.**

Add the following to `.gitignore`:

```gitignore
.env
__pycache__/
*.pyc
venv/
.venv/
```

---

# ▶️ Run Locally

Start the FastAPI server:

```bash
uvicorn main:app --reload
```

The application will be available at:

```text
http://127.0.0.1:8000
```

Then open the application in your browser.

---

# 🔌 API Endpoints

### `GET /`

Returns basic application information.

### `GET /health`

Checks the application and resume loading status.

### `GET /profile`

Returns basic candidate profile information such as role, experience, and skills.

### `POST /chat`

Accepts a natural-language question and returns an AI-generated response based on the resume.

#### Example Request

```json
{
  "question": "What are the candidate's strongest skills?",
  "history": []
}
```

---

# 🐳 Docker

ResumeAI also includes a Docker setup for running the application in an isolated and reproducible environment.

The Docker configuration is located in the:

```text
Docker/
```

directory.

---

## 📁 Docker Structure

```text
Docker/
├── Dockerfile
├── .dockerignore
├── main.py
├── index.html
├── my_resume.pdf
└── requirements.txt
```

The Docker image uses **Python 3.11 Slim**, installs the application dependencies, exposes port `8000`, and starts the FastAPI application using Uvicorn.

---

## 🔑 Configure the API Key

Create a `.env` file inside the `Docker/` directory:

```env
GROQ_API_KEY=your_groq_api_key_here
```

> ⚠️ **Never commit your real API key to GitHub.**

The `.dockerignore` file should exclude sensitive and unnecessary files such as:

```text
.env
venv/
.venv/
__pycache__/
.git/
```

---

## 🏗️ Build the Docker Image

Navigate to the Docker directory:

```bash
cd Docker
```

Build the image:

```bash
docker build -t resumeai .
```

---

## ▶️ Run the Docker Container

Run ResumeAI on port `8000`:

```bash
docker run -d \
  --name resumeai \
  -p 8000:8000 \
  --env-file .env \
  resumeai
```

The application will now be available at:

```text
http://localhost:8000
```

---

## 📋 Check Running Containers

```bash
docker ps
```

You should see the `resumeai` container running with port `8000` mapped to the host.

---

## 📜 View Container Logs

To view the application logs:

```bash
docker logs -f resumeai
```

---

## 🛑 Stop the Container

```bash
docker stop resumeai
```

Remove the container:

```bash
docker rm resumeai
```

---

## 🔄 Rebuild After Changes

If you modify the application code or dependencies:

```bash
docker stop resumeai
docker rm resumeai

docker build -t resumeai .
```

Then start the container again:

```bash
docker run -d \
  --name resumeai \
  -p 8000:8000 \
  --env-file .env \
  resumeai
```

---

## ⚡ Docker Quick Start

```bash
cd ResumeAI/Docker

docker build -t resumeai .

docker run -d \
  --name resumeai \
  -p 8000:8000 \
  --env-file .env \
  resumeai
```

Then open:

```text
http://localhost:8000
```

---

## 🧩 Docker Architecture

```text
                  ┌─────────────────────┐
                  │     Docker Host     │
                  │                     │
                  │  ┌───────────────┐  │
Browser ─────────▶│  │ ResumeAI      │  │
localhost:8000    │  │ Container     │  │
                  │  │               │  │
                  │  │ Python 3.11   │  │
                  │  │ FastAPI       │  │
                  │  │ Uvicorn       │  │
                  │  │ Resume Parser  │  │
                  └──┴───────┬───────┴──┘
                              │
                              ▼
                         Groq API
```

---

# 🎯 Why ResumeAI?

Traditional resumes are static documents.

ResumeAI explores a different approach: turning a resume into an **interactive professional profile** where recruiters and visitors can ask questions directly.

The project demonstrates practical applications of:

* Generative AI
* Prompt Engineering
* Structured Data Extraction
* PDF Processing
* REST APIs
* FastAPI
* Docker
* Frontend/Backend Integration
* Conversational AI

---

# 🚀 Future Improvements

* [ ] Public deployment
* [ ] Portfolio website integration
* [ ] Resume upload functionality
* [ ] Support for multiple resumes
* [ ] Streaming AI responses
* [ ] Voice-based questions
* [ ] Improved job-description matching
* [ ] Automated resume scoring
* [ ] Authentication
* [ ] Database integration
* [ ] Visitor-question analytics

---

# 🔐 Privacy & Security

ResumeAI processes personal information contained within a resume.

If you fork or deploy this project:

* Do not expose API keys.
* Do not commit `.env` files.
* Review the resume before making the repository public.
* Avoid exposing sensitive personal information unnecessarily.
* Rotate API credentials immediately if they are accidentally exposed.

---

# 👨‍💻 Author

**Ansh Sharma**

GitHub: **@sharmaansh**

---

# ⭐ Support

If you find **ResumeAI** interesting or useful, consider giving the repository a ⭐ on GitHub.

---

# 📄 License

This project is intended for personal and educational use. Please review the repository's licensing and dependencies before redistributing or deploying it publicly.
