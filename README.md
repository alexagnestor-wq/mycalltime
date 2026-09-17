# My Call Time

Convert international call times to your chosen city or timezone. A simple web app with no installation needed.

## How to use

1. Paste a time, like `1 pm CET` or `6:00pm–6:30pm GMT +05:00`.
2. Choose your location and confirm the call date.
3. Click **Show my time**.

Switch between 12-hour and 24-hour formats in Settings, or use **Add to Calendar** to download an event for Apple Calendar and other calendar apps.

Your location and time format are remembered. Daylight saving is handled automatically; unclear timezone abbreviations ask for confirmation. If your town isn’t listed, choose a city in the same timezone.

## Run locally

With Node.js 20 or newer installed:

```sh
npm start
```

Open http://127.0.0.1:5173. No dependencies or build step required. To host the app, publish the `dist/` folder with a static web host.

Messages are processed in your browser. The app uses Google Fonts and stores your preferences locally.
