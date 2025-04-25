
#  Defect Report: Incorrect Error Message for Existing Username

| Field              | Description |
|--------------------|-------------|
| **Title**           | Incorrect error message when registering with an existing username |
| **Reported By**     | Jyoti Chiliveri (Tester) |
| **Module**          | User Registration |
| **Severity**        | Medium |
| **Priority**        | High |
| **Status**          | New / Open |


---

# Description
When a new user attempts to register using a username that already exists in the system but enters a different password, the application displays an error message:
> **"Invalid username"**  
This is misleading because the username format is valid, but the username is already taken.

---

##  Steps to Reproduce
1. Navigate to the login page.
2. Click the "Register" link.
3. Enter an existing username (e.g., `Batman`).
4. Enter a new password (e.g., `Test@1234`).
5. Click the "Register" button.

---

## Expected Result
User should receive the message:
> **"Username already exists. Please choose a different username."**

---

## Actual Result
User sees the message:
> **"Invalid username"**

---

##  Impact
- Misleads users into thinking their username format is incorrect.
- Reduces clarity during the registration process.
- Negatively affects the user experience.

---

## Suggested Fix
- Update backend (or frontend) validation to **differentiate** between:
    - Username format validation **(syntax check)**
    - Username duplication check **(uniqueness in database)**
- Return a **specific and accurate error message** based on the validation failure.

---
