# Spill Response Simulator

An interactive lab **chemical-spill response** training simulator — a client-facing
demo for Erudithe showing what a bespoke, designer-led interactive looks like next
to generic click-through courseware.

It is a single, self-contained HTML file: all CSS, SVG and JavaScript are inline.
No external libraries, fonts, images or network calls — it runs offline from a
double-click **and** hosts cleanly on GitHub Pages.

- **`spill-simulator.html`** — the simulator (the file to embed or open directly).
- **`index.html`** — Pages entry point; forwards to the simulator so the site root loads it.
- **`.nojekyll`** — tells GitHub Pages to serve the files verbatim (skip Jekyll processing).

## Run it locally

Open `spill-simulator.html` in Chrome or Edge — no build step, no server required.

## Publish on GitHub Pages

The site is plain static files, so no build workflow is needed. In the repository
on GitHub:

1. Go to **Settings → Pages**.
2. Under **Build and deployment → Source**, choose **Deploy from a branch**.
3. Set **Branch** to `claude/lab-spill-simulator-j4vy05` (or `main` once merged)
   and **Folder** to **`/ (root)`**, then **Save**.
4. Wait ~1 minute for the first deploy. Your site appears at:

   ```
   https://<your-username>.github.io/<repository-name>/
   ```

   The root URL forwards to the simulator automatically. You can also link
   straight to it at `…/spill-simulator.html`.

To embed it in an LMS or another page later, use an `<iframe>` pointing at the
`spill-simulator.html` URL.

## Results hook (for later SCORM wiring)

At debrief the sim calls `window.onSimComplete?.(results)` and logs the same
object to the console. SCORM itself is **not** implemented — this is the seam to
wire it to later. The results object contains: `spillType`, `actions[]` (each with
a timestamp), `score`, `passed` and `timeRemaining`.

## Content note

The chemical behaviour modelled here is deliberately kept generic and
training-plausible. It contains no real dosing, concentrations or procedural
detail, and **must be reviewed and validated by a suitably qualified subject-matter
expert before any use in real workplace training.**
