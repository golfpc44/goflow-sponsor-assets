# GoFlow sponsor assets

Public distribution files for GoFlow sponsor banners and the read-only advertising feed.

## Contents

- `ads.json`: live feed. Initially empty, so the application uses its built-in house ads.
- `banners/`: approved public PNG, JPEG or WebP banners, each no larger than 1.5 MB. A 3:1 aspect ratio is recommended by the app.

Only publish material you have permission to distribute. Never add application source, user backups, credentials, private signing keys or VIP codes to this public repository.

## Publish a campaign

1. Upload the approved image to `banners/` using a new versioned filename, such as `partner-2026-11-v1.webp`.
2. Use the image's direct Raw URL in the desktop Admin Ad Manager, not its GitHub preview-page URL.
3. Set the target link, placement, start/end dates and campaign status in Admin. Export the advertising JSON.
4. Replace `ads.json` with the exported advertising configuration. Increase `revision` for every published change. Keep disabled campaigns Paused or remove them from the feed.
5. Clients load the updated feed when they next successfully sync. Offline clients retain cached content until their local end date; pausing a remote campaign cannot instantly reach an offline phone.

Live feed and example banner path:

`https://raw.githubusercontent.com/golfpc44/goflow-sponsor-assets/main/ads.json`

`https://raw.githubusercontent.com/golfpc44/goflow-sponsor-assets/main/banners/partner-2026-11-v1.webp`

In the private application project, put the real feed URL into `config/ads-sync.json` under `url`, then rebuild the mobile app. The image domain `https://raw.githubusercontent.com` is already allowed in `config/sponsor-trust.json`.

This repository does not store user analytics or provide an authenticated publishing API. Saving changes in the local Admin console alone does not publish them to GitHub. Raw-file caching may delay updates; it is not a guaranteed real-time CDN.
