# Trick or Chores

A Halloween-themed chore app for iPhone. Installs to the home screen and runs full-screen (no Safari bars).

## Files
- `index.html` — the whole app (splash, chores, PIN verification, reward, parent settings)
- `manifest.json` — makes it installable on iPhone
- `sw.js` — lets it work offline once installed
- `icon-192.png`, `icon-512.png`, `apple-touch-icon.png` — app icons

## How it works
1. **Splash** — "Do you want to play a game?" Tap **Yes**.
2. **Chore list** — kid taps a chore, does it, taps "I did it!"
3. **Parent check** — phone goes back to the parent, who enters the PIN (default `1234`) to confirm.
4. Repeat until all chores are done → **reward screen**.
5. **⚙️ (top right)** — parent-only, PIN-gated. Add/remove/edit chores, set tonight's reward text, and change the PIN.

Everything (chores, reward, PIN) is saved on the device via localStorage, so it persists between visits once installed.

## Get it live at a link (free, ~5 minutes) — GitHub Pages
1. Create a free GitHub account if you don't have one, and create a new repository (e.g. `trick-or-chores`).
2. Upload all the files in this folder to that repo (drag-and-drop works on github.com, or use `git push`).
3. In the repo, go to **Settings → Pages**, set Source to the `main` branch / root, and save.
4. GitHub gives you a link like `https://yourname.github.io/trick-or-chores/` — that's your shareable link.

Alternatives that work the same way: **Netlify Drop** (netlify.com/drop — drag the folder in, get an instant link) or **Vercel**. Both are free for a static site like this.

## Installing on iPhone (once it's live)
1. Open the link in **Safari** (must be Safari, not Chrome).
2. Tap the **Share** icon → **Add to Home Screen**.
3. Launch it from the home screen icon — it opens full-screen, no browser bar.

## Using your own animated GIF on the splash screen
1. Save your GIF file in this same folder, named exactly **`splash.gif`**.
2. That's it — `index.html` already looks for `splash.gif` and displays it automatically. If the file isn't there, it falls back to the built-in jack-o-lantern animation, so nothing breaks if you forget this step.
3. Keep the file reasonably small (under ~2–3MB) so it loads fast on cellular data.
4. Make sure you have the rights to use the character/image (something you made, a licensed asset, or personal/family use of art you own) — Claude can't source or generate copyrighted characters for you, but the app is ready to display whatever file you provide.

## Customizing further
- Colors, fonts, and copy all live in `index.html` — the CSS variables at the top of the `<style>` block (`--pumpkin`, `--slime`, etc.) control the palette.
- Default chores/reward/PIN are set in the `defaultState` object near the top of the `<script>` block.
