
# 🌌 Chronicalc

**Chronicalc** is a space-themed, AI-powered interactive web app built with Python Flask and SQLite. It features:

* 🚀 A calculator set in a 3D cosmic background
* 👽 A World UFO Day quiz with voice narration
* 📊 A lightweight backend that stores user scores
* 🌍 Responsive design for both desktop and mobile
* 🗣️ Text-to-speech for quiz questions (gTTS)

---

## 📸 Screenshots

### 🔢 Calculator Interface

### 🛸 Quiz Interface

### 🌌 Background Visual

---

## 🌐 Live Demo

🔗 https://raghuvarandbecse32.github.io/Chronicalc/
---

## 🛠 Tech Stack

* **Frontend:** HTML, CSS, JS, Three.js, responsive design
* **Backend:** Python Flask
* **Database:** SQLite
* **AI Tools:** gTTS for narration, OpenAI-ready
* **Deployment:** Render.com

---

## 🧪 Quiz Topics

1. What does UFO stand for?
2. When is World UFO Day celebrated?
3. What year was the Roswell Incident?
4. Who directed "Close Encounters of the Third Kind"?
5. Where is Area 51 located?
6. Project Blue Book conducted by?
7. Who wrote "War of the Worlds"?
8. First use of "Flying Saucer"
9. UFO Hotspot State in the US

Voice narration plays for each question using Python's gTTS.

---

## 📁 Folder Structure

```
chronicalc/
├── app.py
├── database.db
├── generate_voice.py
├── templates/
│   ├── index.html
│   ├── quiz.html
│   └── intro.html
├── static/
│   ├── css/style.css
│   ├── js/quiz.js
│   ├── js/three.min.js
│   ├── js/space.js
│   └── assets/
│       ├── milkyway-bg.jpg
│       ├── ufo.png
│       └── audio/ (gTTS audio)
├── .gitignore
├── README.md
├── render.yaml
└── requirements.txt
```

---

## 🧠 AI + Voice (gTTS)

### `generate_voice.py`

```python
from gtts import gTTS
import os

questions = [
    "What does UFO stand for?",
    "When is World UFO Day celebrated?",
    "What year was the Roswell Incident?",
    "Who directed Close Encounters of the Third Kind?",
    "Where is Area 51 located?",
    "Project Blue Book was conducted by which organization?",
    "Who wrote The War of the Worlds?",
    "Who coined the term Flying Saucer?",
    "Which state is the UFO hotspot in the USA?"
]

os.makedirs("static/assets/audio", exist_ok=True)

for i, question in enumerate(questions):
    tts = gTTS(question)
    path = f"static/assets/audio/q{i+1}.mp3"
    tts.save(path)
    print(f"Saved: {path}")
```

---

## 📜 .gitignore

```
__pycache__/
*.pyc
*.db
.env
*.mp3
static/assets/audio/*
```

---

## 📝 Git Commit Message

```
git commit -m "🚀 Add UFO quiz with gTTS narration, intro page, Three.js visuals, and optimized UI"
```

---

## 🌐 Deployment on Render

1. Create `render.yaml`:

```yaml
services:
  - type: web
    name: chronicalc
    env: python
    buildCommand: "pip install -r requirements.txt"
    startCommand: "python app.py"
    plan: free
```

2. Push your code to GitHub
3. Go to [render.com](https://render.com)
4. Click **New Web Service** > **Connect to GitHub**
5. Select your repo and add `render.yaml`

---

## 📱 Responsive UI & Performance Optimizations

* Minified JS and CSS where possible
* Responsive design using Flexbox and media queries
* Optimized image sizes and lazy loading
* Single HTTP request for question set in JS

---

## 🌌 HTML Intro Page Included: `intro.html`

Project Title: Chronicalc Challenge Overview: Create an immersive web app that narrates astronomical concepts, integrates 3D visuals and calculates while educating users via themed quizzes. Team: Raghuvaran Damodaran - Code Developer and Video Editor

➡️ Use this as a landing page or welcome intro before the main app!

---

## 💡 How to Run in VS Code

1. Open VS Code and open the `chronicalc/` folder.
2. Create a virtual environment:

   ```bash
   python -m venv venv
   source venv/bin/activate  # or venv\Scripts\activate on Windows
   ```
3. Install requirements:

   ```bash
   pip install -r requirements.txt
   ```
4. Generate quiz narration audio:

   ```bash
   python generate_voice.py
   ```
5. Run the app:

   ```bash
   python app.py
   ```
6. Visit `http://localhost:5000/intro` for the intro, or `/` for calculator, `/quiz` for quiz.

---

## 📜 License

MIT License

---

## ✨ Credits

* Flask, SQLite
* gTTS (Google Text-to-Speech)
* NASA Milky Way imagery
* Open Source Fonts and Icons
