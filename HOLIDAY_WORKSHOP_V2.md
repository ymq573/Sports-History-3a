# Holiday workshop v2

This version turns the holiday layer into a two-year civic calendar rather than a fragile single-API readout.

## Added
- Verified 2024 and 2025 U.S. federal holiday archive in `app.py`.
- Holiday data is fully self-contained in `app.py`; there is no external holiday API or localhost dependency.
- 2024/2025 year switcher and 12-month civic timeline in the Holidays section.
- Football-season holidays (August–December) are visually emphasized.
- The selected football game date is joined to the nearest holiday in the same year when 2024 or 2025 is active.
- Civic × Game Mix uses a 14-day fade window: 100% on the holiday, decreasing to 0% at 14 days.
- The existing light modifier remains capped at 1.35×, so football still drives the room and civic time modifies the atmosphere.
- Default `CFBD_SEASON` in `render.yaml` is 2025 so the football and holiday timelines line up immediately after deployment.

## Deployment
Keep `CFBD_API_KEY` secret in Render. No holiday environment variable is required.
