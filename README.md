# Adeeg Hilib (Example Next.js app)

**What this contains**
- Next.js (app directory) + Tailwind CSS skeleton
- Google Sign-In integration (client-side) — you must provide your Google Client ID
- Supabase client helper (you must provide your Supabase URL and anon key)
- Simple API route to save users to `users` table in Supabase
- Dashboard page that shows sample products

**Quick start**
1. Install dependencies:
   ```bash
   npm install
   ```
2. Create a Supabase project and a `users` table (columns: id (uuid), email (text), name (text), created_at (timestamp))
3. Create a Google OAuth Client ID (Web app) and set authorized origins to http://localhost:3000 and your Vercel URL.
4. Create `.env.local` with:
   ```env
   NEXT_PUBLIC_GOOGLE_CLIENT_ID=your-google-client-id.apps.googleusercontent.com
   NEXT_PUBLIC_SUPABASE_URL=https://your-project.supabase.co
   NEXT_PUBLIC_SUPABASE_ANON_KEY=your-anon-key
   SUPABASE_SERVICE_ROLE_KEY=your-service-role-key (optional for server-side operations)
   ```
5. Run locally:
   ```bash
   npm run dev
   ```
6. Connect GitHub -> Vercel and set the same environment variables in Vercel project settings to deploy.

**Notes**
- This starter decodes Google ID token client-side for demo. For production, verify tokens server-side via Google token verification endpoint or libraries.
- The API route uses the Supabase anon key. For sensitive operations use a service role key on server only and secure it in env vars.
