# Pushup Counter Stream Overlay

Files:
- `overlay.html` = OBS / IRL Toolkit browser source
- `controller.html` = remote controller you can open from anywhere

## Firebase setup

1. Create or open your Firebase project.
2. Go to Realtime Database.
3. Create database.
4. Set rules for testing like this:

```json
{
  "rules": {
    ".read": true,
    ".write": true
  }
}
```

For a real stream, you can time-limit these later.

5. In Firebase project settings, copy the web app config.
6. Paste the config into both `overlay.html` and `controller.html`.

Look for this section in both files:

```js
const firebaseConfig = {
  apiKey: "PASTE_API_KEY",
  authDomain: "PASTE_PROJECT.firebaseapp.com",
  databaseURL: "https://PASTE_PROJECT-default-rtdb.firebaseio.com",
  projectId: "PASTE_PROJECT",
  storageBucket: "PASTE_PROJECT.appspot.com",
  messagingSenderId: "PASTE_SENDER_ID",
  appId: "PASTE_APP_ID"
};
```

## GitHub Pages setup

Upload both files to a GitHub repo.

Then enable GitHub Pages:
Settings → Pages → Deploy from branch → main → root

## URLs

Controller:
`https://YOURUSERNAME.github.io/YOURREPO/controller.html?room=brad-pushups`

Overlay:
`https://YOURUSERNAME.github.io/YOURREPO/overlay.html?room=brad-pushups`

## OBS setup

Add a Browser Source:
- URL: your overlay URL
- Width: 1000
- Height: 1000
- Background: transparent
- Refresh browser when scene becomes active: optional

The overlay is square and will scale cleanly.
