# Daily Prayer & Scripture

A single self-contained HTML page that shows a fresh prayer and Bible verse each day, over a rotating bank of nature photography. No server, no API keys, no costs to operate.

## What it does

When `index.html` is opened in any modern browser, the page displays:

- A time-aware greeting ("Good morning ☀️" / "Good afternoon 🌤️" / "Good evening 🌙") based on the visitor's local clock.
- A warm, encouraging prayer (2–4 sentences).
- A thematically matched Bible verse from the NIV or NLT translation, with reference and translation label.
- The closing line "God is good, all the time."
- A full-bleed nature photograph as the background, with a soft dark overlay for legibility and a small photographer credit in the bottom-right corner.

Four buttons under the card let visitors revisit yesterday's prayer, Shuffle (pull a different prayer from a separate bonus pool — see below), Share the current prayer (uses the native share sheet on mobile, falls back to clipboard on desktop), or Copy it as plain text suitable for pasting into a message. The "← Previous day" button only steps back one day — once you're viewing yesterday it becomes disabled, so visitors can't keep browsing further into the archive. Whenever the visitor is viewing anything other than today's daily prayer (yesterday or a shuffled entry), a subtle "← Back to today's prayer" link appears so they can return in one tap.

## How the rotation works

Everything that rotates does so deterministically based on the calendar date, so every visitor opening the page on the same day sees the same prayer and the same photo. The next day, everyone sees a different one.

- The daily prayer pool contains **100 hand-curated entries**. With deterministic hashing of the date, the same prayer won't recur for over three months, and even when it does, the order is scrambled so it never feels patterned.
- A separate **shuffle pool** of **45 additional entries** powers the Shuffle button. This pool is completely independent of the daily rotation — pressing Shuffle never reveals or "spoils" a prayer from the upcoming daily schedule, and editing one bank has no effect on the other.
- The photo pool contains **24 nature images** (6 mountain vistas, 6 waterfalls, 6 streams/lakes, 6 lush forests). It uses an independent hash from the prayer rotation, so the prayer-and-photo pairing shuffles fresh each day. The photo does NOT change when Shuffle is pressed — only the prayer and verse do.
- If the page is left open across midnight, the prayer, photo, and greeting all refresh automatically without a reload (and any active shuffle is replaced by the new day's daily prayer). The greeting also updates live when the local clock crosses noon or 6 PM.
