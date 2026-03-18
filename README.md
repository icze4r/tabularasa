# The Eraser 🧹

**A Bluesky tool to selectively or completely clear your blocks and mutes.**

Made by Durandal

an [ICZE4R](https://bsky.app/profile/iczer.one) • [→ Open the tool](https://icze4r.github.io/tabularasa/bluesky-eraser.html/)

---

## What it does

Bluesky gives you no bulk management for your blocks or mutes. The Eraser fixes that:

1. Logs in with your app password
2. Fetches your complete block list and mute list from Bluesky's API
3. Shows both in tabbed lists with avatars, handles, and follow status
4. Lets you remove them selectively with checkboxes, or nuke everything at once

Everything runs **entirely in your browser**. No server, no data collection, no tracking.

---

## How to use it

### Online (recommended)

**[https://icze4r.github.io/tabularasa/bluesky-eraser.html/](https://icze4r.github.io/tabularasa/bluesky-eraser.html)**

### Local

Download `index.html` and open it in any browser. No CORS issues — everything talks directly to Bluesky's API.

---

## Setup

**Step 1 — Get an App Password**

Go to [bsky.app/settings/app-passwords](https://bsky.app/settings/app-passwords) and generate one. Never use your main password with third-party tools. Revoke it any time from the same page.

**Step 2 — Connect**

Enter your handle and app password and hit Connect. The tool fetches your follows, blocks, and mutes.

**Step 3 — Choose your tab**

- **🚫 Blocks** — everyone you've blocked
- **🔇 Mutes** — everyone you've muted

**Step 4 — Remove**

*Selective:*
Use the checkboxes to pick individual accounts. Toggle **Skip people I follow** to hide follows from selection. Hit **Unblock Selected** or **Unmute Selected**.

*Nuclear:*
Hit **💥 Unblock All** or **💥 Unmute All** to clear the entire list at once. Confirms before running.

---

## Filters

| Toggle | What it does |
|---|---|
| Skip people I follow | Excludes anyone you currently follow from the selection |

---

## Technical notes

Unblocking works by deleting the underlying AT Protocol block record from your repo — not just calling a simple API endpoint. The tool grabs the record URI during the initial fetch and uses it to delete cleanly. If the URI isn't available for any record it falls back to searching your repo automatically.

---

## Rate limits

- 300ms delay between unblock operations
- 250ms delay between nuclear-mode operations  
- If you hit rate limit errors mid-run, wait a few minutes and reconnect — already-processed accounts are marked done and won't be double-processed in the same session

---

## Privacy & security

- **Your credentials** go directly to `bsky.social` — nowhere else
- **No third-party services** used at all
- **Nothing stored** — no localStorage, no cookies, no analytics
- Single self-contained HTML file — read every line of it

---

## Running on GitHub Pages

1. Fork or clone this repo
2. Rename `bluesky-eraser.html` to `index.html`
3. Go to **Settings → Pages**
4. Set source to **Deploy from a branch** → `main` → `/ (root)`
5. Save — live within about a minute

---

## Related

- **[Spite — Bluesky BlockBack Tool](https://github.com/icze4r/blockback)** — find accounts blocking you and block them back
- **[Mute Manager](https://github.com/icze4r/mute-manager)** — convert mutes to blocks or clear them

---

## Credits

Built with the [Bluesky AT Protocol API](https://docs.bsky.app) — `getBlocks`, `getMutes`, `getFollows`, `deleteRecord`, `unmuteActor`.

---

## License

MIT — do whatever you want with it.
