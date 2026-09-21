# B.A.O Portfolio & Blog
A comprehensive portfolio and blog platform built with React 19, Vite, Tailwind CSS v4, and Supabase. The application serves as a personal website for Binuyo Adegbenga Oluwatosin (B.A.O), featuring a public-facing site with a dynamic blog, portfolio showcases, and a full-fledged administrative dashboard.

## Key Features

- **Modern Tech Stack**: React 19, Vite, TypeScript.
- **Backend & Database**: Powered by Supabase for authentication, PostgreSQL database, and storage.
- **PWA Ready**: Fully installable as a Progressive Web App (PWA) with offline caching and service worker updates.
- **Real-time Notifications**: Web push notifications for newly published blog posts using Supabase Realtime channels.
- **Dynamic SEO**: Implemented via Netlify Edge Functions (`og-image.ts`) to dynamically render Open Graph meta tags for blog posts when accessed by social media crawlers.
- **Rich Text Editing**: Integrated Quill editor for comprehensive blog post creation and formatting in the admin panel.
- **Interactive UI**: Animated with Framer Motion (including read progress bars, page transitions, and interactive components).
- **Responsive Design**: Built with Tailwind CSS v4, utilizing custom dark/light modes and modern CSS features.
- **Admin Dashboard**: A secure, protected route for content management (Posts, Portfolio, Users).

## Architecture & Project Structure

- `src/pages/public/`: Public facing pages (Home, About, Blog, Portfolio, Contact).
- `src/pages/admin/`: Protected admin dashboard for content management.
- `src/components/`: Reusable UI components (buttons, modals, SEO wrapper) styled with Tailwind and Shadcn-like structure.
- `src/layouts/`: Layout wrappers for public and admin routes, handling navigation, search, and real-time subscriptions.
- `src/lib/`: Utility functions and Supabase client configuration.
- `src/store/`: Global state management using Zustand (authentication state).
- `netlify/edge-functions/`: Serverless edge functions for handling dynamic bot requests for SEO.
- `public/`: Static assets, PWA manifests, and icons.

## Prerequisites

- Node.js (v20+)
- A Supabase project

## Environment Variables

Create a `.env` file in the root directory and add your Supabase credentials:

```env
VITE_SUPABASE_URL=your_supabase_project_url
VITE_SUPABASE_ANON_KEY=your_supabase_anon_key
```

## Running the Project Locally

1. **Install dependencies:**
   ```bash
   npm install
   ```

2. **Start the development server:**
   ```bash
   npm run dev
   ```

3. **Build for production:**
   ```bash
   npm run build
   ```

4. **Preview production build:**
   ```bash
   npm run preview
   ```

## Admin Access

The admin dashboard is located at `/admin/login`. Authentication is handled via Supabase Auth. To manage posts and portfolio items, users must have the appropriate roles or be authenticated as an admin in Supabase project setup.

## Deployment

This project is configured for deployment on Netlify. It leverages Netlify Edge Functions for dynamic OG image generation. 

- Push your code to your Git repository.
- Connect the repository to Netlify.
- Ensure the `VITE_SUPABASE_URL` and `VITE_SUPABASE_ANON_KEY` environment variables are set in your Netlify site settings.
- Netlify will automatically build the site using `npm run build` and deploy the output from the `dist` directory.
