# 11. Rewrite Tool

## Purpose

Rewrite Tool is used to automatically modify requests or responses before they reach the server or application.

Unlike Breakpoints, Rewrite works automatically without stopping the request.

---

# Difference Between Breakpoint and Rewrite

## Breakpoint

```text
Request
   ↓
Pause
   ↓
Manual Modification
   ↓
Execute
   ↓
Server
```

Requires manual intervention every time.

---

## Rewrite

```text
Request
   ↓
Rewrite Rule Applied Automatically
   ↓
Modified Request
   ↓
Server
```

No popup.

No manual action.

Automatic execution.

---

# Real-Time Example

Original URL:

```text
https://jsonplaceholder.typicode.com/posts?userId=1
```

Original Response:

```json
{
  "userId": 1,
  "id": 1
}
```

---

# Goal

Automatically convert:

```text
userId=1
```

to:

```text
userId=2
```

before sending the request to the server.

---

# Rewrite Configuration

Navigate:

```text
Tools
→ Rewrite
```

Enable:

```text
✓ Enable Rewrite
```

---

# Add Rewrite Set

Name:

```text
UserId Rewrite
```

---

# Add Location

Host:

```text
jsonplaceholder.typicode.com
```

---

# Add Rule

Type:

```text
Modify Query Param
```

---

# Match Section

Name:

```text
userId
```

Value:

```text
1
```

---

# Replace Section

Name:

```text
userId
```

Value:

```text
2
```

---

# Request Flow

Browser sends:

```text
/posts?userId=1
```

Charles automatically changes:

```text
/posts?userId=2
```

Server receives:

```text
/posts?userId=2
```

---

# Verification

Open:

```text
https://jsonplaceholder.typicode.com/posts?userId=1
```

Browser URL still shows:

```text
userId=1
```

But response contains:

```json
{
  "userId": 2,
  "id": 11
}
```

This proves Rewrite Tool modified the request successfully.

---

# Before Rewrite

Request:

```text
/posts?userId=1
```

Response:

```json
{
  "userId": 1,
  "id": 1
}
```

---

# After Rewrite

Request Sent By Browser:

```text
/posts?userId=1
```

Request Sent By Charles:

```text
/posts?userId=2
```

Response:

```json
{
  "userId": 2,
  "id": 11
}
```

---

# Interview Question

What is Rewrite Tool in Charles Proxy?

Answer:

Rewrite Tool is used to automatically modify requests and responses without manually stopping the traffic. It helps QA engineers test different scenarios by changing URLs, query parameters, headers, and payloads dynamically.

---

# Real-Time Use Cases

* Change User IDs
* Change Query Parameters
* Modify API URLs
* Modify Request Headers
* Simulate Different Users
* Test Different Backend Responses
* Perform Automatic Request Manipulation

---

# Key Learning

Browser requested:

```text
userId=1
```

Charles automatically changed it to:

```text
userId=2
```

Server returned User 2 data.

This confirmed that the Rewrite Rule was successfully applied.

```
```
