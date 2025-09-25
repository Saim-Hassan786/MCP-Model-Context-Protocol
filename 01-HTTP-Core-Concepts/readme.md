# HTTP Protocol – Concepts & Practical Examples

This repository provides a **theoretical overview of HTTP (Hypertext Transfer Protocol)** along with **practical examples** using tools like `curl` and the Python `requests` library.

The aim is to explain HTTP in simple terms and demonstrate how to send and handle HTTP requests programmatically.


## 📖 What is HTTP?

**HTTP (Hypertext Transfer Protocol)** is the protocol that enables communication between computers over the internet. It is mainly used to transmit hypermedia documents such as HTML, JSON, and other structured data.

Without HTTP, computers would be like *staring at each other* without being able to communicate.


## 🌐 Core HTTP Concepts

### 1. HTTP Request-Response Cycle

* **Client (e.g., browser)** establishes a connection with the **server**.
* Connection is built over **TCP/IP** (HTTP/1.x, 2) or **QUIC/UDP** (HTTP/3).
* Request includes:

  * Method (GET, POST, etc.)
  * Target URL
  * HTTP Version
  * Headers
  * Body (optional)
* Server processes the request and sends a response with:

  * HTTP Version
  * Status Code (200, 404, etc.)
  * Reason Phrase
  * Headers
  * Body (optional)

Connections may close or stay alive based on `Connection: keep-alive`.


### 2. Structure of HTTP

```
Start-Line   → Request: (Method, URI, Version) | Response: (Version, Status, Reason)
Headers      → Extra info like Content-Type, Cache-Control
Empty Line   → CRLF separator
Body         → Data (HTML, JSON, etc.)
```


### 3. HTTP Methods

* `GET` → Retrieve data
* `POST` → Submit data / create resource
* `PUT` → Replace resource
* `PATCH` → Update part of resource
* `DELETE` → Delete resource
* `HEAD` → Get only headers
* `OPTIONS` → Show allowed methods


### 4. HTTP Status Codes

* **1xx** → Informational
* **2xx** → Success
* **3xx** → Redirection
* **4xx** → Client Error
* **5xx** → Server Error


### 5. Stateless Architecture

HTTP is **stateless** → each request is independent, and servers don’t remember previous ones.


### 6. HTTP Headers

* **General Headers** → (Date, Connection)
* **Request Headers** → (User-Agent, Accept)
* **Response Headers** → (Content-Type, Server)
* **Entity Headers** → (Content-Length)


## ⚡ HTTP Evolution

1. **HTTP/0.9** → Only GET, no headers, single connection
2. **HTTP/1.0** → Headers + multiple methods, but new TCP connection per request
3. **HTTP/1.1** → Persistent connections (Keep-Alive), but HOL blocking issue
4. **HTTP/2.0** → Multiplexing over TCP, but packet loss blocks streams
5. **HTTP/3.0** → QUIC over UDP, faster and independent packet streams


## 🔐 HTTP with Security

HTTP is insecure by itself. Security is added via **TLS (Transport Layer Security)**, forming **HTTPS** (default on port 443).


## 🛠️ Practical Examples

### 1. Using `curl`

```bash
# Simple GET request
curl https://example.com/

# API request with headers
curl https://reqres.in/api/users?page=2 \
 -H "x-api-key: reqres-free-v1"
```

### 2. Using Python `requests`

#### GET Request

```python
import requests

url = "https://example.com/"
headers = {"Content-Type": "text/html"}

response = requests.get(url, headers=headers)
print("Status Code:", response.status_code)
print("Response:", response.text)
```

#### POST Request

```python
url = "https://reqres.in/api/users/2"
headers = {"x-api-key": "reqres-free-v1", "Content-Type": "application/json"}
body = {"name": "saim", "job": "software engineer"}

response = requests.post(url, headers=headers, json=body)
print("Status Code:", response.status_code)
print("Response:", response.json())
```

#### PUT / PATCH / DELETE / HEAD / OPTIONS

All major HTTP methods are demonstrated in the examples included in the repo.


## 🚀 How to Run

1. Clone the repository:

   ```bash
   git clone https://github.com/<your-username>/<repo-name>.git
   cd <repo-name>
   ```
2. Open in **Google Colab** or run Python scripts locally.
3. Make sure to install dependencies:

   ```bash
   pip install requests
   ```


## 🎯 Purpose

This repository is designed for:

* Beginners learning **HTTP fundamentals**
* Developers practicing **API requests**
* Students exploring **protocol evolution and networking basics**



