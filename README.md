Bonaventure Simeon: Student-Tracker Web App

A simple FastAPI web application for registering students and tracking their weekly progress during the Cloud Native Series.

Repository URL:
https://github.com/bonaventuresimeon/Student-Tracker.git

Original Author:
Chisom Jude — https://github.com/ChisomJude/student-project-tracker

Adopted and Collaborated by:
Bonaventure Simeon

🚀 Key Features
	•	Register new students: Generates a unique ID for each student.
	•	Track weekly progress: Monitor individual student progress over time.
	•	Centralized database: All student data is stored in a single MongoDB instance (hosted on MongoDB Atlas or similar).
	•	RESTful API: Simple endpoints for registration, status check, and progress updates.

📦 Prerequisites
	•	Python 3.10+
	•	Git
	•	MongoDB Atlas account (to obtain your connection string)

💻 Local Development Setup
	1.	Clone the Repository

git clone https://github.com/bonaventuresimeon/Student-Tracker.git
cd Student-Tracker


	2.	Create Virtual Environment & Install Dependencies

python3 -m venv venv
source venv/bin/activate  # On Windows use: venv\Scripts\activate
pip install -r requirements.txt


	3.	Configure Database Connection
	•	Navigate to app/main.py and update the Vault IP if needed.
	•	Set your Vault token environment variable:

export VAULT_TOKEN=<your_vault_token>


	4.	Run the Application Locally

uvicorn app.main:app --host 0.0.0.0 --port 8011 --reload

Visit http://localhost:8011 (or http://vmip:8011 on your server) to see your app in action.

🐳 Docker Instructions
	1.	Build Docker Image

docker build -t student-tracker .


	2.	Run Docker Container

docker run --env-file .env -p 8011:8000 student-tracker


	3.	Push to Docker Hub
Ensure you’re logged in:

docker login

Tag and push your image (replace your-dockerhub-username with your Docker Hub username):

docker tag student-tracker your-dockerhub-username/student-tracker
docker push your-dockerhub-username/student-tracker



📬 API Endpoints

Method	Endpoint	Description
POST	/register?name=YourName	Register new student
GET	/status/{student_id}	View registration and progress
POST	/update/{student_id}?week=week1	Update progress by week

🌐 Deploying to Cloud (Optional)

You can deploy the app on platforms like:
	•	Render
	•	Railway
	•	Fly.io
	•	Azure App Service
	•	Elastic Beanstalk or more

👩🏽‍💻 Built for the Cloud Native Series by Chisom Jude (Original Author) and adopted by Bonaventure Simeon

Feel free to fork, collaborate, and extend this project!
