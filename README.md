# Palma Restaurant Finder Website

A website for finding restaurants in **Palma de Mallorca** with:

- Google rating **>= 4.5**
- Review count between **100 and 500**

## Why this version is easier to access

- It works immediately in **demo mode** (no API key required).
- It switches to **live mode** automatically when `GOOGLE_PLACES_API_KEY` is configured.
- You can deploy it as a public website (Render/Railway/Fly/etc.) and access it from any device.

## Run locally

1. Install dependencies:

   ```bash
   npm install
   ```

2. Optional: create a `.env` file for live Google data:

   ```bash
   GOOGLE_PLACES_API_KEY=your_google_places_api_key
   PORT=3000
   ```

3. Start:

   ```bash
   npm start
   ```

4. Open `http://localhost:3000`

## Deploy as a public website

### Option A: Render (recommended)

1. Push this repo to GitHub.
2. In Render, create a new **Web Service** from the repo.
3. Build command: `npm install`
4. Start command: `npm start`
5. Set environment variable `GOOGLE_PLACES_API_KEY` (optional for live mode).

After deploy, Render gives you a public URL like `https://your-app.onrender.com`.

## API endpoints

- `GET /api/config` → current mode (`demo` or `live`)
- `GET /api/restaurants?minRating=4.5&minReviews=100&maxReviews=500`

## Notes

- Live mode uses Google Places API `places:searchText`.
- Demo mode uses curated sample data in `data/demo-restaurants.json`.
