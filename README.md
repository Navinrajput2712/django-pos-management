📌 Django POS Management Application

A lightweight and efficient Point of Sale (POS) management system built with Django. This web-based system helps businesses manage daily sales transactions, products, categories, and reports efficiently.

🚀 Features
🔹 Product Management

Add, update, delete products

Manage pricing and availability

🔹 Category Management

Organize products under categories

🔹 Sales Transactions

Add sales entries

System automatically generates unique transaction codes

View daily sales and transaction history

🔹 Dashboard

Displays today’s transactions

Shows total sales amount

Quick summary of business performance

🔹 User Authentication

Login page for secure access

Admin panel for managing all data

🛠️ Getting Started

Follow these instructions to set up and run the project on your local machine.

📁 Project Setup Guide
1️⃣ Create & Activate Virtual Environment
python -m venv venv
venv\Scripts\activate      # Windows
source venv/bin/activate   # macOS/Linux

2️⃣ Install Python Dependencies

Install all required packages:

pip install -r requirements.txt

3️⃣ Apply Migrations
python manage.py makemigrations
python manage.py migrate

4️⃣ Create Superuser (Admin Login)
python manage.py createsuperuser


Enter:

Username

Email

Password

5️⃣ Start the Django Server
python manage.py runserver


Backend runs on:
👉 http://127.0.0.1:8000

🌐 Frontend (If Included)

If the project contains a frontend folder:

Install Node.js dependencies:
npm install

Start React/JS frontend:
npm start


Frontend usually runs on:
👉 http://localhost:3000

📂 Available Scripts
Command	Description
python manage.py runserver	Run Django backend
npm start	Run frontend (if included)
