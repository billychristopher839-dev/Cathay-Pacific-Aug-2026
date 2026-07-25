# Brushwings to #1 — Cathay Pacific (August 2026)

A gamified daily to-do / habit tracker. You play the **CEO of Cathay Pacific**.
Complete your daily schedule across all **31 days of August 2026**, open the
entire route network one flight at a time, and climb the Skytrax-style
leaderboard until Cathay is crowned **#1 airline in the world**.

It's a single, fully self-contained `index.html` — no build step, no external
assets, no internet required. Open it and play.

## How it works

- **Edit your flight plan.** Set your own daily tasks and time blocks in the
  Command Deck. Overlapping times are flagged for you.
- **Log each day.** Tick off tasks in the day modal:
  - **≥ 75% complete → +8 points** and a new route opens.
  - **100% complete → +16 points** and a premium route opens.
  - **Under 75%** costs you nothing — the route simply waits.
- **Open the network.** Each qualifying day reveals one real Cathay route,
  ordered from the quiet frontiers (Ürümqi) up to the flagship (London Heathrow).
- **Climb the board.** Live points lift Cathay past ten real rival carriers.
  Finish all 31 days and Cathay is pinned at **#1** — game over, you won.

### Design principle: progress is never punished
Your **unlocked routes are a high-water mark** — a bad day lowers your live
points and breaks your streak, but it **never erases routes you've already
opened**. The game is meant to support consistency, not punish a stumble.

## Saving

Progress is stored with a three-tier fallback, chosen automatically:

1. `window.storage` (Claude workspace, when present)
2. `localStorage` (normal browser / GitHub Pages)
3. in-memory (last resort, current session only)

The footer always tells you which tier is active.

## Deploy on GitHub Pages

1. Put `index.html`, `.nojekyll`, and this `README.md` in a repo.
2. Settings → Pages → deploy from branch (root).
3. The included **`.nojekyll`** file disables Jekyll so nothing is rewritten.

> Tip for local testing: open via a local server (`localhost`) rather than a
> bare `file://` path if you want `localStorage` persistence to behave exactly
> as it will on Pages. The game still runs fine from `file://` — it just falls
> back to in-memory storage in some browsers' null-origin sandboxes.

## Notes

- The **route popularity order is an informed approximation** of Cathay's real
  network and is fully visible in the code if you'd like to reorder it.
- The **"Move Beyond" brand film** uses a click-to-load thumbnail (privacy-friendly
  `youtube-nocookie.com`) so nothing loads until you choose to play it.
- Built to run offline: system fonts only, all imagery inline.
