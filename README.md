AI Powered Vital Monitor
An advanced AI-powered system designed for monitoring and analyzing vital signs in healthcare environments. This intelligent platform leverages AI to generate diagnostic code, analyze patient data patterns, and provide real-time vital sign monitoring.

🚀 Key Features
AI-Powered Vital Sign Analysis: Leverages Google's Gemini models to analyze patient vital signs and generate intelligent alerts and recommendations.

Retrieval-Augmented Generation (RAG): The AI's knowledge is augmented with information from medical protocols, guidelines, and documentation, ensuring context-aware and medically sound analysis.

AI Self-Correction Loop: A unique two-step verification process where the AI reviews and corrects its own analysis, dramatically improving reliability and accuracy of vital sign interpretation.

Structured, Multi-Part Output: Provides comprehensive vital sign analysis including measurements, trend analysis, professional medical interpretation, verification notes, and alert notifications.

Professional Microservices Architecture: Built with a decoupled backend featuring a main orchestrator and a specialized rag_service for scalability and robustness.

Fully Containerized: The entire application is containerized with Docker, ensuring a consistent and easy-to-manage development and deployment environment.

🏛️ Architecture Overview
The AI Powered Vital Monitor is built on a modern, multi-service architecture designed for scalability and maintainability.

(It is highly recommended to create a simple diagram and link it here)

Frontend: A static, single-page application built with HTML, CSS, and JavaScript that provides the user interface for vital sign monitoring.

Orchestrator Service: The central "brain" of the application. A FastAPI server that handles user queries, coordinates with the RAG service, and manages the multi-step LLM workflow for vital sign analysis.

RAG Service: A specialized FastAPI microservice that provides a queryable medical knowledge base, running a Chroma vector database to find relevant context from medical documents.

🛠️ Tech Stack
Component	Technologies & Frameworks
Frontend	HTML5, CSS3, JavaScript
Backend	Python 3.11+, FastAPI, Uvicorn
AI & Machine Learning	Google Generative AI (Gemini), LangChain, ChromaDB (Vector Store), Sentence Transformers (Embeddings)
Containerization	Docker, Docker Compose
CI/CD & Deployment	GitHub Actions, Google Cloud Run / Render

Export to Sheets
⚙️ Getting Started: Local Setup
Follow these steps to set up and run the project on your local machine.

Prerequisites
Git

Docker and Docker Compose

Python 3.11+

Installation & Launch
Clone the repository:

Bash

git clone https://github.com/your-username/your-repo.git
cd your-repo
Create an environment file:
Create a file named .env in the root of the project and add your Google API key:

Code snippet

GOOGLE_API_KEY=your_actual_google_api_key_here
Add Knowledge Base Documents:
Place your medical protocols and vital sign documentation (PDF files) inside the ./rag_source_documents directory.

Build the RAG Index:
This is a one-time setup step to create the vector database.

Bash

# It's recommended to use a virtual environment
python -m venv .venv
source .venv/bin/activate  # On Windows: .venv\Scripts\activate
pip install -r requirements.txt
python rag_index.py
This will create a rag_db folder containing the knowledge base.

Build and Run the Application:
This single command will build all the Docker images and start the services.

Bash

docker-compose up --build
Access the Application:
Once the containers are running, open your web browser and navigate to:
http://localhost:8080

🚀 Usage
Open the web interface.

Type a description of the vital signs you need to monitor or analyze in the chat input.

Press "Send" or hit Enter.

The AI will generate the full analysis in the output panel, organized into tabs for analysis results, data parameters, and monitoring traces.

You can edit the generated analysis and parameters directly in the text areas.

Use the download buttons to save the generated analysis and parameters as separate files.
