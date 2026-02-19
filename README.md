# Voyageur - Family Itinerary Planner **DEMO:**https://whimsical-sunflower-87ee77.netlify.app/

A shared travel planner built with a single-page HTML app + Supabase.

## Why I Built This

I built this project to help my family plan trips together in one place, without messy chat threads and scattered notes.  
I wanted something simple enough for everyone to use, but still practical with itinerary planning, budget tracking, packing lists, and shared updates in real time.

## Features

- Trip planning with destinations, dates, and notes
- Day-by-day itinerary with activities
- Accommodation, transport, budget, and packing tabs
- Currency conversion for activity/expense costs
- Supabase email/password authentication
- Shared collaboration mode for family usage
- Offline cache + queued sync when reconnecting
- Mobile-responsive layout

## Tech Stack

- Frontend: Vanilla HTML/CSS/JavaScript (`index.html`)
- Backend: Supabase (Auth + PostgREST + RLS)

## Local Run

Open with any static server (example):

```bash
npx serve .
```

Then open the local URL in your browser.

## Supabase Setup

1. Create a Supabase project.
2. Add your project URL + anon key in app config (or runtime injection).
3. Run DB migration for `user_id` columns + RLS policies.
4. Keep only **anon/publishable** key in frontend.
5. Never expose **service_role** key in frontend code.

## Shared Family Mode

This app is configured for shared family collaboration:

- All authenticated family members can view shared data.
- Writes include `user_id` for traceability.
- Access behavior is controlled by:

```js
window.__VOYAGEUR_ENABLE_USER_SCOPE
window.__VOYAGEUR_ACCESS_MODE
```

Current default in app:

- user scope: enabled by default
- access mode: `shared`

## Deploy

You can deploy this as static hosting on:

- Vercel
- Netlify
- Cloudflare Pages
- GitHub Pages

After deploy:

1. Set Supabase Auth `Site URL` to your deployed domain.
2. Add redirect URLs in Supabase Auth settings.
3. Test with at least 2 accounts.

## Project Structure

```text
.
├── index.html
└── README.md
```

## License

MIT (or your preferred license).
