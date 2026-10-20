# Handover: "(încă) oameni" event landing page — Version D

Build a single, static, mobile-first landing page for a free spoken word event. The design, copy and information below are **final**. Do not add sections, copy, badges, icons or features that are not listed here.

---

## 1. Scope

- One page, a single scrolling column.
- Designed at **390 px** wide (iPhone 12–15). It must work from 320 px to 480 px wide.
- **Desktop:** not designed. Default: keep the same single column, centered, `max-width: 480px`, with the page background colour on both sides. Confirm with the PM before you change this.
- Static HTML/CSS. No framework is needed. A small JS snippet is used only for video autoplay (section 6).

## 2. Page structure (top to bottom)

1. **Hero video**: full width, no margins, no overlay, no text over it.
2. **Ticket card**: Date / Where → Schedule → Show language → Music → dashed divider → Free / Limited spots → booking button.
3. **About**: heading and 4 paragraphs.
4. **Footer**: divider, © text on the left, Instagram icon on the right.

There is **one** call-to-action only ("Book your spot"). Do not add a sticky bar, a second button, an "Add to calendar" link, an artists section or a title over the hero.

## 3. Exact copy

Use this text exactly, including punctuation, the curly apostrophes (’), the em dash (—) and the Romanian diacritics (ă, î).

**Ticket card**

| Element | Text |
|---|---|
| Label | `DATE` (rendered uppercase from "Date") |
| Value | `Tue, Oct 27` |
| Sub-value | `2026` |
| Label | `WHERE` |
| Value | `Atelier Cafe` |
| Link | `Str. Memorandumului 9 ↗` |
| Label | `SCHEDULE` |
| Row | `18:00` — `Doors open` |
| Row (bold) | `18:45` — `Show starts` |
| Row | `20:00` — `Show ends` |
| Row | `Show language` — `Romanian` |
| Row | `Music` — `Jazz & UK Garage` |
| Price | `Free` |
| Note | `Limited spots` |
| Button | `Book your spot` |

**About**

- Heading: `ABOUT` (rendered uppercase from "About")
- Paragraph 1 (lead): `In a world where it’s hard to keep up with technology, one thing stays the same — we are people in a world of people.`
- Paragraph 2: `An event by Transylvania Spoken Word, bringing Maria Ungureanu, Tina Suciu, Paul Cristian and Cătălin Iovu to the stage.`
- Paragraph 3: `Discover 4 different perspectives in a spoken word poetry show that takes you back to an analog world — among friends and beautiful people, with emotions on your face and vibrations in your heart.`
- Paragraph 4: `After the show, stay for the social night. We’ll play jazz and UK garage, so come ready to mingle and dance.`

**Footer**

- `© Transylvania Spoken Word`
- Instagram icon only (no text). Accessible name: `Transylvania Spoken Word on Instagram`.

**Page meta**

- `<html lang="en">`
- `<title>`: **open question**. Suggested: `(încă) oameni — Transylvania Spoken Word`.

## 4. Design tokens

**Colours**

| Token | Value | Use |
|---|---|---|
| `--bg` | `#ECEAE6` | Page background |
| `--card` | `#FFFFFF` | Ticket card |
| `--ink` | `#161616` | Main text, button background |
| `--ink-body` | `#262626` | About body paragraphs |
| `--muted` | `#5C5C5C` | Labels, secondary text, footer text |
| `--line` | `#E4E2DE` | Lines inside the card |
| `--line-strong` | `#D3D0CA` | Dashed card divider, footer divider |
| `--on-ink` | `#FFFFFF` | Button text |

**Fonts** (Google Fonts)

- `Space Grotesk` 400 / 500 / 600 / 700: all main text.
- `Space Mono` 400 / 700: the labels (Date, Where, Schedule, About) and the times (18:00, 18:45, 20:00).

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@400;500;600;700&family=Space+Mono:wght@400;700&display=swap">
```

**Type scale**

| Element | Font | Size | Weight | Other |
|---|---|---|---|---|
| Labels (Date, Where, Schedule) | Space Mono | 12px | 400 | uppercase, `--muted` |
| Date / venue value | Space Grotesk | 18px | 700 | |
| "2026" | Space Grotesk | 14px | 400 | `--muted` |
| Address link | Space Grotesk | 12px | 400 | `white-space: nowrap`, underlined, `--ink` |
| Schedule times | Space Mono | 16px | 400 (700 for 18:45) | |
| Schedule / info rows | Space Grotesk | 16px | 400 (700 for the 18:45 row) | labels "Show language", "Music" in `--muted` |
| "Free" | Space Grotesk | 26px | 700 | letter-spacing −0.02em |
| "Limited spots" | Space Grotesk | 14px | 600 | `--muted` |
| Button | Space Grotesk | 17px | 700 | |
| "About" heading | Space Mono | 13px | 700 | uppercase, letter-spacing 0.04em |
| Lead paragraph | Space Grotesk | 22px | 600 | line-height 1.35, letter-spacing −0.01em, `--ink` |
| Body paragraphs | Space Grotesk | 17px | 400 | line-height 1.6, `--ink-body` |
| Footer text | Space Grotesk | 13px | 400 | `--muted` |

## 5. Layout and spacing (at 390 px)

- **Hero video:** `width: 100%`, `aspect-ratio: 1 / 1`, `object-fit: cover`, `display: block`. No border radius.
- **Ticket card:** margin `16px 16px 0`, background `--card`, `border-radius: 20px`.
  - **Top row:** a 2-column grid of equal columns. Each cell has `padding: 20px` and a column flex with a 4px gap. Left cell: `border-right: 1px solid --line`. Both cells: `border-bottom: 1px solid --line`.
  - **Schedule block:** `padding: 20px`, column flex with a 12px gap. Each row is `display: flex; justify-content: space-between`. The "Show language" row has `padding-top: 12px; border-top: 1px solid --line`. The "Music" row follows it with no line.
  - **Divider:** `border-top: 2px dashed --line-strong`, `margin: 0 20px`.
  - **Price block:** `padding: 20px`, column flex with a 12px gap. Row 1: "Free" on the left and "Limited spots" on the right, `align-items: baseline`. Row 2: the button.
  - **Button:** full width, `min-height: 56px`, `border-radius: 14px`, background `--ink`, white text, centered, no underline.
- **About:** `padding: 40px 20px 32px`, column flex with a 14px gap, heading `margin-bottom: 2px`, `p { margin: 0 }`.
- **Footer:** `margin: 0 20px`, `padding: 20px 0` (equal space above and below the row), `border-top: 1px solid --line-strong`, `display: flex; justify-content: space-between; align-items: center`.
  - Instagram icon: 15 × 15 px outline icon, stroke `--ink`, stroke-width 2, inside a 26 × 26 px link. **No background, no border.** Make the tap area at least 44 × 44 px (for example, with negative margin and padding, or a pseudo-element) **without** a visible change.
- **No extra space** under the footer: the page ends at the footer's bottom padding.

## 6. Hero video

- **Source asset:** `oameni_slide1_1x1.mp4`, 1080 × 1080, 30 s, about 8 MB, provided by the PM.
- **The PM's team will deliver:** a **WebM** version and a **poster image** (still frame). Use both:

```html
<video class="hero" autoplay muted loop playsinline preload="metadata"
       poster="/assets/oameni-poster.jpg"
       aria-label="Event cover animation">
  <source src="/assets/oameni.webm" type="video/webm">
  <source src="/assets/oameni.mp4"  type="video/mp4">
</video>
```

- It must autoplay muted, loop and play inline on iOS. Add this guard, because some browsers ignore the `muted` attribute set from markup:

```js
const v = document.querySelector('video.hero');
if (v) { v.muted = true; v.play()?.catch(() => {}); }
```

- If the video cannot play, the poster must show. The layout must not jump: keep `aspect-ratio: 1/1` on the element.
- Respect `prefers-reduced-motion: reduce`: pause the video and show the poster.

## 7. Links

| Element | Target | Status |
|---|---|---|
| "Book your spot" | Registration form URL | **Missing — get from PM** |
| "Str. Memorandumului 9 ↗" | Google/Apple Maps link to Atelier Cafe, Str. Memorandumului 9, Cluj-Napoca | **Confirm with PM**; open in a new tab |
| Instagram icon | `https://instagram.com/transylvaniaspokenword` | Final; open in a new tab with `rel="noopener"` |

## 8. Accessibility (required)

- Use real `<a>` elements for the button and the links. Do not use clickable `div`s.
- The Instagram link has `aria-label="Transylvania Spoken Word on Instagram"`, and its SVG has `aria-hidden="true"`.
- Use one `<h2>` for "About". Add a visually hidden `<h1>` with the event name, because the visible name is only inside the video. **Confirm with the PM first** (visually hidden = no visible change).
- All text colours on `--bg` and `--card` pass WCAG AA (4.5:1). Keep it that way.
- Show visible focus styles on all links and the button.

## 9. Open questions for the PM (do not guess)

1. Registration (booking) URL.
2. Maps URL.
3. Page `<title>`, meta description and social share image (Open Graph). A video cannot be the link preview, so the poster image is the likely choice.
4. Desktop behaviour (default above: centered 480 px column).
5. Visually hidden `<h1>` (section 8).

## 10. Acceptance checklist

- [ ] All copy matches section 3 character for character.
- [ ] At 390 px wide, the address "Str. Memorandumului 9 ↗" stays on one line and does not go past the card edge.
- [ ] Only one "Book your spot" button exists on the page.
- [ ] The video autoplays muted and loops on iOS Safari and Android Chrome. The poster shows before playback and if playback fails.
- [ ] The footer has equal padding above and below its row, and there is no empty space after the footer.
- [ ] No horizontal scroll from 320 px to 480 px.
- [ ] Lighthouse accessibility score of 95 or higher.
