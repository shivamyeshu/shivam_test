# Stone Paper Scissors (Android app, MVP)

Two-player online game. One phone creates a room and gets a 5-letter code, the other joins with the code. Phones connect directly (PeerJS), so there is no server to host.

## Get the APK
Every push to `main` builds the APK on GitHub Actions and publishes it under **Releases**.
Direct link: `https://github.com/<your-username>/rps-app/releases/latest/download/rps-app.apk`

Install: open the APK on your phone and allow "Install unknown apps" for your browser when asked.

## Project layout
- `www/index.html` – the whole game (UI + game logic)
- `www/peerjs.min.js` – peer-to-peer library
- `android/` – Capacitor Android project
- `.github/workflows/build-apk.yml` – cloud build

## Build locally (optional, needs Android Studio + Java 21)
```
npm install
npx cap sync android
cd android && ./gradlew assembleDebug
```

## Notes
- Uses the free public PeerJS cloud to connect the two phones. On a few strict mobile networks the connection can fail; adding your own TURN server fixes that later.
