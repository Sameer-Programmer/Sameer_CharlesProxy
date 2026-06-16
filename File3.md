# 8. Block List (API Failure Simulation)

## Purpose

Block List is used to prevent requests from reaching the server.

It helps QA engineers test:

* No Internet scenarios
* API failures
* Retry mechanisms
* Error messages
* Offline handling
* Graceful degradation

---

# Request Flow

## Normal Flow

```text
Mobile/App
    ↓
Charles Proxy
    ↓
Server
    ↓
Charles Proxy
    ↓
Mobile/App
```

## Blocked Flow

```text
Mobile/App
    ↓
Charles Proxy
    X
Server
```

Request never reaches the server.

---

# Test URL

```text
https://jsonplaceholder.typicode.com/todos/1
```

Expected Normal Response:

```json
{
  "userId": 1,
  "id": 1,
  "title": "delectus aut autem",
  "completed": false
}
```

---

# How To Apply Block List

## Step 1

Open Charles Proxy.

Navigate:

```text
Tools
→ Block List
```

---

## Step 2

Enable:

```text
✓ Enable Block List
```

---

## Step 3

Click:

```text
Add
```

---

## Step 4

Enter:

```text
Host:
jsonplaceholder.typicode.com
```

Path:

```text
/ todos / 1
```

(Without spaces)

```text
/todos/1
```

Click:

```text
OK
```

---

# Testing

Open:

```text
https://jsonplaceholder.typicode.com/todos/1
```

Expected Result:

* No response received
* Request blocked
* Error displayed
* API failure simulated

Possible Errors:

```text
ERR_CONNECTION_RESET
```

or

```text
Request Failed
```

or

```text
No Response
```

---

# Verification

In Charles Proxy:

Request appears as blocked.

The request never reaches the server.

---

# Remove Block List

Navigate:

```text
Tools
→ Block List
```

Either:

```text
Uncheck Enable Block List
```

OR

```text
Delete the Block Rule
```

---

# Interview Question

What is Block List in Charles Proxy?

Answer:

Block List is used to prevent requests from reaching the server. It helps QA engineers test API failures, offline scenarios, retry functionality, and application behavior when backend services are unavailable.

---

# Real-Time Scenario

Scenario:

User clicks:

```text
Load Todo Details
```

API:

```text
https://jsonplaceholder.typicode.com/todos/1
```

Using Block List:

```text
jsonplaceholder.typicode.com
```

is blocked.

Validation:

✓ Error message displayed

✓ Retry button displayed

✓ Application does not crash

✓ User-friendly message shown

This simulates a backend outage without disconnecting the internet.

```
```
