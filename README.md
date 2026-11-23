# DevOps Linux & Docker AI Assistant 🚀

A Streamlit-based web application that serves as an AI assistant for DevOps engineers and system administrators. It combines live system monitoring with interactive AI troubleshooting.

---

## ✨ Features

- **AI Chatbot:** Answers Linux, Docker, and DevOps troubleshooting queries using Groq API.
- **System Monitoring:** Displays real-time CPU, Memory, and system status metrics using `psutil`.
- **Voice Assistance:** Converts text responses to speech via ElevenLabs API.
- **Cloud Ready:** Configured for seamless deployment on AWS Elastic Beanstalk.

---

## 🛠️ Tech Stack

- **Frontend & Dashboard:** Streamlit
- **AI Core:** Groq API (LLM)
- **Voice Synthesis:** ElevenLabs API
- **System Metrics:** `psutil`
- **Deployment Platform:** AWS Elastic Beanstalk (Python 3.10 / Linux)

---

## ⚙️ Environment Variables

Set the following environment variables locally in a `.env` file or in AWS Elastic Beanstalk Environment Properties:

env
GROQ_API_KEY=your_groq_api_key
ELEVENLABS_API_KEY=your_elevenlabs_api_key

## 🚀 Quick Start (Local Setup)
Clone the repository:

bash
git clone [https://github.com/Sumbulzahra/streamlit-devops-linux-ai-assistant.git](https://github.com/Sumbulzahra/streamlit-devops-linux-ai-assistant.git)
cd streamlit-devops-linux-ai-assistant

Create and activate a virtual environment:

Bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
Install dependencies:

Bash
pip install -r requirements.txt
Run the application:

Bash
streamlit run app.py

---

## ☁️ Deployment on AWS Elastic Beanstalk
Ensure requirements.txt includes essential packages (streamlit, groq, elevenlabs, psutil, requests, python-dotenv).

Create a .zip archive of the project files (excluding venv/ and .env).

Deploy the .zip file on AWS Elastic Beanstalk Python environment.

Configure GROQ_API_KEY and ELEVENLABS_API_KEY in Configuration > Software > Environment properties.

## 📄 License
This project is licensed under the MIT License.


Phase 2: Create AWS Elastic Beanstalk environment
Step 7. Open AWS Elastic Beanstalk
Open:
AWS Elastic Beanstalk Console







hackmd.io


1. Sign in to your AWS account.
2. Select your AWS Region. For example, ap-south-1 (Mumbai).
3. Click Create application.
Step 8. Configure the application
Use these settings:
Setting	Value
Application name	devops-ai-assistant
Environment tier	Web server environment
Environment name	devops-ai-assistant-env
Platform	Python
Platform branch	Python 3.10, if available
Application code	Upload your code









adex.ltd


Choose the currently available Python platform version compatible with your dependencies.
Step 9. Upload your ZIP file
Under Application code:
1. Select Upload your code.
2. Select Local file.
3. Click Choose file.
4. Select devops-ai-assistant.zip.
5. Click Create environment.








dev.to


AWS will provision the environment and deploy this application.

This may take several minutes.
Phase 3: Configure API keys
Step 10. Configure environment properties
After your environment is created:
1. Open Elastic Beanstalk.
2. Select devops-ai-assistant-env.
3. Go to Configuration.
4. Find Updates, monitoring, and logging or the software configuration section, depending on the console layout.
5. Click Edit.
6. Find Environment properties.
Add these three properties:
Environment properties
PROPERTY 1
GROQ_API_KEY
Required
Value: Your actual Groq API key
PROPERTY 2
ELEVENLABS_API_KEY
Required
Value: Your actual ElevenLabs API key
PROPERTY 3
PORT
Value: 8080
Click Apply to save the configuration.
