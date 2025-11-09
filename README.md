# KeepKleen — Community Cleanliness Social App (WIP)

> KeepKleen is a community-first social platform that encourages local cleanliness initiatives and civic engagement.  
> Built with Next.js (monorepo), Clerk for authentication, and Supabase for data storage. This repository contains a work-in-progress prototype demonstrating core social features and auth integration.

---

## 🔗 Live / Demo
*(No live demo yet — local development only. Add a deployed link here once available.)*

---

## 📖 Project Overview

KeepKleen aims to make local clean-up activities discoverable and social. Users can sign up, create posts about clean-up events, share images, and engage with other community members. The project explores integrating modern auth (Clerk), serverless DB (Supabase), and fast UI with Next.js and Tailwind.

This repo is currently a prototype with some features implemented and other parts under development.

---

## ✨ Key Features (Implemented & Planned)

**Implemented (Prototype)**
- 🔐 Authentication via **Clerk** (signup, login, protected routes)
- 📝 Create and view basic posts (title, description, optional image)
- 📦 Supabase integration for storing posts and user metadata
- 🎨 Responsive UI using **Next.js** + **TailwindCSS**

**Planned / WIP**
- 👍 Like / comment on posts (social interactions)
- 📍 Event creation with geolocation + map view
- 🗂️ Moderation dashboard for admins
- 🔔 Notifications (email / in-app) for event updates
- 📸 Image uploads with cloud storage (Supabase Storage / S3)
- 🚀 Deployment + CI/CD

---

## 🧩 Tech Stack

| Layer | Technology |
|-------|------------|
| Frontend | Next.js (App Router or Pages Router), React |
| Auth | Clerk |
| Database | Supabase (Postgres) |
| Styling | TailwindCSS |
| Hosting (dev) | Vercel / Local |
| Optional | Prisma (if used), React Query / SWR for data fetching |

---

## 🏗️ Recommended Folder Structurekeepkleen/
├── apps/
│ └── web/ # Next.js frontend
│ ├── app/ or pages/ # Routes
│ ├── components/
│ └── public/
├── services/ # Supabase helpers / APIs (optional)
├── scripts/ # Dev scripts
├── .env.local # Environment variables (not committed)
└── package.json

> Note: adapt paths to your repo layout if different.

---

## ⚙️ Environment Variables

Create a `.env.local` file in the frontend (`apps/web` or project root depending on setup) and add:
NEXT_PUBLIC_SUPABASE_URL=your_supabase_url
NEXT_PUBLIC_SUPABASE_ANON_KEY=your_supabase_anon_key

Clerk config

NEXT_PUBLIC_CLERK_FRONTEND_API=your_clerk_frontend_api
CLERK_API_KEY=your_clerk_api_key # server-side (do not expose)


**Security note:** Keep secret keys (Clerk server-side keys, Supabase service_role key) out of frontend and commit-safe files. Use server-side functions or environment on deployment.

---

## 🚀 Local Setup & Run

1. **Clone the repo**
```bash
git clone https://github.com/Bharathreddy374/keepkleen.git
cd keepkleen

cd apps/web   # or your frontend folder
npm install

npm run dev
# Open http://localhost:3000
```
Testing & Common Issues

Ensure your Supabase project is configured (tables for posts, profiles, etc.) and the anon key has appropriate RLS policies for dev.

Clerk configuration: confirm your frontend origin is allowed in Clerk dashboard.

If images fail to upload, confirm storage bucket permissions.

For CORS errors, ensure serverless endpoints accept requests from localhost:3000

<img width="1904" height="988" alt="image" src="https://github.com/user-attachments/assets/e79d3f5e-3019-49e3-ad05-93e83d621f08" />

Roadmap & Next Steps

Implement likes, comments, and real-time updates.

Add image upload support (Supabase Storage).

Build event map view with geolocation filtering.

Implement admin moderation panel & role-based access.

Prepare for deployment on Vercel + set up environment secrets & CI.



