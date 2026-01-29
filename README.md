# CC Lab 2 – Monolithic Architecture

**Course:** Cloud Computing
**Lab:** Monolithic Architecture
**Student SRN:** PES1UG24CS801

---

## 📌 Objective

The objective of this lab is to understand **Monolithic Architecture**, its advantages, limitations, and performance challenges by:

* Building a single FastAPI-based monolithic application
* Demonstrating how a single bug can crash the entire system
* Performing load testing using Locust
* Optimizing slow routes and observing performance improvements

---

## 🧱 Application Overview

This Fest Management System is implemented as a **monolithic application**, where:

* UI
* Business logic
* Database access

are all part of a **single codebase and single deployment unit**.

### Features

* User Registration & Login
* Event Listing
* Event Registration
* My Events Dashboard
* Checkout Page

---

## ⚙️ Tech Stack

* **FastAPI** – Backend framework
* **SQLite** – Database
* **Jinja2** – HTML templating
* **Locust** – Load testing tool
* **Python 3**

---

## 📂 Project Structure

```
CC Lab-2/
│
├── checkout/               # Checkout logic
├── locust/                 # Locust load test files
├── templates/              # HTML templates
├── database.py
├── insert_events.py
├── main.py
├── requirements.txt
├── fest.db
└── README.md
```

---

## ▶️ How to Run the Application

### 1. Create virtual environment

```bash
python3 -m venv .venv
source .venv/bin/activate
```

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

### 3. Initialize database

```bash
python insert_events.py
```

### 4. Run the server

```bash
uvicorn main:app --reload
```

Server will run at:

```
http://127.0.0.1:8000
```

---

## 🌐 Application Routes

| Route        | Description                  |
| ------------ | ---------------------------- |
| `/register`  | User registration            |
| `/login`     | User login                   |
| `/events`    | View all events              |
| `/my-events` | View registered events       |
| `/checkout`  | Checkout and payment summary |

---

## 💥 Monolithic Failure Demonstration

* A deliberate bug was introduced in the `/checkout` module.
* Accessing `/checkout` resulted in a **500 Internal Server Error**.
* This demonstrated how a **single failure can crash the entire monolithic system**.

---

## 🧪 Load Testing (Locust)

Locust was used to simulate concurrent users accessing application routes.

### Tested Routes

* `/checkout`
* `/events`
* `/my-events`

Load tests were performed:

* Before optimization
* After optimization

---

## 🚀 Optimizations Performed

### Route: `/events`

* **Bottleneck:** Unnecessary CPU-intensive loop
* **Fix:** Removed redundant computation
* **Result:** Reduced response time

### Route: `/my-events`

* **Bottleneck:** Artificial delay using a dummy loop
* **Fix:** Removed the dummy loop
* **Result:** Faster request processing

---

## 📸 Screenshots Included

* SS1 – Events page loaded
* SS2 – Monolithic crash
* SS3 – Bug fixed
* SS4 – Checkout load test (before)
* SS5 – Checkout load test (after)
* SS6 – Events route (before)
* SS7 – Events route (after)
* SS8 – My-events route (before)
* SS9 – My-events route (after)

---

## ✅ Conclusion

This lab demonstrates that although monolithic applications are easy to build and deploy initially, they:

* Have a **single point of failure**
* Become difficult to scale
* Are sensitive to performance bottlenecks

This explains why modern systems often evolve toward **microservices architecture**.

---

## 👨‍💻 Author

**Abhishek M Hiremath**
**SRN:** PES1UG24CS801

GitHub: [https://github.com/Abhi-DevHub](https://github.com/Abhi-DevHub)

---

## 📤 Git Commands Used

```bash
git status
git add .
git commit -m "CC Lab 2: Monolithic architecture implementation"
git push origin main
```

---
