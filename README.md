# bring-it-showcase
A one-page showcase for the Bring-IT app. Plain static HTML, no build step.

```sh
python3 -m http.server 4321    # then open http://localhost:4321
```

## Screenshots
Each feature section shows a phone. Drop a screenshot into `screenshots/` with the matching name and it replaces the built-in mock screen:

| File | Section |
|---|---|
| `screenshots/events.png` | Events list |
| `screenshots/details.png` | Event details |
| `screenshots/friends.png` | Friends |
| `screenshots/push.png` | Push notifications (lock screen) |

The phone frame matches an iPhone 18 Pro screenshot (1206×2622). The current files are those captures resized to 600px wide.

They were taken in the iOS Simulator from the bring-it Debug build. The backend ran against a separate `bringit_showcase` database (`db:seed` wipes the database it targets), with event dates moved into the future. Ads were turned off for the session (`useStartAds(false)` in `app/(app)/_layout.tsx`, then reverted). The push screen uses `xcrun simctl push` with copy from `backend/server/utils/notificationText.ts`.

## Store links
The Google Play button points to `app.bringit.mobile`. The App Store button is a placeholder until the app has a listing: set its `href` in the `stores-tpl` template in `index.html`.

Colors and fonts mirror `bring-it/frontend/src/theme/tokens.ts`.
