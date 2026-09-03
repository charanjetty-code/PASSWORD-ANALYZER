# PASSWORD-ANALYZER
# 🔒 Password Security & Analyzer Tool

A lightweight, high-performance web application designed to evaluate password strength, compute information entropy, and generate cryptographically secure passwords in real time. Built using native web technologies with zero external dependencies.

---

## 📌 Project Overview

This project was developed for **[Your Internship / Organization Name]** to demonstrate client-side cryptographic principles, security analysis algorithms, and interactive UI/UX design. 

Unlike traditional analyzers that send raw passwords across a network (exposing credentials to transit risks), this tool performs **100% client-side analysis** using the browser's native Web Crypto API.

---

## ✨ Key Features

* **Real-time Entropy Analysis:** Calculates information entropy ($E = L \times \log_2(R)$) dynamically on every keystroke.
* **Visual Strength Meter:** Maps bits of entropy to an intuitive, color-coded progress bar (Very Weak to Strong).
* **Character Complexity Checks:** Validates passwords against character pool requirements (uppercase, lowercase, numbers, special symbols).
* **Hash-based Reuse Prevention:** Simulates local historical password tracking using client-side SHA-256 hashes (`crypto.subtle.digest`).
* **Cryptographic Generator:** Uses CSPRNG (`window.crypto.getRandomValues`) to output high-entropy alternative passwords with a one-click copy function.
* **Zero Dependencies:** Pure Vanilla HTML5, CSS3, and JavaScript — no external frameworks or npm libraries required.

---

## ⚙️ How the Security Logic Works

### 1. Information Entropy Formula
Entropy measures unpredictable randomness in bits:
$$E = L \times \log_2(R)$$

* **$L$** = Length of the password
* **$R$** = Pool size of character sets used:
  * Lowercase letters ($a-z$): 26
  * Uppercase letters ($A-Z$): 26
  * Numbers ($0-9$): 10
  * Special characters ($!\dots=$): 32

### 2. Strength Thresholds

| Entropy (Bits) | Strength Rating | Security Level |
| :--- | :--- | :--- |
| **< 28 bits** | Very Weak | Vulnerable to instant brute-force |
| **28 – 35 bits** | Weak | Vulnerable to offline dictionary attacks |
| **36 – 59 bits** | Reasonable | Moderate protection |
| **60+ bits** | Strong | High resistance to parallelized cracking |

---

## 🚀 Live Demo & Installation

### Option 1: Access Live Deployment
Try the hosted web application:  
👉 **[Live Demo Link](https://YOUR-GITHUB-USERNAME.github.io/YOUR-REPO-NAME/)**

### Option 2: Local Execution
No installation or server setup is required.

1. Clone the repository:
   ```bash
   git clone [https://github.com/YOUR-GITHUB-USERNAME/YOUR-REPO-NAME.git](https://github.com/YOUR-GITHUB-USERNAME/YOUR-REPO-NAME.git)
