# Teacher feedback edition

Upload app.py, index.html, and static/stadium-night.jpg to your existing GitHub repository, preserving the static folder. Commit and redeploy. The old stadium-night.png can remain; the page now uses the JPG.

The stadium hero is first. The rest of the app uses matching dark concourse panels, scoreboard typography and red accents. The original nine mechanical systems and six fixed lights remain.

Select Season replay on the scoreboard to cycle through completed regular-season weeks every 12 seconds. Restart replay returns to the first completed week. Bye weeks retain a team's last completed result; before its first game no value is shown. Latest mode returns to the newest completed games. This mode is shared by visitors to the same server. API requests remain every 15 minutes, not every replay step. Replay is an accelerated interpretation: the room evolves continuously as the selected game changes, rather than resetting between games.

CFBD_SEASON sets the season for both modes. Choose 2025 for a completed season or keep 2026 for completed games so far. Set it in your host's environment settings and restart the service.

Loading improvements: the server begins serving the page while Numba prepares the simulation in a background thread. A preparing message appears until frames are available. The hero is compressed, the browser polls four times per second, and the simulation publishes eight frames per second. Hosting cold starts can still delay the first visit; these edits do not prevent a free host from sleeping. No live host timing has been measured.

Railway alternative: create a project from your GitHub repository, set the start command to python app.py, set CFBD_API_KEY and CFBD_SEASON as service variables, and generate a public domain in its networking settings. The app binds to the PORT supplied by either Railway or Render. Railway uses paid/usage-based hosting; review its current pricing and set a spending limit. Disable optional Serverless sleep if you want the service continuously available.
