# Holiday calendar setup — self-contained

This build has **no localhost dependency and no second holiday server**.

The 2024 and 2025 U.S. federal holiday dates are stored directly in `app.py` as `HOLIDAY_ARCHIVE`. The Flask backend joins the active College Football Data game date to the nearest holiday and publishes `holiday_proximity` to the existing exhibit rules.

## Render
Only these environment variables are needed:
- `CFBD_API_KEY` — your College Football Data API key
- `CFBD_SEASON` — use `2025` for the current two-year civic-calendar comparison

Do **not** add `HOLIDAY_API_URL` or `HOLIDAY_YEAR`. They are not used in this build.

## Exhibit behavior
- Football points/margin continue to drive temperature, humidity, airflow, and base lighting.
- The selected game's date is compared with the nearest 2024/2025 federal holiday.
- Civic × Game Mix is 100% on the holiday and fades to 0% at 14 days away.
- The mix can amplify the six football-driven light setpoints by up to 1.35×.
