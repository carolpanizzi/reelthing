# reelthing

A personal movie and TV journal. Track what you watched, when you watched it, your rating, notes, genre, runtime, and creator. New users start with an empty library and can import their own Letterboxd export. Library changes are stored in the browser on the user's device.

## Run locally

```sh
npm install
npm run dev
```

Open the local address printed by Vite.

## Import Letterboxd

In Letterboxd, visit **Settings → Import & Export → Export Your Data** and download your archive. Unzip it, choose **Import** in reelthing, and select any combination of `watched.csv`, `ratings.csv`, `diary.csv`, and `reviews.csv`. The importer combines matching rows into film entries, preserves rewatches, and skips entries already in the library. Imports are handled locally in your browser.

The importer uses the diary's `Watched Date` when available and falls back to `Date` from `watched.csv` for other watched titles. The supplied personal archive file is excluded from Git by `.gitignore` and is not bundled into the app.

For a quick demo, the [`examples/letterboxd`](examples/letterboxd) folder contains sample Letterboxd CSVs using real film titles. The watch dates, ratings, and review text are fictional and included only to demonstrate importing. Select any or all of the CSV files in the Import dialog.

## Movie metadata

Open the gear menu, add a TMDB API key, and select **Fetch movie and series metadata**. Each entry's type selects the matching TMDB movie or TV endpoint. TMDB fills in posters, backdrops, synopsis, genre, runtime or seasons, director or creators, cast, and TMDB ratings; results are cached in your local library. To add IMDb ratings too, optionally provide an OMDb API key. Keys are stored in this browser only. TMDB requires attribution; the app includes its logo and required notice in the library settings.

## Data

Your personal library is saved in this browser's local storage. Open the gear menu to download a JSON backup or CSV export. Clearing browser site data will clear your library, so download a backup to keep a copy.
