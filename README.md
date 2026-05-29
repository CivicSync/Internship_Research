Topic:- Node.js Express API Rate Limiting and Abuse Protection.

Team member 
Puja korde
Samiksha gupta

Category:-
Backend Security / Node.js
______________________________________

1.Objective:-
The main objective of this project is to research and develop a prototype system that protects ERP and LMS APIs from:
• brute-force attacks
• spam requests
• API abuse
• scraping
• excessive traffic
using Node.js and Express.js middleware.

______________________________________

2. Proposed Best Approach:-

Layered Middleware-Based Protection System-> The best approach is to use multiple protection layers together instead of relying on a single rate limiter.

______________________________________

3. Working of the system:-
Workflow
   i. User sends request to API.

   ii. Middleware checks:
• IP address
• user ID
• route access
• token validation
• request count

  iii. Different limits are applied for:
• login APIs
• OTP APIs
• password reset
• file upload
• public APIs
• admin APIs


   iv. If request exceeds limit:
request blocked
HTTP 429 returned
suspicious activity logged

   v. Valid requests continue to server.

______________________________________

4. Main Approach Used:-

4.1 IP-Based Rate Limiting
Concept

Limits requests based on client IP address.
Example
• 100 requests per 15 minutes per IP

Purpose
Protects against:
• spam traffic
• bots
• repeated requests

Example Code JavaScript:
const rateLimit = require("express-rate-limit");

const ipLimiter = rateLimit({
   windowMs: 15 * 60 * 1000,
   max: 100,
   message: "Too many requests from this IP"
});

app.use(ipLimiter);

______________________________________

4.2 User ID-Based Limiting
Concept

Tracks requests based on logged-in users.
Example
•  each user gets separate request quota


Purpose
Prevents:
• individual user abuse
• excessive API consumption

______________________________________

4.3 Route-Based Rate Limiting
Concept

Different API routes have different request limits.
Example

API Route                       Limit
Login API                       5 requests/min
OTP API                         3 requests/min
Public APIs                    100 requests/min
Admin APIs                    20 requests/min

Purpose
• Provides customized security for sensitive endpoints.

______________________________________

4.4 Login Endpoint Protection
Concept

Protects login APIs from brute-force attacks.

Example
• After 5 failed login attempts:
IP temporarily blocked

Example Code JavaScript
const loginLimiter = rateLimit({
   windowMs: 10 * 60 * 1000,
   max: 5,
   message: "Too many login attempts"
});

app.use('/login', loginLimiter);

______________________________________

4.5 Token-Based Access Control
Concept

JWT tokens are used to authorize API access.

Purpose
Ensures:
• only authorized users access APIs
• secure communication


Example Code JavaScript
const jwt = require("jsonwebtoken");

const token = jwt.sign(
   {id:user.id},
   "secretkey",
   {expiresIn:"1h"}
);

______________________________________

4.6 Redis-Backed Rate Limiter
Concept

Stores request counters inside Redis database.

Purpose
Useful for:
• large applications
• distributed systems
• cloud servers

Advantages
• faster performance
• scalable
• persistent counters
______________________________________

5. Recommended API Limit Table:-

API Type                   Recommended Limit
Login API                  5 req/min
OTP API                     3 req/min
Password Reset        2 req/min
File Upload                 10 req/min
Public APIs                 100 req/min
Admin APIs                  20 req/min

______________________________________

6. Middleware Prototype Design:-
Middleware Flow

Client Request
      ↓
IP Rate Limiter
      ↓
JWT Authentication
      ↓
Route-Based Limiter
      ↓
Abuse Detection
      ↓
API Endpoint

______________________________________

7. Sample Middleware Code Javascript:-

const express = require('express');
const rateLimit = require('express-rate-limit');

const app = express();

const apiLimiter = rateLimit({
   windowMs: 15 * 60 * 1000,
   max: 100,
   message: "API limit exceeded"
});

app.use('/api', apiLimiter);

app.get('/api/data', (req,res)=>{
   res.send("Protected API");
});

app.listen(3000);

______________________________________

8. Test Cases:-

Test Case                          Expected Result
Normal API request          Success
Excessive requests          Blocked
Invalid token                      Unauthorized
Multiple failed logins         IP blocked
Public API access              Limited after     
                                              threshold
______________________________________

9. Advantages of Proposed Approach:-

• Improves backend security
• Prevents brute-force attacks
• Controls spam traffic
• Reduces server overload
• Protects sensitive APIs
• Provides scalable middleware architecture
______________________________________

10. Future Scope:-

Future improvements may include:
• AI-based anomaly detection
• CAPTCHA integration
• Real-time monitoring dashboard
• Cloud deployment
• Advanced DDoS protection
______________________________________

11. Conclusion:-

The project successfully demonstrates a layered middleware-based API protection system using Node.js and Express.js. By implementing IP-based limiting, route-based control, token authentication, and abuse detection mechanisms, the system improves API security and protects servers from malicious traffic and excessive requests.
