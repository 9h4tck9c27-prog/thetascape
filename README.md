# Thetascape

Pick a world. Follow the light. Feel calmer in a few minutes.

Thetascape is a small web app for slower breathing. You choose one of four worlds (Grid, Contour, Tide or Bloom), choose 1, 5 or 10 minutes, and follow Epsilon, a point of light that traces a square for box breathing: four seconds in, four holding, four out, four holding. After two guided breaths you close your eyes, and a bowl rings when you're done.

## What's here

| File | What it does |
| --- | --- |
| `index.html` | The whole app: screens, the four animated worlds, the breath guide, sound and progress tracking |
| `manifest.webmanifest` | Lets people add Thetascape to their home screen as an app |
| `sw.js` | Keeps the app working offline once it has been opened |
| `icons/` | Home-screen and browser icons, plus a 1024 px master |
| `og-image.png` | The 1200 × 630 preview shown when the link is shared |

There's no build step and no framework. The app is one HTML file.

## Sounds

The four world sounds are included in `audio/`. Each is a 10-minute piece, and they loop with an 8-second crossfade if a session runs longer.

| File | Plays | Included |
| --- | --- | --- |
| `audio/grid.mp3` | In the Grid world | Yes |
| `audio/contour.mp3` | In the Contour world | Yes |
| `audio/tide.mp3` | In the Tide world | Yes |
| `audio/bloom.mp3` | In the Bloom world | Yes |
| `audio/opening.mp3` | Once, when you tap the star | No, licensed separately |
| `audio/bowl-end.mp3` | Once, when a session ends | No, licensed separately |

Add the last two files to `audio/` to hear the opening flute and the closing bowl. Without them those moments are simply silent.

## Run it locally

```sh
python3 -m http.server 8000
```

Then open http://localhost:8000. Opening `index.html` directly as a file also works, but offline caching only starts when it's served.

## Put it online with GitHub Pages

1. In the repository on GitHub, open **Settings → Pages**.
2. Under **Build and deployment**, choose **Deploy from a branch**, pick `main` and the root folder, then **Save**.
3. After a minute the app is live at `https://<your-username>.github.io/thetascape/`.

A site published this way plays the four world sounds. The opening flute and closing bowl stay silent until those two files are hosted somewhere you're licensed to put them.

## Before launch

- Fill in the placeholders in the Privacy and Terms sheets in `index.html`: `[CONTACT EMAIL]`, `[OWNER NAME]` and `[DATE]`.
- Set `SHARE_URL` near the top of the script to the app's public address.
- The sharing tags in `index.html` point to `https://9h4tck9c27-prog.github.io/thetascape/`. If the app moves to its own domain, update the `og:url`, `og:image` and `twitter:image` addresses.
- When you change the app, bump `CACHE` in `sw.js` (for example to `thetascape-v2`) so returning visitors get the new version.

## Privacy

Thetascape has no accounts, ads or analytics. Sessions and "how do you feel" answers are stored only in the visitor's own browser.

© Thetascape. All rights reserved.
