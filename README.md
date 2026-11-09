# Derbi Paint Booth

A color tryout tool for a 2007 Derbi Senda DRD special edition. Paint every part of the bike, try finishes, save designs, compare them side by side, and pick colors straight from inspiration photos.

## Open it

Double-click `index.html`. It runs in any modern browser with no install.

For full features, serve the folder instead of opening the file. Some browsers block color picking from photos and photo storage on `file://` pages.

```bash
npm run serve
```

Then open the address it prints, usually http://localhost:3000.

## What it does

- **Bike drawing:** a side view of the Senda DRD with a left and a right side. Each side shows its own parts: chain and magneto cover on the left, clutch cover, kickstart and rear brake on the right.
- **Paint sheet:** 15 part groups across body, frame, wheels, engine and details. The bigger surfaces take a finish: gloss, matte, metallic or candy.
- **Picker on the bike:** click a part to paint it. Shift-click adds more parts to paint together. "Select all parts in this color" grabs every part that shares a color.
- **Presets:** Original green, Dark purple, Electric, and Black and red.
- **Backdrops:** concrete wall, city street, dark garage and studio white.
- **Garage:** save named designs. They stay in the browser on that computer.
- **Side by side:** compare any two designs.
- **Inspiration:** a strip of reference photos. Open one to pick colors from it, or use the palette taken from the photo, and apply it to any part. "Add photos" stores your own pictures in the browser.
- **Copy paint list:** every part's color code and finish as text for the paint shop.

## Project layout

| File | What it is |
|---|---|
| `paint-booth.html` | The source. All markup, styles and code live here. |
| `index.html` | Generated from `paint-booth.html` by `build.js`. Don't edit it by hand. |
| `build.js` | Wraps the source into a standalone page. No dependencies. |
| `inspiration/` | Reference photos: `insp-NN.jpg` (max 1400 px) and `insp-NN-t.jpg` thumbnails. |

## Change something

1. Edit `paint-booth.html`.
2. Run `npm run build` (or `node build.js`).
3. Open `index.html` to check it.

`paint-booth.html` has no `<!doctype>`, `<html>`, `<head>` or `<body>` tags on purpose: the same file is also published as a Claude artifact, which adds those itself.

## Add inspiration photos

Photos added with the "Add photos" tile only live in that browser. To build a photo into the project for everyone:

1. Save it as `inspiration/insp-20.jpg` (long side about 1400 px) and a small copy as `inspiration/insp-20-t.jpg` (long side about 420 px).
2. Add a caption to the end of the `INSP` list in `paint-booth.html`. Photos are matched to captions by their order in the list.
3. Run `npm run build`.

## Notes

- Screen colors are a guide only. Match the codes against real paint chips in daylight, especially candy and metallic finishes.
- The inspiration photos were collected from the internet for personal reference. Keep the repository private, or remove the photos before sharing it publicly.
