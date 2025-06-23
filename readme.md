# Test Scenarios for Facebook Authentication

This repository contains comprehensive test scenarios for Facebook's **Login** and **Sign-Up** flows. You can use these as templates for manual testing or automate them in your preferred test framework.

---

## Table of Contents

1. [Login Scenarios](#login-scenarios)
   - [1.1 Valid Login](#11-valid-login)
   - [1.2 Invalid Login](#12-invalid-login)
   - [1.3 Redirection](#13-redirection)
2. [Sign-Up Scenarios](#sign-up-scenarios)
   - [2.1 Valid Sign-Up](#21-valid-sign-up)
   - [2.2 Invalid Sign-Up](#22-invalid-sign-up)
   - [2.3 Redirection](#23-redirection)
3. [Additional Test Techniques](#additional-test-techniques)
   - [3.1 Equivalence Partitioning](#31-equivalence-partitioning)
   - [3.2 Boundary Value Analysis](#32-boundary-value-analysis)

---

## Login Scenarios

### 1.1 Valid Login

1. **Validate using valid data**
2. **Password encryption & paste-block**
   - Ensure password field is masked and paste is prohibited.
3. **Email login**
   - Use a registered email address.
4. **Phone login (with country code)**
   - Example: `+201008977574`.
5. **Phone login (without country code)**
   - Example: `01008977574`.
6. **Change password then login**
   - Update password in settings, then login with the new password.

### 1.2 Invalid Login

- Leave email/phone field empty.
- Leave password field empty.
- Invalid email format (e.g., `mohamed1234`).
- Typo in email (e.g., `mohamedalii7403@gamil.com`).
- After password change, login with the _old_ password.
- Unregistered email/phone.
- Too short/long phone number.
- Too short/long email address.
- Too short/long password.
- **Account lockout**: Three consecutive failed attempts within 3 minutes → ban for 10 minutes.
- After successful login, pressing “Back” should return to the News Feed (home page).

### 1.3 Redirection

- **Successful login** → News Feed (home page).
- **Forgot account** → Find My Account page.
- **Create new account** → Sign-Up page.

---

## Sign-Up Scenarios

### 2.1 Valid Sign-Up

- Fill all fields with valid data (using mobile number or email).
- Minimum and maximum length for first name and surname (1 and 50 characters).
- Age:
  - Between 13 and 18 → parent approval required.
  - Between 18 and 120 → allowed.
- Valid gender selection.
- Use Arabic letters in name fields (if supported).
- Password rules:
  - Length between 6 and 50 characters.
  - Must include uppercase, lowercase, digits, and special characters (e.g., `&`, `_`, `!`).
- Password field masked and paste-blocked.

### 2.2 Invalid Sign-Up

- Leave any mandatory field empty (first name, surname, gender, mobile/email, password).
- Age &lt; 13 or &gt; 120.
- Invalid email format or typo (same as login).
- Email or mobile number already registered.
- Special characters or spaces in name fields (if not allowed).

### 2.3 Redirection

- **After successful sign-up** → News Feed (home page).
- **Already have an account?** → Login page.

---

## Additional Test Techniques

### 3.1 Equivalence Partitioning

| Field            | Invalid Partition             | Valid Partition                |
|------------------|-------------------------------|--------------------------------|
| First Name       | 0 chars, 51+ chars            | 25 chars                       |
| Date of Birth    | 24‑Jun‑2012, 22‑Jun‑1905       | 24‑Jun‑1975                    |
| Password Length  | 5 chars, 51+ chars            | 26 chars                       |

### 3.2 Boundary Value Analysis

| Field            | Boundary Cases (Invalid)        | Boundary Cases (Valid)       |
|------------------|---------------------------------|------------------------------|
| First Name       | 0, 51 chars                     | 1, 50 chars                  |
| Date of Birth    | 24‑Jun‑2012, 23‑Jun‑1905        | 23‑Jun‑2012, 24‑Jun‑1975     |
| Password Length  | 5, 51 chars                     | 6, 50 chars                  |

---

*Feel free to extend these scenarios, link to detailed test-case templates, or integrate with your automation suite.*

