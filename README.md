# Password Reset Frontend

React + Bootstrap single-page app for password reset (Forgot + Reset pages).

## Live & Repos

- **Frontend (Netlify):** https://password-reset-ronten.netlify.app
- **Backend (Render):** https://password-reset-backend-r7x4.onrender.com
- **GitHub (frontend):** https://github.com/jayachandran-student/password-reset-frontend
- **GitHub (backend):** https://github.com/jayachandran-student/password-reset-backend

## Tech Stack

- React (CRA), React Router v6
- Bootstrap
- Axios

## Pages & Routes

- `/forgot-password` — request reset email
- `/reset-password/:token` — set a new password

## Environment Variable

Create `.env` in project root:

REACT_APP_API_URL=https://password-reset-backend-r7x4.onrender.com

> Netlify: add the same env var in **Site settings → Build & Deploy → Environment**.

## SPA Redirect (Netlify)

To prevent 404s on deep links:

- Create `public/_redirects` with:
  /\* /index.html 200

## Local Setup

```bash
git clone https://github.com/jayachandran-student/password-reset-frontend.git
cd password-reset-frontend
npm install
# add .env as above
npm start

Build & Deploy (Netlify)

Build command: npm run build

Publish directory: build

Node version: add .nvmrc with 18

Environment variables:

REACT_APP_API_URL=https://password-reset-backend-r7x4.onrender.com

How It Works

Forgot Password

POST ${REACT_APP_API_URL}/api/auth/forgot-password

Shows success/error message from server

Reset Password

POST ${REACT_APP_API_URL}/api/auth/reset-password/:token with { password }

On success, token is invalidated
```
