# Authentication – Test Cases

## 1. Sign Up (Registration)

### Positive Scenarios
- Verify that user is able to register on the website with valid details
- Verify that user sees the dashboard/home page after successful registration

### Field Validation
- Verify that error is shown when Password and Confirm Password do not match
- Verify that user is not able to register when any mandatory field is missing
- Verify email format validation for the email field
- Verify password follows defined complexity rules (min length, uppercase, number, special character)
- Verify password field is masked
- Verify confirm password field is masked
- Verify leading and trailing spaces are trimmed from input fields
- Verify maximum character limit for each input field
- Verify special characters handling in input fields

### Duplicate & Data Validation
- Verify that user is not able to register with an already registered email
- Verify system behavior when registering with an already existing username (if applicable)

### Security
- Verify password is not visible in URL or request payload
- Verify sensitive data is encrypted in network requests
- Verify form submission is prevented on multiple clicks (double submit)

### Behavior & Session
- Verify user remains logged in after successful registration (if applicable)
- Verify verification email is sent after successful registration (if applicable)

---

## 2. Sign In (Login)

### Positive Scenarios
- Verify that user is able to login with correct email and password
- Verify that user is redirected to dashboard/home page after successful login

### Negative Scenarios
- Verify that user is not able to login with correct email and wrong password
- Verify that user is not able to login with wrong email and correct password
- Verify that user is not able to login with wrong email and wrong password
- Verify that login is not allowed when email field is empty
- Verify that login is not allowed when password field is empty

### Field Validation
- Verify password field is masked
- Verify login fields do not accept only spaces
- Verify system behavior with very long input values

### Security
- Verify account is locked after multiple failed login attempts (if applicable)
- Verify login error message does not reveal whether email exists
- Verify application is protected against SQL injection
- Verify application is protected against script injection (XSS)
- Verify CAPTCHA is shown after multiple failed login attempts (if applicable)

### Session Management
- Verify user session is created after successful login
- Verify session expires after defined inactivity time
- Verify user cannot access dashboard using browser back button after logout
- Verify user cannot open dashboard in a new tab after logout

---

## 3. Logout

### Functional
- Verify that user is able to logout successfully using logout button
- Verify user is redirected to login page after logout

### Session & Security
- Verify user session is destroyed after logout
- Verify browser back button does not restore session
- Verify logout works correctly from multiple browser tabs
- Verify authentication cookies are cleared after logout

---

## 4. Forgot Password Functionality

### Positive Scenarios
- Verify that user receives password reset email after submitting registered email
- Verify that user is able to create a new password using reset link
- Verify that user is able to login using newly created password

### Negative & Validation
- Verify error message is shown when unregistered email is entered
- Verify password reset is not allowed with invalid or expired token
- Verify old password cannot be reused after reset

### Security
- Verify password reset link expires after defined time
- Verify password reset link cannot be reused
- Verify reset token cannot be manipulated

### Session
- Verify user is logged out from all active sessions after password reset (if applicable)

---

## 5. General Authentication Security

- Verify application enforces HTTPS
- Verify authentication cookies are marked as Secure and HttpOnly
- Verify brute force attack protection is implemented
- Verify sensitive information is not stored in browser storage

---

## Exclusions
- Third-party authentication (Google, Facebook, etc.) 


