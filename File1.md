# Charles Proxy Revision Notes

# 1. Mobile Connection Setup

## Purpose

Connect Mobile and Laptop through Charles Proxy to capture network traffic.

## Steps

1. Connect Laptop and Mobile to the same Wi-Fi network.
2. Install Charles Proxy on Windows.
3. Configure Mobile Proxy Settings.

Example:

```text
Host : <Laptop IP Address>
Port : 8888
```

4. Save settings.
5. Charles will show:

```text
Allow Connection?
```

6. Click:

```text
Allow
```

## Verification

Open any website from mobile.
I took for Testing is https://jsonplaceholder.typicode.com/posts

Traffic should appear in Charles Proxy.

---

# 2. SSL Proxying (HTTPS Decryption)

## Purpose

Decrypt HTTPS traffic and view actual Request and Response data.

## Steps

Navigate:

```text
Proxy
→ SSL Proxying Settings
```

Enable:

```text
✓ Enable SSL Proxying
```

Add:

```text
Host : *
Port : 443
```

## Verification

Open:

```text
https://jsonplaceholder.typicode.com/posts
```

If SSL Proxying is working:

* Request headers are visible
* Response JSON is visible
* HTTPS traffic is decrypted

## Interview Question

What is SSL Proxying?

Answer:

SSL Proxying is used to decrypt HTTPS traffic so that requests and responses can be viewed, analyzed, and modified for testing and debugging purposes.

---

# 3. Filtering

## Purpose

Used to find specific APIs quickly from large amounts of traffic.

## Example

Filter:

```text
jsonplaceholder
```

Only matching traffic is displayed.

## Interview Question

Why do we use Filters in Charles Proxy?

Answer:

Filters are used to quickly locate specific domains, APIs, requests, or responses from a large amount of captured network traffic.

---

# 4. Repeat Request

## Purpose

Resend an already captured request without performing the action again in the application.

## Steps

1. Select a request.
2. Right Click.
3. Select:

```text
Repeat
```

Charles sends the request again.

---

## Request Flow

Normal Flow

```text
Mobile
   ↓
Charles
   ↓
Server
   ↓
Charles
   ↓
Mobile
```

Repeat Flow

```text
Charles
   ↓
Server
   ↓
Charles
```

Charles itself becomes the client and sends the request directly to the server.

---

## Interview Question

What is Repeat in Charles Proxy?

Answer:

Repeat = Charles itself becomes the client and sends the same request to the server again.

Repeat is used to resend an existing request without performing the action again in the application. It helps in debugging and retesting APIs quickly.

```
```
