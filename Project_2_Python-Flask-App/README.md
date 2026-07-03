✅ Practice 3 — Python Flask App (Intermediate)

📌 Project structure

app/
 ├─ app.py
 ├─ requirements.txt
 └─ Dockerfile


📌 app.py

from flask import Flask
app = Flask(__name__)

@app.route("/")
def home():
    return "Hello from Flask in Docker!"

if __name__ == "__main__":
    app.run(host="0.0.0.0")


📌 requirements.txt

flask


📌 Dockerfile

FROM python:3.9-slim
WORKDIR /app
COPY requirements.txt .
RUN pip install -r requirements.txt
COPY . .
CMD ["python", "app.py"]


🔹 Build & Run

docker build -t flask-app .
docker run -d --name falst-app -p 5000:5000 flask-app


Test the URl : publicip:5000