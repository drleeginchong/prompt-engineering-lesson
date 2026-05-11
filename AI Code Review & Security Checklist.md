# AI Code Review & Security Checklist

This document provides a structured framework for reviewing AI-generated code during pair programming sessions. Follow the **Ask -> Refine -> Validate** workflow to ensure production readiness.

---

## 🛠️ Functional & Quality Review
*   [ ] **Syntax & Execution:** Does the code run without errors in the local environment?
*   [ ] **Requirement Match:** Does the output fulfill the specific **Task** and **Context** provided?
*   [ ] **Hallucination Check:** Are all imported libraries and called APIs real and up-to-date?
*   [ ] **Complexity:** Does the code meet performance **Constraints** (e.g., Time/Space complexity)?
*   [ ] **Maintainability:** Is the code "Pythonic" (PEP 8) and readable for future human maintainers?

---

## 🔒 Security Risk Audit (Critical)

| Risk Category | Check | Mitigation |
| :--- | :--- | :--- |
| **Injections** | Are user inputs sanitized before being used in SQL or Shell commands? | Use parameterized queries/ORMs. |
| **Secrets** | Are there any hardcoded API keys, passwords, or tokens? | Use `.env` or Secret Managers. |
| **Authentication** | Are permission checks robust, or are they easily bypassed logic? | Use proven Auth frameworks. |
| **Cryptography** | Is it using modern, secure algorithms (e.g., Argon2, AES-256)? | Avoid MD5 or SHA-1 for passwords. |
| **Error Handling** | Do error messages leak system paths or sensitive data? | Use structured logging with masking. |

---

## 🤝 Pair Programming "Validation" Questions
1. **The "Why" Test:** Do we fully understand the logic, or are we trusting the "probability" of the AI?
2. **The "Regression" Test:** Does this change break existing functionality elsewhere in the project **Context**?
3. **The "Sandbox" Test:** Has this code been tested with malicious or "garbage" input?

---
*Generated based on the **Ask, Refine, Validate** workflow.*
