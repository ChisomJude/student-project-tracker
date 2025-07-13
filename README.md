# Student-Project-Tracker Web APP
A simple FastAPI web application for registering students and tracking their weekly progress during the Cloud Native Series.

### Key Features:
- Register new students (generates a unique ID).
- Track weekly progress for each student.
- All students use one central MongoDB (hosted on MongoDB Atlas or similar).
- Simple endpoints for registration, status check, and progress update.

## 📦 Prerequisites
- Python 3.10+
- Git
- MongoDB Atlas account (to get your connection string)

---

## 💻 Local Development Setup

### 1. Clone the Repository
```bash
git clone https://github.com/chisomjude/student-project-tracker.git
cd student-project-tracker
```

### 2. Create Virtual Environment & Install Dependencies
```bash
python3 -m venv venv
source venv/bin/activate  # On Windows use: venv\Scripts\activate
pip install -r requirements.txt
```

### 3.Db Conenctions
- At this stage you need to export your vault credentials given :

```export VAULT_ADDR=
   export VAULT_TOKEN=
```

### 4. Run the Application Locally
```bash
uvicorn app.main:app --host 0.0.0.0 --port 8000 --reload
```
Visit `http://vmip:8000` to see your app in action.

---

## 🐳 Docker Instructions

### 1. Build Docker Image
write a dockerfile to build the app, your dockerfile should sit at the root directory of this project - ie student-project-tracker

```bash
docker build -t student-tracker .
```

### 2. Run Docker Container
- At this stage you need to export your vault credentials before you run the app to ensure the app can access vault, the run the command below to run the app

```bash
docker run --env-file .env -p 8000:8000 student-tracker
```

### 3. Push to Docker Hub
Ensure you're logged in, create a account with dockerhub if you dont have one.
```bash
docker login
```
Tag and push your image:
```bash
docker tag student-tracker your-dockerhub-username/student-tracker

docker push your-dockerhub-username/student-tracker
```

---

## 📬 API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST   | `/register?name=YourName` | Register new student |
| GET    | `/status/{student_id}`    | View registration and progress |
| POST   | `/update/{student_id}?week=week1` | Update progress by week |

---

## 🌐 Deploying to Cloud (Optional)
You can deploy the app on platforms like:
- Render
- Railway
- Fly.io
- Azure App Service
- Elastic Beanstalk or more


## 👩🏽‍💻 Built for the Cloud Native Series by Chisom
This project is used for learning cloud-native tools and Handson-Project.

Feel free to fork and extend it!
