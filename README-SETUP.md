# Edgar Quinones — GitHub Pages portfolio starter

This is a four-page **static HTML/CSS** site for the existing repository:

**https://github.com/EdgarQuinones/EdgarQuinones.Github.io**

## Install

1. Download and unzip `edgar_portfolio_site.zip`.
2. Open the `EdgarQuinones.Github.io` repository, **not** the `edgarquinones` GitHub-profile README repository and **not** the `Combat-Systems` repository.
3. Replace its existing `index.html` with the `index.html` here.
4. Add `styles.css`, `about.html`, `projects.html`, and `devlogs.html` beside it in the repository root.
5. In repository **Settings → Pages**, select **Deploy from a branch**, `main`, `/ (root)` if not already selected.
6. Commit all files. Your pages will live at:
   - `https://edgarquinones.github.io/`
   - `https://edgarquinones.github.io/about.html`
   - `https://edgarquinones.github.io/projects.html`
   - `https://edgarquinones.github.io/devlogs.html`

Your original repository `README.md` can stay unchanged. The `Combat-Systems` Jekyll blog is a **separate** repository and stays unchanged.

## Add real game screenshots

The colorful card artworks are deliberately generic gradient **placeholders**, not screenshots of your games.

1. Put your screenshots in `assets/`, for example `assets/perrfect-fortune.png` and `assets/ground-zero.png`.
2. In `styles.css`, find `.project-art.fortune` and `.project-art.ground`. Set a real image background, for example:

   ```css
   .project-art.fortune {
     background-image: linear-gradient(to top, rgba(0,0,0,.45), transparent),
                       url('assets/perrfect-fortune.png');
   }
   ```

3. If the image already contains the title, remove the `.art-title` div for that card from the corresponding HTML to avoid doubling it.

## Make an itch.io game playable within the portfolio

**A link or the normal itch.io widget is not the same as embedding an interactive game.**

1. Export your Unity game as a **WebGL** build.
2. Upload the build to itch.io as an **HTML5 / playable in browser** game.
3. In your itch.io creator dashboard, open the project and select **Distribute → Embed game** (the exact menu text can change).
4. Copy **the playable game embed iframe** from itch.io, not the standard store widget.
5. Open `projects.html`. Near the bottom is a commented-out example section labeled `PLAYABLE GAME EMBED EXAMPLE`. Add a real `<section>` there with the exact iframe provided by itch.io. Don't invent the iframe URL.

Example layout once you have valid embed code:

```html
<section class="section" id="play-game">
  <div class="section-head"><h2>Play Perrfect Fortune</h2></div>
  <div class="info-card">
    <!-- Paste itch.io's playable HTML5 game iframe here -->
  </div>
</section>
```

Alternatively, you can host your own Unity WebGL build on GitHub Pages, but that requires publishing the generated build files (`index.html`, `Build/`, and `TemplateData/`) to a suitable path and configuring them correctly.

## Adding project links

Add an itch.io game-page button to any project's `.card-links` when you know the public URL:

```html
<a href="https://YOUR-ITCH-USERNAME.itch.io/YOUR-GAME-SLUG"
   target="_blank" rel="noopener noreferrer">Play Game ↗</a>
```

No itch.io URLs were guessed in this starter because you haven't provided them yet.

**Note:** `EdgarQuinones/Angle-of-Survival` was private when checked. Its project card has no public source-code link. If you make it public, add the button.

## Optional customization

- **Site color:** edit `--accent` at the top of `styles.css`.
- **About:** edit `about.html`.
- **Featured games:** edit the two `<article class="project-card">` elements in `index.html`.
- **All games:** edit `projects.html`.
- **Devlogs:** edit `devlogs.html`.
- **Navigation:** links are at the top of each HTML file. Update all four if you add another page.

Official documentation:
- GitHub Pages: https://docs.github.com/en/pages/getting-started-with-github-pages/what-is-github-pages
- itch.io HTML5 games: https://itch.io/docs/creators/html5
- itch.io game embeds: https://itch.io/updates/introducing-game-embeds
