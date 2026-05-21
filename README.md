# AIRA — AI Readiness Assessment

A single-file kiosk quiz for the Mindteam booth at the NAARB 2026 tech expo. Answers three questions about an arbitrator's work, AI experience, and biggest hesitation, then renders a personalized 5-day AI quick-start plan on screen. Captures email leads to `localStorage` for manual follow-up after the event.

## What it does

- Three-question quiz → personalized 5-day plan rendered in-browser
- Email capture saves to `localStorage` only — no external services, no webhooks, no backend
- Hidden admin screen: **long-press the Mindteam logo on the welcome screen for ~1.5 seconds**
  - View captured leads
  - Export as CSV (for Zoho Campaigns import)
  - Export as JSON (backup)
  - Copy CSV to clipboard
  - Clear all (after exporting)
- "Next visitor →" reset button after each capture
- 90-second idle timer auto-resets the kiosk if a session is abandoned mid-quiz

## iPad kiosk setup

1. Open the deployed URL in Safari on iPad
2. Tap Share → Add to Home Screen → launch from home screen icon for fullscreen
3. (Optional) Enable Guided Access (Settings → Accessibility → Guided Access) to lock the iPad to just this app for the booth

## Tech

Single static `index.html` — no build step, no dependencies. Deploys as static files anywhere.

## Origin

Adapted from the original quiz built by Isabelle for the same expo. Pivoted to a kiosk pattern with local-only capture for in-person collection and manual list import.
