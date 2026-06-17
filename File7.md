# 12. Compose

## Purpose

Compose is used to manually create and send HTTP requests directly from Charles Proxy without performing actions in the application.

It works similar to Postman.

---

# Request Flow

```text
Tester
   ↓
Charles Compose
   ↓
Server
   ↓
Response
```

Application is not required.

---

# Uses

* API Testing
* Request Modification
* Debugging APIs
* Testing Different Endpoints
* Sending Custom Requests
* Verifying Backend Responses

---

# Practical Example

Original Request:

```text
https://jsonplaceholder.typicode.com/todos/1
```

---

# Steps

### Step 1

Capture a request.

Example:

```text
https://jsonplaceholder.typicode.com/todos/1
```

---

### Step 2

Right Click Request

```text
Compose
```

---

### Step 3

Modify URL

```text
https://jsonplaceholder.typicode.com/todos/2
```

---

### Step 4

Click:

```text
Execute
```

---

# Expected Response

```json
{
  "userId": 1,
  "id": 2,
  "title": "quis ut nam facilis et officia qui",
  "completed": false
}
```

---

# Interview Question

What is Compose in Charles Proxy?

Answer:

Compose is used to manually create and send HTTP requests directly from Charles Proxy without using the application. It helps testers verify APIs and debug backend services quickly.

---

# Real-Time Scenario

Suppose the application login is failing.

QA captures the Login API.

Using Compose:

```text
Modify Username
Modify Password
Execute
```

QA can validate API behavior without opening the application.

================================================================

# 13. Map Remote

## Purpose

Map Remote is used to redirect requests from one server to another server.

The application thinks it is calling one server, but Charles silently redirects the request to another server.

---

# Request Flow

## Normal Flow

```text
Application
      ↓
Production Server
      ↓
Response
```

---

## Map Remote Flow

```text
Application
      ↓
Charles Proxy
      ↓
QA/UAT Server
      ↓
Response
```

---

# Practical Example

Original Request:

```text
https://jsonplaceholder.typicode.com/todos/1
```

---

# Map Remote Configuration

## From

Protocol:

```text
https
```

Host:

```text
jsonplaceholder.typicode.com
```

Path:

```text
/todos/1
```

---

## To

Protocol:

```text
https
```

Host:

```text
jsonplaceholder.typicode.com
```

Path:

```text
/todos/2
```

---

# Steps

### Step 1

Navigate:

```text
Tools
→ Map Remote
```

---

### Step 2

Click:

```text
Add
```

---

### Step 3

Configure:

```text
FROM:
/todos/1

TO:
/todos/2
```

---

### Step 4

Enable:

```text
✓ Enable Map Remote
```

---

### Step 5

Open:

```text
https://jsonplaceholder.typicode.com/todos/1
```

---

# Verification

Original Response:

```json
{
  "id": 1,
  "title": "delectus aut autem"
}
```

Mapped Response:

```json
{
  "id": 2,
  "title": "quis ut nam facilis et officia qui"
}
```

This confirms Map Remote redirected the request.

---

# Difference Between Rewrite and Map Remote

| Rewrite                   | Map Remote                          |
| ------------------------- | ----------------------------------- |
| Modifies request/response | Redirects request to another server |
| Same server               | Different server/environment        |
| Changes parameters/body   | Changes destination                 |

---

# Interview Question

What is Map Remote in Charles Proxy?

Answer:

Map Remote is used to redirect requests from one server to another server. It helps QA engineers test QA, UAT, or Mock environments without changing application configurations.

---

# Real-Time Scenario

Production API:

```text
api.prod.company.com
```

QA API:

```text
api.qa.company.com
```

Using Map Remote:

```text
api.prod.company.com
↓
api.qa.company.com
```

The application continues to use the Production URL while Charles redirects traffic to the QA environment.

```
```
