# AIRA — AI Readiness Assessment

A Mindteam product line for in-person AI-readiness conversations with professionals.
Each subfolder is a self-contained variant; deploy whichever one is current for the event.

## Modules

### `naa/` — National Academy of Arbitrators (NAARB 2026)

The deployed variant for the Mindteam booth at the NAARB 2026 tech expo in Chicago.
A three-question quiz that generates a personalized 5-day AI quick-start plan for
arbitrators. Captures email leads to `localStorage` for manual follow-up between
sessions and post-event list import to Zoho Campaigns.

### `kiosk/` — Generic baseline

The first cut of the kiosk version. Preserved as a reference; the NAA module forks
from this for event-specific refinements (real logo, larger UI, honest follow-up copy).

## Kiosk pattern

All variants share the same shape:

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
2. Tap Share → Add to Home Screen → launch from home-screen icon for fullscreen
3. (Optional) Enable Guided Access (Settings → Accessibility → Guided Access) to lock the iPad to just this app for the booth

## Deployment

Netlify is configured to publish from the active module's folder (see `netlify.toml`).
To switch which module is deployed, edit the `publish` value in `netlify.toml`.

## Tech

Single static `index.html` per module — no build step, no dependencies.

## Origin

Adapted from an earlier version built by Isabelle for the same expo. Pivoted to a kiosk
pattern with local-only capture for in-person collection and manual list import.
