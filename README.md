# My Call Time

A minimal dark-themed app that converts recruiter messages into the user’s chosen city or timezone.

## Run locally

Install Node.js 20 or newer, then run `npm start` from this folder. Open http://127.0.0.1:5173. No dependencies or build step are required. Set the `PORT` environment variable to use a different port.

## Use

1. Paste a time, such as `1 pm CET` or `Wednesday September 16 at 6:00pm - 6:30pm (GMT +05:00)`.
2. Choose **Your location** using the searchable city/timezone field. Confirm the source date, including the year. Clarify the source timezone if prompted.
3. Select **Show my time**.
4. Use **Add to Calendar** to download an `.ics` file. Open it in Apple Calendar and confirm the import.

Settings offers 12-hour and 24-hour formats; 12-hour is the default. The time format and destination timezone are saved in this browser. Belgrade is the initial default.

## Upload to GitHub

Create an empty repository on GitHub, then run these commands from this folder, substituting your repository URL:

```sh
git init -b main
git add .
git commit -m "Add My Call Time"
git remote add origin https://github.com/YOUR-USERNAME/YOUR-REPOSITORY.git
git push -u origin main
```

Extract the ZIP first and upload the folder's contents, including `.gitignore`. This export contains no credentials, account-specific Sites settings, or previous Git history. Uploading the source does not publish a website automatically.

## Hosting

Serve the contents of `dist/` with any static web host. No environment variables, API keys, backend, or build command are needed. Assets use relative paths, so hosting under a repository subpath is supported.

## Files

- `dist/index.html` — page markup
- `dist/style.css` — dark theme and responsive layout
- `dist/core.js` — parsing, timezone conversion, calendar generation
- `dist/app.js` — interactions and preferences
- `scripts/serve.cjs` — local preview server

Run `npm run check` for JavaScript syntax checks.

## Timezone behavior

The parser supports common short time phrases, named months, ISO dates, GMT/UTC offsets, selected city names, and IANA timezone identifiers. It is not a general natural-language or invitation parser. Review the interpreted time and source date before converting.

City timezones use the browser's timezone database. Explicit offsets remain fixed. Ambiguous abbreviations prompt for clarification. Times skipped or repeated during daylight-saving transitions require an exact UTC offset. Calendar files use UTC timestamps to preserve the instant and duration.

Missing years and weekday/date mismatches are flagged. When no end time is supplied, the selected duration controls the calendar event.

## Privacy and fonts

Messages are processed locally in the browser, not sent to an API. The app loads DM Sans from Google Fonts, with a system-font fallback. The time-format and destination-timezone preferences are saved in local browser storage.

No open-source license has been selected. Choose a license if you intend to permit reuse of a public repository.

The destination list includes the IANA timezones supported by the browser, with extra familiar city aliases. If your town is not listed, select a representative city in the same timezone.
