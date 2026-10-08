EURO20 500-ODDS OVERSEER — FINAL ANDROID V3
==========================================
This final Android V3 is a mobile-first PWA plus a secure server relay.

IMPORTANT
- Analysis/prediction only. It does not log into Betway, place bets, cash out, or manage stakes.
- Betway does not appear to provide a general public developer odds API; this build therefore uses an independent odds-data provider through the relay.
- The API key stays server-side as an environment variable.
- The browser app calls /api/odds, avoiding exposing the provider key in Android.
- The 500.00 target is a research target, not a guarantee. The engine may return NO VALID 500 SET.

RECOMMENDED PROVIDER
Odds-API.io currently advertises Betway odds coverage and a free test tier. ParlayAPI is also supported by the relay adapter. Check provider terms/pricing before use.

FILES
frontend/  PWA
server/    Node/Express relay

SERVER SETUP
1. Install Node.js 20+.
2. cd server
3. npm install
4. Copy .env.example to .env
5. Put your provider key in ODDS_API_IO_KEY (or PARLAY_API_KEY).
6. npm start
7. Serve frontend from the same origin in production, or configure a reverse proxy.

ENV
PORT=8787
ODDS_API_IO_KEY=YOUR_KEY
PARLAY_API_KEY=YOUR_KEY

ANDROID INSTALL
The app must be hosted over HTTPS for the normal Chrome PWA install flow.
In Android Chrome, open the hosted app, tap ⋮, then Install and create shortcut / Install.
Google documents this exact flow here:
https://support.google.com/chrome/answer/9658361/use-progressive-web-apps-android

SECURITY
Do not put provider API keys in app.js, index.html, or the manifest.
Do not use a Betway username/password.
