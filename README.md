# Diniru Driving Training School - Backend API

A secure, scalable, and robust RESTful API built entirely with Node.js, Express, and TypeScript according to Rapid Application Development (RAD) principles. This backend powers the driving school management application, handling roles, authentication vectors, and data models with MongoDB Atlas.

---

## 🌐 Deployed URLs

* **Live Backend API:** [https://dds-be.vercel.app](https://dds-be.vercel.app)
* **Live Frontend:** [https://dds-fe.vercel.app](https://dds-fe.vercel.app)

---

## 🚀 Key Features

* **Advanced Role-Based Security:** Fully decoupled authorization matrix supporting dynamic access controls for `STUDENT` and `ADMIN` users.
* **Hybrid Authentication Mechanism:**
  * Native secure signup/login using password hashing via **bcryptjs** and native **JWT** vectors.
  * Integration with **Google OAuth 2.0** verification workflow issuing internal system-level tokens.
* **Never-Expiring Admin Access:** Custom token utility architecture ensuring a permanent token lifecycle for the `ADMIN` role, paired with an optimized lifespan for student access tokens.
* **Granular Database Layer:** Clean, relational document modeling leveraging Mongoose with unique indexing for student NIC numbers and email fields.
* **Comprehensive Student Profiling:** Direct API abstractions allowing administrators to fetch structured student profiles by utilizing either their DB Object ID, NIC number, or Registered Phone Number.

---

## 🛠️ Tech Stack & Tools

* **Runtime Environment:** Node.js
* **Framework:** Express.js with TypeScript compilation
* **Database Object Modeling:** Mongoose & MongoDB Atlas (Cloud Database)
* **Security & Cryptography:** JSON Web Tokens (JWT), bcryptjs
* **Authentication Service:** Google Auth Library (`google-auth-library`)
* **Environment Configuration:** dotenv

---

## 📂 System Architecture & Folder Structure

Adheres strictly to the standard industry boilerplate configuration for server separation:

```text
backend/
├── src/
│   ├── config/       # Database connections & environment initializations
│   ├── controllers/  # Route managers executing logical requests (authController.ts)
│   ├── middleware/   # Request interceptors & authentication guards (authMiddleware.ts)
│   ├── models/       # Schema blueprints definition (userModel.ts, studentModel.ts)
│   ├── routes/       # Explicit endpoint declarations mapping
│   ├── services/     # Pure database query orchestration layers (authService.ts)
│   ├── util/         # Helper functions (token token.ts processing)
│   └── index.ts      # Application execution master node
├── .env.example      # System environmental structural blueprint
├── package.json      # Project dependencies configuration
└── tsconfig.json     # Strict static compilation definitions