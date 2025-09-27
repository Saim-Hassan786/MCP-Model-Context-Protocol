# 📘 REST API Basics with Python (`requests`)

This project demonstrates how to work with REST APIs using Python’s `requests` library. It focuses on both **REST theory** and **practical implementation**, making it useful for beginners looking to understand how RESTful services work and how to interact with them programmatically.


## 📌 What is REST?

**REST** stands for **Representational State Transfer**. It’s not a software or protocol, but a **set of rules (architecture style)** for designing **scalable, reliable, and efficient** web services.

Introduced by **Roy Fielding in 2000**, REST helps build web applications that work smoothly over the internet by following certain principles.


## 🧱 Core Principles of REST

REST has **6 core principles** that guide how the client (frontend) and server (backend) interact:

### 1. 🧍‍♂️ Client-Server Architecture

* The **client** and **server** are independent.
* Client requests data; the server processes and responds.
* Both can be updated separately without affecting each other.

### 2. ❌ Statelessness

* Each request is independent.
* The server does **not remember previous requests**.
* This makes the system more scalable and easier to manage.

### 3. 🧠 Cacheability

* The server tells the client whether it can **store the response** (cache it).
* Reduces repeated requests and improves performance.

### 4. 🧑‍💻 Code on Demand (Optional)

* The server can send **executable code** (like JavaScript) to the client.
* Rarely used, but can add extra functionality without updating the whole client.

### 5. 🏗️ Layered System

* The client doesn’t need to know how many layers (e.g., load balancer, security) exist between it and the server.
* Makes the system **modular and scalable**.

### 6. 🔗 Uniform Interface

A consistent way of interacting between client and server. It includes:

* **Resource Identification**: Every piece of data is identified by a URL.
* **Manipulation via Representations**: The client interacts with data through representations (usually JSON).
* **Self-descriptive Messages**: Each request/response contains all the information needed (like headers, status codes).
* **HATEOAS**: The server guides the client through available actions using links in responses.


## 🔁 Idempotence

An operation is **idempotent** if repeating it gives the same result every time:

* ✅ `GET`, `PUT`, `DELETE`, `OPTIONS`, `HEAD` — Idempotent
* ❌ `POST` — Not idempotent (creates a new resource each time)
* ⚠️ `PATCH` — May or may not be idempotent depending on how it’s used


## 🧪 Code Demonstration

### ✅ 1. `GET` Request – Fetch a Post

```python
get_post(post_id)
```

* Uses `GET` method to fetch a post from `https://jsonplaceholder.typicode.com/posts/{id}`
* Prints status, post title, and content.

### ✅ 2. `POST` Request – Create a Post

```python
create_post(title, body, user_id)
```

* Uses `POST` method to create a new post.
* Sends a JSON payload to the server.
* Prints status and response details.

> Example Response:

```json
{
  "title": "My New Post",
  "body": "Myself Saim hassan AKhtar",
  "userId": 123,
  "id": 101
}
```

> Even though the resource isn’t actually saved on the placeholder API, it **simulates** a successful post creation.


## 📦 Requirements

* Python 3.x
* `requests` library

Install it using:

```bash
pip install requests
```


## 📚 Summary

This project:

* Explains **REST architecture** in simple terms.
* Demonstrates how to use Python to **consume** REST APIs.
* Teaches the use of `GET` and `POST` requests with real-world examples.


## 🧑‍💻 Author

**Saim Hassan Akhtar**
Aspiring AI Engineer
💬 *"Learning by doing — one API call at a time."*


Would you like me to generate a `.md` version of this README for GitHub?

