Extract Monitor Dashboard
A simple dashboard built using:

HTML
CSS
JavaScript
FastAPI
JSON Log Files
Project Structure
project/

├── index.html

├── css/
│   └── style.css

├── js/
│   └── script.js

├── logs/
│   ├── Execution_Extract/
│   ├── Portfolio_Extract/
│   └── TimeBox_Extract/

└── backend/
    ├── main.py
    ├── requirements.txt
    └── services/
        └── file_reader.py
Step 1 - Create Virtual Environment
Navigate to backend folder:

cd backend
Create virtual environment:

python -m venv venv
Activate virtual environment.

Windows
venv\Scripts\activate
Linux / Mac
source venv/bin/activate
Step 2 - Install Dependencies
Install required packages:

pip install -r requirements.txt
Or install manually:

pip install fastapi uvicorn python-multipart
Verify installation:

pip list
Step 3 - Run FastAPI Backend
Start FastAPI server:

uvicorn main:app --reload
Expected output:

INFO:     Uvicorn running on http://127.0.0.1:8000
INFO:     Application startup complete
Step 4 - Verify Backend APIs
Health Check
Open:

http://127.0.0.1:8000/
Response:

{
    "status": "UP"
}
Applications API
Open:

http://127.0.0.1:8000/applications/2026-10-05
Summary API
Open:

http://127.0.0.1:8000/summary/2026-10-05
Application Details API
Open:

http://127.0.0.1:8000/application/Execution_Extract/2026-10-05
Step 5 - Run Frontend
Open a new terminal at project root.

Example:

cd project
Start a simple HTTP server:

python -m http.server 5500
Expected output:

Serving HTTP on :: port 5500
Step 6 - Open Dashboard
Open browser:

http://localhost:5500
Dashboard will load and fetch data from:

http://127.0.0.1:8000
Development Workflow
Start Backend
cd backend

venv\Scripts\activate

uvicorn main:app --reload
Start Frontend
Open another terminal:

cd project

python -m http.server 5500
Open Browser
http://localhost:5500
Stop Application
Stop backend:

CTRL + C
Stop frontend:

CTRL + C
Deactivate virtual environment:

deactivate
Common Issues
Module Not Found
Install dependencies:

pip install -r requirements.txt
Port Already In Use
Run FastAPI on another port:

uvicorn main:app --reload --port 8001
Update API URLs inside:

js/script.js
Example:

http://127.0.0.1:8001
Dashboard Shows No Data
Verify logs exist:

logs/
├── Execution_Extract/
├── Portfolio_Extract/
└── TimeBox_Extract/
Verify API:

http://127.0.0.1:8000/applications/2026-10-05
If API returns data, dashboard should display records.

Default URLs
Backend:

http://127.0.0.1:8000
Frontend:

http://localhost:5500
Dashboard:

http://localhost:5500/index.html
