# SARAR INDUSTRIES Backend

Express API for the SARAR INDUSTRIES website. It stores brands, products, users, and customer enquiries in Supabase.

## Requirements

- Node.js 22 or later
- A Supabase project with the schema, policies, seed data, and `product-media` storage bucket configured

## Local setup

1. Copy `.env.example` to `.env` and fill in the private Supabase URL/server key and a unique `JWT_SECRET`.
2. Install dependencies with `npm ci`.
3. Start the API with `npm start`.
4. Check `http://localhost:5000/api/health`.

Create the initial administrator once with `ADMIN_EMAIL` and a temporary unique `ADMIN_PASSWORD` (at least 16 characters) in `.env`, then run `npm run bootstrap:admin`. Remove the temporary password afterward.

## Render deployment

Set the service root directory to the repository root, build command to `npm ci`, and start command to `npm start`. Configure `NODE_ENV=production`, `SUPABASE_URL`, `SUPABASE_SECRET_KEY`, `SUPABASE_STORAGE_BUCKET=product-media`, a generated `JWT_SECRET`, and `FRONTEND_URL` to the website origin. Render provides `PORT` automatically. Set additional allowed website origins in `CORS_ORIGINS` when needed.

Never commit `.env` or server secrets.
