# Blendin — The Imposter Game

A single-file, no-build web app. Free to host on Vercel, works great as an
"app" on your iPhone home screen (Add to Home Screen = full-screen, no browser bar).

## Deploy to Vercel (free, ~2 minutes)

**Easiest way — no coding tools required:**

1. Go to https://vercel.com and sign up (free) with GitHub, GitLab, or email.
2. Click **Add New → Project**, then choose **"Deploy without Git"** /
   drag-and-drop (Vercel shows a drop zone) — drag in this whole folder
   (`imposter-app`, containing `index.html` and `vercel.json`).
3. Click **Deploy**. In ~20 seconds you'll get a live URL like
   `https://blendin-yourname.vercel.app`.

**Alternative (GitHub route, also free):**
1. Create a new GitHub repo, upload `index.html` and `vercel.json` to it.
2. On vercel.com click **Add New → Project → Import Git Repository**, pick the repo.
3. Framework preset: "Other" (it's plain HTML, no build step). Click **Deploy**.

## Add it to your iPhone like a real app

1. Open your new Vercel URL in **Safari** on your iPhone.
2. Tap the **Share** icon (square with an arrow) at the bottom.
3. Tap **Add to Home Screen**.
4. It now opens full-screen with its own icon — no Safari address bar.

## How to play

1. Set the number of players and type in names.
2. Pick a word category.
3. Tap **Start Round** — the app secretly picks one random imposter and a word.
4. It tells you who starts. Pass the phone person to person; each player taps
   their card once to see either **the word** or **IMPOSTER** — no one else
   should look.
5. Once everyone's seen their card, go around describing the word out loud
   with one clue each (the imposter has to fake it and blend in).
6. When you're ready, tap reveal to find out who the imposter was, then
   score the round and start the next one. Scores persist across rounds
   in the session, and player names are remembered on that phone for next time.

## Editing word packs

Open `index.html` in any text editor and look for the `const PACKS = {`
block near the top of the `<script>` section — it's clearly marked with a
comment. Each category is a simple object with an emoji, a label, and a
list of words. To add a word, add it to a list; to add a whole new
category, copy an existing block and give it a new key. New packs show
up automatically as a chip on the setup screen — no other code needs to
change. Redeploy `index.html` to Vercel after editing.

There's also an **Unhinged** pack included (dark humor, drama, chaotic
party energy — flagged 18+) for rowdier groups.

> **Note on opening it locally:** if you just double-click `index.html`
> on your computer instead of going through Vercel, that's fine — the
> word packs are built into this one file, so there's nothing else it
> needs to load.

## Notes

- 100% client-side — no backend, no database, no accounts. Free Vercel
  static hosting is all you need.
- Works offline after first load (just don't force-quit before it loads once).
- Everything (players, last-used category) is saved in the browser's
  local storage on that device only.
