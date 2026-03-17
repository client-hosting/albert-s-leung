# The Art of Albert S. Leung — Audio/Video Player System

A beautiful, branded audio/video player, QR code generator, and play button toolkit 
for the art book honouring Albert S. Leung.

---

## What's included

| File | Purpose |
|------|---------|
| `player.html` | The reader-facing player — opens when a QR code is scanned |
| `admin.html` | Your management dashboard — add clips, generate QR codes, get play button code |
| `assets/fonts/Effra_Bold.ttf` | Effra Bold font (headings) |
| `assets/fonts/Effra_Light.ttf` | Effra Light font (body / captions) |

---

## Quick Start (GitHub Pages — free hosting)

### 1. Create a GitHub repository

1. Go to https://github.com → **New repository**
2. Name it: `albert-leung`
3. Set to **Public**
4. Click **Create repository**

### 2. Upload your files

Upload this entire folder to the repository:
- `player.html`
- `admin.html`
- `assets/` (the whole folder, including fonts)

### 3. Enable GitHub Pages

1. In your repo → **Settings** → **Pages**
2. Source: **Deploy from a branch** → Branch: `main` → Folder: `/ (root)`
3. Click **Save**
4. Your site will be live at: `https://YOUR-USERNAME.github.io/albert-leung/`

---

## Adding a clip (step-by-step)

### Step 1: Record and prepare the clip
- iPhone Voice Memos → .m4a (works perfectly)
- Rename clearly: `great-blue-heron.mp3`
- Aim for 2–8 minutes per clip

### Step 2: Host the clip file
Upload to your GitHub repo in a `clips/` folder.
Your clip URL will be: `https://YOUR-USERNAME.github.io/albert-leung/clips/great-blue-heron.mp3`

For video or large files, use Cloudflare R2 (free tier is generous):
1. Cloudflare dashboard → R2 → Create bucket `albert-leung-clips` → Public
2. Upload your file → copy the public URL

### Step 3: Register the clip in player.html
Open `player.html` in a text editor. Find the `CLIPS` object (around line 60).
Add your new entry:

```javascript
"great-blue-heron": {
  title:   "Great Blue Heron",
  medium:  "Acrylic on canvas — Albert in conversation",
  context: "Albert describes the patient hours spent watching herons along the shoreline…",
  type:    "audio",   // or "video"
  src:     "https://YOUR-USERNAME.github.io/albert-leung/clips/great-blue-heron.mp3",
  thumb:   "https://YOUR-USERNAME.github.io/albert-leung/images/great-blue-heron.jpg",
},
```

Or use **admin.html → Add New Clip** tab to generate this code automatically.

### Step 4: Generate the QR code
Open **admin.html → QR Codes** tab:
- Enter the Clip ID: `great-blue-heron`
- Enter your Base URL: `https://YOUR-USERNAME.github.io/albert-leung`
- Click **Generate QR Code**
- Click **Download PNG** → transparent background, print-ready

**Print size:** Minimum 1.5 × 1.5 cm; recommended 2.5 × 2.5 cm

### Step 5: Get the play button for digital editions
Open **admin.html → Play Buttons** tab:
- Enter the Clip ID and Base URL
- Choose your button variant
- Copy the HTML snippet
- Paste into your digital layout

---

## Player URL structure

Every clip has its own URL:
```
https://YOUR-USERNAME.github.io/albert-leung/player.html?clip=CLIP-ID
```

This is what the QR code encodes, and what the play button links to.

---

## Tip for Mark's visit with Albert

Record on iPhone (Voice Memos or Camera app). No special equipment needed — 
Albert's voice is the treasure. 

Suggested clips to capture:
- His memories of arriving in Canada in 1960
- What he feels when he watches a bird
- The story behind Great Blue Heron
- His approach to colour and patience
- A message to future generations

Upload the files and register them using the admin tool. Each one can have 
its own QR code placed beside the relevant page or photo in the book.

---

## Brand colours

| Name | Hex |
|------|-----|
| Autumn Glory (primary) | `#E36519` |
| Pale Gold (secondary) | `#C5A958` |
| Charcoal (tertiary) | `#191919` |
| Cream Glow (light) | `#FAF6EE` |

Font: **Effra** — Bold for headings, Light for body and captions.
