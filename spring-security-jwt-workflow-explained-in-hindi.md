1. # Ye App hai kya? (Spring Security JWT)

Ye app LOGIN + SECURITY system hai.
Iska kaam hota hai:

1. User ka account banana (signup)
2. User ko login karwana
3. Har request ko secure karna bina baar-baar password pooche

# Is app ka naam hota hai:

Spring Security + JWT (JSON Web Token)

1. Is app me flow kya hota hai?
2. Signup (User register hota hai)
3. Client → /api/auth/signup → DB me user save

2. # Login (User apni identity prove karta hai)

Client → /api/auth/signin → JWT Token milta hai

Example response:

{
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9..."
}

Ye token temporary ID card jaisa hota hai.

3. # Protected API (Security ka asli kaam)

Client → /api/test/user + TOKEN → Access allowed
Client → /api/test/user (no token) → 401 Unauthorized

4. # JWT Token kya hota hai? (Bahut simple)

JWT ek digital pass hai.

Isme hota hai:
1. Kaun user hai
2. Uske roles (ROLE_USER, ROLE_ADMIN)
3. Expiry time
4. Aur ye server verify karta hai, DB me baar-baar nahi jaata.

5. # Spring Security ka role kya hai?

Spring Security:
1. Check karta hai token valid hai ya nahi
2. Check karta hai user allowed hai ya nahi
3. Galat request ko rok deta hai

Example:

Without token → BLOCK
With valid token → ALLOW
Tumhari app ke main parts

1. AuthController

/signup
/signin

2. JwtUtils

Token generate
Token validate

3. SecurityConfig

Kaunsa API open hai
Kaunsa secure hai

4. Database

users
roles

6. # Issey kab use karte hain?

Use karo jab:

Web application
Mobile app backend
Microservices
REST APIs
Frontend + Backend alag ho

Use mat karo jab:

Simple college project
Internal tool without login
Server-side rendered session apps

Real-world examples

App	Use
Amazon	JWT / OAuth
Netflix	Token-based auth
Zomato	JWT
Swiggy	JWT
Banking API JWT

7. # Simple analogy (Yaad rahega)

Signup = Aadhaar banwana
Login = Aadhaar verify
JWT Token = Entry pass
Protected API = Secure area

8. # One-line summary

Spring Security JWT app ek secure login system hai jo token ke through APIs ko protect karta hai — bina baar-baar password bheje.