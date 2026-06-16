# 9. Network Throttling

## Purpose

Network Throttling is used to simulate slow internet conditions by intentionally delaying network traffic.

It helps QA engineers test:

* Slow Internet
* Weak Network
* API Delays
* Loader Visibility
* Timeout Handling
* Retry Functionality
* Application Stability

---

# Request Flow

## Normal Network

```text id="a1"
Mobile/App
    ↓
Server
    ↓
Response (500ms)
```

## Throttled Network

```text id="a2"
Mobile/App
    ↓
Server
    ↓
Response (5-20 seconds)
```

Charles intentionally slows down the network traffic.

---

# How To Enable

Navigate:

```text id="a3"
Proxy
→ Throttle Settings
```

Enable:

```text id="a4"
✓ Enable Throttling
```

Click:

```text id="a5"
OK
```

---

# Test URL

```text id="a6"
https://jsonplaceholder.typicode.com/todos/1
```

---

# Expected Result

Normal:

```text id="a7"
Response < 1 second
```

Throttled:

```text id="a8"
Response 5-20 seconds
```

---

# What We Observed

Response Times:

```text id="a9"
3 Seconds
13 Seconds
17 Seconds
```

---

# Loader Validation

Observed:

```text id="a10"
Horizontal Loader
```

during slow response.

Validation:

✓ Loader appears

✓ Loader disappears after response

✓ App remains responsive

✓ No crash

---

# How To Disable

Navigate:

```text id="a11"
Proxy
→ Throttle Settings
```

Disable:

```text id="a12"
Enable Throttling
```

---

# Interview Question

What is Network Throttling in Charles Proxy?

Answer:

Network Throttling is used to simulate slow internet conditions by intentionally delaying network traffic. It helps QA engineers validate loaders
