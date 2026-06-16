# Sameer_CharlesProxy
# Charles Proxy Mobile Setup Guide

## Step 1 - Connect Devices

1.  Connect Laptop and Mobile to the same Wi‑Fi network.

## Step 2 - Install Charles Proxy

1.  Download and install Charles Proxy on Windows.

## Step 3 - Install Charles Certificate on Windows

1.  Open Charles Proxy.
2.  Help → SSL Proxying → Install Charles Root Certificate.
3.  Select **Current User**.
4.  Click **Next**.
5.  Select **Automatically Select the Certificate Store**.
6.  Click **Finish**.
7.  Verify message: **The import was successful**.

## Step 4 - Get Charles IP Address

1.  Help → SSL Proxying → Install Charles Root Certificate on a Mobile
    Device or Remote Browser.
2.  Note down the IP and Port.

Example: - IP: 192.168.29.56 - Port: 8888

## Step 5 - Export Certificate

1.  Help → SSL Proxying → Save Charles Root Certificate.
2.  Save as **Certificate (.pem)**.
3.  Send the PEM file to mobile using:
    -   Gmail
    -   WhatsApp
    -   Google Drive
    -   USB

## Step 6 - Configure Proxy in Mobile

1.  Open Wi‑Fi Settings.

2.  Select connected Wi‑Fi.

3.  Click Settings icon.

4.  Click Pencil/Edit icon.

5.  Open Advanced Options.

6.  Set Proxy = Manual.

7.  Enter:

    Host: 192.168.29.56

    Port: 8888

8.  Click Save.

## Step 7 - Allow Device in Charles

1.  Charles will display:
    -   Allow Connection?
2.  Click Allow.

## Step 8 - Install Certificate in Android

1.  Settings → Security & Privacy → Encryption & Credentials.
2.  Install a Certificate.
3.  Select CA Certificate.
4.  Choose the downloaded PEM certificate.
5.  Install certificate.

## Step 9 - Enable SSL Proxying

1.  Proxy → SSL Proxying Settings.
2.  Enable SSL Proxying.
3.  Add:
    -   Host: \*
    -   Port: 443
4.  Click OK.

## Step 10 - Verify

1.  Open any HTTPS website from mobile.
2.  Requests should appear in Charles.
3.  HTTPS request and response data should be visible.

## Success Criteria

-   Mobile connected to Charles Proxy
-   SSL Certificate installed
-   HTTPS traffic visible
-   Ready for API Testing
