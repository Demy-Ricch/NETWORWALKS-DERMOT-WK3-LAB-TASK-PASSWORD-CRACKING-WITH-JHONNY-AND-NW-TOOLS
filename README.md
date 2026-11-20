# NETWORWALKS-DERMOT-WK3-LAB-TASK-PASSWORD-CRACKING-WITH-JHONNY-AND-NW-TOOLS
# Week 3 Lab: PDF Hash Extraction & Dictionary Password Cracking

## 📌 Overview
This lab focuses on offline password recovery and vulnerability assessment for encrypted PDF documents. Using **John the Ripper (Johnny GUI)** and the **Networkwalks Hash Calculator / Password Cracker** lab environment, encrypted PDF hashes were extracted and subjected to dictionary attacks to recover plaintext passwords and capture target flags.

## 🛠️ Tools & Environment
* **Cracking Suite:** John the Ripper (`john` / Johnny GUI)[cite: 2]
* **Hash Extraction:** Networkwalks Hash Calculator (`pdf2john` / Hashcat-compatible `$pdf$` format)[cite: 6]
* **Attack Vector:** Offline Dictionary Attack (Built-in & Custom Wordlists)[cite: 4, 5]
* **Target Files:** `My-Locked-PDF1.pdf`, `My-Locked-PDF2.pdf`[cite: 1, 3]

## 🔍 Lab Workflow

### 1. Hash Extraction
* Inspected the encrypted PDF files (`My-Locked-PDF1.pdf` — Revision R4, Version V4, 128-bit key length)[cite: 6].
* Extracted the crackable `$pdf$` hash string locally without uploading sensitive file contents[cite: 6].

### 2. Dictionary Attack Execution
* Loaded the extracted `$pdf$` hash into **Johnny (John the Ripper GUI)** and the **Networkwalks Password Cracker**[cite: 2, 4, 5].
* Ran a dictionary attack matching hashed wordlist candidates against the target PDF hash[cite: 4, 5].
* **Recovered Password (Target 1):** `password1`[cite: 2, 5]

### 3. Verification & Flags Captured
Unlocked both PDF documents using the recovered credentials to verify access and retrieve the lab completion flags:
* **Flag 1 (`My-Locked-PDF1.pdf`):** `nw{networkwalks_flag1_jtr_270521_1}`[cite: 1]
* **Flag 2 (`My-Locked-PDF2.pdf`):** `nw{networkwalks_persistence_jtr_270521}`[cite: 3]

## 🛡️ Defensive Takeaways & Mitigation
* **Avoid Common Wordlist Passwords:** Simple, predictable passwords (`password1`) are immediately compromised by basic dictionary attacks[cite: 2, 5].
* **Enforce High Entropy:** Use long passphrases (14+ characters) combining random words, symbols, and numbers to make offline dictionary and brute-force attacks computationally infeasible.
* **Modern Encryption Standards:** Utilize AES-256 encryption over older RC4/128-bit schemes where supported.

---
*Disclaimer: All techniques and tools documented in this repository were performed strictly within an authorized educational lab environment provided by Networkwalks Academy[cite: 1, 5].*
