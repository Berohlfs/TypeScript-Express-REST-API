# 🚀 TypeScript Express REST API

Welcome! This project of mine is a backend REST API built with **TypeScript**, **Express.js**, and **Prisma** ORM. It comes with robust features like JWT-based authentication, file uploads, email handling, and a clean modular architecture.

---

## 📁 Project Structure

```
src/
├── controllers/         # Business logic (e.g. user controller)
├── helpers/             # Utilities: email (Nodemailer), FTP, DB access
├── middlewares/         # Auth, file upload config, etc.
├── routes.ts            # Centralized route definitions
├── index.ts             # Entry point for the Express app
├── utils/               # Generic utilities and shared logic
```

---

## 🧰 Main Libraries Used

| Library             | Purpose |
|---------------------|---------|
| **Express.js**       | Core HTTP routing library |
| **TypeScript**       | Adds static typing and better developer tooling |
| **Prisma ORM**       | Type-safe database access |
| **argon2**           | Secure password hashing |
| **jsonwebtoken**     | JWT-based user authentication |
| **multer**           | Middleware for file uploads |
| **nodemailer**       | Library for sending emails using SMTP |
| **basic-ftp**        | FTP client to interact with file servers |
| **zod**              | Schema validation and type inference |
| **dotenv**           | Environment variable loader |

---

## 🔐 Authentication Strategy

The API uses **JWT (JSON Web Token)** for secure, stateless authentication.

- Passwords are hashed using `argon2` before being stored.
- On login, a JWT token is issued.
- Protected routes check for a valid `Authorization: Bearer <token>` header using middleware in `middlewares/auth.ts`.

---

## 📤 File Uploads

Handled by **Multer**, which allows multipart form-data uploads, with custom configurations in:

```
src/middlewares/multer.ts
```

You can restrict types, size, and file destinations easily here.

---

## 📧 Email Handling

Using **Nodemailer**, this app can send transactional emails:

- SMTP config pulled from `.env`
- Email templates or plain messages
- See `helpers/nodemailer.ts` for customization

---

## 🔌 Database

- Uses **Prisma ORM**
- Schema is defined in `prisma/schema.prisma`

---

## 🧪 API Style & Development

- RESTful endpoints
- Typed request/response contracts
- Validations handled via `zod` and middleware

---

## 🛠️ Scripts

| Script            | Description                      |
|-------------------|----------------------------------|
| `npm run dev`     | Watches and rebuilds with `tsup` |
| `npm run start`   | Runs the compiled JS             |
| `npm run build`   | Builds the API into `dist/`      |

---

## 🧾 Environment Variables

Create a `.env` file with:

```env
DATABASE_URL=

ORIGIN=
PORT=

ACCESS_SECRET=

FTP_HOST=
FTP_USER=
FTP_PORT=
FTP_PASSWORD=
FTP_SECURE=

EMAIL_HOST=
EMAIL_PORT=
EMAIL_USER=
EMAIL_PASSWORD=
EMAIL_SECURE=
```

---

## 👨‍💻 Author

Developed by **Bernardo Rohlfs**
