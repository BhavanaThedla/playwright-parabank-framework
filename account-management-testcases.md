# Account Management – Test Cases

This document covers test scenarios for core banking features including **Account Opening, Money Transfer, and Account Deletion**.

---

## 1. Account Opening

### Positive Scenarios
- Verify that the user is able to create a fresh account
- Verify that the user is able to create multiple accounts
- Verify that the account number for multiple accounts is unique (not duplicated)
- Verify that the user is able to view the newly created account
- Verify that newly created account appears in Accounts Overview
- Verify that newly created account appears in Transfer Funds dropdown
- Verify newly created account status is **Active**

### Field & Input Validation
- Verify account cannot be created without selecting an account type
- Verify default balance is correctly assigned to a new account (if applicable)
- Verify account number follows expected format and length
- Verify system prevents duplicate account creation on page refresh
- Verify account creation is blocked when session expires

### Security & Reliability
- Verify sensitive account details are not exposed in URL
- Verify backend failure shows user-friendly error message
- Verify multiple clicks on "Open Account" do not create duplicate accounts

---

## 2. Money Transfer

### Positive Scenarios
- Verify that the user is able to transfer money from one account to another
- Verify balance is reduced in the source account after transfer
- Verify balance is increased in the destination account after transfer
- Verify successful transfer confirmation message is displayed
- Verify transaction reference/ID is generated
- Verify transfer appears in transaction history
- Verify transfer persists after logout and login

### Negative Scenarios
- Verify transfer is not allowed when amount exceeds available balance
- Verify transfer is not allowed between the same source and destination account
- Verify transfer amount cannot be zero
- Verify transfer amount cannot be negative
- Verify transfer fails when destination account is deleted or inactive

### Field Validation
- Verify transfer amount accepts only numeric values
- Verify transfer supports decimal values (e.g., 100.50)
- Verify minimum transfer amount rules (if applicable)

### Concurrency & Reliability
- Verify multiple transfers in quick succession are handled correctly
- Verify system prevents duplicate transfers on double click
- Verify behavior when network interruption occurs during transfer
- Verify browser refresh does not duplicate the transaction

### Security
- Verify unauthorized users cannot perform transfers
- Verify account numbers are masked where required
- Verify transfer data is encrypted over network

---

## 3. Account Deletion

### Positive Scenarios
- Verify that user is able to delete an account
- Verify that user is not able to delete all accounts
- Verify deleted account does not appear on dashboard
- Verify transfer statements are still visible after account deletion

### Validation
- Verify account with non-zero balance cannot be deleted (if applicable)
- Verify account with pending transactions cannot be deleted
- Verify deletion confirmation message/modal appears
- Verify deletion action is irreversible

### Functional Behavior
- Verify deleted account cannot be used for money transfer
- Verify deleted account cannot be accessed via direct URL
- Verify dashboard balances recalculate correctly after deletion
- Verify transaction history shows proper reference for deleted account
- Verify multiple accounts can be deleted sequentially without errors

### Reliability
- Verify backend/API failure during deletion shows proper error message

---

## 4. Cross-Module / System Test Cases

### Data Consistency
- Verify data consistency across Accounts Overview, Transfer Funds, and Transaction History
- Verify balances match between UI and backend data

### Session & Behavior
- Verify system behavior on browser refresh during account creation
- Verify system behavior on browser refresh during money transfer
- Verify system behavior on browser refresh during account deletion
- Verify same user accessing application in multiple browser tabs

### Error Handling
- Verify proper user-friendly error messages are displayed
- Verify technical or stack trace errors are not exposed to users

### UI Protection
- Verify UI disables action buttons during API processing
- Verify system prevents double submission

---

## Exclusions
- Authentication (Sign up, Login, Logout, Forgot Password) – Covered separately
