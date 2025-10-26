# AutoCA

A smart expense management system with JWT authentication, OCR invoice reading, and expense forecasting.
The system allows users to track income/expenses, scan invoices, and get financial insights through a clean dashboard.



# Project Structure:

backend/                → Node.js + Express API (JWT Auth, MongoDB)

frontend/expense-tracker → React SPA (Axios, Protected Routes)

ai_services/            → FastAPI microservices

   ├─ ocr_api.py        → OCR + invoice parsing + auto-category
   
   └─ forecast_api.py   → Time-series forecasting & insights
   
backend/eng.traineddata → Tesseract traineddata (OCR)

# Features:

1.Category	Features

2.Core App	Add income/expenses, monthly reports, secure login

3.Security	JWT-based authentication (Bearer Token flow)

4.OCR AI	Upload invoice → extract amount → auto-categorize

5.Forecasting AI	Predict future expenses + highlight spending patterns

6.Dashboard	Visual summaries, insights, and clean UI


# AI Logic:

Module	Techniques:

1.OCR	pdfplumber + Tesseract (pytesseract), regex extraction

2.Classification	Keyword rules + TF-IDF + Logistic Regression fallback

3.Forecasting	Pandas + Exponential Smoothing (Holt-Winters)

4.User feedback is stored and used to improve categorization over time (mini-learning loop).

# Authentication (JWT)

Login returns { token, user }

Token is stored 

Axios auto-injects Authorization: Bearer <token>

401 = instant logout + redirect to /login


# Tech Stack

Frontend: React (Axios, React Router), CSS

Backend: Node.js, Express, MongoDB, JWT

AI Microservices: Python, FastAPI, pandas, scikit-learn, pdfplumber, pytesseract, statsmodels

# Quick Start (Local Setup)

1.Backend:

cd backend

npm install

npm run dev


Runs at: http://localhost:5000

2.Frontend:

cd frontend/expense-tracker

npm install

npm run dev


Runs at: http://localhost:3000

3.AI Services:

cd ai_services

uvicorn ai_services.ocr_api:app --host 0.0.0.0 --port 8001 --reload

uvicorn ai_services.forecast_api:app --host 0.0.0.0 --port 5005 --reload


# Troubleshooting

make sure the backend in connected successfully

make sure that the frontend , backend and microservices are running on the proper port 

OCR incorrect → check Tesseract installation + raw text output

401 errors → verify token in localStorage and Bearer header

Forecast fail → add more transaction history


# Future Enhancements

1.More Accurate forecasting model:

         a. Logical and useful Insights from financial analysis 

         b. Any recipts and handwritting recognition

         c. Integrate a RAG model for insights and forecast

2.Cloud deployment 


.....

 
 
 
 
 
# Status...

The current forecasting model lacks accuracy, need to optimize the model.

This is an active, evolving project focused on personal finance automation using MERN and AI microservices.




