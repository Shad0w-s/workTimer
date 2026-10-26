# Flip Timer

A full-screen flip-clock study timer inspired by Flocus. Open `index.html` in any browser, or run it with Docker.

## Features
- **Clock**: animated flip cards, or a plain "Simple" style (top-bar button or `A`).
- **Quick timers**: one-tap presets (5–60 min) or a custom h/m/s time, with an editable label.
- **Programs**: build sequences like *Study 10 → Break 5*, set the number of rounds, and save them by name.
  - Drag the grip handle to reorder steps (mouse or touch). Steps can be duplicated or removed.
  - Unnamed steps show as "Timer 1", "Timer 2", … and can be renamed to anything.
  - Durations take minutes (`25`) or minutes:seconds (`1:30`), with −/+ buttons.
  - Every step uses your default alarm sound unless you pick a different one for that step.
  - Saved programs save automatically as you edit them. Templates open as a new, unsaved copy.
  - Click a step chip under the clock to jump to that step.
- **Sound**: 7 alarm sounds with volume and preview, keep ringing until dismissed, auto-advance, desktop notifications, optional tick.
- **Themes**: 9 color themes (menus match the theme), 22 illustrated scenes, your own image, and scene dimming.

## Shortcuts
`Space` start/pause · `R` reset · `S` next step · `F` fullscreen · `A` clock style · `T` timers · `P` programs · `1–8` presets · `Esc` close

Settings, saved programs and your custom background are stored in your browser (localStorage).

## Deploy with Docker (Linux)
The image is nginx serving static files and works on both amd64 and arm64.

```sh
git clone https://github.com/Shad0w-s/workTimer.git && cd workTimer
docker compose up -d --build        # serves on http://<server>:8080
```

Without compose:

```sh
docker build -t flip-timer .
docker run -d --name flip-timer --restart unless-stopped -p 8080:80 flip-timer
```

To change the port, edit `ports` in `docker-compose.yml` (e.g. `"80:80"`). To update: `git pull && docker compose up -d --build`.

## Backgrounds
The 22 scenic backgrounds in `backgrounds/` are original lofi/anime-style illustrations generated with OpenAI Codex
image generation (see `backgrounds/CREDITS.md`). To swap one, replace `backgrounds/<name>.jpg` and
`backgrounds/thumbs/<name>.jpg` with files of the same name, or use **Theme → Upload image**.
