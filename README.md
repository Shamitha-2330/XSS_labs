# SocialSphere Security Labs: XSS Vulnerability Demos

## What Is This Project?

This project is an interactive way to learn about Cross-Site Scripting (XSS) vulnerabilities through hands-on practice. It contains six labs, each demonstrating a different type of XSS vulnerability. The labs allow users to experiment with real-world XSS exploitation techniques and explore proper mitigation strategies. The project is inspired by the PortSwigger Web Security Academy.

## Live Demo

You can try the labs online by visiting the live demo:

**[SocialSphere XSS Labs on Netlify](https://681daefb576dd64136636a37--venerable-figolla-744090.netlify.app/)**

## Features

* Test six types of XSS vulnerabilities: reflected, DOM-based, and stored.
* Learn how attackers exploit web apps using tools like Burp Suite.
* Understand how to fix XSS issues with secure coding techniques.
* Practice web security skills in a safe and controlled environment.

## Prerequisites

To run this project locally, you will need:

* A web browser (Chrome, Firefox, etc.)
* Git to clone the repository
* Visual Studio Code (VS Code) for editing and running the project
* Burp Suite to analyze and test XSS vulnerabilities

## Installation and Setup

### Step 1: Clone the Repository

Open your terminal in VS Code and run:

```bash
git clone https://github.com/Shamitha-2330/XSS_Labs.git
cd SocialSphere-XSS-Labs
```

### Step 2: Open in VS Code

* Launch Visual Studio Code.
* Open the project folder via `File > Open Folder`.

### Step 3: Install Recommended Extensions

Open the Extensions tab in VS Code and install:

* Live Server
* Prettier
* ESLint (optional)

### Step 4: Run the Project

* Right-click `index.html` and select **"Open with Live Server"**.
* Your browser will open to `http://localhost:5500`.

## Usage

### Explore the Labs

Each HTML file represents a different XSS lab:

* `easy-vuln.html`: Easy XSS Lab (search feature)
* `medium-vuln.html`: Medium XSS Lab (search results)
* `difficult-vuln.html`: Difficult XSS Lab (profile bio)
* `easy2-vuln.html`: Easy Lab 2 (comment section)
* `medium2-vuln.html`: Medium Lab 2 (feedback form)
* `very-difficult-vuln.html`: Difficult Lab 2(group chat)

Start from `index.html` or `labs.html` and explore each vulnerability.

### Test XSS Payloads

Use test payloads such as:

```html
<script>alert('XSS')</script>
```

Or try URI-based payloads:

```html
javascript:alert('XSS')
```

Use [Burp Suite](https://portswigger.net/burp) to intercept and manipulate requests for deeper testing.

## How to Find the Vulnerabilities

1. Open Burp Suite and configure your browser to use it as a proxy.
2. Submit input in the lab forms or search boxes (e.g., "test").
3. Intercept the HTTP request and modify the parameters with payloads.
4. Observe the reflected output in the response or page DOM.
5. Confirm whether the payload executes or is improperly rendered.

## How to Fix the XSS Problems

### 1. Sanitize User Input

Use libraries like DOMPurify to remove or neutralize harmful HTML.

```javascript
outputElement.innerHTML = DOMPurify.sanitize(userInput);
```

### 2. Avoid `innerHTML`

Use `textContent` instead to insert plain text, not HTML.

```javascript
outputElement.textContent = userInput;
```

### 3. Implement Content Security Policy (CSP)

Add a strong CSP header to prevent inline scripts:

```http
Content-Security-Policy: script-src 'self'
```

### 4. Validate Input on Server and Client Side

Ensure all input follows the expected format. Reject anything suspicious.

### 5. Avoid Dangerous Patterns

Do not use JavaScript features that allow DOM manipulation with untrusted input.

### 6. Keep Testing

Regularly scan and test your applications using Burp Suite or similar tools.

## Project Structure

```
SocialSphere-XSS-Labs/
├── index.html
├── labs.html
├── easy-vuln.html
├── medium-vuln.html
├── difficult-vuln.html
├── easy2-vuln.html
├── medium2-vuln.html
├── very-difficult-vuln.html
├── very-difficult-desc.html
└── assets/
```


## Acknowledgments

* Inspired by the PortSwigger Web Security Academy.
* Thanks to my teachers and peers for their support.
