# HANDOFF: GTA VI Launch Answers (`gta6-launch-answers`)

## 1. Live URLs & Account Verification

| Item | Value |
| :--- | :--- |
| **Live Production URL** | https://gta6-launch-answers.vercel.app/ |
| **Live Sitemap URL** | https://gta6-launch-answers.vercel.app/sitemap.xml |
| **Live Robots URL** | https://gta6-launch-answers.vercel.app/robots.txt |
| **GitHub Repository URL** | https://github.com/AA29I/gta6-launch-answers |
| **Vercel Project Name** | `gta6-launch-answers` |
| **GitHub Account Used** | **`AA29I`** (Muhammad Ahmad Amir — `ahmedaamirctn@gmail.com`, GitHub User ID `106842958`) |
| **Vercel Account Used** | **`aa29i`** (`ahmedaamirctn@gmail.com`, Vercel User ID `iSPiSScNwBZD23lu4BQe5P44`, personal Hobby scope `mett-global` / `aa29i's projects`) |
| **Domain Purchased?** | **No** — deployed on the free `.vercel.app` subdomain over HTTPS as required. |

> **Account Rule Verification Note:** Before creating the repository or deploying, the machine's credentials were inspected. Git Credential Manager held both `AA29i` and `Rehanminhas03`. All GitHub API and Git push operations were explicitly pinned to Ahmad's account (`AA29I`), and Vercel CLI (`vercel whoami`) was verified as signed into Ahmad's account (`aa29i` / `ahmedaamirctn@gmail.com`). Rehan's accounts were never used.

---

## 2. Live Deployment Verification Checks (Section 8, Step 7)

All checks were executed against the live deployed site (`https://gta6-launch-answers.vercel.app/`) using headless Chromium via Playwright and HTTP probes:

| Check | Result | Verification Details |
| :--- | :---: | :--- |
| **1. Live URL & HTTP 200** | **PASS** | `https://gta6-launch-answers.vercel.app/` returns `HTTP 200 OK`. |
| **2. Live Countdown Ticking** | **PASS** | Counts down every second to `2026-11-19 00:00:00` in the visitor's local timezone (`#cd-days`, `#cd-hours`, `#cd-minutes`, `#cd-seconds` verified ticking from `3d 1h 52m 43s` to `3d 1h 52m 41s`). |
| **3. Automatic Launch-State Flip** | **PASS** | Tested by advancing clock past `2026-11-19T00:00:00` local time: `#hero-headline` automatically changes to `"GTA VI is out now"` and all four countdown cells display `"0"`. |
| **4. Sticky Mini Countdown Bar** | **PASS** | `#sticky-bar` (`GTA VI — Nov 19` + remaining `d/h/m/s`) stays hidden while hero is in view and slides into the top bar (`is-visible`) once the hero scrolls out of view without covering anchor content (`scroll-padding-top: 68px`). |
| **5. Add to Calendar Link** | **PASS** | Links to `https://calendar.google.com/calendar/render?action=TEMPLATE&text=GTA+VI+launch+day&dates=20261119/20261120&details=...` (all-day Google Calendar event on `2026-11-19` titled `"GTA VI launch day"`). |
| **6. World Table IANA Timezone Maths** | **PASS** | Computes `2026-11-19 00:00` in all 9 cities (`Los Angeles`, `New York`, `London`, `Berlin`, `Dubai`, `Karachi`, `Mumbai`, `Tokyo`, `Sydney`) using `Intl.DateTimeFormat` and converts each into the visitor's local timezone:<ul><li>**Spot-check Tokyo (`Asia/Tokyo`, UTC+9)**: `2026-11-19 00:00 JST` = `2026-11-18T15:00:00Z` → renders as **`8:00 PM | Wed, Nov 18, 2026`** in `Asia/Karachi` (UTC+5).</li><li>**Spot-check Los Angeles (`America/Los_Angeles`, UTC-8)**: `2026-11-19 00:00 PST` = `2026-11-19T08:00:00Z` → renders as **`1:00 PM | Thu, Nov 19, 2026`** in `Asia/Karachi` (UTC+5).</li></ul> |
| **7. Instant Search & Empty State** | **PASS** | Filtering for `"79.99"` displays 1 matching card; filtering for `"xyznomatch123"` displays 0 cards and reveals the friendly `"No answer matches yet"` state; clicking reset restores all 10 cards. |
| **8. All 10 Answer Cards Word-for-Word** | **PASS** | All 10 questions (`<h3>`), answers, `"Checked 15 Nov 2026"` labels, and `"Status: ..."` notes match Section 5 word-for-word in the served HTML. |
| **9. Platform Strip & Channel CTA** | **PASS** | `PlayStation 5` and `Xbox Series X|S` store search cards (no affiliate tags) and full-width `"Watch Lamplit on YouTube"` button (`https://www.youtube.com/channel/UCuQe1HBp3wTwYS6ad5IwYtQ`) with exact subline verified. |
| **10. Legal Footer Word-for-Word** | **PASS** | Matches Section 7 word-for-word. |
| **11. Phone (`360px`) & Desktop (`1280px`) Layout** | **PASS** | Verified at `360x800` (`scrollWidth === 360`, zero horizontal overflow) and `1280x900` (`scrollWidth === 1280`, zero horizontal overflow). All interactive tap targets are `>= 44px` tall. |
| **12. Console Errors & External Images** | **PASS** | `0` console errors, `0` page errors, `0` external images, `0` Rockstar/Take-Two assets. Only external requests are Google Fonts (`Outfit` & `Plus Jakarta Sans`). |
| **13. Sitemap, Robots, Canonical & JSON-LD** | **PASS** | `/sitemap.xml` (`HTTP 200`) and `/robots.txt` (`HTTP 200`) carry `https://gta6-launch-answers.vercel.app/`. Canonical, Open Graph, and Twitter URL tags match `https://gta6-launch-answers.vercel.app/`. `FAQPage` JSON-LD parses with 0 errors and matches all 10 visible cards word-for-word. |

---

## 3. Google Search Console: 2-Minute Finishing Steps for Ahmad (Section 6.2)

Because Google Search Console requires an interactive browser session signed into your Google account, complete these three quick steps in your browser (takes under 2 minutes):

1. **Add Property & Verify Ownership**:
   - Open [Google Search Console](https://search.google.com/search-console) signed in with Ahmad's Google account (`ahmedaamirctn@gmail.com`).
   - Click the property selector (top-left) → **Add property** → choose **URL prefix** and enter:
     ```text
     https://gta6-launch-answers.vercel.app/
     ```
   - Under **Other verification methods**, choose **HTML tag** (or **HTML file**).
   - If you copy the `<meta name="google-site-verification" content="..." />` tag (or download the `google*.html` file into `D:\GTA6`), commit and push to `main` (Vercel is connected to `AA29I/gta6-launch-answers` and will auto-deploy in ~5 seconds), then click **Verify**.
2. **Submit Sitemap**:
   - In the left sidebar, click **Sitemaps**.
   - Under **Add a new sitemap**, enter:
     ```text
     sitemap.xml
     ```
   - Click **Submit** and confirm the status reads **Success**.
3. **Request Homepage Indexing**:
   - Click **URL Inspection** in the left sidebar (or top search bar) and paste:
     ```text
     https://gta6-launch-answers.vercel.app/
     ```
   - Click **Request Indexing**.

---

## 4. Details Currently Marked Unconfirmed / Pattern-Based & Freshness Protocol

Per the Honesty Rule (Section 5) and Freshness Protocol (Section 6.6), the following items are explicitly labelled as unconfirmed, reported, or pattern-based as of the **15 Nov 2026** check date:

1. **Card 3 — PC Release (`Is it coming to PC?`)**: Marked `Status: Status as of the check date.` (Not at launch; Rockstar has not announced a PC release date.)
2. **Card 4 — Regional Unlock Hour (`What time does it unlock?`)**: Marked `Status: Pattern based, not yet confirmed per region.` (Expected around midnight local time on November 19 following Rockstar's usual pattern.)
3. **Card 7 — Price (`How much will it cost?`)**: Marked `Status: Reported price, not yet on Rockstar's site at check date.` (Standard edition widely reported at $79.99, not yet posted on Rockstar's own site.)
4. **Card 8 — Download Size & Preload (`How big is the download, and when does preload open?`)**: Marked `Status: File size unconfirmed as of the check date.`
5. **Card 9 — Early Access (`Is there early access?`)**: Marked `Status: Status as of the check date.`
6. **Card 10 — Online Mode (`Will there be an online mode?`)**: Marked `Status: Status as of the check date.`

**How to update when Rockstar confirms any detail (Section 6.6):**
In **one single commit**, update inside `index.html` and `sitemap.xml`:
1. The visible card answer text (`<p class="answer-body">`)
2. The card status badge (`<span class="status-note">`)
3. The `"Checked"` date on every card (`<span class="check-date">`) and in the legal footer
4. The matching `acceptedAnswer.text` entry inside the `<script type="application/ld+json">` `FAQPage` block
5. The `<lastmod>` date in `sitemap.xml`
6. Log the update in this `HANDOFF-launch-page.md` file, then `git push origin main` (which automatically deploys to `https://gta6-launch-answers.vercel.app/`).
