# Post Curator 🌊

**A Bluesky tool to scan your posts, sort and filter by engagement, and delete the ones you don't want.**

Made by [ICZE4R](https://bsky.app/profile/iczer.one) • [→ Open the tool](https://icze4r.github.io/post-curator/)

---

## What it does

Bluesky gives you no way to bulk-manage your post history. Post Curator fixes that:

1. Logs in with your app password
2. Scans your posts (with optional reply inclusion) in paginated batches
3. Lets you sort by likes, reposts, replies, quotes, or date
4. Lets you set engagement thresholds — anything below gets highlighted
5. Lets you select posts individually, in bulk, or automatically by threshold
6. Deletes selected posts permanently via the official Bluesky API

Everything runs **entirely in your browser**. No server, no data collection, no tracking.

---

## How to use it

### Online (recommended)

Just open the tool: **[https://icze4r.github.io/post-curator/](https://icze4r.github.io/post-curator/)**

### Local

Download `index.html` and open it in any browser. No CORS issues — everything goes directly to Bluesky's API.

---

## Setup

**Step 1 — Get an App Password**

Go to [bsky.app/settings/app-passwords](https://bsky.app/settings/app-passwords) and create one. Use this instead of your main password. You can revoke it at any time.

**Step 2 — Choose what to scan**

Before connecting, select what you want to scan:
- **Posts** — your original posts only
- **Replies** — your replies to others only
- **Both** — everything

**Step 3 — Connect and scan**

Enter your handle and app password and hit **Connect & Scan →**. The tool loads your posts in batches of 100. Hit **Load More** to keep paginating until you've pulled as much history as you want.

**Step 4 — Filter and sort**

Use the filter bar to set minimum thresholds:
- **Min likes / reposts / replies / quotes** — posts below any of these get highlighted in red and marked "below threshold"

Sort the list by any metric or by date, ascending or descending.

**Step 5 — Select**

Three quick-select options:
- **Select all** — everything currently visible
- **Deselect all** — clear your selection
- **Select below threshold** — automatically checks every post that doesn't meet your thresholds

Or check/uncheck individual posts manually. Click any post's text to expand it if it's truncated.

**Step 6 — Delete**

Hit **🗑 Delete Selected**. You'll get a confirmation prompt first. The tool deletes posts one at a time with a small delay, and shows a live log of results.

---

## Filter reference

| Field | What it does |
|---|---|
| Min Likes | Highlights posts with fewer likes than this value |
| Min Reposts | Highlights posts with fewer reposts than this value |
| Min Replies | Highlights posts with fewer replies than this value |
| Min Quotes | Highlights posts with fewer quotes than this value |

All thresholds are independent — a post is marked "below threshold" if it falls short on **any** active threshold.

---

## Notes

- **Deletion is permanent.** There is no undo. The tool asks for confirmation before proceeding.
- Posts are loaded 100 at a time — use **Load More** to paginate through older history.
- The tool adds a 300ms delay between deletions to stay within Bluesky's rate limits.
- Deleted posts are greyed out in the list but not removed until you refresh or reset, so you can see what was processed.
- Post text is truncated to 3 lines by default — click any post to expand it.

---

## Privacy & security

- **Your credentials** go directly to `bsky.social` — nowhere else.
- **Nothing is stored** — no localStorage, no cookies, no external analytics.
- The entire tool is a single self-contained HTML file. You can read every line of it.

---

## Running on GitHub Pages

1. Fork or clone this repo
2. Rename `bluesky-curator.html` to `index.html`
3. Go to **Settings → Pages**
4. Set source to **Deploy from a branch** → `main` → `/ (root)`
5. Save — live within about a minute at `https://yourusername.github.io/post-curator/`

---

## Related Spite tools

- **[Spite — Bluesky BlockBack Tool](https://github.com/icze4r/blockback)** — find accounts blocking you and block them back
- **[Mute Manager](https://github.com/icze4r/mute-manager)** — convert mutes to blocks or clear them all
- **[The Eraser](https://github.com/icze4r/eraser)** — selectively or completely clear your blocks and mutes

---

## Credits

Built with the [Bluesky AT Protocol API](https://docs.bsky.app) — `getAuthorFeed`, `deleteRecord`.

---

## License

MIT — do whatever you want with it.
