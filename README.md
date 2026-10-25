# มีอะไรจะให้คนสวยด้วยแหละะ💌 — storybook website

A plain HTML + CSS + JavaScript website. **No build step, no installation.**
All illustrations are drawn in code (inline SVG), so there are no image files to lose.

## Files

```
index.html          the page (browser tab title is set here)
css/style.css       all styling
js/script.js        story, illustrations, music, buttons, and THE LETTER
audio/              put your 2 music files here (see below)
.nojekyll           tells GitHub Pages to publish the files as-is
README.md           this file
```

## 1. Write your letter
Open `js/script.js` in any text editor (Notepad, VS Code). Near the top, find:

```
const SHOW_DRAFT_BADGE = true;
const LETTER = `...text...`;
```
Replace the text between the two backticks (`) with your own letter. Line breaks you type are kept.
Then change `SHOW_DRAFT_BADGE` to `false` so the small "draft" note disappears. Save the file.

## 2. Add the music (optional — the site works silently without it)
Check each track's license on Pixabay, download them yourself, then save them as exactly:

```
audio/story.mp3     (plays from the first page, the story music)
audio/ending.mp3    (plays after she chooses "ให้โอกาส")
```
Use lowercase names. GitHub Pages is case-sensitive. Keep each file well under 25 MB.

## 3. Test on your computer
Easiest: double-click `index.html`. It should open and work.
(If music does not play this way, use the method below, which behaves like the real website.)

With Python installed: open a terminal inside this folder and run
`python3 -m http.server 8000` (Windows: `python -m http.server 8000`),
then visit http://localhost:8000 in your browser. Press Ctrl+C in the terminal to stop.

Test: open the story, read through all pages, press "ไม่ให้" four times, go back to the letter,
then press "ให้โอกาส" and wait about 20 seconds for the ending. Try it on your phone too.

## 4. Publish on GitHub Pages
1. Make a free account at github.com and click **New repository**.
2. Pick a plain name (for example `little-story`). Choose **Public** (free Pages requires it
   unless you have a paid plan). Click **Create repository**.
3. Click **uploading an existing file**. Unzip the download, then drag the **contents** of the
   folder into the page: `index.html`, `README.md`, `.nojekyll` and the `css`, `js`, `audio` folders.
   `index.html` must be at the top level of the repository, not inside another folder.
   (If your computer hides `.nojekyll` it is fine to skip it.)
4. Click **Commit changes**.
5. Go to **Settings → Pages**. Under **Build and deployment**, set Source to
   **Deploy from a branch**, Branch **main**, folder **/ (root)**, then **Save**.
6. Wait 1–3 minutes. The address appears at the top of that page:
   `https://YOUR-USERNAME.github.io/little-story/`
   Send her that link.

All paths in the site are relative, so it works at that project address.
The page asks search engines not to list it (`noindex`), but anyone with the link can open it.
The repository name becomes part of the link, so choose a neutral one that does not reveal the surprise.

## Updating later
Open the file on GitHub, click the pencil icon, edit, and commit. For music, use
**Add file → Upload files** inside the `audio` folder. Changes appear after a minute or two;
refresh with Ctrl+Shift+R if you still see the old version.

## Fonts
The fonts (Sarabun, Mali, Cormorant Garamond) load from Google Fonts, so they need an internet connection.
Without it, the site falls back to the device's normal fonts and stays readable.
To host fonts yourself, download the three families from fonts.google.com, put the files in a
`fonts/` folder, and replace the Google `<link>` in `index.html` with `@font-face` rules in `css/style.css`.

## Troubleshooting
- No music: the mp3 files are missing, misnamed, or the phone is in silent mode. Tap the speaker icon.
- Blank page after publishing: `index.html` is probably inside a subfolder, or Pages is not enabled yet.
- Old version showing: hard refresh, or wait a couple of minutes.
