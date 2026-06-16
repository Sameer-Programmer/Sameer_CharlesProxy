# Charles Proxy - Breakpoints Notes

## What is a Breakpoint?

A Breakpoint in Charles Proxy is used to pause an HTTP/HTTPS request or response before it reaches the server or the mobile application.

It allows QA engineers to:

* Inspect requests
* Modify requests
* Inspect responses
* Modify responses
* Simulate edge cases
* Test application behavior

---

# Request and Response Flow

Normal Flow:

```text
Mobile/App
    ↓
Server
    ↓
Mobile/App
```

Breakpoint Flow:

```text
Mobile/App
    ↓
Charles Proxy (Pause)
    ↓
Execute
    ↓
Server
    ↓
Charles Proxy (Pause)
    ↓
Execute
    ↓
Mobile/App
```

---

# How To Apply Breakpoint

## Step 1

Open Charles Proxy.

## Step 2

Capture a request.

Example:

```text
/posts
```

## Step 3

Right Click on the request.

Select:

```text
Breakpoints
```

Breakpoint is now enabled.

---

# How To Test

Refresh the page or trigger the API again.

Charles will stop the request.

---

# Request Breakpoint Window

First popup:

```text
Edit Request
```

Purpose:

* View request headers
* Modify request path
* Modify query parameters
* Modify request body

Example:

Original:

```text
:path: /posts
```

Modified:

```text
:path: /posts?userId=5
```

Click:

```text
Execute
```

Request is sent to server.

---

# Response Breakpoint Window

Second popup:

```text
Edit Response
```

Purpose:

* View response JSON
* Modify response data
* Simulate backend responses

Example:

Original:

```json
{
  "userId": 1,
  "title": "Original Title"
}
```

Modified:

```json
{
  "userId": 999,
  "title": "Modified Through Charles"
}
```

Click:

```text
Execute
```

Modified response is sent to mobile/app.

---

# What We Practiced

## Response Modification

Modified:

```json
"userId": 999
```

Observed modified data on mobile.

Result:

Charles changed the response before it reached the application.

---

## Request Modification

Original:

```text
/posts
```

Modified:

```text
/posts?userId=5
```

Response received:

```json
"userId": 5
```

Result:

Server processed the modified request and returned filtered data.

---

# Important Interview Point

Response Modification:

* QA controls final output.

Request Modification:

* Backend controls final output based on modified input.

---

# Interview Question

What are Breakpoints in Charles Proxy?

Answer:

Breakpoints are used to pause HTTP/HTTPS requests and responses. They allow testers to inspect, modify, delay, or block network traffic before it reaches the server or the application.

```
```
