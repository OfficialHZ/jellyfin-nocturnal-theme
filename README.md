# 🌙 Nocturnal — a Jellyfin theme

A dark, night-inspired theme for Jellyfin with a Netflix-style layout, deep navy
backgrounds and violet-to-blue accents.

## Features

- **Login and server screens:** glass card over a blurred poster wall
- **Home:** see-through top bar, pill switcher for Home/Favorites, bold row
  titles, cards whose picture zooms inside its frame on hover
- **Side menu:** floating glass panel with icon chips
- **Movie and show pages:** Netflix-style hero with the backdrop behind the
  info, poster on the left, big "▶ Play" button, round cast photos, seasons in
  one row and a Netflix-style episode list
- **Library pages:** centered toolbar, A–Z picker, gradient count badges
- **Filter and Sort windows:** rounded panels with toggle chips
- **Video player:** Netflix-style controls, gradient progress bar, restyled
  Skip Intro button
- **Search, Settings menu and admin Dashboard** styled to match
- **Phones and touch screens** adjusted, plus focus styles for TV remotes

## Installation

1. In Jellyfin, open **Dashboard → Branding**.
2. Paste this into **Custom CSS code** and click **Save**:

```css
@import url('https://cdn.jsdelivr.net/gh/OfficialHZ/jellyfin-nocturnal-theme@main/theme.css');

:root {
  /* Your server's address, so the login background works in every app */
  --noc-login-bg: url('http://YOUR-SERVER-IP:8096/Branding/Splashscreen');
}
```

3. Refresh the page (Ctrl+F5). In the desktop app, restart it and sign in once
   so it picks up the new CSS.

> After an update to the theme, jsDelivr can take up to ~12 hours to serve the
> new version. To pin a specific version, replace `@main` with a release tag,
> for example `@v1.0.0`.

### Login background

The login screen uses your **splash screen image** as its background. Upload
one in **Dashboard → Branding → Splash screen** (a wall of posters looks great).

### Optional: "Connected to" pill on the login screen

Paste this into **Dashboard → Branding → Login disclaimer**:

```html
<span class="noc-status">Connected to <b>My Server</b></span>
```

## Customization

Add any of these below the `@import` line, inside `:root { }`, to change the
look without editing the theme:

| Variable | Default | What it does |
|---|---|---|
| `--noc-accent` | `#38bdf8` | Main accent color (buttons, highlights) |
| `--noc-accent-2` | `#8b5cf6` | Second gradient color |
| `--noc-bg` | `#07080d` | Page background |
| `--noc-font` | `'Inter', sans-serif` | Font |
| `--noc-card-radius` | `8px` | How rounded posters and tiles are |
| `--noc-login-title` | `"HZ Server"` | Title on the login screen |
| `--noc-login-subtitle` | `"Sign in to your media server"` | Subtitle on the login screen |
| `--noc-login-blur` | `14px` | Blur of the login background (`0px` = sharp) |
| `--noc-row-title-size` | `2.5em` | Size of row titles on the home screen |
| `--noc-card-title-size` | `1.6em` | Size of names under cards on the home screen |
| `--noc-library-labels` | `block` | `none` hides the names under library tiles |
| `--noc-play-label` | `"Play"` | Text on the movie page Play button |
| `--noc-detail-poster` | `block` | `none` hides the poster on movie pages |
| `--noc-poster-width` | `15vw` | Poster size on movie pages |
| `--noc-detail-text-size` | `1.25em` | Text size on movie pages |
| `--noc-season-width` | `11vw` | Size of season posters |
| `--noc-episode-thumb` | `17vw` | Size of episode thumbnails |

Example:

```css
:root {
  --noc-accent: #f472b6;          /* pink instead of blue */
  --noc-login-title: "Movie Night";
}
```

## Compatibility

- Built and tested on **Jellyfin 10.11** (web client and Jellyfin Media Player 1.12).
- Works with the web client, the desktop app, the mobile apps, and the LG
  (webOS) and Samsung (Tizen) TV apps.
- **Not supported:** Android TV, Fire TV, Roku and Apple TV (Swiftfin). Those
  apps are native and don't use Custom CSS.

### Plugins with specific styling

- [Media Bar](https://github.com/IAmParadox27/jellyfin-plugin-media-bar):
  themed banner, plus a fix for home rows sliding under the banner
- [Intro Skipper](https://github.com/intro-skipper/intro-skipper):
  styled Skip Intro / Skip Credits button

## Known limitations

- In the desktop app, dark fades behind the video controls aren't drawn over
  the video (the app only shows solid elements there). Controls use text
  shadows instead. In a browser the fades show normally.
- Custom CSS can't change the browser tab icon or the desktop app's title bar.

## License

MIT