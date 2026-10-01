# Hacker101 CTF - Postbook Writeup

## 1. Introduction to the Challenge and Objective
This write-up covers the resolution of the **Postbook** challenge from **Hacker101 CTF**. The primary objective of this challenge is to thoroughly evaluate a social media-style application implementing full CRUD (Create, Read, Update, Delete) functionalities, identifying logical flaws, session issues, and authorization bypasses.

---

## 2. Reconnaissance & Feature Analysis
* **Core Functionality:** The application simulated a mini social platform where users could register, log in, create posts, edit profiles, and interact with other users' content.
* **Surface Mapping:** Analyzing request parameters, user IDs, and session cookies revealed how user actions were authorized across different administrative and peer-to-peer endpoints.

---

## 3. Exploitation Strategy
1. **Parameter Manipulation:** Tested post IDs and user identifiers to check for Insecure Direct Object References (IDOR), allowing access to private content belonging to other users.
2. **Session and State Validation:** Examined session handling mechanisms to see if privileges could be escalated or actions performed on behalf of other accounts.
3. **Flag Recovery:** Successfully located and extracted the flags tied to specific unauthorized actions and administrative features within the platform.

---

## 4. Lessons Learned
* **Strict Authorization Checks:** Every CRUD operation (especially Read, Update, and Delete) must validate whether the active session owner holds the appropriate permissions for that specific resource.
* **Predictable Identifiers:** Utilizing sequential IDs without proper access control layers makes applications highly vulnerable to enumeration and data leakage.

---

## 5. References
* [Hacker101 CTF](https://hacker101.com/) - Official security challenge platform.
* [OWASP Authorization Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Authorization_Cheat_Sheet.html)

---

## Acknowledgments
Special thanks to **HackerOne** and the creators of **Hacker101** for providing an exceptional platform for hands-on web security practice.

---

 📝 **Note on Flags:** All flags in this repository have been replaced with the standard placeholder format (`^FLAG^xxxxxxxx...$FLAG$`) to comply with platform guidelines.
