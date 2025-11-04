# Cryptography Introduction - TryHackMe Room Writeup

![TryHackMe](https://img.shields.io/badge/TryHackMe-Cryptography_Introduction-red)
![Domain](https://img.shields.io/badge/Domain-Cryptography-blue)
![Difficulty](https://img.shields.io/badge/Difficulty-Beginner-green)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)
![Category](https://img.shields.io/badge/Category-Cybersecurity-yellow)

This repository contains my personal notes and answers from the **Cryptography Introduction** room on TryHackMe. This room provides a foundational understanding of core cryptographic concepts, from ancient ciphers to modern protocols like TLS.

## 📚 Room Overview

The room is structured into several tasks, each focusing on a different area of cryptography:

*   **Task 1:** Introduction & Classical Ciphers (Caesar, Substitution, Transposition)
*   **Task 2:** Symmetric Encryption (AES, GPG, OpenSSL)
*   **Task 3:** Asymmetric Encryption (RSA)
*   **Task 4:** Diffie-Hellman Key Exchange
*   **Task 5:** Hashing & HMAC
*   **Task 6:** PKI and SSL/TLS
*   **Task 7:** Authenticating with Passwords
*   **Task 8:** Cryptography in Practice

---

## 🗝️ My Notes & Key Insights

### Task 1: Introduction
This task was a great warm-up, revisiting historical ciphers. It solidified my understanding of why these methods are obsolete.
*   **Caesar Cipher:** A simple substitution cipher with a very small keyspace (only 25 possible keys), making it vulnerable to brute-force attacks.
*   **Mono-alphabetic Substitution:** While having a massive keyspace (`26!` possibilities), it's easily broken by **frequency analysis** of letters in a language.
*   **Transposition Cipher:** This cipher doesn't substitute letters but rearranges them according to a key. It was interesting to see a cipher that operates on the position of characters rather than their identity.

### Task 2: Symmetric Encryption
Here, I learned about modern symmetric ciphers and got hands-on with encryption tools.
*   **Core Concept:** A single, shared secret key is used for both **encryption and decryption**.
*   **Algorithms:** DES is broken, but **AES** (with 128, 192, or 256-bit keys) is the modern standard and considered secure.
*   **Block vs. Stream Ciphers:** AES is a block cipher (processes data in fixed-size blocks), while algorithms like ChaCha20 are stream ciphers (process data bit-by-bit).
*   **Hands-On Practice:** I used `gpg` and `openssl` to encrypt and decrypt files, which was crucial for understanding the practical application.
    *   **GPG Command:** `gpg --symmetric --cipher-algo AES256 --armor -o encrypted.txt.gpg message.txt`
    *   **OpenSSL Command:** `openssl aes-256-cbc -pbkdf2 -iter 10000 -e -in message.txt -out encrypted_message`

### Task 3: Asymmetric Encryption
This was a paradigm shift from a single shared key to a key pair.
*   **Core Concept:** Uses a **public key** (shared with everyone) and a **private key** (kept secret).
    *   **Confidentiality:** Encrypt with the recipient's *public* key. Only their *private* key can decrypt it.
    *   **Authenticity/Non-Repudiation:** "Sign" a message by encrypting its hash with your *private* key. Anyone can verify it with your *public* key, proving it came from you.
*   **RSA:** The most well-known asymmetric algorithm. Its security relies on the computational difficulty of factoring large prime numbers.
*   **Hands-On Practice:** I used OpenSSL to generate an RSA key pair and perform encryption/decryption, which made the theory much more concrete.
    *   **Generate Key Pair:** `openssl genrsa -out private.pem 2048` & `openssl rsa -in private.pem -pubout -out public.pem`

### Task 4: Diffie-Hellman Key Exchange
This task solved a critical problem: how to establish a shared secret over an insecure channel.
*   **Core Concept:** Allows two parties to jointly establish a shared secret over a public channel. The magic lies in modular exponentiation; even if an eavesdropper sees all the exchanged values, they cannot feasibly calculate the shared secret.
*   **The Weakness:** The classic Diffie-Hellman is vulnerable to a **Man-in-the-Middle (MitM)** attack because the exchanged values are not authenticated. This flaw is what makes **PKI (Task 6)** necessary.

### Task 5: Hashing
Hashing is fundamental for data integrity and password storage.
*   **Core Concept:** A one-way function that takes input of any size and produces a fixed-size "digest" or "checksum".
*   **Properties:** A small change in the input creates a completely different, unpredictable hash (avalanche effect).
*   **Algorithms:** **MD5** and **SHA-1** are broken. **SHA-256** and **SHA-3** are current secure standards.
*   **HMAC:** A mechanism that uses a cryptographic key in conjunction with a hash function to provide both integrity and authenticity for a message.

### Task 6: PKI and SSL/TLS
This task tied everything together, showing how asymmetric crypto, hashing, and symmetric crypto work in concert to secure web traffic.
*   **PKI (Public Key Infrastructure):** A framework that uses **Certificate Authorities (CAs)** as trusted third parties to vouch for the ownership of public keys via **digital certificates**.
*   **SSL/TLS Handshake:** The process that uses PKI and asymmetric encryption to securely negotiate a symmetric session key, which is then used for fast and secure communication.
*   **Hands-On Practice:** I inspected a certificate file using `openssl x509 -in cert.pem -text -noout`, which helped me understand the contents of a real-world X.509 certificate.

### Task 7: Authenticating with Passwords
This task highlighted the importance of proper password storage.
*   **Never Store Plaintext Passwords.**
*   **Hashing is not enough** due to **rainbow tables**. The solution is to use a **salt**—a random value unique to each password—before hashing.
*   **Key Derivation Functions (KDFs)** like **PBKDF2** are essential. They intentionally make the hashing process slow and computationally expensive to resist brute-force attacks.

---

## 💡 My Recommendations & Self-Insights

1.  **Don't Skip the Math (Completely):** While you don't need to be a mathematician, having a high-level intuition for concepts like modular arithmetic (for RSA and Diffie-Hellman) makes the "why" much clearer.
2.  **Get Hands-On:** The real learning happened when I used `gpg` and `openssl` in the terminal. Theory is essential, but practice cements understanding.
3.  **Connect the Dots:** The most valuable insight was seeing how all these concepts (symmetric, asymmetric, hashing, PKI) are not isolated but are combined to build secure systems like HTTPS. Understanding the role of each part is key.
4.  **Security is a Chain:** This room reinforced that security is only as strong as its weakest link. Using AES-256 is pointless if you're using a weak key exchange or storing passwords in plaintext.
5.  **Practical Application:** Learning how to use GPG and OpenSSL commands gave me practical skills I can immediately apply in real-world scenarios for file encryption and secure communication.

---

## ✅ Conclusion

Completing the **Cryptography Introduction** room was an incredibly rewarding experience. It successfully demystified complex topics and provided a solid, practical foundation in cryptography. I now feel confident in my understanding of the differences between symmetric and asymmetric encryption, the purpose of hashing and digital certificates, and how these elements integrate to protect data in transit and at rest. This knowledge is fundamental for anyone pursuing a career in cybersecurity.

The hands-on exercises with GPG and OpenSSL were particularly valuable, as they transformed abstract concepts into practical skills. Understanding how all these cryptographic components work together in real-world applications like HTTPS was the most enlightening part of this learning journey.

**How likely are you to recommend this room to others?**
**10/10** - It's a perfectly paced, beginner-friendly introduction to a critical domain that balances theory with practical application.

---
**🔗 Connect with me on TryHackMe:** [https://tryhackme.com/p/Petras20](https://tryhackme.com/p/Petras20)  
**📂 GitHub Repository:** [https://github.com/Petrasec202](https://github.com/Petrasec202)

---

*This writeup reflects my personal learning journey through the Cryptography Introduction room. Feel free to reach out if you have any questions or want to discuss these concepts further!*

---

## 🏆 Badges Earned
![Room Completion](https://img.shields.io/badge/Room_Completion-100%25-brightgreen)
![Learning Path](https://img.shields.io/badge/Learning_Path-Pre_Security-orange)
![Skills Gained](https://img.shields.io/badge/Skills-Cryptography_Fundamentals-blue)
