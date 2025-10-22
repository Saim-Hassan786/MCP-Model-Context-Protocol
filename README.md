## 1. HTTP Core Concepts

### Overview
The **HyperText Transfer Protocol (HTTP)** is the foundational protocol of the web.  
It defines how clients (usually browsers or applications) and servers exchange messages over the internet.

### Key Principles

- **Client–Server Model:**  
  The client sends a request; the server processes and returns a response.

- **Statelessness:**  
  Each request is independent — the server does not retain client context between requests.
  (State must be managed externally, e.g., with cookies, sessions, or tokens.)

- **Request–Response Cycle:**  
  - A client initiates a request with an HTTP **method** (`GET`, `POST`, `PUT`, `DELETE`, etc.)  
  - The server returns a **status code** and **response body**.

- **Methods (Verbs):**
  | Method | Purpose |
  |---------|----------|
  | `GET` | Retrieve data |
  | `POST` | Submit data or create a resource |
  | `PUT` | Update or replace a resource |
  | `PATCH` | Partially update a resource |
  | `DELETE` | Remove a resource |

- **Status Codes:**
  | Range | Meaning | Example |
  |--------|----------|---------|
  | 1xx | Informational | 100 Continue |
  | 2xx | Success | 200 OK |
  | 3xx | Redirection | 301 Moved Permanently |
  | 4xx | Client Error | 404 Not Found |
  | 5xx | Server Error | 500 Internal Server Error |

### Core Headers
HTTP headers provide meta-information for requests and responses, such as:
- `Content-Type`: format of the body (e.g., `application/json`)
- `Authorization`: credentials or tokens
- `Cache-Control`: caching policies


## 2. REST Architecture

### Overview
**REST (Representational State Transfer)** is an architectural style that applies HTTP’s principles to design web APIs.  
Defined by Roy Fielding’s dissertation (2000), REST emphasizes *simplicity, scalability,* and *uniform interfaces.*

### REST Constraints

1. **Client–Server:**  
   Separation of user interface (client) and data storage (server).

2. **Statelessness:**  
   Each request must contain all necessary information — the server stores no client context.

3. **Cacheable:**  
   Responses must define if they are cacheable to improve network efficiency.

4. **Uniform Interface:**  
   Consistent, predictable interactions using standard HTTP methods and media types.

5. **Layered System:**  
   Clients need not know if they’re connected directly to the end server or through intermediaries.

6. **Optional: Code-on-Demand:**  
   Servers can extend client functionality by sending executable code (e.g., JavaScript).

### Resource Orientation
- **Resources** are key entities (e.g., users, orders, posts).  
- Each resource is identified by a **URI** (e.g., `/api/users/1`).  
- **Representations** (usually JSON) describe the resource state.

### Benefits
- Simplicity and scalability  
- Clear use of HTTP methods and status codes  
- Easy integration and interoperability

### Limitations
- Stateless overhead (must resend context)  
- Not ideal for real-time or bidirectional communication  
- Ambiguity in versioning and partial updates


## 3. JSON-RPC

### Overview
**JSON-RPC** (JSON Remote Procedure Call) is a *lightweight* remote procedure call protocol encoded in JSON.  
It enables communication between a client and server by invoking named methods with parameters.

Unlike REST, JSON-RPC focuses on *actions (methods)* rather than *resources.*

### Core Characteristics

- **Transport-Agnostic:**  
  Usually runs over HTTP or WebSockets, but not limited to them.

- **Request Structure:**
  ```json
  {
    "jsonrpc": "2.0",
    "method": "subtract",
    "params": [42, 23],
    "id": 1
  }

