# 10. Map Local

## Purpose

Map Local is used to replace the actual server response with a local file stored on the tester's machine.

It helps QA engineers perform:

* Mock Testing
* Frontend Testing
* Backend Independent Testing
* Edge Case Testing
* UI Validation
* Test Data Simulation

---

# Request Flow

## Normal Flow

```text id="m1"
Mobile/App
    ↓
Server
    ↓
Response
    ↓
Mobile/App
```

## Map Local Flow

```text id="m2"
Mobile/App
    ↓
Charles Proxy
    ↓
Local JSON File
    ↓
Mobile/App
```

Server response is replaced by a local file.

---

# Test URL

```text id="m3"
https://jsonplaceholder.typicode.com/todos/1
```

Normal Response:

```json id="m4"
{
  "userId": 1,
  "id": 1,
  "title": "delectus aut autem",
  "completed": false
}
```

---

# Create Local JSON File

File Name:

```text id="m5"
todo_local.json
```

Content:

```json id="m6"
{
  "userId": 999,
  "id": 999,
  "title": "Sameer Local Mock Response",
  "completed": true
}
```

Save the file.

---

# How To Apply Map Local

## Step 1

Capture the request:

```text id="m7"
https://jsonplaceholder.typicode.com/todos/1
```

---

## Step 2

Right Click Request

Select:

```text id="m8"
Map Local
```

---

## Step 3

Browse and select:

```text id="m9"
todo_local.json
```

Click:

```text id="m10"
OK
```

---

## Step 4

Refresh the URL:

```text id="m11"
https://jsonplaceholder.typicode.com/todos/1
```

---

# Expected Result

Instead of server response:

```json id="m12"
{
  "userId": 1,
  "id": 1
}
```

You receive:

```json id="m13"
{
  "userId": 999,
  "id": 999,
  "title": "Sameer Local Mock Response",
  "completed": true
}
```

---

# Verification

This proves:

```text id="m14"
Response came from local file
```

and not from the server.

---

# How To Remove Map Local

Navigate:

```text id="m15"
Tools
→ Map Local
```

Select the mapping.

Click:

```text id="m16"
Remove
```

Click:

```text id="m17"
OK
```

---

# Verification After Removal

Refresh:

```text id="m18"
https://jsonplaceholder.typicode.com/todos/1
```

Original server response should appear again.

---

# Important Difference

| Feature    | Purpose                           |
| ---------- | --------------------------------- |
| Breakpoint | Manual modification every request |
| Rewrite    | Automatic modification            |
| Map Local  | Replace response using local file |

---

# Interview Question

What is Map Local in Charles Proxy?

Answer:

Map Local is used to replace a server response with a local file stored on the tester's machine. It helps QA engineers perform mock testing, frontend validation, and testing without depending on backend services.

---

# Real-Time Scenario

Backend API is not ready.

Frontend team needs data for testing.

QA creates:

```text id="m19"
todo_local.json
```

Maps it to:

```text id="m20"
/todos/1
```

Frontend receives mock data and testing can continue without waiting for backend completion.

```
```
