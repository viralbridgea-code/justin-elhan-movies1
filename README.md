# JUSTIN ELHAN MOVIES — free website starter

This is a mobile-friendly movie catalogue with categories, search, and an admin sign-in page. You add a movie title, poster image URL, description, and a MediaFire/official download URL from your phone. Visitors see the listing on the public website.

## Important limitation
This starter publishes **movie listings and links**, not movie files. The file remains on MediaFire or another host. Only share films/posters/downloads you own or are licensed to distribute. Do not use it to distribute copyrighted movies without permission.

## What you need
- A free Supabase account (database + admin sign-in).
- A free GitHub account (host the website with GitHub Pages).

## Setup

### 1) Create the database
1. Create a project at https://supabase.com/.
2. Open **SQL Editor** in your Supabase dashboard.
3. Open `supabase_setup.sql`, copy all of it, paste it into SQL Editor, and click **Run**.

### 2) Create your admin login
1. In Supabase, open **Authentication → Users → Add user**.
2. Create your admin email and password.
3. Copy the new user's **UID**.
4. In SQL Editor, run this command after replacing the example UID:
   `insert into public.admin_users (user_id) values ('PASTE-YOUR-USER-UID-HERE');`

Do not put a service-role key in the website. Never share your admin password.

### 3) Connect the website to Supabase
1. In Supabase open **Project Settings → API** (or **Connect**).
2. Copy the **Project URL** and the **anon/public key**.
3. Open `index.html` in a text editor.
4. Replace `PASTE_YOUR_SUPABASE_PROJECT_URL` and `PASTE_YOUR_SUPABASE_ANON_KEY` with those values.
5. Save the file. The anon/public key is designed for browser use; security is enforced by the SQL policies. Never use the service-role/secret key here.

### 4) Publish free with GitHub Pages
1. Create a GitHub repository named `justin-elhan-movies`.
2. Upload `index.html` to the repository's root.
3. Open **Settings → Pages**.
4. Under Build and deployment choose **Deploy from a branch**, select `main` and `/ (root)`, then Save.
5. Wait for GitHub Pages to publish. Your free address will look like `https://YOUR-USERNAME.github.io/justin-elhan-movies/`.

### 5) Add movies from your phone
1. Open your published website.
2. Tap **Admin**.
3. Sign in with your admin email/password.
4. Enter the movie title, category, poster image URL, authorized MediaFire/official link, and description.
5. Tap **Publish movie**. Refresh the public page to see it.

## Notes
- Poster images should be public HTTPS image URLs.
- The MediaFire link should be a direct share page URL, not a private account link.
- If you change the Supabase project or keys, update `index.html` and republish it.
- Free plan limits and provider terms can change. Check the current provider dashboards for limits.
