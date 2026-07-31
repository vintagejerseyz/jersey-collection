# Jersey Collection

A React storefront for a Karachi football jersey store, connected to Supabase (products, orders, categories, discount codes, settings, storage, and admin auth).

## Run it locally

```bash
npm install
npm run dev
```

Opens at http://localhost:5173. Since this runs as a normal website (not inside claude.ai's sandboxed preview), the Supabase login and data calls in `src/App.jsx` will work normally here.

## Deploy to Vercel

1. Push this folder to a GitHub repo
2. Go to vercel.com → **Add New Project** → import that repo
3. Framework preset: **Vite** (auto-detected)
4. Build command: `npm run build`, output directory: `dist` (defaults, no change needed)
5. Deploy — you'll get a live URL like `jersey-collection.vercel.app`

## Deploy to Netlify

1. Push this folder to a GitHub repo
2. Go to app.netlify.com → **Add new site** → **Import an existing project**
3. Build command: `npm run build`, publish directory: `dist`
4. Deploy

Both also support drag-and-drop: run `npm run build` locally first, then drag the generated `dist` folder onto Netlify's deploy page (no GitHub needed for a quick test).

## Supabase config

Your Project URL and publishable key are already set in `src/App.jsx` near the top:

```js
const SUPABASE_URL = "https://knrcyjiefwcashecmopq.supabase.co";
const SUPABASE_ANON_KEY = "sb_publishable_ehwsMOILwOBrAXsJGESBLQ_l67AxvHc";
```

The database schema, RLS policies, storage bucket, and stock-decrement function were already created via the SQL script you ran earlier. Nothing else to configure — admin login, product CRUD, image upload, and checkout all talk to Supabase directly once this is running as a real deployed site.

## Admin access

Go to `/` → footer → **Admin Dashboard**, and log in with the admin user you created in Supabase → Authentication → Users.
