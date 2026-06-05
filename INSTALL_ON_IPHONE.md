# Install IRONCLAD on your own iPhone (free, no App Store)

This uses Xcode with a **free Apple ID** — no $99 developer account needed.
Note: with a free account the app stays installed for **7 days**, then you just
re-run it from Xcode to renew (or it's free forever once you join the paid program).

Everything below the project is already done: the iOS app, icon, splash, and
CocoaPods are all set up. Bundle ID: `com.ironclad.app` · App name: `IRONCLAD`.

## 1. Install Xcode (one time)
- Get **Xcode** from the Mac App Store (large download).
- Then run once in Terminal:
  ```bash
  sudo xcode-select -s /Applications/Xcode.app/Contents/Developer
  sudo xcodebuild -license accept
  ```

## 2. Add your free Apple ID to Xcode (one time)
- Open Xcode → **Settings… → Accounts → +** → **Apple ID** → sign in with your normal Apple ID.

## 3. Open the project
```bash
cd "/Users/shiva/Documents/GitHub/Gym-Workout-Program"
npm run open:ios          # opens ios/App/App.xcworkspace
```

## 4. Set signing
- In Xcode, select the **App** target → **Signing & Capabilities** tab.
- Check **Automatically manage signing**.
- **Team:** choose your name (Personal Team).
- If you see a "bundle identifier is not available" error, change the
  **Bundle Identifier** to something unique like `com.shiva.ironclad`,
  then also edit `appId` in `capacitor.config.json` and run `npm run sync`.

## 5. Plug in your iPhone & run
- Connect your iPhone with a USB cable. On the phone tap **Trust** if asked.
- At the top of Xcode, pick your **iPhone** as the run destination.
- Press the **▶ Run** button.

## 6. Trust the app on the iPhone (first time only)
- On the iPhone: **Settings → General → VPN & Device Management** →
  tap your Apple ID → **Trust**.
- Launch **IRONCLAD** from your home screen. Done!

## Renewing after 7 days (free account only)
- Reconnect the iPhone, open the project, press **▶ Run** again.

## After editing the app
Whenever you change `workout-app.html`:
```bash
npm run sync              # rebuilds www/ and copies it into the iOS app
```
then press **▶ Run** in Xcode again.
