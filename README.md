# Trade Desk — public record

**Paper / hypothetical results – not real trades. Not investment advice.**

Every trading day at 06:35 and 12:10 (Los Angeles) the day's picks (ticker, side, entry, stop, target, publish time and a
random nonce) are serialised and hashed with SHA-256. **Only the hash** is committed here (`commits/<date>.json`) before the
picks are sent anywhere. After the market closes the exact hashed text is published in `reveals/<date>_<slot>.json`.

Verify a day: `sha256sum reveals/2026-10-07_0635.json` (macOS: `shasum -a 256`) must equal the `sha256` committed that
morning in `commits/2026-10-07.json` — see the commit history for when it was pushed.

Results are in R (1R = the planned distance from entry to stop). Closed results are appended to `trades/*.jsonl` and never
rewritten or deleted. Start date: 2026-10-07. Page: https://record.kcventures.xyz/
