# Task No: 10

# Secure API Authorization, Input Validation and Permission Checks

## For Qviple ERP & LMS

### Team Members

* Vansh Kulkarni
* Sarvesh Kulkarni

---

# 1. Introduction

ERP and LMS systems store important information such as student records, attendance, assignments, fees, and examination data. Since many users access the system, backend API security becomes very important.

In this project, we researched secure API authorization, input validation, and permission checks for Node.js Express APIs used in ERP and LMS systems.

The project mainly focuses on preventing unauthorized access, invalid requests, hidden privilege escalation, and mass assignment using secure backend practices.

---

# 2. Objective

The objective of this project is:

* To study secure API design
* To implement role-based access control
* To validate user inputs properly
* To secure APIs using middleware
* To prevent unauthorized access, mass assignment, bad input, and privilege escalation

---

# 3. Technologies and Concepts Used

| Technology / Concept | Purpose                   |
| -------------------- | ------------------------- |
| Node.js              | Backend runtime           |
| Express.js           | API framework             |
| JWT Authentication   | User authentication       |
| Middleware           | Request verification      |
| express-validator    | Input validation          |
| RBAC                 | Role-Based Access Control |

---

# 4. Role-Based Access Control (RBAC)

Role-Based Access Control is used to provide different permissions to different users according to their role so that unauthorized access is prevented.

### Examples

* Admin has complete access
* Teachers can manage assignments
* Students can only view their courses
* Parents can view student progress

RBAC improves security and prevents unauthorized access.

---

# 5. Role-Permission Matrix

| Role          | Permissions                              |
| ------------- | ---------------------------------------- |
| Admin         | Full system access                       |
| Teacher       | Upload assignments and manage attendance |
| Student       | View courses and assignments             |
| Parent        | View student progress                    |
| Accountant    | Manage fee records                       |
| Support Staff | Handle support requests                  |

---

# 6. Security Threat Report

During research, we identified some common security threats affecting ERP and LMS APIs.

### Unauthorized Access

Users accessing restricted APIs or data without permission.

### SQL Injection

Malicious SQL queries inserted through input fields.

### Broken Access Control

Improper permission checks allowing restricted operations.

### Invalid Input

Incorrect or harmful user data affecting application behavior.

### Privilege Escalation

Low-level users gaining higher-level permissions.

### Weak Passwords

Simple passwords increasing risk of account compromise.

### Mass Assignment

Users may submit hidden fields such as role or permissions to gain unauthorized access.

---

# 7. Risk Severity Table

| Threat                | Severity | Possible Impact             |
| --------------------- | -------- | --------------------------- |
| Unauthorized Access   | High     | Data leakage                |
| SQL Injection         | High     | Database compromise         |
| Weak Passwords        | Medium   | Account hacking             |
| Invalid Input         | Medium   | Application errors          |
| Privilege Escalation  | High     | Unauthorized control        |
| Broken Access Control | High     | Security bypass             |
| Mass Assignment       | High     | Unauthorized privilege gain |

---

# 8. Input Validation

Input validation ensures that only safe and valid data enters the system.

### Validation Libraries Researched

* express-validator
* Joi
* Zod

### Benefits

* Prevent invalid form submission
* Prevent malicious input
* Prevent empty fields
* Prevent harmful scripts

---

## 8.1 Mass Assignment Prevention

Mass Assignment is a security vulnerability where a user sends additional fields in a request that should not be modified.

### Example

json
{
  "name": "Rahul",
  "email": "rahul@gmail.com",
  "role": "admin"
}


If the API updates all fields directly, the user may gain unauthorized privileges.

### Prevention Methods

* Allow only approved fields to be updated
* Ignore unknown request fields
* Validate all requests using express-validator, Joi, or Zod
* Never allow users to modify role, permissions, or account status
* Use field whitelisting before database updates

---

# 9. Validation Examples

| Field        | Validation Rule                 |
| ------------ | ------------------------------- |
| Email        | Must contain valid email format |
| Password     | Minimum 8 characters            |
| Phone Number | Digits only                     |
| Name         | Cannot be empty                 |
| File Upload  | Allow only safe file types      |

---

## 9.1 Validation Checklist

| Validation Check        | Purpose                         |
| ----------------------- | ------------------------------- |
| Email Validation        | Verify valid email format       |
| Password Length Check   | Enforce minimum password length |
| Required Fields Check   | Prevent empty values            |
| Phone Number Validation | Allow digits only               |
| File Type Validation    | Restrict unsafe uploads         |
| Unknown Field Rejection | Block unexpected fields         |
| Role Field Protection   | Prevent role modification       |
| Input Sanitization      | Remove harmful scripts          |

---

# 10. Sample Input Validation Code

js
const { body, validationResult } = require('express-validator');

app.post('/register',
[
  body('email').isEmail(),
  body('password').isLength({ min: 8 })
],
(req, res) => {

  const errors = validationResult(req);

  if (!errors.isEmpty()) {
    return res.status(400).json({ errors: errors.array() });
  }

  res.send("Valid Input");
});


---

# 11. API Authorization

API authorization ensures that only authorized users can access protected routes and sensitive data.

### Examples

* Students should not access admin APIs
* Teachers should not modify fee records
* Parents should only view their child's information

Authorization improves backend security and protects sensitive data.

---

# 12. Protected API Examples

| API Route            | Authorized User |
| -------------------- | --------------- |
| GET /student/courses | Student         |
| POST /teacher/upload | Teacher         |
| DELETE /admin/user   | Admin           |
| GET /fees/details    | Accountant      |
| GET /parent/progress | Parent          |
| GET /support/tickets | Support Staff   |

---

# 13. Middleware Security

Middleware acts as a security layer between the request and the API.

### Middleware verifies:

* User role
* Authentication
* Permissions
* Validation rules

before allowing access to protected APIs.

---

## 13.1 Sample Middleware Plan

### Step 1: Authentication

Verify JWT token and identify the user.

### Step 2: Authorization

Check whether the user has permission to access the API.

### Step 3: Input Validation

Validate request data using express-validator, Joi, or Zod.

### Step 4: Permission Check

Verify ownership and access rights for requested resources.

### Step 5: API Execution

Allow API execution only after all checks pass.

### Middleware Flow


Request
↓
JWT Authentication
↓
Role Verification
↓
Input Validation
↓
Permission Check
↓
API Access Granted




# 14. Sample Middleware Code

js
function checkAdmin(req, res, next){

   if(req.user.role !== "admin"){
      return res.status(403).send("Access Denied");
   }

   next();
}




# 15. Module-Wise Security Checklist

| Module            | Security Check              |
| ----------------- | --------------------------- |
| Login             | Password validation         |
| Student Dashboard | Student-only access         |
| Teacher Panel     | Teacher role verification   |
| Admin Panel       | Admin middleware protection |
| Fee Management    | Accountant access only      |
| File Upload       | File type validation        |

---

# 16. Recommended Security Fixes

* Use JWT authentication
* Validate all user inputs
* Implement role-based middleware
* Use strong password policies
* Restrict API access by role
* Use HTTPS for secure communication
* Prevent direct database access
* Limit failed login attempts
* Use field whitelisting to prevent mass assignment
* Reject unexpected request parameters
* Log suspicious activities

---

# 17. Challenges Faced

* Understanding API authorization flow
* Learning validation libraries
* Researching backend security concepts
* Designing role-based access control

These challenges were solved through documentation research and practical examples.

---

# 18. Conclusion

In this project, we studied secure API authorization, input validation, and permission checks for ERP and LMS systems.

We researched common backend security threats and methods to improve API security using:

* Role-Based Access Control (RBAC)
* Middleware validation
* Secure API design practices

This project helped us understand practical backend security concepts used in real-world ERP and LMS applications.
