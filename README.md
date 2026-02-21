[README.md](https://github.com/user-attachments/files/25457250/README.md)
# വാക്ക്‌മേഘം — Malayalam Word Cloud Studio

A browser-based word cloud generator built specifically for Malayalam (മലയാളം). Paste any Malayalam text and instantly generate beautiful, customizable word clouds with live preview.

**[▶ Try it live →](https://nethahussain.github.io/vaakkumegham/)**

---

## Features

### Text Processing
- Automatic word frequency analysis
- Filters out അർത്ഥരഹിത വാക്കുകൾ (meaningless filler words like ആണ്, ഉണ്ട്, ഒരു, ഈ, the, and)
- Adjustable minimum frequency threshold
- Supports up to 300 words
- Built-in word frequency table with bar charts

### Malayalam Fonts
Six Malayalam fonts loaded from Google Fonts:

| Font | Style |
|------|-------|
| Manjari | Modern sans-serif |
| Noto Sans Malayalam | Clean, universal |
| Gayathri | Elegant sans-serif |
| Chilanka | Handwritten/cursive |
| Noto Serif Malayalam | Traditional serif |
| Anjali Old Lipi | Classic old-script |

Font weight options: Thin, Normal, Bold, Black.

### Shape Masks
Words are placed within one of 7 shape masks:

- ▬ ചതുരം (Rectangle)
- ● വൃത്തം (Circle)
- ♥ ഹൃദയം (Heart)
- ★ നക്ഷത്രം (Star)
- ◆ വജ്രം (Diamond)
- ▲ ത്രികോണം (Triangle)
- ☁ മേഘം (Cloud)

### Color Palettes
10 curated palettes + custom color picker:

- ക്ലാസിക് · കേരളം · സൂര്യൻ · കടൽ · മഴവില്ല്
- പ്രകൃതി · രാത്രി · വസന്തം · മണ്ണ് · നിയോൺ

### Live Preview
- SVG-based preview updates in real time
- Style changes (background, colors, opacity, font) apply instantly without regeneration
- Layout changes auto-regenerate with 400ms debounce
- Hover any word to see its size, frequency, rotation, and color

### Preview Toolbar
- Zoom controls (10%–300%) with Fit and 1:1 buttons
- Grid overlay toggle for alignment
- Fullscreen mode

### Export
- **PNG** — high resolution raster image
- **SVG** — scalable vector, ideal for print

### Canvas Sizes
Three presets: 4:3 (800×600), 16:9 (1200×675), 9:16 (1080×1920).

### Additional Controls
- 5 rotation modes: None, 0°/90° mix, Fixed angle, Random, All angles
- Word spacing (0–30px)
- Spiral density (1–10)
- Font size range (min/max)
- Opacity control
- Background color with 8 presets
- Background gradients: linear, radial, vertical

---

## Usage

1. Open [the live site](https://nethahussain.github.io/vaakkumegham/) or `index.html` locally
2. Paste Malayalam text in the **ടെക്സ്റ്റ്** (Text) tab
3. Adjust layout in the **ലേഔട്ട്** (Layout) tab — shape, rotation, canvas size
4. Customize appearance in the **രൂപം** (Style) tab — font, colors, background
5. Download from the **എക്സ്പോർട്ട്** (Export) tab — PNG or SVG

Words that appear more frequently in the input text will appear larger in the cloud.

---

## How It Works

### Word Processing
1. Input text is tokenized and punctuation/numbers are stripped
2. Optional stop-word filtering removes common filler words
3. Words are sorted by frequency and limited to the configured maximum

### Cloud Generation
1. Each word's font size is calculated proportionally to its frequency
2. Words are placed using an Archimedean spiral algorithm starting from the center
3. A grid-based collision detection system (4px cells) prevents overlaps
4. Shape mask functions constrain placement within the selected shape boundary
5. Placement attempts up to 4500 spiral positions per word

### Rendering
- **Preview**: Live inline SVG — style changes are instant, layout changes trigger regeneration
- **PNG export**: Hidden HTML5 canvas renders the final image
- **SVG export**: Generates clean SVG markup from placed word data

---

## Technical Details

- **Single HTML file** — no build step, no dependencies to install
- **React 18** via CDN (UMD build)
- **Babel standalone** for JSX compilation in the browser
- **Google Fonts** for all Malayalam typefaces
- Zero backend — runs entirely in the browser

### Browser Support
Modern browsers with ES6+ support: Chrome, Firefox, Safari, Edge.

---

## Local Development

No setup needed. Just open the file:

```bash
git clone https://github.com/nethahussain/vaakkumegham.git
cd vaakkumegham
open index.html
```

Or serve it locally:

```bash
python3 -m http.server 8000
# Open http://localhost:8000
```

---

## Deploy to GitHub Pages

1. Push `index.html` to the `main` branch
2. Go to **Settings → Pages**
3. Set Source to **Deploy from a branch** → **main** → **/ (root)**
4. Site will be live at `https://nethahussain.github.io/vaakkumegham/`

---

## License

MIT

---

## Credits

- Fonts: [Google Fonts](https://fonts.google.com/) — Manjari, Noto Sans Malayalam, Gayathri, Chilanka, Noto Serif Malayalam, Anjali Old Lipi
- UI framework: [React](https://react.dev/)
- Built with [Claude](https://claude.ai/) by Anthropic
