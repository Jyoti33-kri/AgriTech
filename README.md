🌱 AgriTech — Smart Farming Solutions

AgriTech Banner

SWoC 2026 License: MIT PRs Welcome

📚 Table of Contents

Overview

Quick Start

Application Preview

System Architecture

Core Features

Tech Stack
Project Structure
Backend vs Frontend
Security & Reliability
Environment Variables
Roadmap
Contribution Flow
Team
Contributing & Support
Contributors
Production Deployment
API Keys Guide
Reporting Issues
License
FAQ
⚠️ Note: For production deployment, use a WSGI server like gunicorn instead of Flask's built-in server.

⚠️ Never commit your .env file or API keys to the repository. Always keep secrets private!

AgriTech is an AI-powered smart agriculture platform designed to assist farmers with crop recommendations, yield prediction, plant disease detection, and community-driven collaboration—enabling sustainable and data-driven farming practices.

📌 Overview
AI-driven decision support for modern agriculture
Early-stage plant disease detection
Crop yield forecasting using machine learning models
Collaborative ecosystem for farmers and stakeholders
🚀 Quick Start
1️⃣ Clone the Repository
git clone https://github.com/omroy07/AgriTech.git
cd AgriTech
2️⃣ Run Backend (Primary – Flask)
pip install -r requirements.txt
python app.py
Backend URL:

http://localhost:5000
🔍 Backend Health Check

GET http://localhost:5000/health
Expected response:

{ "status": "ok" }
3️⃣ Run Frontend

cd src/frontend
python -m http.server 8000
Frontend URL:

http://localhost:8000
Note: Backend and frontend must be running simultaneously for proper functionality.

🖥️ Application Preview
AgriTech Dashboard AgriTech Dashboard

AgriTech Dashboard AgriTech Dashboard

🏗️ System Architecture
User Input: Soil data and plant images
Backend Processing: Flask APIs and model routing
ML Inference:
CNNs for disease detection
Random Forest / XGBoost for crop recommendation
Regression models for yield prediction
Output: Predictions with insights and actions
🌟 Core Features
🌾 Crop Recommendation
📉 Yield Prediction
🔬 Disease Detection
� AI Chatbot - Platform guidance & agriculture support
�🤝 Farmer Community
🛒 Shopkeeper Listings
🤖 AI Chatbot
AgriTech's AI-powered chatbot provides comprehensive support for farmers:

Features
Platform Guidance: Explains how to use all AgriTech features and tools
Agriculture Support: Answers farming questions, crop recommendations, pest control
Decision Making: Provides region-specific, season-based farming advice
Image Analysis: Upload plant photos for disease detection and diagnosis
24/7 Support: Always available for instant farming assistance
Technical Implementation
Dual Mode: AI-powered (Google Gemini) + Rule-based fallback
Smart Matching: Fuzzy search with keyword analysis for accurate responses
Offline Capability: Works without internet using JSON-based responses
Image Processing: Analyzes plant photos for disease identification
Usage
# Start the chatbot server
npm install
node server.js

# Access at: http://localhost:3000/chat
API Endpoints
POST /api/chat - Send messages and images for AI analysis
🛠️ Tech Stack
🎨 Frontend
HTML5
CSS3
JavaScript (ES6)
⚙️ Backend
Python (Flask)
Node.js (Optional)
🤖 Machine Learning
TensorFlow
Scikit-learn
OpenCV
🗄️ Database & DevOps
MySQL
MongoDB
Firebase
Docker
GitHub Actions
📂 Project Structure
AGRITECH/
├── app.py                      # 🐍 Flask Backend (Main entry point)
├── server.js                   # 🟢 Node.js Chatbot Server
├── package.json                # Node.js dependencies
├── requirements.txt            # Python dependencies
├── firebase.js                 # Firebase config fetching
├── 📁 chatbot/
│   ├── chat.html               # 🤖 Chatbot interface
│   ├── chat.js                 # Chatbot client logic
│   ├── chat.css                # Chatbot styling
│   ├── json-chatbot.js         # Rule-based chatbot engine
│   └── chatbot-responses.json  # Predefined responses
├── 📁 src/
│   └── 📁 frontend/            # 🌐 Frontend UI (HTML, CSS, JS)
│       ├── 📁 pages/           # Individual page files
│       ├── 📁 css/             # Stylesheets
│       └── 📁 js/              # Client-side scripts
├── 📁 Crop Recommendation/   # 🌾 Crop recommendation module
├── 📁 Disease Prediction/     # 🔬 Disease detection module
├── 📁 Crop Yield Prediction/   # 📊 Yield forecasting module
├── 📁 Community/               # 💬 community/forum backend
├── 📁 images/                  # 📸 Screenshots and assets
├── 📄 README.md                # This file
└── 📄 CONTRIBUTING.md          # Contribution guidelines
Backend vs Frontend
Backend (app.py at root): Flask server handling APIs, Firebase config
Frontend (src/frontend/): Static HTML/CSS/JS served via Python HTTP server
Optional Node Server (server.js): Alternative chat backend (not required)
🔐 Security & Reliability
Image sanitization using OpenCV
Secrets stored in .env files
ML models evaluated using standard performance metrics (accuracy varies by model and dataset)
⚙️ Environment Variables
GEMINI_API_KEY=your_api_key
FIREBASE_API_KEY=your_key
FIREBASE_AUTH_DOMAIN=your_project.firebaseapp.com
FIREBASE_PROJECT_ID=your_project_id
FIREBASE_STORAGE_BUCKET=your_bucket.appspot.com
FIREBASE_MESSAGING_SENDER_ID=your_sender_id
FIREBASE_APP_ID=your_app_id
FIREBASE_MEASUREMENT_ID=your_measurement_id
🛣️ Roadmap
Cloud Deployment
Mobile Application
Real-Time Weather API
AI Chatbot ✅ COMPLETED
Multilingual Support
🤝 Contribution Flow
Fork → Clone → Branch → Commit → Push → Pull Request → Review → Merge
Read CONTRIBUTING.md for SWoC 2026 guidelines.

👥 Team
Name	Role
Om Roy	Project Lead · Web · ML
Shubhangi Roy	ML · Backend
🤝 Contributing & Support
We love contributions! Please read our CONTRIBUTING.md to get started with SWoC 2026 tasks. Whether it's fixing bugs, adding features, or improving documentation, your help is always welcome!

✨ Contributors
Thanks to all the wonderful people contributing to this project! 💖
Contributors

View full contribution graph

For production use, run the backend with a WSGI server like gunicorn:

pip install gunicorn
gunicorn app:app
🔑 API Keys Guide
Gemini API Key: Google AI Studio se generate karein.
Firebase Keys: Firebase Console se apne project ke liye keys lein.
API keys ko .env file me store karein (kabhi bhi repo me commit na karein).
🐞 Reporting Issues
Found a bug or want a new feature? Open an issue.

📄 License
This project is licensed under the MIT License.

🛠️ Common Issues & Fixes
❌ ModuleNotFoundError 👉 Run pip install -r requirements.txt

❌ Firebase config error 👉 Ensure .env values match Firebase Console

❌ CORS issue 👉 Make sure backend runs before frontend

❌ Port already in use 👉 Change port in app.py or stop previous process

❓ FAQ
Q: The project is not running. What should I do? A: Make sure all Python dependencies are installed, the .env file is properly configured, and the correct API keys are being used.

Q: How do I get a Gemini/Firebase API key? A: Refer to the “API Keys Guide” section above for step-by-step instructions.

Q: I am seeing the warning “This is a development server…” on the Flask server. What does it mean? A: This server is intended only for development. For production, use a WSGI server such as Gunicorn.

Q: I accidentally pushed my .env file. What should I do? A: Immediately rotate/regenerate your API keys, remove the .env file from Git tracking, add it to .gitignore, and clean the repository history if required.

Q: The /health endpoint is not responding. What could be wrong? A: Ensure the backend server is running correctly and that the /health route is properly implemented.

Made with ❤️ by the AgriTech Community — SWoC 2026

About
AgriTech is an AI-powered web platform that offers crop recommendations, yield prediction, disease detection, and collaborative tools to empower farmers and promote smart, sustainable agriculture.

agri-tech-6rs5.vercel.app/
Topics
flask machine-learning sustainability ai agriculture web-application yield-prediction smart-farming plant-disease-detection crop-recommendation
Resources
 Readme
License
 MIT license
Code of conduct
 Code of conduct
Contributing
 Contributing
Security policy
 Security policy
 Activity
Stars
 89 stars
Watchers
 0 watching
Forks
 227 forks
Report repository
Releases
No releases published
Packages
No packages published
Contributors
133
@omroy07
@SatyamPandey-07
@Khushi5155
@Sunidhi037
@Eshajha19
@trivedikavya
@pratyushjha06
@Adez017
@Baibhab-Adhikari
@janavipandole
@Swetagupta05
@ShubhangiRoy12
@keshripritesh
@MadhuTiwari-345
+ 119 contributors
Deployments
500+
 Production – agri-tech 40 minutes ago
 Production – agri-tech-6rs5 38 minutes ago
+ more deployments
Languages
Jupyter Notebook
78.9%
 
HTML
9.5%
 
Python
4.2%
 
CSS
4.0%
 
JavaScript
3.4%
 
Batchfile
0.0%
Footer
© 2026 GitHub, Inc.
Footer navigation
Terms
Privacy
Security
Statu
