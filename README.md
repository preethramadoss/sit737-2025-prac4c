**Calculator Major Project Microservice**


**Overview**
This microservice provides basic arithmetic operations (**addition, subtraction, multiplication, division**) along with **advanced operations** like **exponentiation, square root, and modulo** using REST API endpoints. It is built using **Node.js** and **Express**, with **Winston** for logging requests and errors.


**Project Structure**

**Installation & Setup**

**Prerequisites**
Ensure you have:
-> [Node.js](https://nodejs.org/en/download/) installed (v14 or later).
-> [Git](https://git-scm.com/) installed.
-> A code editor like **VS Code**.

**Step 1: Clone the Repository**
git clone https://github.com/preethramadoss/sit737-2025-prac4c.git
cd sit737-2025-prac4c

**Step 2: Install Dependencies**
npm install

**Step 3: Run the Server**
node server.js
Your API is now running at http://localhost:3040.

**API Endpoints & Usage**
Each endpoint accepts query parameters (n1 and n2).

**Addition**
Request:
GET http://localhost:3040/add?n1=10&n2=5
Response:
{ "statuscode": 200, "data": 15 }

**Subtraction**
Request:
GET http://localhost:3040/sub?n1=20&n2=5
Response:
{ "statuscode": 200, "data": 15 }

**Multiplication**
Request:
GET http://localhost:3040/mul?n1=3&n2=4
Response:
{ "statuscode": 200, "data": 12 }

**Division**
Request:
GET http://localhost:3040/div?n1=10&n2=2
Response:
{ "statuscode": 200, "data": 5 }

**Handling Division by Zero**
GET http://localhost:3040/div?n1=10&n2=0
Response:
{ "statuscode": 500, "msg": "Cannot divide by zero" }

**Advanced Operations**
**Exponentiation (/exp)**
Request:
GET http://localhost:3040/exp?n1=2&n2=3
Calculation:
2^3 = 8
Response:
{ "statuscode": 200, "data": 8 }

**Square Root (/sqrt)**
Request:
GET http://localhost:3040/sqrt?n1=25
Calculation:
√25 = 5
Response:
{ "statuscode": 200, "data": 5 }

**Handling Negative Input for Square Root**
GET http://localhost:3040/sqrt?n1=-9
**Response:**
{ "statuscode": 200, "data": "Square root of negative number is not allowed" }

**Modulo (/mod)**
Request:
GET http://localhost:3040/mod?n1=10&n2=3
Calculation:
10 % 3 = 1
Response:
{ "statuscode": 200, "data": 1 }

**Handling Modulo by Zero**
GET http://localhost:3040/mod?n1=10&n2=0
Response:
{ "statuscode": 500, "msg": "Modulus by zero is not allowed" }

**Error Handling**
**Error Case	Example Request	Response**
Missing n1 or n2	/add?n1=10	{ "statuscode": 500, "msg": "Invalid input values" }
Non-numeric input	/add?n1=abc&n2=5	{ "statuscode": 500, "msg": "Invalid input values" }
Division by zero	/div?n1=10&n2=0	{ "statuscode": 500, "msg": "Cannot divide by zero" }

**Logging**
This project uses Winston to log:

Requests to logs/combined.log
Errors to logs/error.log

**Example Log Entries
Successful Request:**
{"level":"info","message":"New add operation requested: 10 and 5","service":"calculator-project"}

**Error (Invalid Input):**
{"level":"error","message":"Invalid value for n1","service":"calculator-project"}

**How to Update & Push Changes to GitHub**
Step 1: Commit & Push Your Code
git add .
git commit -m "Added calculator microservice"
git push origin main

Step 2: Verify on GitHub
Visit: https://github.com/preethramadoss/sit737-2025-prac4c
Ensure all files are correctly uploaded.
