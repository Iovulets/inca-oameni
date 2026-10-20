# Handover: "(încă) oameni" event landing page

Build a single, static landing page for a free spoken word event. The page has **two layouts**: mobile and desktop. The design, copy and information below are **final**. Do not add sections, copy, badges, icons or features that are not listed here.

---

## 1. Scope

- One page. On both layouts it is a single column.
- **Mobile:** designed at 390 px wide. It must work from 320 px up to the breakpoint.
- **Desktop:** designed at 1440 px wide. It is the same single column, centered, 720 px wide.
- **Breakpoint:** `768px`. Below it, use the mobile layout. At 768 px and wider, use the desktop layout.
- Static HTML/CSS. No framework is needed. A small JS snippet is used only for the video (section 7).

## 2. Page structure (top to bottom, both layouts)

1. **Hero video**: square on mobile, 16:9 on desktop. No overlay and no text over it.
2. **Ticket card**: Date / Where → Schedule → Show language → Music → dashed divider → Free / Limited spots → booking button.
3. **About**: heading and 4 paragraphs.
4. **Footer**: divider, © text on the left, Instagram icon on the right.

There is **one** call-to-action only ("Book your spot"). Do not add a sticky bar, a second button, an "Add to calendar" link, an artists section or a visible title.

## 3. Exact copy

Use this text exactly, including punctuation, the curly apostrophes (’), the em dash (—) and the Romanian diacritics (ă, î).

**Ticket card**

| Element | Text |
|---|---|
| Label | `Date` (displayed in uppercase with CSS) |
| Value | `Tue, Oct 27` |
| Sub-value | `2026` |
| Label | `Where` (uppercase with CSS) |
| Value | `Atelier Cafe` |
| Link | `Str. Memorandumului 9 ↗` |
| Label | `Schedule` (uppercase with CSS) |
| Row | `Doors open` — `18:00` |
| Row (bold) | `Show starts` — `18:45` |
| Row | `Show ends` — `20:00` |
| Row | `Show language` — `Romanian` |
| Row | `Music` — `Jazz & UK Garage` |
| Price | `Free` |
| Note | `Limited spots` |
| Button | `Book your spot` |

In every row, the **label is on the left and the value is on the right**. In the schedule rows, the time is the value on the right.

**About**

- Heading: `About` (uppercase with CSS)
- Paragraph 1 (lead): `In a world where it’s hard to keep up with technology, one thing stays the same — we are people in a world of people.`
- Paragraph 2: `An event by Transylvania Spoken Word, bringing Maria Ungureanu, Tina Suciu, Paul Cristian and Cătălin Iovu to the stage.`
- Paragraph 3: `Discover 4 different perspectives in a spoken word poetry show that takes you back to an analog world — among friends and beautiful people, with emotions on your face and vibrations in your heart.`
- Paragraph 4: `After the show, stay for the social night. We’ll play jazz and UK garage, so come ready to mingle and dance.`

**Footer**

- `© Transylvania Spoken Word`
- Instagram icon only, with no text. Accessible name: `Transylvania Spoken Word on Instagram`.

**Page meta**

- `<html lang="en">`
- `<title>`: **open question** (section 10). Suggested: `(încă) oameni — Transylvania Spoken Word`.

## 4. Design tokens (both layouts)

**Colours**

| Token | Value | Use |
|---|---|---|
| `--bg` | `#ECEAE6` | Page background |
| `--card` | `#FFFFFF` | Ticket card |
| `--ink` | `#161616` | Main text, button background, Instagram icon |
| `--ink-body` | `#262626` | About body paragraphs |
| `--muted` | `#5C5C5C` | Labels, secondary text, footer text |
| `--line` | `#E4E2DE` | Lines inside the card |
| `--line-strong` | `#D3D0CA` | Dashed card divider, footer divider, video background while it loads |
| `--on-ink` | `#FFFFFF` | Button text |

**Fonts** (Google Fonts)

- `Space Grotesk` 400 / 500 / 600 / 700: all main text.
- `Space Mono` 400 / 700: the labels (Date, Where, Schedule, About) and the times (18:00, 18:45, 20:00).

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@400;500;600;700&family=Space+Mono:wght@400;700&display=swap">
```

## 5. Mobile layout (below 768 px; designed at 390 px)

**Page:** background `--bg`, no outer padding. The column is the full screen width.

**Hero video:** `width: 100%`, `aspect-ratio: 1 / 1`, `object-fit: cover`, `display: block`, **no border radius**, touching the top and the sides of the screen.

**Ticket card:** margin `16px 16px 0`, background `--card`, `border-radius: 20px`.

- **Top row:** 2 equal columns. Each cell: `padding: 20px`, column flex, gap 4px. Left cell: `border-right: 1px solid var(--line)`. Both cells: `border-bottom: 1px solid var(--line)`.
- **Schedule block:** `padding: 20px`, column flex, gap 12px. Each row: `display: flex; justify-content: space-between`. The "Show language" row has `padding-top: 12px; border-top: 1px solid var(--line)`. The "Music" row follows it with no line.
- **Divider:** `border-top: 2px dashed var(--line-strong)`, `margin: 0 20px`.
- **Price block:** `padding: 20px`, column flex, gap 12px. Row 1: "Free" on the left and "Limited spots" on the right, `align-items: baseline`. Row 2: the button.
- **Button:** full width, `min-height: 56px`, `border-radius: 14px`, background `--ink`, text `--on-ink`, centered, no underline.

**About:** `padding: 40px 20px 32px`, column flex, gap 14px. Heading `margin-bottom: 2px`. `p { margin: 0 }`.

**Footer:** `margin: 0 20px`, `padding: 20px 0` (equal space above and below the row), `border-top: 1px solid var(--line-strong)`, `display: flex; justify-content: space-between; align-items: center`. There is **no** extra space under the footer.

**Mobile type scale**

| Element | Font | Size | Weight | Other |
|---|---|---|---|---|
| Labels (Date, Where, Schedule) | Space Mono | 12px | 400 | uppercase, `--muted` |
| Date / venue value | Space Grotesk | 18px | 700 | |
| "2026" | Space Grotesk | 14px | 400 | `--muted` |
| Address link | Space Grotesk | 12px | 400 | `white-space: nowrap`, underlined, `--ink` |
| Schedule labels | Space Grotesk | 16px | 400 (700 for "Show starts") | |
| Schedule times | Space Mono | 16px | 400 (700 for 18:45) | |
| "Show language" / "Music" labels | Space Grotesk | 16px | 400 | `--muted` |
| "Romanian" / "Jazz & UK Garage" | Space Grotesk | 16px | 400 | |
| "Free" | Space Grotesk | 26px | 700 | letter-spacing −0.02em |
| "Limited spots" | Space Grotesk | 14px | 600 | `--muted` |
| Button | Space Grotesk | 17px | 700 | |
| "About" heading | Space Mono | 13px | 700 | uppercase, letter-spacing 0.04em, `--ink` |
| Lead paragraph | Space Grotesk | 22px | 600 | line-height 1.35, letter-spacing −0.01em, `--ink` |
| Body paragraphs | Space Grotesk | 17px | 400 | line-height 1.6, `--ink-body` |
| Footer text | Space Grotesk | 13px | 400 | `--muted` |

## 6. Desktop layout (768 px and wider; designed at 1440 px)

The structure and copy are the same as mobile. Only these values change.

**Page:** background `--bg` across the full window. Outer padding `64px 40px 0`. The page is at least the full window height (`min-height: 100vh`). The footer sits at the bottom of the window when the content is shorter than the window.

**Column:** `width: 100%`, `max-width: 720px`, centered (`margin: 0 auto`).

**Hero video:** `width: 100%`, **`aspect-ratio: 16 / 9`**, `object-fit: cover`, **`border-radius: 20px`**, background `--line-strong` while it loads.

**Ticket card:** margin `24px 0 0` (no side margin; the card is the full column width). `border-radius: 20px`.

- **Top row cells:** `padding: 28px 32px`, gap 6px.
- **Schedule block:** `padding: 28px 32px`, gap 14px.
- **Divider:** `margin: 0 32px`.
- **Price block:** `padding: 28px 32px`, **one row**: "Free" with "Limited spots" under it on the left (column flex, gap 2px, `flex: 1`), and the button on the right, `align-items: center`, gap 24px.
- **Button:** **not full width**: `padding: 0 48px`, `min-height: 56px`, `border-radius: 14px`.

**About:** `padding: 64px 32px 48px`, gap 16px.

**Footer:** `margin: 0`, `padding: 24px 0` (equal space above and below the row), the full column width.

**Desktop type scale changes** (everything not listed is the same as mobile)

| Element | Size | Other |
|---|---|---|
| Date / venue value | 24px | weight 700, letter-spacing −0.01em |
| Address link | 15px | `white-space: nowrap` |
| Schedule, "Show language" and "Music" rows | 17px | |
| "Free" | 30px | weight 700, letter-spacing −0.02em |
| Lead paragraph | 30px | weight 600, line-height 1.3, letter-spacing −0.015em |
| Body paragraphs | 18px | line-height 1.65 |

## 7. Hero video

The assets are already in the project folder: `event cover assets/`.

| Layout | Video | Backup image (poster) | Size |
|---|---|---|---|
| Mobile | `oameni_slide1_1x1 (1).webm` | `B · Slide 1@1x.png` | 1080 × 1080 |
| Desktop | `oameni_slide1_16x9.webm` | `B · Slide 1 16 9@1x.png` | 1920 × 1080 |

- The file names have spaces, brackets and a "·" character. Copy the files into the site's assets folder with web-safe names (for example `cover-1x1.webm`, `cover-1x1.png`, `cover-16x9.webm`, `cover-16x9.png`). Do not change the original files.
- The two posters are PNG files of 2.5 MB and 4.5 MB. Convert copies to optimized JPG or WebP for the web. Do not change the originals.
- **Load only one video.** Use one `<video>` element and choose its source with JS at load time. Do not put two video elements on the page and hide one with CSS, because the browser then downloads both.

```html
<video class="hero" autoplay muted loop playsinline preload="metadata"
       aria-label="Event cover animation"></video>
```

```js
const v = document.querySelector('video.hero');
if (v) {
  const desktop = window.matchMedia('(min-width: 768px)').matches;
  v.poster = desktop ? '/assets/cover-16x9.jpg' : '/assets/cover-1x1.jpg';
  v.src    = desktop ? '/assets/cover-16x9.webm' : '/assets/cover-1x1.webm';
  v.muted = true;                        // some browsers ignore the muted attribute
  if (!window.matchMedia('(prefers-reduced-motion: reduce)').matches) {
    v.play()?.catch(() => {});
  } else {
    v.removeAttribute('autoplay');       // show the poster only
  }
}
```

- The element must have the correct aspect ratio from the start (1/1 on mobile, 16/9 on desktop, set in CSS), so the layout does not jump while the video loads.
- **No MP4 versions exist yet.** Some older Safari versions cannot play WebM. They will show the poster image. This is accepted for now. If MP4 files are added later, add them as a second source.

## 8. Links

| Element | Target | Status |
|---|---|---|
| "Book your spot" | Registration form URL | **Missing: get it from the PM** |
| "Str. Memorandumului 9 ↗" | Google/Apple Maps link to Atelier Cafe, Str. Memorandumului 9, Cluj-Napoca | **Confirm with the PM**. Open in a new tab. |
| Instagram icon | `https://instagram.com/transylvaniaspokenword` | Final. Open in a new tab with `rel="noopener"`. |

**Instagram icon:** a 15 × 15 px outline icon (rounded square, circle, dot), stroke `--ink`, stroke-width 2, inside a 26 × 26 px link. **No background and no border.** Make the tap area at least 44 × 44 px without a visible change (for example, with a pseudo-element).

## 9. Accessibility (required)

- Use real `<a>` elements for the button and the links. Do not use clickable `div`s.
- The Instagram link has `aria-label="Transylvania Spoken Word on Instagram"`. Its SVG has `aria-hidden="true"`.
- Use one `<h2>` for "About".
- The event name shows only inside the video. Add a visually hidden `<h1>` with the event name, but **confirm with the PM first** (section 10). It causes no visible change.
- All text colours pass WCAG AA (4.5:1) on `--bg` and `--card`. Keep it that way.
- Show a visible focus style on all links and on the button.

## 10. Open questions for the PM (do not guess)

1. Registration (booking) URL.
2. Maps URL.
3. Page `<title>`, meta description and social share image (Open Graph). The 16:9 poster is the likely share image.
4. Visually hidden `<h1>` (section 9).

## 11. Acceptance checklist

- [ ] All copy matches section 3 character for character.
- [ ] In the schedule, the labels are on the left and the times are on the right.
- [ ] At 390 px, "Str. Memorandumului 9 ↗" stays on one line and does not go past the card edge.
- [ ] There is only one "Book your spot" button on the page.
- [ ] Mobile shows the square video. Desktop shows the 16:9 video. The page downloads only one of them.
- [ ] The video autoplays muted and loops on iOS Safari and Android Chrome. The poster shows before playback and when playback is not possible.
- [ ] The footer has equal space above and below its row. There is no empty space after the footer.
- [ ] No horizontal scroll from 320 px to 1920 px.
- [ ] The desktop column is 720 px wide and centered at 1440 px.
- [ ] Lighthouse accessibility score of 95 or higher.
