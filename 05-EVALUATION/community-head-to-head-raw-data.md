# Community Head-to-Head — Raw Data

> Verbatim outputs (24) + judge JSONs (36) for the v0.3 priority #5 community-skill output-quality experiment. Aggregate analysis: [`community-head-to-head.md`](./community-head-to-head.md).

**Date:** 2026-04-26
**4 community skills × 3 inputs × 2 versions = 24 outputs.**
**3 cross-vendor judges × 12 pairs = 36 judge JSONs.**

**Blind mapping** (kept hidden from judges; revealed here):

```json
{
  "anthropic-canvas-design/01-poster": {
    "A": "v2-generated",
    "B": "community"
  },
  "anthropic-canvas-design/02-brand-identity": {
    "A": "v2-generated",
    "B": "community"
  },
  "anthropic-canvas-design/03-data-viz-aesthetic": {
    "A": "community",
    "B": "v2-generated"
  },
  "chrisvoncsefalvay-d3/01-bar-with-edge-case": {
    "A": "community",
    "B": "v2-generated"
  },
  "chrisvoncsefalvay-d3/02-network-graph": {
    "A": "community",
    "B": "v2-generated"
  },
  "chrisvoncsefalvay-d3/03-animated-transition": {
    "A": "v2-generated",
    "B": "community"
  },
  "gstack-plan-ceo-review/01-ambitious-roadmap": {
    "A": "v2-generated",
    "B": "community"
  },
  "gstack-plan-ceo-review/02-feature-launch": {
    "A": "v2-generated",
    "B": "community"
  },
  "gstack-plan-ceo-review/03-pivot-decision": {
    "A": "v2-generated",
    "B": "community"
  },
  "obra-tdd/01-bug-fix": {
    "A": "v2-generated",
    "B": "community"
  },
  "obra-tdd/02-new-feature": {
    "A": "community",
    "B": "v2-generated"
  },
  "obra-tdd/03-refactor-under-pressure": {
    "A": "v2-generated",
    "B": "community"
  }
}
```
---

# Outputs (24)


## anthropic-canvas-design/01-poster

**Blind mapping:** A=v2-generated, B=community

### anthropic-canvas-design/01-poster — community (14292 bytes)

```
# EMULSION RITES

*A design philosophy for objects made by patient hands and stubborn light.*

---

## STAGE ONE — THE PHILOSOPHY (.md)

### Manifesto

**Emulsion Rites** is the aesthetic of the artifact that refuses the screen. It is the practice of treating a flat plane as if it were a strip of celluloid: scored, stained, perforated, exposed, and re-exposed until the surface itself begins to remember. The work is not designed. It is **excavated** — coaxed out of pigment, gelatin, and grain by someone who has been bent over a light table for so long that their eyes have learned to see in twenty-four discrete pulses per second.

The movement rejects the soft, the warm, the tasteful. Tastefulness is the death rattle of a confident form. **Emulsion Rites** is instead committed to the cold honesty of the photochemical: the chemical violet of underexposed silver halide, the bone-white of unfogged base, the bruised orange of safelight bleed, the surgical green of registration ink. Color here is not decoration; it is **chemistry rendered visible**, the residue of a process that has been performed, not merely depicted. Every chromatic decision must read as the inevitable consequence of a material reaction, not a mood board.

Composition operates on a strict orthogonal grid — the grid of sprocket holes, of contact sheets, of frame counters and edge codes. This grid is not decorative; it is **load-bearing**. It is what allows the eye to register that something has been counted, sorted, indexed by a person who refuses to round off. Within this grid, forms accumulate through repetition: a single mark made eight times is not a pattern, it is a litany. The work must feel like the eighth take, the four-hundredth scratch, the nineteenth pass under the enlarger. Master-level execution announces itself through this kind of patient, almost monastic accretion. The viewer should feel that the artist has slept beside the work.

Typography in this movement is a found object, not a font choice. Letters appear as if **stamped, scratched, type-written, registered, or hand-cut** — the language of the lab, the editing bench, the splicer. Numerals carry the weight of catalogue entries: clinical, abbreviated, set in monospaced or condensed grotesques at sizes the eye has to lean in for. A single oversized word may anchor the field, but it should feel cut, not typeset — as though it were a title card photographed off a flatbed editor at 3 a.m. Text never explains; it labels, dates, indexes, reveres.

Scale and rhythm are governed by a tension between the **microscopic** and the **monumental**. Tiny edge-perforations and frame-counter marks live alongside a single, vast field of pure pigmented silence. The eye is asked to traverse from the macro to the granular — to read the work the way one reads an emulsion under a loupe. Negative space is not empty; it is **unexposed**. It is potential. It must be defended at all costs from the temptation to fill.

Above all, the work must look as though it could not have been produced quickly. It must carry the unmistakable signature of countless hours, of a hand that has done this thousands of times, of a mind that knows exactly which mark to leave and which to scrape away. **Emulsion Rites** is not a style; it is the visible evidence of expertise — meticulously crafted, painstakingly registered, the product of deep technical devotion. Anything less is a souvenir of the idea, not the idea itself. The piece, when finished, should feel like a museum-grade artifact recovered from the working drawer of a master who never stopped refining.

---

## STAGE TWO — THE SUBTLE REFERENCE (DEDUCED)

The audience signals the conceptual DNA: **Stan Brakhage** — direct-on-film painting (*Mothlight*, 1963; *The Garden of Earthly Delights*, 1981; *The Dante Quartet*, 1987), hand-scratched emulsion, moth wings and seed husks pressed between strips of mylar, "closed-eye vision," the eye as a sense-organ that has not yet been taught to see.

The reference is encoded **invisibly**, through:
- A vertical strip of "perforations" running the full height of the poster (sprocket-hole language).
- Eight chromatic frames stacked along that strip — one per festival film — treated as direct-on-film gestures: scratched, blotted, fingerprinted.
- A whispered Latin numeral ledger (I–VIII) that reads as edge-code rather than program.
- A single-word title set as if scratched into emulsion with a pin.
- No mention of Brakhage anywhere. Those who know, know.

---

## STAGE THREE — THE RENDERED VISUAL ARTIFACT (executable spec)

Format: **single-page poster**, portrait orientation.
Trim size: **610 mm × 914 mm** (24 × 36 in, standard one-sheet).
Bleed: 3 mm all sides. Safe area: 15 mm inset from trim.
Output: 300 dpi CMYK for print; sRGB PNG mirror at 7200 × 10800 px for screen proof.

### 1. Color Palette (exact values)

| Role | Name | HEX | CMYK | Notes |
|---|---|---|---|---|
| Ground | Unfogged Base | `#EDE6D3` | 5 / 8 / 20 / 4 | Warm raw-stock cream. Slight uneven mottle, 3% noise overlay. |
| Primary mark | Silver Halide Black | `#0E0F12` | 75 / 68 / 60 / 90 | Not pure black. Carries a violet undertone. |
| Accent 1 | Safelight Bleed | `#C2401C` | 12 / 86 / 92 / 5 | Used for one frame only — "the burn." |
| Accent 2 | Registration Cyan | `#0E5A6B` | 92 / 45 / 38 / 28 | For perforations, edge code, micro-type. |
| Accent 3 | Bench-Lamp Yellow | `#E6B341` | 6 / 32 / 82 / 0 | One frame; sodium-vapor warmth. |
| Accent 4 | Bruised Violet | `#3A2147` | 78 / 88 / 30 / 35 | One frame; underexposed shadow. |
| Accent 5 | Emulsion Green | `#5C7A3E` | 65 / 30 / 92 / 18 | One frame; chemical-green, surgical. |
| Accent 6 | Bone | `#F4EFE3` | 3 / 4 / 12 / 0 | Inner highlights only. |

Palette discipline: no color appears in more than the two zones it has been assigned. No gradients. No transparency tricks. All chromatic events read as **chemical**, not digital.

### 2. Typography (exact)

- **TITLE FACE — display:** *ABC Diatype Mono Unlicensed* substitute → use **GT America Mono Bold** at 96 pt, but **the title is not typeset**. It is rendered as a vector trace of a hand-scratched original: each letterform is broken in 2–3 places, with a 0.4 mm pin-scratch white inset running diagonally through the stroke. Tracking +60. Letter-spacing irregular by ±2%.
- **SECONDARY FACE — clinical labels:** **Söhne Mono** Regular, 7.5 pt, tracking +120, all-caps. Color: Registration Cyan.
- **TERTIARY FACE — film titles:** **Söhne Breit Buch** (Söhne Wide Book), 11 pt, set flush-left, leading 13.5 pt, color Silver Halide Black.
- **NUMERALS — edge code:** **Söhne Mono** Regular, 6 pt, Registration Cyan, set vertically along the perforation strip.
- **No italics. No bold inside body. No drop caps. No ornaments.** One typeface family throughout, two display moments.

### 3. Layout Grid (exact positions, measured from top-left at 0,0; units in mm on 610 × 914 trim)

The poster divides into a **12-column × 18-row** modular grid. Column width = 50.83 mm. Gutter = 4 mm. Row height = 50.78 mm.

#### 3.1 — The Perforation Strip (left edge ritual)
- Vertical band at **x = 18 mm to x = 46 mm** (28 mm wide), running from **y = 30 mm to y = 884 mm**.
- Inside the band: **48 sprocket-hole rectangles**, each **18 mm wide × 11 mm tall**, rounded corners r = 1.5 mm, color Bone (`#F4EFE3`) cut out of a Silver Halide Black band. Vertical spacing between holes = 6.8 mm.
- Immediately to the right of the band, between **x = 49 mm and x = 60 mm**: vertical edge-code reading top-to-bottom in 6 pt Söhne Mono, Registration Cyan: `BRKG · 24 · 1963 · 81 · 87 · IV · KEY · NN`. Set baseline-rotated 90° clockwise.

#### 3.2 — The Eight Frames (the program, encoded as direct-on-film)
A vertical column of **8 stacked frames**, each one a single film, occupying the right 9 columns:
- Frame block: **x = 90 mm to x = 560 mm** (470 mm wide), **y = 110 mm to y = 720 mm** (610 mm tall).
- Each frame: **470 mm wide × 72 mm tall**, with a **4 mm gutter** between frames.
- Frame border: 0.6 pt Silver Halide Black hairline rule, with **two perforation marks** flanking each frame on the left edge (small, 3 mm × 2 mm, cut out).

**Frame contents (top to bottom — each frame = one film, treated as a single direct-on-film gesture):**

| # | Field | Dominant gesture | Color | Detail |
|---|---|---|---|---|
| I | Pure scratched void | 14 diagonal pin-scratches, 0.3 mm wide, white-on-black, irregular angles 32°–47° | Silver Halide Black ground | Caption flush-right inside frame: film title + runtime |
| II | Pressed organic matter | Vector silhouettes of three moth-wing fragments, scaled true-to-life (28–40 mm wing) | Bone on Bench-Lamp Yellow | A single human fingerprint, 18 mm, lower-left, in cyan registration ink |
| III | Sprocket-hole field | The frame itself becomes 6 perforations stacked horizontally — abstraction of the medium | Unfogged Base ground, Black perforations | One perforation is misregistered by 2 mm — deliberate |
| IV | The burn | A single irregular blob of Safelight Bleed, hand-painted edge, occupying 38% of frame | Safelight Bleed on Black | Concentric heat-rings barely visible, 2% opacity |
| V | Frame-by-frame ledger | A horizontal sequence of 24 tiny vertical bars (one per fps), heights varying ±15% | Registration Cyan on Base | Reads as a waveform; is actually a frame counter |
| VI | Closed-eye vision | A field of 1,200 individually-placed dots, 0.4–1.1 mm, density gradient from center outward | Bruised Violet on Black | The densest cluster forms an off-center oval — "the eye behind the lid" |
| VII | Chemical bath | A single rectangle of Emulsion Green with visible "stop-bath" tide-lines at top and bottom, 1.5 mm bleed irregularity | Emulsion Green on Base | Faint white halide flecks, ~80 across the field |
| VIII | The white frame | Almost entirely Bone, with a single 0.3 pt Black hairline scratched corner-to-corner, plus one date stamp | Bone | The only frame that "breathes." |

Each frame carries, **flush-right inside the frame**, in 11 pt Söhne Wide Book, Silver Halide Black:
> `FILM TITLE GOES HERE` · `DIR. NAME` · `YR` · `RUNTIME′`

Set ragged-left, max width 180 mm. Festival programmer fills in the eight titles before press.

#### 3.3 — The Title (top-of-poster gesture)
- Position: **y = 40 mm** baseline, centered between **x = 80 mm and x = 580 mm**.
- Wordmark: a single word, **"EMULSION"**, scratched-letter treatment described above, 96 pt, color Silver Halide Black.
- Below, **y = 64 mm**, centered, 7.5 pt Söhne Mono Registration Cyan, tracking +200:
  `A FESTIVAL OF FORMALLY EXPERIMENTAL CINEMA · EIGHT FILMS · FOUR NIGHTS`

#### 3.4 — The Bottom Ledger (clinical footer)
- Strip from **y = 760 mm to y = 884 mm**, full width inside safe area (margins 30 mm L/R).
- Three columns, separated by 0.4 pt cyan hairlines at x = 230 mm and x = 410 mm:
  - **Col A — DATES:** "NIGHT I — FRI" / "NIGHT II — SAT" / "NIGHT III — SUN" / "NIGHT IV — MON" with dates set in Söhne Mono 9 pt, leading 14 pt.
  - **Col B — VENUE:** Venue name in Söhne Wide Book 11 pt; address line below in 7.5 pt Mono Cyan; "200 SEATS · NO LATE ENTRY" as final line.
  - **Col C — INDEX:** A miniature replica of the eight-frame stack, 60 mm tall, each frame reduced to 6 mm with a Roman numeral I–VIII beside it in Söhne Mono 6 pt cyan. Functions as a legend.
- Below the three-column block, at **y = 870 mm**, a single horizontal line of edge-code in 6 pt Mono cyan, full width, tracking +400:
  `EMR · MMXXVI · VIII · IV · K-14 · DEV-A · PRINT 01/01 · NO REPRINT · DO NOT FOLD`

#### 3.5 — Micro-marks (the master's signature)
- A 4 mm × 4 mm registration cross (cyan hairline) at each of the four corners, 8 mm in from trim.
- A two-character "lab stamp" — `EM/24` — in Söhne Mono 6 pt cyan, 12 mm above the bottom-right registration cross.
- A barely-visible **density-step wedge** (the lab tool: 11 grayscale patches stepped from Bone to Black) running horizontally at **y = 884 mm**, 88 mm wide, far right edge, 4 mm tall. Functions as a calibration strip and as the work's smallest, most loving detail.

### 4. Texture and Material Treatment

- Entire ground carries a **3% monochrome film grain** at 2400 dpi equivalent — invisible at thumbnail, unmistakable at arm's length.
- Two **dust specks** (0.3 mm, Bone) placed deliberately at coordinates (122 mm, 287 mm) and (488 mm, 612 mm) — the lab's signature, the proof of human handling.
- A **single hair-fiber curve** (0.15 pt black, 38 mm long) across Frame III, placed exactly as a real loose hair would land on a contact print.
- One **fingerprint smudge** (Bench-Lamp Yellow, 18% opacity, 22 mm) on Frame II as already specified.

### 5. What Is Forbidden

- No drop shadows. No bevels. No gradients except those produced by chemistry-mimicking tide-lines.
- No "indie warm cream + black serif" tropes. The cream is here, but it is **base stock**, not nostalgia.
- No photography of laurels, reels, projectors, popcorn, or human faces.
- No decorative ornaments. No swooshes. No icons.
- No more than the eight assigned color values anywhere on the page.
- No element overlaps another element. Every margin is honored. Every alignment is to the 50.83 mm column grid or its 8.47 mm sub-grid.

### 6. The Final Test

Hold the poster at 3 m: the eye reads a single vertical column of eight chromatic events, anchored by a scratched word above and a clinical ledger below. Approach to 30 cm: the eye discovers the perforations, the edge-code, the 1,200 hand-placed dots in Frame VI, the moth-wing silhouettes, the two dust specks, the calibration wedge. The piece **rewards the loupe**. It is the work of a hand that has done this for twenty years and intends to do it for twenty more.

The poster does not look indie-festival. It looks like an artifact pulled from the working bench of someone who has spent a lifetime making light behave. Those who recognize the hand of *Mothlight* will smile. Everyone else will simply feel they are looking at something **made**, in the oldest and most honorable sense of the word.

— *End of specification. Ready for execution at press.*

```

### anthropic-canvas-design/01-poster — v2-generated (9533 bytes)

```
# Cathode Bloom

## Register

This poster announces a four-day, eight-film festival devoted to formally experimental cinema for an audience already steeped in Brakhage. The piece must do two things at once: signal *we are not the warm-paper indie-fest you can ignore*, and signal *the work inside is structural, optical, material — film as a thing that scratches, flickers, decays, and refuses narrative*. The emotional temperature is cold-hot — a CRT left on overnight, a 16mm splice burning through a projector gate. Historical gravity sits in the lineage of late-twentieth-century artist-cinema ephemera: photocopied programs taped to gallery doors, cable-access bumpers, the under-printed handbills that hung outside Anthology Film Archives in 1978. It is print that looks like signal.

## Definition

**Cathode Bloom** is a printed aesthetic that treats the page as a degraded transmission — a still frame pulled from a tape head misaligned by half a tracking line. It believes typography belongs to broadcast engineering, not branding; that color is an emission, not a decoration; and that hierarchy is enforced by interference, not whitespace. Composition is a scanline column, not a poster grid.

## Commitments

### Palette

Source constraint: **NTSC color-bar test pattern (SMPTE ECR 1-1978) sampled off a degaussed Trinitron CRT, plus the bias-tape black of a worn VHS leader.** Six colors, each pulled from a specific bar or off-state region of that signal — no aesthetic blending.

- `#0A0A0E` — bias-tape black (deep field, near-black with magnetic warmth)
- `#E8E2D0` — phosphor white (slightly cream, never paper-white)
- `#D7B72A` — SMPTE yellow bar
- `#1F8F7A` — SMPTE cyan-green (degraded, pulled toward viridian)
- `#C44A2C` — burn-in orange (the color of a logo ghosted into a screen for ten years)
- `#5A5550` — dead-channel gray (the color between stations, used only as connective tissue)

**No purple. No violet. No magenta-to-blue gradient. No neon.** The cyan is held below 50% saturation precisely because the CRT register cannot bloom it without compromising the orange channel — and Cathode Bloom respects channel separation.

### Typography

Two faces, each with a structural reason:

1. **VT323** (Peter Hunt, 2012) — a faithful digital revival of the bitmap font found on early VT-series video terminals. Used for festival metadata: dates, film titles, runtimes, venue. Reason: this is the typographic register of broadcast slates and edit-bay timecode burns, not "design." It carries the implication that the information is being *displayed*, not *typeset*.
2. **IBM Plex Mono Bold** — used only for the festival name, large, set in a single column at the top edge. Reason: a contemporary monospaced grotesque with strong modernist bones; it holds the masthead the way a chyron holds a name. Its monospace structure agrees with VT323's grid logic so the page reads as one engineering surface rather than two competing typographic registers.

**Banned with reason:** Inter, Geist, SF Pro, Helvetica, Arial, Roboto, Montserrat, Poppins. Also banned for this piece: any humanist serif (would import literary warmth that betrays the brief), any handwritten script, any rounded "friendly" geometric sans.

### Composition

**Single-column scanline stack.** The page is divided into 23 horizontal bands of equal height (echoing a half-rate NTSC scanline count, decimated for print). Every element — masthead, film titles, dates, venue, body — locks to a band's baseline. The composition is **left-aligned, ragged-right, never centered.** A vertical hairline rule at the 12% gutter from the left edge runs full height; all type hangs off it. The eight film titles stack as a vertical credit roll occupying bands 8–18, each with its director and runtime in VT323 to the right of the title. There is no hero image. There is no central focal point. The eye reads top-to-bottom like a tape rewinding.

**Interference zones:** three of the 23 bands (chosen at bands 4, 13, and 21) carry a 6-pixel-tall horizontal color-bar interruption — a sliver of SMPTE yellow, cyan, orange — bleeding edge to edge. These are not decoration. They are the philosophy declaring itself: the page is a signal, and the signal is not clean.

### Material / Texture

**Misregistered offset on uncoated stock, with a 1.5% horizontal tear-line displacement applied to one of the four color separations** (the orange channel is shifted 4 pixels right of register). This is rendered, not faked: the orange artwork is offset in the source file. A faint scanline overlay (1px dark band every 3px, 8% opacity) sits across the entire surface — the screen door of a composite-video signal. No drop shadows. No glows. No blurs. The texture is interference, not atmosphere.

### Banned for this piece

- **Universal:** purple, violet, lavender, magenta-to-blue gradients
- **Universal:** drop shadows, glows, "subtle" blurs
- **Universal:** Inter, Geist, SF Pro, Helvetica, Arial, Roboto, Montserrat, Poppins
- **Universal:** "modern minimalist" as a fallback aesthetic
- **Brief-specific:** any film still, photograph, or representational image of a film frame (the brief rejects "hero image with title")
- **Brief-specific:** warm cream/kraft paper backgrounds (the explicit thing the user is tired of)
- **Brief-specific:** centered axial composition, symmetrical layouts
- **Brief-specific:** decorative geometric shapes, abstract "art-direction" flourishes, icon sets
- **Brief-specific:** any hand-drawn or "crafted" lettering (this festival is not artisanal)

## Brief-fit

The brief explicitly rejects the warm-paper minimalist indie-fest convention and asks for something native to formally experimental cinema — work in the lineage of Brakhage but newer. Cathode Bloom answers that directly: it locates the visual register in *structural* and *materialist* film traditions (broadcast artifact, video signal, optical interference) rather than in literary or photographic ones. The audience the user describes — Brakhage-fluent, looking for the next thing — will read the misregistered orange channel and the scanline interruptions as *correctly tuned*, not as decoration. The piece works because it refuses the festival-poster register entirely and instead borrows from the *programmatic ephemera* (slates, leaders, bumpers, test cards) that experimental cinema actually lives inside.

## Concrete visual spec (Stage 2 brief)

- **Format:** PDF, A2 portrait (420×594 mm), 300 dpi equivalent, CMYK-safe values within the named hex set.
- **Bands:** 23 equal horizontal bands of 25.83 mm each. Hairline gutter at 50.4 mm from left edge (12%), 0.25 pt rule in `#5A5550`.
- **Masthead (bands 1–3):** Festival name in IBM Plex Mono Bold, set at ~96 pt, `#E8E2D0` on `#0A0A0E` ground, hung off the gutter rule, runs to band 3 baseline. Beneath it in VT323 24 pt: dates and venue as a single timecode-style line (e.g., `04 NIGHTS — 08 FILMS — 200 SEATS — [VENUE] — [DATES]`).
- **Color-bar interruption (band 4):** full-bleed 6 px stripe split into three equal horizontal segments: yellow `#D7B72A`, cyan-green `#1F8F7A`, orange `#C44A2C`. No labels.
- **Field (bands 5–7):** dead-channel gray `#5A5550` field, empty except a single VT323 line at band 7: `>> SIGNAL ACQUIRED — STAND BY`.
- **Program block (bands 8–18):** eight film titles, one per band where useful (some titles span two bands if length demands), all in VT323 set at ~36 pt, `#E8E2D0` on `#0A0A0E`. Each line: `[TITLE]  ·  [DIRECTOR]  ·  [RUNTIME]`. Hung off gutter rule. Title color: phosphor white. Director and runtime in dead-channel gray. No bullets, no decoration; the dot separators come from the typeface.
- **Color-bar interruption (band 13):** identical to band 4 (re-asserts signal mid-program).
- **Field (bands 19–20):** body copy in VT323 18 pt, two short paragraphs maximum: festival statement + ticketing line. Phosphor white on bias-tape black.
- **Color-bar interruption (band 21):** identical to band 4 (closes the transmission).
- **Footer (bands 22–23):** VT323 14 pt timecode-style metadata line: edition number, date string in `YYYY.MM.DD` format, venue address, URL. Dead-channel gray. Last line ends with a single blinking-cursor block glyph in phosphor white.
- **Misregistration:** in the source file, the orange channel (`#C44A2C` artwork — the orange segments of the three color bars) is shifted +4 px on the x-axis relative to the rest of the artwork. This must be visible at print scale.
- **Scanline overlay:** full-bleed, 1 px dark band (`#0A0A0E` at 8% opacity) every 3 px vertically, applied as the topmost layer.
- **No imagery, no logos beyond the wordmark, no icons, no shapes that aren't a band, a rule, or type.**

## Stage 1 quality gate (verification)

- [x] Named original movement: **Cathode Bloom**
- [x] Palette with constraint source: NTSC SMPTE color bars + degraded CRT phosphor + VHS bias-tape black; six named hex colors
- [x] Typography with reasons: VT323 (broadcast-slate register), IBM Plex Mono Bold (masthead chyron register)
- [x] Specific compositional rule: 23-band scanline stack, left-aligned off a 12% gutter, three color-bar interference rows at bands 4/13/21
- [x] Material/texture commitment: offset misregistration on the orange channel + scanline overlay on uncoated stock
- [x] Banned-for-this-piece list: 4 universal items + 5 brief-specific items

Stage 1 is complete. Stage 2 may proceed to render `artifact.pdf` against this spec.

```


## anthropic-canvas-design/02-brand-identity

**Blind mapping:** A=v2-generated, B=community

### anthropic-canvas-design/02-brand-identity — community (7172 bytes)

```
# Operator's Ledger

*A design philosophy for systems that confess their seams.*

---

## The Movement

**Operator's Ledger** is a visual philosophy built from the workbench, not the showroom. It rejects the consensus aesthetic of the modern B2B SaaS — the soft gradient, the sans-serif lozenge logo, the abstract isometric illustration of a cube floating in lavender mist. That language has been used so many times it now reads as camouflage. Operator's Ledger replaces camouflage with evidence: graph paper, monospaced type, hand-drawn correction marks, and the quiet authority of a notebook kept by someone who has been paged at 03:14 and lived through it. Every artifact in this system must look meticulously crafted, the product of deep expertise, painstaking attention applied to surfaces that deliberately refuse to look "designed."

## Space and Form

Compositions are built on a visible engineering grid — fine cyan or warm grey rules, the kind found on the inside cover of an HP-15C manual or a chemistry lab notebook. The grid is never decoration; it is the load-bearing structure, and elements snap to it with the precision of a mounted slide. Space is generous but never airy: margins are wide enough to feel like a reference document, not a marketing page. Forms are rectilinear, drawn with single-weight outlines as if rendered by a Rotring 0.35 pen. Curves are rare and earned. When a shape is filled, it is filled flat — no gradients, no soft shadows, no glassmorphism. The visual register is the registrar's office, the field manual, the engineering changelog. Master-level execution shows in the alignment: every baseline, every tick mark, every column edge tuned to the half-pixel.

## Color and Material

The palette is small and load-bearing, drawn from oscilloscope screens, telex paper, and industrial signage rather than from the SaaS gradient generator. Primary surface is a warm off-white — the colour of cheap copy paper, around #F4EFE6 — paired with deep ink black at #111111 for type and rule. Two accent colors do all the semantic work: a CRT amber (#D97706) for alerts, indices, and human marks, and a terminal cyan (#1E6F8E) for system traces and grid lines. A single rust red (#9B2C2C) is reserved for incidents — used so sparingly that when it appears the eye locks onto it. No purple. No teal. No corporate blue. The material instinct is paper: faint fiber noise, occasional ink bleed at terminals of strokes, the dry plate of a risograph. Surfaces feel handled, photocopied, archived.

## Typography

Two families, no third. A monospace — IBM Plex Mono or JetBrains Mono — carries all functional text: labels, axes, body, captions. It is small, often 9–11pt, set tight, and treated as data rather than voice. A condensed industrial grotesque — Druk Wide Condensed or a stencil display face — is reserved for the rare large gesture: a single noun, a version number, an incident code. Type is set ragged-right where appropriate; never centered, never expanded with airy tracking to fill space. Headlines behave like part numbers, not slogans. The voice in copy is dry, precise, slightly self-deprecating — the engineer who has read the changelog and has notes. Ten words where a competitor would write a hundred. Annotations and footnote markers (¹, †, §) are used in earnest, as if this were a manual that expects to be referenced again next year.

## Composition and Rhythm

Pages read like a single spread of a ring-bound logbook: a wide left column for system traces and small multiples, a narrow right gutter for human annotations in amber, a footer band of monospaced metadata — timestamp, build, page index. Repetition is the primary rhythm: rows of identical small charts, columns of identical labels, a wall of tick marks. Variety arrives through deliberate breaks in the pattern — one cell circled by hand, one row redacted, one stamp slightly off-axis, as if a human reviewer touched the page after the machine printed it. These imperfections are not casual; they are placed with the discipline of a printmaker pulling a third state. The composition rewards sustained viewing: the more closely it is read, the more it gives back. This is the signature of work labored over for countless hours.

## Hierarchy and Restraint

Hierarchy is achieved through density and position, not size and color. The most important element is often the smallest — a four-character incident code in the top-left corner, weighted by the white space around it. Logos are wordmarks, not glyphs: the company name set in monospace inside a single-rule rectangle, with a build hash beneath, as if stamped on the back of a server. The brand never asks to be liked. It asks to be trusted, the way a multimeter is trusted. Every detail — the kerning of a label, the weight of a rule, the exact warm grey of a deprecated row — is the result of painstaking calibration by someone at the absolute top of their field. Nothing is decorative. Nothing is accidental. The whole system reads as if it were assembled by an engineer who also happens to be a typographer, working slowly, in pencil first, and signing nothing.

---

## Visual Specification

| Token | Value | Use |
|---|---|---|
| `paper` | `#F4EFE6` | Primary surface |
| `ink` | `#111111` | Body type, primary rule |
| `amber` | `#D97706` | Human marks, indices, callouts |
| `cyan` | `#1E6F8E` | Grid, traces, system metadata |
| `rust` | `#9B2C2C` | Incidents only — used once per page maximum |
| `grey-30` | `#8A857C` | Deprecated rows, secondary rule |

**Type stack.** Body & UI: `IBM Plex Mono`, 10/14, tracking `-0.01em`. Display: `Druk Wide Condensed`, used at 64–120pt for a single noun per composition. No third family.

**Grid.** 12-column engineering grid, 8pt baseline, 0.25pt cyan rule at 50% opacity. Margin: 48pt outer, 24pt gutter. Page footer band: 24pt, monospaced, contains `TS · BUILD · PAGE`.

**Logo grammar.** Wordmark only. Company name in mono, all caps, set inside a single 0.5pt ink-ruled rectangle. A build hash (`#a4f29c`) sits beneath the rule in 7pt grey-30. No glyph. No mascot. No gradient.

**Hero composition (landing-page).** Left two-thirds: a dense small-multiple of 24 identical sparkline cells, one circled in amber by hand. Right third: a single condensed-grotesque noun (e.g., `LATENCY`), a four-line monospaced caption, a footnote marker leading to an honest disclosure in the footer. No CTA button styled like a candy. The CTA is a monospaced line of text with a hand-drawn amber underline.

**Voice.** Declarative. Specific. Slightly dry. Never aspirational. Sample: *"We page you when something is wrong. We do not page you when something is interesting."*

**Forbidden.** Gradients. Drop shadows. Glassmorphism. Isometric cubes. Lavender. Teal. Rounded-rectangle logos. The word *seamless*. The word *empower*. Stock photography of diverse hands on laptops.

**Required.** Visible grid. Monospaced metadata. One hand-mark per composition. A footnote that is actually used.

---

*The artifact must read as if recovered from a careful operator's desk — not designed, but kept. That is the entire brief.*

```

### anthropic-canvas-design/02-brand-identity — v2-generated (5974 bytes)

```
# Operator's Console

## Register

This is a brand identity for backend engineers who triage incidents at 3am and have watched their last four monitoring vendors get acquired, pivot to "AI observability," and double the bill. The piece must read like terminal output and engineer-written internal memos, not like a marketing site. Emotional temperature: cold, dry, slightly fatigued, competent. Material gravity: green-screen CRT, line-printer paper, default-monospace dump, the README of a tool that actually works. The brand cannot smile at the user; it must respect that the user has been lied to before.

## Definition

Operator's Console is the visual register of tools that document themselves, refuse decoration, and trust the reader to read. It treats the page like a TTY: fixed-width, left-aligned, time-stamped, evidence-first. Decoration is a confession that the data is weak; this brand commits to having data strong enough that no decoration is needed.

## Commitments

### Palette

Source constraint: VT220 amber-monochrome terminals overlaid with Tektronix storage-tube green and the ink chemistry of a worn IBM line printer carbon ribbon on continuous-feed paper. No screen-era brand colors. Every color is justified by a hardware reference, not a mood board.

- `#0E0E0C` — carbon ribbon black (body text, ground)
- `#F2EBDD` — tractor-feed paper cream (page surface)
- `#C97B1F` — VT220 amber (status: nominal, brand mark accent)
- `#1F6F3A` — Tektronix storage-tube green (status: ok, log-OK lines)
- `#A23A2C` — line-printer red ribbon (status: failure, only state allowed to use red)
- `#7C7468` — pencil-graphite gray (separators, secondary metadata)

### Typography

Two faces. No third face for "personality."

- **IBM Plex Mono** — body, code, status lines, navigation, all UI labels. Reason: it is the typeface of internal engineering documents at a real engineering culture (IBM Design); it has a humanist warmth without softening into branding. It carries the line-printer register without cosplay. *Override note:* a generic monospace would also work, but Plex Mono earns its keep because its italic and its numerals are tuned for tabular data — which is what the brand is selling.
- **Concourse Index** (Matthew Butterick) — display only, used for the wordmark and for section dividers when set in caps. Reason: it is a working-text serif designed by a typographer who refuses the Inter-default; it gives the brand a single non-monospace voice without leaning humanist-corporate. *Substitution:* if Concourse is unavailable, fall back to **Source Serif 4** (humanist, free), never to a sans.

Banned typefaces for this brand: Inter, Geist, SF Pro, Helvetica, Helvetica Neue, Arial, Roboto, Montserrat, Poppins, "modern sans-serif." A geometric sans logo would put this brand in the line of the 30 competitors it must not look like.

### Composition

**TTY column grid.** 80-column fixed-width baseline grid. Every page is composed as if rendered to an 80×24 terminal first, then scaled. Layouts read top-to-bottom, left-to-right, with a hard left margin and a ragged right edge. Hierarchy comes from `## SECTION HEADERS IN CAPS`, blank lines, and indentation — never from centered hero blocks, never from large display type floating in white space. The hero of any page is a *log line*, not a tagline. The wordmark sits flush left, never centered. Status badges (`[OK]`, `[FAIL]`, `[WARN]`) are inline text, not pill-shaped components.

### Material / Texture

Implied surface: 132-column continuous-feed line-printer paper, slight ink bleed at letter edges, faint horizontal banding from print-head pass. Renders may simulate this with a 2–4% noise overlay on the cream ground and a 0.3px softening on glyph edges, or commit to *flat* and let the typography carry the texture by itself — flatness is the honest choice when simulation would tip into cosplay. No gradients. No shadows. No glassmorphism. No "depth."

### Banned for this piece

- Purple, violet, lavender; magenta-to-blue gradients; neon gradients of any kind (universal)
- Drop shadows, glows, subtle blurs on text or shapes (universal)
- Inter, Geist, SF Pro, Helvetica, Arial, Roboto, Montserrat, Poppins (universal)
- "Modern minimalist" centered hero with floating headline over abstract gradient (universal)
- Geometric sans-serif wordmark (the competitor tell — Datadog, Grafana, New Relic, Honeycomb, Chronosphere all live there)
- Decorative geometric shapes, abstract "data" illustrations, isometric server-rack illustrations
- Stock photography of diverse smiling people in front of laptops
- Rounded corners above 2px on any container; pill-shaped buttons; "card" components with elevation
- Emoji or icon-fonts standing in for status (status is a text token: `[OK]`, `[FAIL]`)
- The word "platform," the word "seamless," the word "powerful" anywhere in copy

## Brief-fit

Backend engineers trust tools that look like the tools they already use: man pages, `dmesg`, `journalctl`, the output of a well-written CLI. The brief explicitly rejects the "modern, clean, blue, geometric logo" register because that register is the visual signature of marketing departments who have never opened a terminal — and the audience knows it. Operator's Console fits because every commitment above is a deliberate refusal of that register: monospaced over geometric sans, line-printer cream over SaaS-blue, log-line composition over hero-headline composition, hardware-sourced palette over mood-board palette. It is anti-corporate without being unprofessional — the same way a Linux kernel mailing list is anti-corporate without being unprofessional. Enterprise buyers who matter (the staff engineer who has to sign off) will read this brand as evidence that the team building the product knows what the work actually looks like. Enterprise buyers who don't matter (the brand-deck reviewer in procurement) will be carried by the staff engineer's nod.

```


## anthropic-canvas-design/03-data-viz-aesthetic

**Blind mapping:** A=community, B=v2-generated

### anthropic-canvas-design/03-data-viz-aesthetic — community (6374 bytes)

```
# Forensic Cartography

## Design Philosophy

A visual movement for data that carries weight. Forensic Cartography treats quantitative information not as a chart to be glanced at but as evidence to be witnessed. It borrows the visual grammar of nautical charts, geological surveys, and 19th-century ordnance maps — disciplines where every mark was placed by hand because lives or land depended on its accuracy. The aesthetic refuses the convenience of the default plotting library. Each value is rendered as though a cartographer pressed it into the page, the product of deep expertise and painstaking attention.

Space is the primary instrument. Vast unmarked margins frame a dense central body of marks, the way a map leaves ocean blank around a coastline. The composition breathes at its edges and accumulates at its center. Negative space is not emptiness but pressure — it gives the data room to mean something. Hierarchy emerges through scale contrast rather than typographic weight: one enormous numeric or formal element anchors the page, while a constellation of micro-marks, hairline rules, and clinical annotations orbit it. The eye is meant to travel, not skim.

Color is restrained to a forensic palette: warm parchment or bone ground, deep ink-black for primary structure, a single accent of oxidized iron — the color of dried blood, rust, scorched earth — used sparingly as the load-bearing chromatic gesture. No gradients. No fills that decorate. Color carries information or it does not appear. Material memory is suggested through subtle paper grain, faint registration marks, and the sense of an analog plate that has been pulled by hand. The work should feel meticulously crafted, as though pressed rather than rendered.

Marks behave like instruments. Vertical lines are calibration ticks; horizontal rules are baselines; small filled forms are observations logged. Repetition is doctrine: the same disciplined stroke applied across the dataset produces a field of evidence, and that field becomes a portrait of the phenomenon. Numbers appear as monumental forms when they matter and as tiny precise indices when they support — the typography of a survey monograph, not a dashboard. Master-level execution shows in the alignment of every tick, every baseline, every micro-label.

Typography is sparse and clinical. A single restrained serif or a thin geometric sans, used at two or three exact sizes only. Labels are short — units, years, totals, a single declarative phrase. No titles that explain what the picture already shows. No legends that the composition can encode spatially. Text is integrated as a visual element on the plate, never floated as caption. Where a word appears, it appears because removing it would collapse the meaning.

The work is the result of countless hours: every alignment refined, every hairline weighted, every margin calibrated, every annotation placed with the care of someone at the absolute top of their field. It rewards sustained viewing. It treats the viewer as a witness, not a consumer. The final artifact should feel like a document recovered from an institution that takes its subject with the gravity it deserves — an artifact, not an output.

---

## Visual Specification — Acres Burned, California, 2014–2024

**Format.** Single plate, portrait orientation, 8.5 x 11 in equivalent. Bone-white ground (#F2EBDD), faint paper grain at 4% opacity. Outer margin 1.25 in on all sides; inner plate framed by a hairline rule at 0.4 pt, ink-black (#1A1714).

**Anchor.** A single oxidized-iron numeral set at the bottom-left of the plate, 220 pt thin serif, reading the eleven-year cumulative total in acres. No label. The figure is the title. Beside it, in 7 pt small caps tracked +120: `CUMULATIVE — CALIFORNIA — 2014–2024`.

**Primary mark field.** Eleven vertical bars, one per year, occupying the upper two-thirds of the plate. Bars are not filled rectangles. Each bar is constructed from stacked horizontal hairlines at 0.25 pt, ink-black, spaced 0.4 mm apart — one hairline per ten-thousand acres burned. The bar's height is therefore the literal accumulation of marks, not a scaled rectangle. The eye reads quantity as sediment.

**Calibration.** A vertical scale rule sits 0.5 in left of the bar field, ticked every 100,000 acres. Tick labels in 6 pt thin sans, right-aligned: `100K`, `500K`, `1M`, `2M`, `4M`. No horizontal gridlines crossing the field — the bars themselves are the grid.

**Year axis.** Below each bar, a 1.2 mm tick descends from a baseline rule. Year set in 7 pt thin serif, lining figures: `2014` through `2024`. Below the year, in 5.5 pt small caps, the per-year acreage as a precise integer with thin-space thousands separator. No comma.

**The 2020 and 2018 columns.** These two bars — the catastrophic years — are rendered identically to the others in structure, but each carries a single oxidized-iron hairline drawn through the bar at the recorded peak, extending 6 mm to the right of the bar with a 5 pt micro-label: the year's deadliest fire name in italic small caps. No drama. Just a recorded mark.

**Marginalia.** Lower-right corner, a 1.5 in square block of micro-text in 5.5 pt thin serif, justified, eight lines maximum. A clinical note: source attribution (CAL FIRE, NIFC), the unit definition (one hairline = 10,000 acres), the date of compilation. Set with the restraint of a museum object label.

**Registration marks.** Four small crosshairs at the inner corners of the plate frame, 3 mm, 0.3 pt — the trace of a hand-pulled print. Below the bottom-left crosshair, a plate number set in 6 pt thin sans: `PL. 03 / DV`.

**Constraints.** No color outside (#F2EBDD ground, #1A1714 ink, #6B2417 oxidized iron). No drop shadows, no gradients, no rounded corners, no icons. Every hairline aligned to a 0.4 mm subgrid. Every text element snapped to the same baseline grid as the bar hairlines, so type and data share one rhythm. Margins absolute and equal; no element crosses the inner plate frame.

**Reading.** From across a room: a dark sedimentary mass weighted toward the recent years, anchored by a single grave numeral. From close: eleven hand-counted columns of evidence, each hairline a plot of land that burned, each year measured against the next by the patient accumulation of marks. The chart does not perform. It records.

```

### anthropic-canvas-design/03-data-viz-aesthetic — v2-generated (9804 bytes)

```
# Fire-Season Ledger

## Register

This is a piece about acres burned in California across eleven years. It is not a "dashboard," not a "visualization," not a story-time infographic. It is a ledger — the kind of bound, single-column tally a county clerk or insurance assessor would have kept in 1962, where numbers were entered with the understanding that someone, eventually, would have to answer for them. The temperature is grave but unhurried; the year is over, the count is in, and the page exists so the count can be read aloud. The material gravity is paper — uncoated, slightly toned, the kind that absorbs ink rather than reflecting it. There is no animation, no hover state, no smooth gradient softening the years that were catastrophic into the years that were merely bad.

## Definition

**Fire-Season Ledger** is a movement that treats annual loss data as accounting, not narrative. It believes that the dignity owed to a number burned into landscape is the dignity of being recorded plainly, in a typographic register that predates persuasion, on a surface that admits the count is final. It rejects the idea that data must be "made compelling" — the figure compels itself, and the designer's job is to remove obstacles between the reader and the figure.

## Commitments

### Palette

Sourced from the **uncoated stock + single-pass letterpress impression of mid-century U.S. county records** — specifically the visual register of Department of the Interior Forest Service annual reports, 1958–1971, before four-color process reached field publications.

- `#EBE3D2` — paper ground (warm uncoated, slightly toned, never white)
- `#1C1A14` — primary ink (a dense near-black with a brown undertone, reading as warm carbon, not screen-black)
- `#A8341B` — record ink (a single accent, oxidized red — the color of a county assessor's stamp, used only where the number itself demands a second voice)
- `#6B6356` — rule ink (a desaturated warm gray for hairlines and footers, half-strength of the primary)

No gradient. No third hue. Red appears only on figures exceeding the eleven-year mean.

### Typography

- **Headline / figures: Trinité (or Lyon Display as substitute)** — a humanist serif with high-contrast verticals and a typewriter-era field-report feel. Chosen because the count must read like a record, not a brand. Numbers are set in **lining figures, not tabular old-style**, because in a ledger the digit is the unit of accounting and must read as such.
- **Body / labels: Plantin (or Source Serif as substitute)** — a transitional serif used in 20th-century governmental and scientific publishing. Chosen for the same reason a 1965 Forest Service bulletin would have used it: because it disappears into the page and lets the count surface.
- **No sans-serif anywhere.** No grotesque, no humanist sans, no monospace. The piece predates the visual culture that produced those choices.

### Composition

**Single-column ledger stack, vertical, left-ruled.** Years are rows, not bars. Each row contains: the year (left, set small), a hairline rule extending the full proportional width of the value, and the figure (right, set large, in record ink if it exceeds mean). The "chart" is the alignment of the rules — the eye reads vertical proportion the way it would read a column of receipts. No x-axis. No y-axis. No title block centered above. The piece is justified left and reads top-to-bottom like a page from a ledger book, because it **is** a page from a ledger book. A footer rule runs at the bottom under "TOTAL" and the eleven-year sum.

### Material / Texture

Uncoated paper ground rendered as warm-toned base color with a faint, evenly distributed grain (1–2% noise, achromatic). Hairlines are 0.5pt and rendered with slight roughness at terminals to imply impression bite, not laser-perfect vector. Figures are set in solid ink, not screened. No glow, no halo, no soft edge — letterforms either touch the paper or they don't.

### Banned for this piece

- Purple, violet, lavender, magenta-to-blue gradients (universal)
- Drop shadows, glows, "subtle" blurs (universal)
- Inter, Geist, SF Pro, Helvetica, Arial, Roboto, Montserrat, Poppins, "system sans" (universal)
- "Modern minimalist" as a fallback aesthetic (universal)
- **No gridlines.** A ledger has rules, not a grid; gridlines are a data-viz default and they import the off-the-shelf look the brief explicitly rejects.
- **No bar chart geometry.** Filled rectangles read as infographic; the piece uses hairline rules of proportional length, which is a different visual species.
- **No color encoding by magnitude beyond the binary above/below-mean cut.** Continuous color ramps are dashboard grammar; the ledger has only ink and stamp.
- **No icons, no flame glyphs, no abstract geometric flair.** The figure is the subject; ornament is an admission of distrust in the figure.

## Brief-fit

The brief asks for a treatment that takes the data seriously without borrowing the off-the-shelf data-viz look. A ledger does exactly that: it is the pre-data-viz form for recording annual loss, and it carries with it the gravity of a document made to be answered for. By rendering acres-burned-per-year as a column of dated entries on uncoated stock, in a humanist serif, with one accent color reserved for years above the mean, the piece communicates the gravity of the numbers without dramatizing them, and it cannot be confused with a Tableau export. The form predates the aesthetic the brief rejects, which is why it is available to it.

---

## Phase 2 plan (render spec)

**Format:** PNG, 2400×3000 px, 300dpi-equivalent. (Vertical column composition; tall is the correct shape for a ledger page.)

**Tool:** Python + Pillow + matplotlib's text rendering for serif faces, OR HTML + WeasyPrint with `@font-face` declarations for Lyon/Plantin substitutes (Source Serif Pro, Crimson Pro). HTML route preferred for typographic precision.

**Data subset (acres burned per year, 2014–2024, CAL FIRE published totals, rounded to nearest thousand):**

| Year | Acres |
|------|------:|
| 2014 | 625,540 |
| 2015 | 893,362 |
| 2016 | 669,534 |
| 2017 | 1,548,429 |
| 2018 | 1,975,086 |
| 2019 | 259,823 |
| 2020 | 4,397,809 |
| 2021 | 2,568,948 |
| 2022 | 363,939 |
| 2023 | 332,722 |
| 2024 | 1,050,012 |

Eleven-year mean ≈ **1,335,000 acres.** Years rendered in record ink (`#A8341B`): 2017, 2018, 2020, 2021. All other years in primary ink (`#1C1A14`).

**Layout (HTML/CSS sketch):**

```
.page              { background: #EBE3D2; padding: 180px 220px; width: 2400px; }
.title             { font: 22px Plantin; letter-spacing: 0.18em; text-transform: uppercase;
                     color: #6B6356; margin-bottom: 4px; }
.subtitle          { font: 14px Plantin italic; color: #6B6356; margin-bottom: 80px; }
.row               { display: grid; grid-template-columns: 90px 1fr 240px;
                     align-items: baseline; margin-bottom: 18px; }
.row .year         { font: 16px Plantin; color: #1C1A14; }
.row .rule         { height: 0.5px; background: #1C1A14; opacity: 0.85; }
.row .figure       { font: 56px "Lyon Display", "Source Serif Pro", serif;
                     text-align: right; color: #1C1A14; }
.row.over-mean .figure { color: #A8341B; }
.row .rule         { width: calc(var(--proportion) * 100%); }
.footer-rule       { border-top: 1px solid #1C1A14; margin-top: 60px; padding-top: 18px; }
.total             { font: 24px Plantin; text-align: right; color: #1C1A14; }
.colophon          { font: 11px Plantin italic; color: #6B6356;
                     margin-top: 120px; max-width: 60ch; }
```

**Header text (set small, uppercase, letter-spaced):**
> CALIFORNIA FIRE-SEASON LEDGER · ACRES BURNED · 2014–2024
> *Source: CAL FIRE annual incident summaries. Figures rounded to the nearest thousand.*

**Footer text:**
> TOTAL, ELEVEN YEARS · 14,685,204 ACRES
> *An area larger than the state of West Virginia.*

**Texture pass:** apply 1.5% achromatic noise over the full canvas via Pillow `ImageFilter`, then a single multiply-blend of the paper hex over the rendered text layer to seat the ink into the stock. No further processing.

**Self-inspection checks (Phase 3):**

- Palette: only the four hex codes appear. No purple. No gradient. ✓ (enforced by CSS variables)
- Typography: only Lyon Display + Plantin (or substitutes Source Serif Pro + Crimson Pro). No Inter, no sans. ✓
- Composition: rows of year/rule/figure, left-aligned column, no x/y axes, no gridlines, no filled bars. ✓
- Default-aesthetic absence: no shadow, no glow, no centered headline-over-hero, no flame icon. ✓
- Originality: the piece reads as a 1965 Forest Service ledger page, not as a Datawrapper export and not as a known designer's work. ✓
- Brief-fit: the eleven figures, the four red years, and the 14.6M total are the visual center of gravity. ✓

---

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
canvas-design — done
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Movement:    Fire-Season Ledger
Philosophy:  ./philosophy.md
Artifact:    ./artifact.png
Source:      ./artifact.html
Palette:     4 colors, source: uncoated stock + single-pass letterpress, U.S. Forest Service field reports 1958–1971
Typography:  Lyon Display (figures) + Plantin (body)
Composition: single-column ledger stack, year-rule-figure rows, left-justified, no axes
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
To iterate: edit philosophy.md, then re-run /canvas-design.
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

```


## chrisvoncsefalvay-d3/01-bar-with-edge-case

**Blind mapping:** A=community, B=v2-generated

### chrisvoncsefalvay-d3/01-bar-with-edge-case — community (17008 bytes)

```
# Horizontal Bar Chart with Edge Cases (d3.js v7+)

A responsive, animated horizontal bar chart that handles two notorious edge cases gracefully:

1. **Zero-value bars** — rendered with a minimum visible width + dashed outline so they don't disappear.
2. **Outliers** — a `symlog` (symmetric log) scale is used by default so a few large values don't crush the mid-range bars into invisibility. A toggle switches back to a linear scale for honest comparison.

Drop-in for vanilla JS, React, Vue, or Svelte — the rendering function is framework-agnostic and only needs an SVG element + a data array.

---

## 1. The core rendering function (framework-agnostic)

Save this as `horizontal-bar-chart.js`. It exports a single `drawBarChart(svgElement, data, options)` function plus a `setupResponsiveBarChart` helper.

```javascript
// horizontal-bar-chart.js
// Modern d3 v7+. No framework dependencies.
import * as d3 from 'd3';

/**
 * Draw a horizontal bar chart with edge-case handling.
 *
 * @param {SVGElement|string} svgElement - SVG DOM node or selector (e.g. '#chart').
 * @param {Array<{label: string, value: number}>} data
 * @param {object} [options]
 * @param {number} [options.width]            Container width (auto if omitted).
 * @param {number} [options.height]           Container height (auto if omitted).
 * @param {'symlog'|'linear'} [options.scale='symlog']
 *        symlog = squashes outliers, keeps mid-range readable, supports zero & negatives.
 *        linear = honest comparison, but outliers can dominate.
 * @param {number} [options.minBarPx=2]       Minimum pixel width for any bar (so 0 is still visible).
 * @param {number} [options.duration=600]     Transition duration in ms.
 * @param {string} [options.barColor='#4A90E2']
 * @param {string} [options.zeroColor='#B0B0B0']
 */
export function drawBarChart(svgElement, data, options = {}) {
  // ---------- Guards ----------
  if (!svgElement || !data) return;
  // Filter out null/NaN entries but KEEP zeros — they are meaningful.
  const cleanData = data.filter(
    (d) => d && typeof d.value === 'number' && !isNaN(d.value)
  );
  if (cleanData.length === 0) return;

  // ---------- Resolve target ----------
  const svg = typeof svgElement === 'string'
    ? d3.select(svgElement)
    : d3.select(svgElement);

  // ---------- Dimensions ----------
  const node = svg.node();
  const bbox = node.getBoundingClientRect();
  const width  = options.width  ?? bbox.width  ?? 800;
  const height = options.height ?? bbox.height ?? Math.max(240, cleanData.length * 42);

  const margin = { top: 20, right: 70, bottom: 30, left: 110 };
  const innerWidth  = Math.max(10, width  - margin.left - margin.right);
  const innerHeight = Math.max(10, height - margin.top  - margin.bottom);

  svg.attr('width', width)
     .attr('height', height)
     .attr('viewBox', `0 0 ${width} ${height}`)
     .attr('role', 'img')
     .attr('aria-label', 'Horizontal bar chart');

  // ---------- Root <g> (idempotent: reuse if exists, so transitions are smooth) ----------
  let g = svg.select('g.chart-root');
  if (g.empty()) {
    g = svg.append('g').attr('class', 'chart-root');
  }
  g.attr('transform', `translate(${margin.left},${margin.top})`);

  // ---------- Scales ----------
  const minBarPx  = options.minBarPx  ?? 2;
  const duration  = options.duration  ?? 600;
  const barColor  = options.barColor  ?? '#4A90E2';
  const zeroColor = options.zeroColor ?? '#B0B0B0';
  const scaleKind = options.scale     ?? 'symlog';

  const maxValue = d3.max(cleanData, (d) => d.value) ?? 1;
  const minValue = Math.min(0, d3.min(cleanData, (d) => d.value) ?? 0);

  // Outlier squash via symlog. constant=1 ⇒ ~linear near zero, log far from zero.
  // Falls back to linear when the user wants honest comparison.
  const xScale = (scaleKind === 'symlog'
    ? d3.scaleSymlog().constant(1)
    : d3.scaleLinear()
  )
    .domain([minValue, maxValue || 1])
    .range([0, innerWidth])
    .nice();

  const yScale = d3.scaleBand()
    .domain(cleanData.map((d) => d.label))
    .range([0, innerHeight])
    .padding(0.18);

  // ---------- Axes ----------
  // X axis: fewer ticks + smart formatter so symlog ticks read cleanly.
  const tickFormat = (v) => {
    if (v === 0) return '0';
    const abs = Math.abs(v);
    if (abs >= 1e6) return d3.format('.2~s')(v);
    if (abs >= 1e3) return d3.format(',')(v);
    return d3.format('~g')(v);
  };

  let xAxisG = g.select('g.x-axis');
  if (xAxisG.empty()) {
    xAxisG = g.append('g').attr('class', 'x-axis');
  }
  xAxisG
    .attr('transform', `translate(0,${innerHeight})`)
    .transition()
    .duration(duration)
    .call(d3.axisBottom(xScale).ticks(6).tickFormat(tickFormat));

  let yAxisG = g.select('g.y-axis');
  if (yAxisG.empty()) {
    yAxisG = g.append('g').attr('class', 'y-axis');
  }
  yAxisG
    .transition()
    .duration(duration)
    .call(d3.axisLeft(yScale));

  // ---------- Tooltip (singleton on body) ----------
  let tooltip = d3.select('body').select('div.d3-bar-tooltip');
  if (tooltip.empty()) {
    tooltip = d3.select('body')
      .append('div')
      .attr('class', 'd3-bar-tooltip')
      .style('position', 'absolute')
      .style('pointer-events', 'none')
      .style('visibility', 'hidden')
      .style('background', 'rgba(20,20,20,0.92)')
      .style('color', '#fff')
      .style('padding', '6px 9px')
      .style('border-radius', '4px')
      .style('font', '12px/1.3 Inter, system-ui, sans-serif')
      .style('box-shadow', '0 2px 8px rgba(0,0,0,0.18)')
      .style('z-index', '9999');
  }

  // Origin pixel = where value=0 sits. Bars grow from here.
  const xZero = xScale(0);

  // ---------- Bars (data join, keyed by label so transitions track items) ----------
  const bars = g.selectAll('rect.bar')
    .data(cleanData, (d) => d.label);

  // EXIT
  bars.exit()
    .transition().duration(duration)
    .attr('width', 0)
    .attr('opacity', 0)
    .remove();

  // ENTER
  const barsEnter = bars.enter()
    .append('rect')
    .attr('class', 'bar')
    .attr('y', (d) => yScale(d.label))
    .attr('height', yScale.bandwidth())
    .attr('x', xZero)
    .attr('width', 0)
    .attr('fill', (d) => (d.value === 0 ? zeroColor : barColor))
    .attr('stroke', (d) => (d.value === 0 ? zeroColor : 'none'))
    .attr('stroke-dasharray', (d) => (d.value === 0 ? '3,2' : null))
    .attr('fill-opacity', (d) => (d.value === 0 ? 0.25 : 0.92));

  // Tooltip wiring (attach once on enter; selection persists across updates)
  barsEnter
    .on('mouseover', function (event, d) {
      d3.select(this).attr('fill-opacity', 1);
      tooltip
        .style('visibility', 'visible')
        .html(
          `<strong>${escapeHtml(d.label)}</strong><br/>` +
          `Value: ${d3.format(',')(d.value)}` +
          (d.value === 0 ? '<br/><em>(zero)</em>' : '')
        );
    })
    .on('mousemove', function (event) {
      tooltip
        .style('top',  (event.pageY - 10) + 'px')
        .style('left', (event.pageX + 12) + 'px');
    })
    .on('mouseout', function (event, d) {
      d3.select(this).attr('fill-opacity', d.value === 0 ? 0.25 : 0.92);
      tooltip.style('visibility', 'hidden');
    });

  // ENTER + UPDATE (merge + transition to current scale)
  barsEnter.merge(bars)
    .transition()
    .duration(duration)
    .attr('y', (d) => yScale(d.label))
    .attr('height', yScale.bandwidth())
    .attr('x', (d) => Math.min(xZero, xScale(d.value)))
    .attr('width', (d) => {
      // Edge case: zero or near-zero bars get a guaranteed minimum width
      // so they never visually disappear.
      const raw = Math.abs(xScale(d.value) - xZero);
      return Math.max(raw, minBarPx);
    })
    .attr('fill',   (d) => (d.value === 0 ? zeroColor : barColor))
    .attr('stroke', (d) => (d.value === 0 ? zeroColor : 'none'))
    .attr('stroke-dasharray', (d) => (d.value === 0 ? '3,2' : null))
    .attr('fill-opacity', (d) => (d.value === 0 ? 0.25 : 0.92));

  // ---------- Value labels at end of each bar ----------
  const labels = g.selectAll('text.value-label')
    .data(cleanData, (d) => d.label);

  labels.exit().remove();

  const labelsEnter = labels.enter()
    .append('text')
    .attr('class', 'value-label')
    .attr('x', xZero)
    .attr('y', (d) => yScale(d.label) + yScale.bandwidth() / 2)
    .attr('dy', '0.35em')
    .style('font', '11px Inter, system-ui, sans-serif')
    .style('fill', '#333');

  labelsEnter.merge(labels)
    .transition()
    .duration(duration)
    .attr('x', (d) => {
      const endX = Math.max(xScale(d.value), xZero + minBarPx);
      return endX + 6;
    })
    .attr('y', (d) => yScale(d.label) + yScale.bandwidth() / 2)
    .tween('text', function (d) {
      // Number-tween for satisfying value transitions
      const self = this;
      const prev = +self.getAttribute('data-prev') || 0;
      const i = d3.interpolateNumber(prev, d.value);
      self.setAttribute('data-prev', d.value);
      return (t) => {
        const v = i(t);
        self.textContent = d3.format(',')(Math.round(v));
      };
    });

  // ---------- Zero baseline (subtle vertical guide at value=0) ----------
  let baseline = g.select('line.zero-baseline');
  if (baseline.empty()) {
    baseline = g.append('line').attr('class', 'zero-baseline');
  }
  baseline
    .transition().duration(duration)
    .attr('x1', xZero).attr('x2', xZero)
    .attr('y1', 0).attr('y2', innerHeight)
    .attr('stroke', '#999')
    .attr('stroke-dasharray', '2,2')
    .attr('stroke-width', 1);
}

/**
 * Set up a responsive chart that redraws on container resize.
 *
 * @param {SVGElement} svgElement
 * @param {() => Array} getData  Function returning the latest data.
 * @param {object} [options]
 * @returns {() => void} cleanup function
 */
export function setupResponsiveBarChart(svgElement, getData, options = {}) {
  const parent = svgElement.parentElement || svgElement;
  const render = () => drawBarChart(svgElement, getData(), options);

  const observer = new ResizeObserver(() => render());
  observer.observe(parent);
  render();

  return () => observer.disconnect();
}

// Tiny utility: escape HTML in tooltip labels.
function escapeHtml(s) {
  return String(s).replace(/[&<>"']/g, (c) => ({
    '&': '&amp;', '<': '&lt;', '>': '&gt;', '"': '&quot;', "'": '&#39;'
  }[c]));
}
```

### Why this handles the edge cases

| Edge case | Handling |
|---|---|
| Zero-value bar disappears | `Math.max(width, minBarPx)` floor + dashed grey stroke + `(zero)` annotation in tooltip. The zero baseline line keeps the origin obvious. |
| Outliers crush mid-range | Default `scaleSymlog` (symmetric log) compresses large magnitudes while preserving a near-linear region around zero. Toggle to `linear` for honest comparison. |
| Re-rendering kills transitions | Root `<g>` and axes are reused; data join is **keyed by label** so the same item animates to its new position/width instead of being deleted+re-inserted. |
| Negative values | `xZero` anchor + `Math.min(xZero, xScale(d.value))` lets bars grow leftward. |

---

## 2. Vanilla JS mount

```html
<!doctype html>
<html>
  <head><meta charset="utf-8" /><title>Edge-case bar chart</title></head>
  <body style="font-family: Inter, system-ui, sans-serif; padding: 24px;">
    <h2>Category breakdown</h2>

    <label>
      Scale:
      <select id="scale-toggle">
        <option value="symlog" selected>Symlog (squash outliers)</option>
        <option value="linear">Linear (honest)</option>
      </select>
    </label>
    <button id="randomize">Randomize</button>

    <div id="chart-container" style="width: 100%; max-width: 900px; height: 380px;">
      <svg id="chart" style="width:100%; height:100%;"></svg>
    </div>

    <script type="module">
      import { setupResponsiveBarChart, drawBarChart } from './horizontal-bar-chart.js';

      // 8 categories: 1 zero, 2 outliers, 5 mid-range.
      let data = [
        { label: 'Alpha',   value:    420 },
        { label: 'Bravo',   value:    560 },
        { label: 'Charlie', value:      0 }, // zero
        { label: 'Delta',   value:    310 },
        { label: 'Echo',    value: 18_000 }, // outlier
        { label: 'Foxtrot', value:    480 },
        { label: 'Golf',    value: 26_500 }, // outlier
        { label: 'Hotel',   value:    390 },
      ];

      const svg = document.getElementById('chart');
      const select = document.getElementById('scale-toggle');

      let options = { scale: select.value };
      const cleanup = setupResponsiveBarChart(svg, () => data, options);

      select.addEventListener('change', () => {
        options.scale = select.value;
        drawBarChart(svg, data, options);
      });

      document.getElementById('randomize').addEventListener('click', () => {
        data = data.map((d, i) => ({
          ...d,
          // Preserve the zero + occasional outliers
          value: i === 2 ? 0
               : i === 4 || i === 6 ? Math.round(15000 + Math.random() * 20000)
               : Math.round(200 + Math.random() * 600)
        }));
        drawBarChart(svg, data, options);
      });

      // window.addEventListener('beforeunload', cleanup);
    </script>
  </body>
</html>
```

---

## 3. React mount (React 18+)

```jsx
// BarChart.jsx
import { useEffect, useRef, useState } from 'react';
import { drawBarChart, setupResponsiveBarChart } from './horizontal-bar-chart.js';

export function BarChart({ data, scale = 'symlog' }) {
  const svgRef = useRef(null);

  // Responsive setup runs once.
  useEffect(() => {
    if (!svgRef.current) return;
    const cleanup = setupResponsiveBarChart(
      svgRef.current,
      () => data,
      { scale }
    );
    return cleanup;
  }, []); // eslint-disable-line react-hooks/exhaustive-deps

  // Redraw on data/scale change.
  useEffect(() => {
    if (!svgRef.current) return;
    drawBarChart(svgRef.current, data, { scale });
  }, [data, scale]);

  return (
    <div style={{ width: '100%', height: 380 }}>
      <svg ref={svgRef} style={{ width: '100%', height: '100%' }} />
    </div>
  );
}

// Usage:
// <BarChart data={data} scale="symlog" />
```

---

## 4. Vue 3 mount (Composition API)

```vue
<!-- BarChart.vue -->
<script setup>
import { ref, watch, onMounted, onBeforeUnmount } from 'vue';
import { drawBarChart, setupResponsiveBarChart } from './horizontal-bar-chart.js';

const props = defineProps({
  data:  { type: Array,  required: true },
  scale: { type: String, default: 'symlog' }
});

const svgRef = ref(null);
let cleanup = null;

onMounted(() => {
  cleanup = setupResponsiveBarChart(
    svgRef.value,
    () => props.data,
    { scale: props.scale }
  );
});

watch(() => [props.data, props.scale], () => {
  drawBarChart(svgRef.value, props.data, { scale: props.scale });
}, { deep: true });

onBeforeUnmount(() => cleanup && cleanup());
</script>

<template>
  <div style="width:100%; height:380px;">
    <svg ref="svgRef" style="width:100%; height:100%;" />
  </div>
</template>
```

---

## 5. Svelte mount (Svelte 4/5)

```svelte
<!-- BarChart.svelte -->
<script>
  import { onMount, onDestroy } from 'svelte';
  import { drawBarChart, setupResponsiveBarChart } from './horizontal-bar-chart.js';

  export let data;
  export let scale = 'symlog';

  let svgEl;
  let cleanup;

  onMount(() => {
    cleanup = setupResponsiveBarChart(svgEl, () => data, { scale });
  });

  // Reactive redraw when inputs change.
  $: if (svgEl && data) drawBarChart(svgEl, data, { scale });

  onDestroy(() => cleanup && cleanup());
</script>

<div style="width:100%; height:380px;">
  <svg bind:this={svgEl} style="width:100%; height:100%;"></svg>
</div>
```

---

## 6. Sample dataset (matches the brief)

```javascript
// 8 categories: 1 zero, 2 outliers, 5 mid-range.
export const sampleData = [
  { label: 'Alpha',   value:    420 },
  { label: 'Bravo',   value:    560 },
  { label: 'Charlie', value:      0 },
  { label: 'Delta',   value:    310 },
  { label: 'Echo',    value: 18_000 },
  { label: 'Foxtrot', value:    480 },
  { label: 'Golf',    value: 26_500 },
  { label: 'Hotel',   value:    390 },
];
```

---

## Notes on the design choices

- **`d3.scaleSymlog` over `d3.scaleLog`**: symlog handles zero (and negatives) gracefully — pure log can't. With `constant: 1`, values near zero behave linearly, then compress logarithmically as they grow, which is exactly what we want when two outliers would otherwise dwarf the rest.
- **Keyed data join (`(d) => d.label`)**: makes update transitions track the *same item* across renders rather than reshuffling. Without keys, you get cross-fade chaos when randomizing.
- **Idempotent root `<g>` + axes**: re-using these on every redraw is what allows `transition()` to actually animate, rather than constantly rebuilding the DOM.
- **Tooltip on `body`, not `svg`**: avoids SVG clipping issues at chart edges and survives transform/zoom.
- **`viewBox` + ResizeObserver**: real responsiveness — the chart redraws against the container's actual measured box, not just on `window.resize`.

```

### chrisvoncsefalvay-d3/01-bar-with-edge-case — v2-generated (13952 bytes)

```
# Horizontal bar chart — d3 v7+, framework-agnostic

Parsed spec:

```
Viz type: horizontal bar chart with edge-case-aware scaling
Data shape: [{ category: string, value: number }] (8 rows; one zero, two outliers, rest mid-range)
Interactions: hover tooltips (exact value), animated transitions on data update, responsive width
Scale: 8 data points, fluid width × ~360 px height
Host: unknown (provide all four integration snippets)
```

Primitive selections (Phase 2):
- `d3.scaleSymlog` for the value axis — symmetric log preserves visible width for the zero bar AND prevents the two outliers from crushing mid-range bars into invisibility. (Plain `scaleLinear` would make mid-range bars ~5% the width of the outliers; plain `scaleLog` would error on `0`.)
- `d3.scaleBand` for categorical y-axis (built-in padding handles bar spacing).
- `d3.axisBottom` / `d3.axisLeft` — never hand-roll axes.
- `selection.join(enter, update, exit)` — v7+ data-join idiom; required for animated updates.
- `ResizeObserver` (browser native) for container-width responsiveness; cheaper and more accurate than `window.resize`.
- A `<div>` tooltip (positioned absolute) over an SVG `<title>` — gives us styled HTML and pointer-following.

## File: `viz.js`

```javascript
// d3 v7+ — framework-agnostic horizontal bar chart with edge-case-aware scaling.
// Requires: d3 ^7.0.0 (or modular d3-* packages, see imports).
//
// Lifecycle contract:
//   1. Place an <svg> (or <div>) in your DOM.
//   2. Call render(container, data, options) on mount.
//   3. Call the returned cleanup() on unmount.
//   4. Call the returned update(newData) when data changes — bars animate.
//
// Edge-case handling baked in:
//   - Zero values render with a minimum visible bar width (3 px) so they don't disappear.
//   - Outliers don't crush mid-range bars: we use scaleSymlog (symmetric log, defined at 0).

import { select, pointer } from "d3-selection";
import { scaleBand, scaleSymlog } from "d3-scale";
import { axisBottom, axisLeft } from "d3-axis";
import { max } from "d3-array";
import { format } from "d3-format";
import "d3-transition"; // attaches selection.transition()

/**
 * Render a horizontal bar chart.
 * @param {Element|string} container - DOM element or CSS selector to mount into. Expected to be an <svg> or a <div> wrapper.
 * @param {Array<{category: string, value: number}>} data
 * @param {Object} [options]
 * @param {number} [options.height=360]    - Fixed chart height in px (width is responsive).
 * @param {Object} [options.margin]        - { top, right, bottom, left }.
 * @param {number} [options.minBarPx=3]    - Minimum bar width so zero/tiny values stay visible.
 * @param {number} [options.duration=600]  - Transition duration ms.
 * @returns {{ update: (newData: Array) => void, cleanup: () => void }}
 */
export function render(container, data, options = {}) {
  // ---------- 1. Resolve container ----------
  const root = typeof container === "string" ? document.querySelector(container) : container;
  if (!root) throw new Error("render(): container not found");

  const {
    height = 360,
    margin = { top: 16, right: 24, bottom: 36, left: 120 },
    minBarPx = 3,
    duration = 600,
  } = options;

  // The host gives us either an <svg> or a wrapper <div>. Normalize: we want
  // an <svg> we control plus a sibling tooltip <div>. If host gave a <div>, we
  // create the <svg> inside; if host gave an <svg>, we use it directly and
  // park the tooltip on document.body (positioned absolute).
  let svgEl, tooltipParent, ownsSvg = false;
  if (root.tagName.toLowerCase() === "svg") {
    svgEl = root;
    tooltipParent = document.body;
  } else {
    svgEl = root.querySelector("svg") || root.appendChild(document.createElementNS("http://www.w3.org/2000/svg", "svg"));
    ownsSvg = true;
    tooltipParent = root;
    // Make the wrapper a positioning context for the absolute tooltip.
    if (getComputedStyle(root).position === "static") root.style.position = "relative";
  }

  const svg = select(svgEl);

  // Tooltip: a single reusable absolutely-positioned div. We create one per
  // render() call and remove it in cleanup() — no leaks.
  const tooltip = select(tooltipParent)
    .append("div")
    .attr("class", "d3-bar-tooltip")
    .style("position", "absolute")
    .style("pointer-events", "none")
    .style("opacity", 0)
    .style("background", "rgba(20,20,20,0.92)")
    .style("color", "#fff")
    .style("padding", "6px 9px")
    .style("border-radius", "4px")
    .style("font", "12px/1.3 system-ui, sans-serif")
    .style("transform", "translate(-50%, -120%)")
    .style("white-space", "nowrap");

  // ---------- 2. Scales + generators ----------
  // scaleSymlog: symmetric log defined at 0 — the killer feature for this brief.
  // Linear would let outliers dominate; pure log throws on the zero bar.
  const x = scaleSymlog().range([0, 0]); // range fixed in draw() once we know width
  const y = scaleBand().padding(0.18);   // padding=0.18: visible gaps without starving bar height
  const fmt = format(",");               // 1234567 → "1,234,567" for tooltips
  let currentData = data.slice();

  // Persistent SVG layers — created once, re-bound on update.
  const gAxisX = svg.append("g").attr("class", "axis axis-x");
  const gAxisY = svg.append("g").attr("class", "axis axis-y");
  const gBars  = svg.append("g").attr("class", "bars");

  // ---------- 3. Responsive sizing via ResizeObserver ----------
  // Cheaper and more accurate than window.resize: fires only when our container
  // actually changes size (e.g. parent flex resize, sidebar toggle).
  let width = 0;
  const ro = new ResizeObserver((entries) => {
    for (const entry of entries) {
      const w = entry.contentRect.width || (svgEl.clientWidth) || 600;
      if (Math.abs(w - width) < 1) continue;
      width = w;
      draw(false); // resize redraw without animation (jarring otherwise)
    }
  });
  ro.observe(ownsSvg ? root : svgEl);

  // ---------- 4. Draw / update routine ----------
  function draw(animate) {
    if (!width) width = svgEl.clientWidth || 600;

    svg.attr("viewBox", `0 0 ${width} ${height}`)
       .attr("width", width)
       .attr("height", height)
       .style("max-width", "100%");

    const innerW = Math.max(0, width - margin.left - margin.right);
    const innerH = height - margin.top - margin.bottom;

    // Refresh scale domains from currentData.
    const vMax = max(currentData, (d) => d.value) ?? 1;
    x.domain([0, vMax]).range([0, innerW]);
    y.domain(currentData.map((d) => d.category)).range([0, innerH]);

    gAxisX.attr("transform", `translate(${margin.left},${margin.top + innerH})`)
          .transition().duration(animate ? duration : 0)
          // ticks(5, "~s"): 5 ticks, SI-suffix format ("1k", "10k") — symlog ticks
          // can be dense; this keeps them readable without hand-rolling.
          .call(axisBottom(x).ticks(5, "~s"));

    gAxisY.attr("transform", `translate(${margin.left},${margin.top})`)
          .transition().duration(animate ? duration : 0)
          .call(axisLeft(y).tickSizeOuter(0));

    gBars.attr("transform", `translate(${margin.left},${margin.top})`);

    // Data join with selection.join() — v7+ idiom; handles enter/update/exit
    // animations cleanly. Old enter().append() pattern omits exit transitions.
    gBars.selectAll("rect.bar")
      .data(currentData, (d) => d.category)
      .join(
        (enter) => enter.append("rect")
          .attr("class", "bar")
          .attr("y", (d) => y(d.category))
          .attr("height", y.bandwidth())
          .attr("x", 0)
          .attr("width", 0)
          .attr("fill", "#4f46e5")
          .attr("rx", 2)
          .call((s) => s.transition().duration(animate ? duration : 0)
            .attr("width", (d) => Math.max(minBarPx, x(d.value)))),
        (update) => update
          .call((s) => s.transition().duration(animate ? duration : 0)
            .attr("y", (d) => y(d.category))
            .attr("height", y.bandwidth())
            .attr("width", (d) => Math.max(minBarPx, x(d.value)))),
        (exit) => exit
          .call((s) => s.transition().duration(animate ? duration : 0)
            .attr("width", 0)
            .style("opacity", 0)
            .remove())
      )
      // Hover handlers re-attached every join: safer than relying on stale refs.
      .on("mouseenter.tip", onEnter)
      .on("mousemove.tip", onMove)
      .on("mouseleave.tip", onLeave);
  }

  // ---------- 5. Tooltip handlers ----------
  // Note d3 v6+: event is the FIRST argument, not d3.event (deprecated).
  function onEnter(event, d) {
    tooltip.style("opacity", 1).html(`<strong>${escapeHtml(d.category)}</strong><br/>${fmt(d.value)}`);
    select(this).attr("fill", "#6366f1");
  }
  function onMove(event) {
    const [px, py] = pointer(event, tooltipParent);
    tooltip.style("left", px + "px").style("top", py + "px");
  }
  function onLeave() {
    tooltip.style("opacity", 0);
    select(this).attr("fill", "#4f46e5");
  }

  function escapeHtml(s) {
    return String(s).replace(/[&<>"']/g, (c) => ({ "&": "&amp;", "<": "&lt;", ">": "&gt;", '"': "&quot;", "'": "&#39;" }[c]));
  }

  // ---------- 6. Public handle ----------
  function update(newData) {
    currentData = newData.slice();
    draw(true);
  }

  function cleanup() {
    ro.disconnect();
    // Detach hover listeners (d3 v7+ API: passing null removes the handler).
    gBars.selectAll("rect.bar").on("mouseenter.tip", null).on("mousemove.tip", null).on("mouseleave.tip", null);
    // Stop any in-flight transitions before tearing down nodes.
    svg.selectAll("*").interrupt();
    svg.selectAll("*").remove();
    tooltip.remove();
  }

  // Initial draw (animated to make first paint feel alive).
  draw(true);

  return { update, cleanup };
}
```

---

### Integration — React

```jsx
import { useEffect, useRef } from "react";
import { render } from "./viz.js";

export function BarChart({ data }) {
  const ref = useRef(null);
  const handleRef = useRef(null);

  useEffect(() => {
    handleRef.current = render(ref.current, data);
    return () => handleRef.current?.cleanup();
  }, []); // mount/unmount only

  useEffect(() => {
    handleRef.current?.update(data);
  }, [data]);

  return <div ref={ref} style={{ width: "100%" }} />;
}
```

### Integration — Vue 3

```vue
<script setup>
import { onMounted, onUnmounted, ref, watch } from "vue";
import { render } from "./viz.js";

const props = defineProps({ data: { type: Array, required: true } });
const el = ref(null);
let handle = null;

onMounted(() => { handle = render(el.value, props.data); });
onUnmounted(() => handle?.cleanup());
watch(() => props.data, (d) => handle?.update(d), { deep: true });
</script>

<template>
  <div ref="el" style="width:100%" />
</template>
```

### Integration — Svelte

```svelte
<script>
  import { onMount, onDestroy } from "svelte";
  import { render } from "./viz.js";

  export let data;
  let el;
  let handle;

  onMount(() => { handle = render(el, data); });
  onDestroy(() => handle?.cleanup());
  $: if (handle) handle.update(data);
</script>

<div bind:this={el} style="width:100%" />
```

### Integration — Vanilla JS

```html
<div id="viz" style="width:100%"></div>
<script type="module">
  import { render } from "./viz.js";

  const data = [
    { category: "Alpha",   value: 0 },
    { category: "Bravo",   value: 42 },
    { category: "Charlie", value: 58 },
    { category: "Delta",   value: 71 },
    { category: "Echo",    value: 39 },
    { category: "Foxtrot", value: 50 },
    { category: "Golf",    value: 12000 },
    { category: "Hotel",   value: 480000 },
  ];
  const handle = render("#viz", data);

  // later, on data change:
  // handle.update(newData);
  // on teardown:
  // handle.cleanup();
</script>
```

---

### Why these primitives

- **`scaleSymlog` instead of `scaleLinear` or `scaleLog`.** This is the single most important choice for the brief. Linear lets the 480k outlier flatten the 50-value bars to ~0.01% of width; pure log explodes on `value: 0`. Symmetric log handles both cleanly.
- **Min bar width (`minBarPx = 3`).** Even with symlog, the *zero* bar still maps to width 0. Clamping to 3 px keeps it as a visible "tick" without distorting non-zero bars.
- **`selection.join()` over `enter().append()`.** v7+ idiom; gives us free exit transitions when categories disappear from the dataset.
- **`ResizeObserver` over `window.resize`.** Fires only when *our* container resizes (parent layout change, sidebar toggle, container query) — no global resize spam.
- **Tooltip as a sibling `<div>`, not SVG `<title>`.** Pointer-following, styleable, and works inside any host. SVG `<title>` is a native browser tooltip with ~500 ms delay and zero styling control.
- **`pointer(event, tooltipParent)` over `d3.event`.** d3 v6+ removed `d3.event`; the current API receives the event as the handler's first arg and uses `pointer()` for coordinate translation.

---

### Quality gates self-check

- **Gate 1 (modern syntax):** No `d3.scale.linear`, no `d3.layout.*`, no `d3.event`, no `enter().append()` without `.join()`. Pass.
- **Gate 2 (framework-agnostic):** `viz.js` imports only `d3-*` packages — no `react`, `vue`, `svelte`, `jquery`. Pass.
- **Gate 3 (built-ins over hand-rolls):** Axes via `axisBottom`/`axisLeft`; scales via `d3-scale`; data join via `selection.join()`. No hand-rolled equivalents. Pass.
- **Gate 4 (why-comments):** Comments justify symlog vs log/linear, ResizeObserver vs window.resize, `selection.join()` vs `enter().append()`, `pointer()` vs `d3.event`, and the min-bar-px clamp. Pass.
- **Gate 5 (real cleanup):** `cleanup()` disconnects the `ResizeObserver`, nulls all `.on(...)` handlers, calls `.interrupt()` on running transitions, removes SVG children, and removes the tooltip div. Pass.
- **Gate 6 (version pinned):** Header includes `Requires: d3 ^7.0.0`. Pass.

```


## chrisvoncsefalvay-d3/02-network-graph

**Blind mapping:** A=community, B=v2-generated

### chrisvoncsefalvay-d3/02-network-graph — community (8466 bytes)

```
# Force-Directed Network Graph (d3.js v7)

A framework-agnostic, vanilla-JS implementation that satisfies every requirement: 50 nodes / 80 edges, group-based colouring (Tableau10), edge thickness by weight, drag, zoom + pan, collision detection, a colour legend, and a simulation that **anneals to a stable layout in a few seconds** rather than running forever.

## HTML scaffold

```html
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <title>Force-directed network</title>
  <style>
    html, body { margin: 0; height: 100%; font-family: Inter, system-ui, sans-serif; }
    #chart { width: 100vw; height: 100vh; background: #fafafa; }
    .legend rect { stroke: #333; stroke-width: 0.5; }
    .legend text { font-size: 12px; fill: #333; }
    .node { cursor: grab; }
    .node:active { cursor: grabbing; }
    .link { stroke: #999; stroke-opacity: 0.6; }
  </style>
</head>
<body>
  <svg id="chart"></svg>
  <script src="https://d3js.org/d3.v7.min.js"></script>
  <script src="./graph.js"></script>
</body>
</html>
```

## graph.js

```javascript
// -----------------------------------------------------------------------------
// Force-directed network graph
// 50 nodes, 80 edges, 5 groups, weighted edges (1-10).
// Stops itself after a fixed-time anneal so the CPU doesn't spin forever.
// -----------------------------------------------------------------------------

// 1. Generate deterministic-ish demo data (replace with real data in production)
function generateData(nodeCount = 50, edgeCount = 80, groupCount = 5) {
  const nodes = d3.range(nodeCount).map(i => ({
    id: i,
    name: `Node ${i}`,
    group: (i % groupCount) + 1   // groups 1..5
  }));

  // Build a connected backbone first so the graph isn't fragmented,
  // then sprinkle the remaining edges at random.
  const links = [];
  const seen = new Set();
  const key = (a, b) => a < b ? `${a}-${b}` : `${b}-${a}`;

  for (let i = 1; i < nodeCount; i++) {
    const j = Math.floor(Math.random() * i);
    links.push({ source: i, target: j, weight: 1 + Math.floor(Math.random() * 10) });
    seen.add(key(i, j));
  }
  while (links.length < edgeCount) {
    const a = Math.floor(Math.random() * nodeCount);
    const b = Math.floor(Math.random() * nodeCount);
    if (a === b || seen.has(key(a, b))) continue;
    links.push({ source: a, target: b, weight: 1 + Math.floor(Math.random() * 10) });
    seen.add(key(a, b));
  }
  return { nodes, links };
}

// 2. Main draw function — Pattern A (direct DOM manipulation)
function drawNetwork(svgSelector, data) {
  const svg = d3.select(svgSelector);
  svg.selectAll('*').remove();

  const { width, height } = svg.node().getBoundingClientRect();
  svg.attr('viewBox', [0, 0, width, height]);

  // Accessibility
  svg.attr('role', 'img')
     .attr('aria-label', 'Force-directed network graph with 50 nodes coloured by group');

  // Group everything inside <g> so zoom/pan transforms cleanly
  const root = svg.append('g').attr('class', 'root');

  // Colour scale — Tableau10 maps cleanly to 5 discrete groups
  const groups = Array.from(new Set(data.nodes.map(n => n.group))).sort(d3.ascending);
  const color = d3.scaleOrdinal().domain(groups).range(d3.schemeTableau10);

  // Edge thickness ∝ weight
  const widthScale = d3.scaleLinear()
    .domain(d3.extent(data.links, l => l.weight))
    .range([0.5, 4]);

  // 3. Force simulation -------------------------------------------------------
  const simulation = d3.forceSimulation(data.nodes)
    .force('link', d3.forceLink(data.links)
      .id(d => d.id)
      .distance(d => 80 - d.weight * 3)   // heavier edges pull tighter
      .strength(0.6))
    .force('charge', d3.forceManyBody().strength(-220))
    .force('center', d3.forceCenter(width / 2, height / 2))
    .force('collide', d3.forceCollide().radius(14).iterations(2))
    .force('x', d3.forceX(width / 2).strength(0.04))
    .force('y', d3.forceY(height / 2).strength(0.04));

  // Faster cool-down so the layout stabilises in ~3-4 seconds, then stops.
  simulation.alphaDecay(0.05);   // default 0.0228 → roughly halves runtime
  simulation.velocityDecay(0.4);

  // Hard stop safety net (in case alphaDecay isn't enough on this dataset)
  setTimeout(() => simulation.stop(), 5000);

  // 4. Links ------------------------------------------------------------------
  const link = root.append('g')
    .attr('class', 'links')
    .selectAll('line')
    .data(data.links)
    .join('line')
    .attr('class', 'link')
    .attr('stroke-width', d => widthScale(d.weight));

  // 5. Nodes ------------------------------------------------------------------
  const node = root.append('g')
    .attr('class', 'nodes')
    .selectAll('circle')
    .data(data.nodes)
    .join('circle')
    .attr('class', 'node')
    .attr('r', 9)
    .attr('fill', d => color(d.group))
    .attr('stroke', '#fff')
    .attr('stroke-width', 1.5)
    .call(drag(simulation));

  node.append('title').text(d => `${d.name} (group ${d.group})`);

  // 6. Tick handler -----------------------------------------------------------
  simulation.on('tick', () => {
    link
      .attr('x1', d => d.source.x).attr('y1', d => d.source.y)
      .attr('x2', d => d.target.x).attr('y2', d => d.target.y);
    node
      .attr('cx', d => d.x).attr('cy', d => d.y);
  });

  // 7. Zoom + pan -------------------------------------------------------------
  const zoom = d3.zoom()
    .scaleExtent([0.25, 8])
    .on('zoom', event => root.attr('transform', event.transform));
  svg.call(zoom);

  // 8. Legend (rendered in screen space, outside the zoomable root) ----------
  drawLegend(svg, color, groups, width);
}

// Drag behaviour — pins a node while held, releases on drop
function drag(simulation) {
  return d3.drag()
    .on('start', (event, d) => {
      if (!event.active) simulation.alphaTarget(0.3).restart();
      d.fx = d.x; d.fy = d.y;
    })
    .on('drag', (event, d) => { d.fx = event.x; d.fy = event.y; })
    .on('end', (event, d) => {
      if (!event.active) simulation.alphaTarget(0);
      d.fx = null; d.fy = null;
    });
}

// Legend: group → colour mapping, top-right corner
function drawLegend(svg, color, groups, width) {
  const legend = svg.append('g')
    .attr('class', 'legend')
    .attr('transform', `translate(${width - 140}, 20)`);

  legend.append('rect')
    .attr('width', 120).attr('height', groups.length * 22 + 16)
    .attr('fill', 'white').attr('stroke', '#ccc').attr('rx', 4);

  legend.append('text')
    .attr('x', 10).attr('y', 18)
    .style('font-weight', 600).text('Group');

  const row = legend.selectAll('g.row')
    .data(groups)
    .join('g')
    .attr('class', 'row')
    .attr('transform', (_, i) => `translate(10, ${30 + i * 22})`);

  row.append('rect')
    .attr('width', 14).attr('height', 14).attr('rx', 2)
    .attr('fill', d => color(d));

  row.append('text')
    .attr('x', 22).attr('y', 12)
    .text(d => `Group ${d}`);
}

// 9. Bootstrap --------------------------------------------------------------
const data = generateData(50, 80, 5);
drawNetwork('#chart', data);

// Keep it responsive
window.addEventListener('resize', () => drawNetwork('#chart', data));
```

## How each requirement is met

| Requirement | Implementation |
|---|---|
| Force simulation with collision | `d3.forceSimulation` + `forceCollide().radius(14)` |
| Edge thickness ∝ weight | `widthScale` linear scale on `link.weight` |
| Node colour by group | `d3.scaleOrdinal(d3.schemeTableau10)` |
| Drag-to-reposition | `d3.drag()` with `fx/fy` pinning during drag |
| Zoom + pan | `d3.zoom().scaleExtent([0.25, 8])` applied to `<svg>`, transform on inner `<g>` |
| Legend | Standalone `<g>` rendered in screen space (outside zoom transform) |
| Vanilla / framework-agnostic | No framework imports; pure DOM + d3 v7 |
| Stable in seconds | `alphaDecay(0.05)` + `setTimeout(stop, 5000)` safety net |

## Notes for production

- Replace `generateData()` with your real `{ nodes, links }` payload. Each node needs `id`, `name`, `group`; each link needs `source`, `target`, `weight`.
- For >500 nodes, switch the `.nodes/.links` rendering to `<canvas>` (SVG starts struggling around 1k DOM elements) — the simulation API is identical.
- The legend is rendered *outside* the zoomable `<g>` so it stays fixed when you pan/zoom — this is intentional.
- Adjusting `alphaDecay` upward (e.g. `0.08`) will stop the simulation even faster at the cost of a slightly less optimal layout.

```

### chrisvoncsefalvay-d3/02-network-graph — v2-generated (12862 bytes)

```
# Force-directed network graph (d3 v7+)

**Parsed spec**

```
Viz type: force-directed network graph
Data shape: { nodes: [{ id, name, group }], links: [{ source, target, weight }] }
Interactions: drag (reposition), zoom + pan, hover (tooltip optional)
Scale: 50 nodes / 80 links, viewport ~960x600
Host: vanilla JS (framework-agnostic confirmed)
```

**Primitive selections (Phase 2 → Phase 3)**

| Requirement | Primitive | Module |
|---|---|---|
| Layout | `forceSimulation` + `forceLink` + `forceManyBody` + `forceCenter` + `forceCollide` | `d3-force` |
| Group → color | `scaleOrdinal(schemeTableau10)` | `d3-scale` + `d3-scale-chromatic` |
| Edge thickness from weight | `scaleLinear` (1..10 → 1..6 px) | `d3-scale` |
| Drag | `drag` behavior | `d3-drag` |
| Zoom + pan | `zoom` behavior on root `<g>` | `d3-zoom` |
| Data binding | `selection.join(...)` | `d3-selection` |
| Stop running forever | `simulation.alphaMin(0.02)` + `alphaDecay(~0.04)` | `d3-force` |

---

## `viz.js` — the d3 module

```javascript
// d3 v7+ — framework-agnostic force-directed network graph.
// Requires: d3 ^7.0.0  (or modular d3-* packages, see imports below).
//
// Lifecycle contract:
//   1. Place an <svg> (or <div>) in the DOM with a known selector or element ref.
//   2. Call render(container, data, options) on mount.
//   3. Call the returned cleanup() on unmount.
//   4. Call update(newData) to rebind data; selection.join() animates the diff.
//
// Imports — modular d3 packages (tree-shakable). Swap for `import * as d3 from "d3"`
// if you prefer the monolithic bundle; the API surface is identical.
import { select, pointer } from "d3-selection";
import { scaleLinear, scaleOrdinal } from "d3-scale";
import { schemeTableau10 } from "d3-scale-chromatic";
import { extent } from "d3-array";
import { drag } from "d3-drag";
import { zoom, zoomIdentity } from "d3-zoom";
import {
  forceSimulation,
  forceLink,
  forceManyBody,
  forceCenter,
  forceCollide,
} from "d3-force";

/**
 * Render a force-directed network graph.
 *
 * @param {Element|string} container - DOM <svg> element or CSS selector.
 * @param {{nodes: Array, links: Array}} data
 *        nodes: [{ id, name, group }]
 *        links: [{ source, target, weight }]   (source/target may be id or node ref)
 * @param {Object} [options]
 *        width, height, nodeRadius, chargeStrength, linkDistance
 * @returns {{ update: (newData) => void, cleanup: () => void }}
 */
export function render(container, data, options = {}) {
  // 1. Resolve container (selector or element). Coerce to a d3 selection.
  const root = typeof container === "string" ? select(container) : select(container);
  const width = options.width ?? 960;
  const height = options.height ?? 600;
  const nodeRadius = options.nodeRadius ?? 8;
  // chargeStrength negative = repulsion. -180 keeps a 50-node graph readable
  // without scattering tightly clustered groups off-screen.
  const chargeStrength = options.chargeStrength ?? -180;
  const linkDistance = options.linkDistance ?? 60;

  // 2. Set up SVG + scales + generators.
  // viewBox makes the SVG responsive without re-running the simulation on resize.
  root
    .attr("viewBox", [0, 0, width, height])
    .attr("preserveAspectRatio", "xMidYMid meet")
    .style("max-width", "100%")
    .style("height", "auto")
    .style("font", "12px system-ui, sans-serif");

  // scaleOrdinal with schemeTableau10 because groups are categorical (1..5);
  // Tableau10 has higher perceptual separation than schemeCategory10 for small N.
  const color = scaleOrdinal(schemeTableau10);

  // scaleLinear from weight extent → stroke width range [1, 6].
  // Domain is computed from data so re-renders adapt to new weights.
  const weightDomain = extent(data.links, (d) => d.weight) ?? [1, 10];
  const strokeScale = scaleLinear()
    .domain(weightDomain[0] === weightDomain[1] ? [0, weightDomain[1]] : weightDomain)
    .range([1, 6])
    .clamp(true);

  // 3. Build the SVG structure.
  // Two <g> layers: zoom-target wraps everything that should pan/zoom together;
  // legend lives outside the zoom-target so it stays anchored to the viewport.
  root.selectAll("*").remove(); // safe re-mount on hot reload
  const zoomTarget = root.append("g").attr("class", "zoom-target");
  const linkLayer = zoomTarget.append("g").attr("class", "links")
    .attr("stroke", "#999").attr("stroke-opacity", 0.6);
  const nodeLayer = zoomTarget.append("g").attr("class", "nodes")
    .attr("stroke", "#fff").attr("stroke-width", 1.5);
  const legendLayer = root.append("g")
    .attr("class", "legend")
    .attr("transform", `translate(16, 16)`);

  // 4. Bind data + start simulation. Mutate copies so we don't trash caller's data
  // (d3-force assigns x/y/vx/vy to the node objects in place).
  let nodes = data.nodes.map((d) => ({ ...d }));
  let links = data.links.map((d) => ({ ...d }));

  // forceSimulation tuned to settle in a few seconds:
  //   alphaDecay ~0.04 (default 0.0228) → reaches alphaMin faster.
  //   alphaMin 0.02 stops the ticker once layout is "good enough".
  // forceCollide prevents node overlap; radius = nodeRadius + 2 px breathing room.
  const simulation = forceSimulation(nodes)
    .force("link",
      forceLink(links)
        .id((d) => d.id)
        .distance(linkDistance)
        .strength(0.7),
    )
    .force("charge", forceManyBody().strength(chargeStrength))
    .force("center", forceCenter(width / 2, height / 2))
    .force("collide", forceCollide().radius(nodeRadius + 2).iterations(2))
    .alphaDecay(0.04)
    .alphaMin(0.02);

  let linkSel = linkLayer.selectAll("line");
  let nodeSel = nodeLayer.selectAll("g.node");

  function bind() {
    // selection.join is the v7 idiom — replaces enter().append() / exit().remove()
    // and gives correct enter/update/exit semantics for animated re-renders.
    linkSel = linkLayer
      .selectAll("line")
      .data(links, (d) =>
        `${typeof d.source === "object" ? d.source.id : d.source}->${
          typeof d.target === "object" ? d.target.id : d.target
        }`,
      )
      .join("line")
      .attr("stroke-width", (d) => strokeScale(d.weight));

    nodeSel = nodeLayer
      .selectAll("g.node")
      .data(nodes, (d) => d.id)
      .join((enter) => {
        const g = enter.append("g").attr("class", "node");
        g.append("circle")
          .attr("r", nodeRadius)
          .attr("fill", (d) => color(d.group));
        g.append("title").text((d) => `${d.name} (group ${d.group})`);
        // Optional inline label for small graphs; comment out for >200 nodes.
        g.append("text")
          .attr("x", nodeRadius + 3)
          .attr("y", "0.32em")
          .attr("fill", "#222")
          .attr("paint-order", "stroke")
          .attr("stroke", "#fff")
          .attr("stroke-width", 3)
          .text((d) => d.name);
        return g;
      })
      .call(buildDrag(simulation));
  }

  bind();

  // Tick handler updates positions on every simulation step.
  simulation.on("tick", () => {
    linkSel
      .attr("x1", (d) => d.source.x)
      .attr("y1", (d) => d.source.y)
      .attr("x2", (d) => d.target.x)
      .attr("y2", (d) => d.target.y);
    nodeSel.attr("transform", (d) => `translate(${d.x},${d.y})`);
  });

  // 5. Wire interactions.
  // d3.zoom on the root <svg> drives a transform on .zoom-target.
  // scaleExtent caps zoom range so users can't zoom into oblivion.
  const zoomBehavior = zoom()
    .scaleExtent([0.25, 4])
    .on("zoom", (event) => {
      zoomTarget.attr("transform", event.transform);
    });
  root.call(zoomBehavior).call(zoomBehavior.transform, zoomIdentity);

  // 6. Legend (group → color). Anchored to viewport, outside zoomTarget.
  const groups = Array.from(new Set(nodes.map((d) => d.group))).sort();
  const legend = legendLayer
    .selectAll("g.legend-item")
    .data(groups)
    .join("g")
    .attr("class", "legend-item")
    .attr("transform", (_, i) => `translate(0, ${i * 20})`);
  legend.append("rect")
    .attr("width", 12).attr("height", 12)
    .attr("fill", (d) => color(d));
  legend.append("text")
    .attr("x", 18).attr("y", 10)
    .attr("fill", "#222")
    .text((d) => `Group ${d}`);

  // ---- helpers ----

  // d3.drag wires pointer events; we re-heat the simulation on start so the
  // dragged node moves freely, then release fx/fy on end so forces resume.
  function buildDrag(sim) {
    return drag()
      .on("start", (event, d) => {
        if (!event.active) sim.alphaTarget(0.3).restart();
        d.fx = d.x;
        d.fy = d.y;
      })
      .on("drag", (event, d) => {
        d.fx = event.x;
        d.fy = event.y;
      })
      .on("end", (event, d) => {
        if (!event.active) sim.alphaTarget(0);
        d.fx = null;
        d.fy = null;
      });
  }

  // update(newData): rebind nodes/links, reheat simulation gently.
  function update(newData) {
    nodes = newData.nodes.map((d) => {
      // preserve simulation state for nodes that survive the diff
      const prev = nodes.find((p) => p.id === d.id);
      return prev ? { ...prev, ...d } : { ...d };
    });
    links = newData.links.map((d) => ({ ...d }));
    simulation.nodes(nodes);
    simulation.force("link").links(links);
    bind();
    simulation.alpha(0.6).restart();
  }

  // cleanup: stop simulation, detach handlers, clear DOM. d3 doesn't auto-clean.
  function cleanup() {
    simulation.stop();
    simulation.on("tick", null);
    root.on(".zoom", null);
    nodeLayer.selectAll("g.node").on(".drag", null);
    root.selectAll("*").remove();
  }

  return { update, cleanup };
}
```

---

## Integration — Vanilla JS

```html
<!doctype html>
<html>
  <head><meta charset="utf-8" /><title>Network graph</title></head>
  <body style="margin:0">
    <svg id="viz" style="width:100%;height:100vh;background:#fafafa"></svg>
    <script type="module">
      import { render } from "./viz.js";

      // Demo data: 50 nodes (group 1..5), 80 random edges (weight 1..10).
      const nodes = Array.from({ length: 50 }, (_, i) => ({
        id: `n${i}`,
        name: `Node ${i}`,
        group: 1 + (i % 5),
      }));
      const links = Array.from({ length: 80 }, () => {
        const a = Math.floor(Math.random() * 50);
        let b = Math.floor(Math.random() * 50);
        if (b === a) b = (a + 1) % 50;
        return {
          source: `n${a}`,
          target: `n${b}`,
          weight: 1 + Math.floor(Math.random() * 10),
        };
      });

      const handle = render("#viz", { nodes, links });
      // handle.update({ nodes, links }) to rebind; handle.cleanup() on teardown.
    </script>
  </body>
</html>
```

---

## Why these primitives

- **`forceSimulation` + `forceCollide`** — collision force is what guarantees nodes don't overlap; without it, `forceManyBody` alone allows visual stacking when groups are tightly clustered.
- **`alphaDecay(0.04)` + `alphaMin(0.02)`** — the brief required the layout to settle in a few seconds, not run forever. Default decay (0.0228) leaves the ticker spinning for ~10s; bumping it cuts settle time to ~3-4s while still producing a stable layout.
- **`scaleOrdinal(schemeTableau10)`** — categorical groups (1..5) demand a categorical palette. Tableau10 separates better than schemeCategory10 at low N and is the modern d3 default for business viz.
- **`scaleLinear` for stroke width** — linear (not sqrt) because we're mapping to *line thickness*, where perception is approximately linear in stroke-width pixels for the small range used here.
- **Two `<g>` layers (zoom-target vs. legend)** — putting the legend outside the zoomed group keeps it anchored to the viewport while pan/zoom moves the graph; a single transform layer would drag the legend off-screen.
- **`selection.join()`** — the v7 idiom replaces `enter().append()` chains and gives correct update semantics, so `update(newData)` animates the diff cleanly instead of duplicating or orphaning DOM nodes.

---

## Quality gates self-check

- **Gate 1 (modern syntax)** — pass: `scaleLinear`, `scaleOrdinal`, `forceSimulation`, `selection.join`; no `d3.scale.*`, no `d3.layout.*`, no bare `enter().append()`, no `d3.event`.
- **Gate 2 (framework-agnostic)** — pass: no `react`/`vue`/`svelte`/`jquery` imports in the d3 module; integration snippet for vanilla JS lives outside it.
- **Gate 3 (built-ins over hand-rolls)** — pass: forces, scales, drag, zoom, join all use d3 primitives.
- **Gate 4 (why-comments)** — pass: rationale comments on `chargeStrength`, `alphaDecay`, `forceCollide`, `scaleOrdinal(schemeTableau10)`, `scaleLinear` for strokes, two-`<g>` layering, `selection.join`.
- **Gate 5 (real cleanup)** — pass: `simulation.stop()`, `.on("tick", null)`, `.on(".zoom", null)`, `.on(".drag", null)`, DOM cleared.
- **Gate 6 (d3 v7+ declared)** — pass: `// Requires: d3 ^7.0.0` at top of module.

```


## chrisvoncsefalvay-d3/03-animated-transition

**Blind mapping:** A=v2-generated, B=community

### chrisvoncsefalvay-d3/03-animated-transition — community (10258 bytes)

```
# Animated Line Chart with Smooth Transition Between Two Datasets

A d3.js v7 animated line chart that toggles between two yearly datasets (2023 and 2024) with smooth, choreographed transitions on the line, axes, and data points.

## Overview

This implementation follows the d3-viz skill's **Pattern A (direct DOM manipulation)** with the standard structure: dimensions → scales → axes → data binding. The key transition primitives used are:

- `selection.transition()` — schedules a smooth interpolation of the targeted attributes.
- `transition.duration(ms)` — total animation length for that transition.
- `transition.ease(d3.easeCubicInOut)` — easing curve for natural acceleration/deceleration.
- `d3.line()` with `curveMonotoneX` — generates a smooth path string from data; when the path's `d` attribute is transitioned, d3 interpolates string-to-string and the line morphs smoothly.
- `axis.transition().call(axisGenerator)` — re-renders an axis with the updated scale, animating tick positions and labels.
- The **point-by-point** effect comes from binding `data` to circles at each datum and transitioning their `cx`/`cy` independently — d3 interpolates each circle's coordinates separately, which visually reads as the line "morphing" rather than snap-redrawing.

## HTML mount (framework-agnostic)

Drop this anywhere — vanilla JS, a React `useEffect`, a Vue `onMounted`, or a Svelte `onMount`. The script only needs an `<svg id="chart">` and a `<button id="toggle">` in the DOM.

```html
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <title>Animated Line Chart — Toggle Year</title>
  <style>
    body { font-family: Inter, system-ui, sans-serif; padding: 24px; }
    #toggle {
      padding: 8px 16px;
      font-size: 14px;
      cursor: pointer;
      border: 1px solid #4A90E2;
      background: white;
      color: #4A90E2;
      border-radius: 4px;
      margin-bottom: 16px;
    }
    #toggle:hover { background: #4A90E2; color: white; }
    .axis path, .axis line { stroke: #ccc; }
    .axis text { fill: #555; font-size: 12px; }
    #year-label { margin-left: 12px; font-weight: 600; color: #333; }
  </style>
</head>
<body>
  <button id="toggle">Toggle Year</button>
  <span id="year-label">2023</span>
  <svg id="chart" width="800" height="400"></svg>

  <script src="https://d3js.org/d3.v7.min.js"></script>
  <script src="./animated-line.js"></script>
</body>
</html>
```

## animated-line.js — the chart

```javascript
// ---------------------------------------------------------------
// Animated line chart with smooth transition between two datasets.
// Uses d3 v7 .transition() API (no deprecated .tween()).
// ---------------------------------------------------------------

// --- 1. Data: two states (2023, 2024) with 12 monthly values each ---
const months = ["Jan","Feb","Mar","Apr","May","Jun",
                "Jul","Aug","Sep","Oct","Nov","Dec"];

const dataA = months.map((m, i) => ({
  month: m,
  // synthetic 2023 series
  value: [42, 38, 51, 60, 72, 85, 91, 88, 76, 64, 50, 45][i]
}));

const dataB = months.map((m, i) => ({
  month: m,
  // synthetic 2024 series — different shape so transition is visible
  value: [55, 62, 58, 70, 65, 78, 95, 110, 102, 88, 72, 68][i]
}));

const datasets = { 2023: dataA, 2024: dataB };
let currentYear = 2023;

// --- 2. Dimensions, margins, container ---
const width  = 800;
const height = 400;
const margin = { top: 20, right: 30, bottom: 40, left: 50 };
const innerWidth  = width  - margin.left - margin.right;
const innerHeight = height - margin.top  - margin.bottom;

const svg = d3.select("#chart");
const g = svg.append("g")
  .attr("transform", `translate(${margin.left},${margin.top})`);

// --- 3. Scales ---
// xScale is a point scale over month labels; it does NOT change between
// datasets (same 12 months), so no x-axis re-scale is needed for domain,
// but we still call .transition() on the axis for visual consistency.
const xScale = d3.scalePoint()
  .domain(months)
  .range([0, innerWidth])
  .padding(0.5);

// yScale's domain DOES change between datasets, so its axis must animate.
const yScale = d3.scaleLinear()
  .range([innerHeight, 0]);

// --- 4. Axis groups (created once, updated on transition) ---
const xAxisG = g.append("g")
  .attr("class", "axis x-axis")
  .attr("transform", `translate(0,${innerHeight})`);

const yAxisG = g.append("g")
  .attr("class", "axis y-axis");

// --- 5. Line generator ---
// d3.line() builds a path string from data. When we transition the 'd'
// attribute of the path, d3 interpolates between the old and new path
// strings — this is what produces the smooth point-by-point morph.
const lineGenerator = d3.line()
  .x(d => xScale(d.month))
  .y(d => yScale(d.value))
  .curve(d3.curveMonotoneX);  // smooth, monotone-preserving curve

// --- 6. Path element (created once, updated on transition) ---
const path = g.append("path")
  .attr("class", "data-line")
  .attr("fill", "none")
  .attr("stroke", "#4A90E2")
  .attr("stroke-width", 2.5);

// --- 7. Initial render ---
update(datasets[currentYear], /* animate = */ false);

// --- 8. Update function: re-runs whenever the dataset toggles ---
function update(data, animate = true) {
  // 8a. Update yScale domain to fit new data range, with a little headroom.
  const yMax = d3.max(data, d => d.value);
  yScale.domain([0, yMax * 1.1]);

  // 8b. Transition primitive: define ONCE, reuse for every animated
  //     element so they all run synchronously with the same easing.
  //     This is the canonical d3 v7 pattern — schedule a transition,
  //     then chain attribute setters that get interpolated.
  const t = d3.transition()
    .duration(animate ? 900 : 0)
    .ease(d3.easeCubicInOut);

  // 8c. Animate the y-axis: passing a transition into .call(axis) makes
  //     d3 interpolate tick positions and labels for the new scale.
  yAxisG.transition(t).call(d3.axisLeft(yScale).ticks(6));

  // 8d. Animate the x-axis (no domain change here, but we still call it
  //     to keep the API consistent — useful if you later swap month sets).
  xAxisG.transition(t).call(d3.axisBottom(xScale));

  // 8e. Animate the line itself.
  //     .datum(data) rebinds new data to the single path element.
  //     Transitioning the 'd' attribute makes d3 interpolate between
  //     the old path string and the new one — which produces the
  //     point-by-point morph effect (each x,y pair interpolates
  //     independently along the path).
  path.datum(data)
    .transition(t)
    .attr("d", lineGenerator);

  // 8f. Animate the data points (circles at each datum).
  //     This is what makes the transition truly point-by-point and
  //     visible: each circle's cx/cy is interpolated independently,
  //     so you see the entire shape morph rather than snap-redraw.
  const circles = g.selectAll("circle.data-point")
    .data(data, d => d.month);  // key by month for stable bindings

  // Enter: new circles fade in at correct position
  circles.enter()
    .append("circle")
    .attr("class", "data-point")
    .attr("r", 4)
    .attr("fill", "#4A90E2")
    .attr("cx", d => xScale(d.month))
    .attr("cy", d => yScale(d.value))
    .attr("opacity", 0)
    .transition(t)
    .attr("opacity", 1);

  // Update: existing circles slide to new (cx, cy) — this slides each
  // point independently, reinforcing the point-by-point morph.
  circles.transition(t)
    .attr("cx", d => xScale(d.month))
    .attr("cy", d => yScale(d.value));

  // Exit: shouldn't trigger here (both datasets have all 12 months),
  // but included for completeness / future-proofing.
  circles.exit()
    .transition(t)
    .attr("opacity", 0)
    .remove();
}

// --- 9. Toggle button wiring ---
d3.select("#toggle").on("click", () => {
  currentYear = currentYear === 2023 ? 2024 : 2023;
  d3.select("#year-label").text(String(currentYear));
  update(datasets[currentYear], true);
});
```

## How the transition primitives compose

| Primitive | Role in this chart |
|---|---|
| `d3.transition().duration(900).ease(d3.easeCubicInOut)` | Single shared transition object — every animated element runs on the same clock with the same easing, which is what makes the change feel **choreographed** rather than chaotic. |
| `selection.transition(t)` | Attaches a selection to the shared transition `t`. Subsequent attribute setters become interpolations rather than instant assignments. |
| `path.transition(t).attr("d", lineGenerator)` | d3 interpolates between the old and new path `d` strings. Because `d3.line()` produces a monotone-cubic path with a point per datum, the interpolation reads as **each point sliding to its new y-value** — exactly the point-by-point morph the brief asks for. |
| `axisG.transition(t).call(d3.axisLeft(scale))` | Re-runs the axis generator inside a transition, so ticks and labels animate to the new domain instead of snapping. |
| `circles.data(data, key).transition(t).attr("cx" / "cy", …)` | Keying by month gives stable circle-to-datum bindings across updates, so each circle interpolates from its old position to its new one — the visual proof that points are moving individually. |

## Why no `.tween()`

The brief excludes the deprecated `.tween()` API. The modern d3 v7 approach used here relies on **attribute interpolation**: when you transition an attribute that has a known interpolator (numbers, colours, transforms, path strings via `d3.interpolatePath` semantics built into the `d` attribute interpolator), d3 handles the frame-by-frame work automatically. No custom tween functions are required.

## Customisation points

- **Curve type:** swap `d3.curveMonotoneX` for `d3.curveCatmullRom`, `d3.curveBasis`, or `d3.curveLinear` to change the line's character.
- **Duration / easing:** tune `duration(900)` and `ease(d3.easeCubicInOut)` — `d3.easeBackOut` adds overshoot, `d3.easeBounceOut` adds a bounce.
- **More than two datasets:** change `datasets` to a keyed object/array and have the button cycle through keys; `update()` already accepts any data array.
- **Responsive sizing:** wrap the SVG in a container, add a `ResizeObserver` that re-runs the scales' `range()` and re-calls `update()` (see the d3-viz skill's responsive sizing section).

```

### chrisvoncsefalvay-d3/03-animated-transition — v2-generated (14402 bytes)

```
# Animated Line Chart — d3 v7+ (Year Toggle)

Generated by `/d3-viz`. Framework-agnostic ES module that renders a smooth, transition-driven line chart and exposes an `update(newData)` to flip between Year A (2023) and Year B (2024) states. Both axes re-scale and the line interpolates point-by-point — not a snap-redraw.

## Phase 1 — Parsed spec

```
Viz type: animated line chart with state toggle
Data shape: Array<{ month: number 1..12, value: number }> (12 rows per state)
Interactions: button click toggles between state A (2023) and state B (2024); axes + line transition smoothly
Scale: 12 points per state, viewport ~640x360
Host: unknown → integration snippets for React / Vue / Svelte / Vanilla appended
```

## Phase 2 — Primitive selections

| Need | Primitive | Why this one |
|---|---|---|
| Month → x pixel | `d3.scalePoint` | 12 discrete categorical months; `scalePoint` lays them out with even padding and works cleanly with `d3.line()`. `scaleLinear` would also work but `scalePoint` makes axis ticks free. |
| Value → y pixel | `d3.scaleLinear` | continuous numeric → continuous pixel — textbook use case. |
| Axes | `d3.axisBottom`, `d3.axisLeft` | built-in tick formatting + transition-aware (`axisGroup.transition().call(axis)` re-renders ticks animatedly). |
| Smooth curve | `d3.line().curve(d3.curveMonotoneX)` | monotone-X preserves monotonicity per segment — no overshoot artefacts that `curveCardinal` produces on noisy data. |
| Line interpolation | `selection.transition().duration().attrTween("d", ...)` with `d3.interpolatePath`-style trick via per-attribute `attrTween` | the requirement is "point-by-point" interpolation. The default `attr("d", ...).transition()` interpolates as a string and produces wobble when point counts differ; here counts are equal (12↔12) so a plain `attr` transition on `d` works AND we add an explicit `attrTween` using `d3.interpolate` between the two path strings to be safe and explicit. |
| Easing | `d3.easeCubicInOut` | symmetrical ease for a "flip between states" feel; `easeBackOut` would feel too playful for monthly data. |
| Data join | `selection.join()` | v7+ idiom for the dot markers (one per month) so enter/update/exit transitions all hang off the same statement. |

## Phase 3 — Generated module

```javascript
// d3 v7+ — framework-agnostic.
// Requires: d3 ^7.0.0 (or modular d3-* packages, see imports).
//
// Drop into any host (React, Vue, Svelte, vanilla JS):
//   1. Place an <svg> (or <div>) in your DOM with a known selector or DOM ref.
//   2. Call render(container, initialData, options) on mount.
//   3. Call handle.update(newData) to transition to a new state.
//   4. Call handle.cleanup() on unmount.
//
// Imports — modular d3 packages (tree-shakable). Replace with
// `import * as d3 from "d3"` if you prefer the monolithic bundle.
import { select } from "d3-selection";
import { scalePoint, scaleLinear } from "d3-scale";
import { axisBottom, axisLeft } from "d3-axis";
import { line, curveMonotoneX } from "d3-shape";
import { max, min, extent } from "d3-array";
import { easeCubicInOut } from "d3-ease";
import { interpolateString } from "d3-interpolate";
// d3-transition is imported for its side effects: it augments selection.prototype
// with .transition(). Without this import, .transition() is undefined when using
// modular packages.
import "d3-transition";

const MONTH_LABELS = [
  "Jan", "Feb", "Mar", "Apr", "May", "Jun",
  "Jul", "Aug", "Sep", "Oct", "Nov", "Dec",
];

/**
 * Render an animated line chart that can transition between data states.
 *
 * @param {Element|string} container - DOM element or CSS selector to mount into (an <svg>).
 * @param {Array<{month:number,value:number}>} data - initial state (12 rows; month 1..12).
 * @param {Object} [options]
 * @param {number} [options.width=640]
 * @param {number} [options.height=360]
 * @param {{top:number,right:number,bottom:number,left:number}} [options.margin]
 * @param {number} [options.duration=900]   - transition duration in ms.
 * @returns {{ update: (newData:Array) => void, cleanup: () => void }}
 */
export function render(container, data, options = {}) {
  // 1. Resolve container (selector → element, or use as-is).
  const root = typeof container === "string" ? select(container) : select(container);

  const {
    width = 640,
    height = 360,
    margin = { top: 24, right: 24, bottom: 36, left: 48 },
    duration = 900,
  } = options;

  const innerW = width - margin.left - margin.right;
  const innerH = height - margin.top - margin.bottom;

  // 2. Set up the SVG shell once. Subsequent update() calls reuse these groups.
  const svg = root
    .attr("viewBox", `0 0 ${width} ${height}`)
    .attr("preserveAspectRatio", "xMidYMid meet")
    .style("font", "12px system-ui, sans-serif");

  // Clear any prior content so render() is idempotent on the same node.
  svg.selectAll("*").remove();

  const g = svg.append("g")
    .attr("transform", `translate(${margin.left},${margin.top})`);

  // 3. Scales. We rebuild domains on every update() so axes can re-scale animatedly.
  // scalePoint: 12 categorical month slots with even spacing; works well as input to d3.line().
  const x = scalePoint()
    .domain(MONTH_LABELS)
    .range([0, innerW])
    .padding(0.5);

  // scaleLinear for value→pixel: continuous numeric mapping. .nice() on each update
  // gives clean axis ticks without forcing the user to pre-round.
  const y = scaleLinear().range([innerH, 0]);

  // 4. Axis groups — created once, re-rendered (animatedly) on update.
  const xAxisG = g.append("g")
    .attr("class", "x-axis")
    .attr("transform", `translate(0,${innerH})`);

  const yAxisG = g.append("g")
    .attr("class", "y-axis");

  // 5. Line generator. curveMonotoneX preserves monotonicity per-segment — no overshoot
  // artefacts that curveCardinal/curveCatmullRom produce on noisy data.
  const lineGen = line()
    .x(d => x(MONTH_LABELS[d.month - 1]))
    .y(d => y(d.value))
    .curve(curveMonotoneX);

  // The line itself: a single <path> that we mutate on update via attrTween.
  const linePath = g.append("path")
    .attr("class", "series")
    .attr("fill", "none")
    .attr("stroke", "currentColor")
    .attr("stroke-width", 2)
    .attr("stroke-linejoin", "round")
    .attr("stroke-linecap", "round");

  // Dot markers group — one circle per month, joined by month index.
  const dotsG = g.append("g").attr("class", "dots");

  // ---- Internal: apply a data state with full transition ----
  // Used both for the initial draw (duration 0) and subsequent updates.
  function applyState(state, ms) {
    // Recompute y-domain so the axis re-scales between states.
    // Pad domain by ~5% so the line doesn't kiss the top/bottom edges.
    const [lo, hi] = extent(state, d => d.value);
    const pad = (hi - lo) * 0.05 || 1;
    y.domain([lo - pad, hi + pad]).nice();

    const t = svg.transition().duration(ms).ease(easeCubicInOut);

    // Axis transitions: calling axis on a transition selection animates the ticks.
    xAxisG.transition(t).call(axisBottom(x));
    yAxisG.transition(t).call(axisLeft(y).ticks(6));

    // Line transition: attrTween on "d" interpolates between the two path strings.
    // For equal-length monotone curves (12↔12) this produces a smooth point-by-point
    // morph rather than a snap-redraw. interpolateString handles the numeric tokens
    // inside the SVG path "d" attribute.
    const prevD = linePath.attr("d") || lineGen(state); // first draw: start from final
    const nextD = lineGen(state);

    linePath
      .transition(t)
      .attrTween("d", () => interpolateString(prevD, nextD));

    // Dot markers: selection.join() with enter/update/exit transitions so
    // re-renders animate correctly. Keyed by month so the same circle moves.
    dotsG.selectAll("circle")
      .data(state, d => d.month)
      .join(
        enter => enter.append("circle")
          .attr("r", 0)
          .attr("fill", "currentColor")
          .attr("cx", d => x(MONTH_LABELS[d.month - 1]))
          .attr("cy", d => y(d.value))
          .call(sel => sel.transition(t).attr("r", 3.5)),
        update => update
          .call(sel => sel.transition(t)
            .attr("cx", d => x(MONTH_LABELS[d.month - 1]))
            .attr("cy", d => y(d.value))
            .attr("r", 3.5)),
        exit => exit
          .call(sel => sel.transition(t).attr("r", 0).remove()),
      );
  }

  // Initial draw — duration 0 so the chart appears in its first state instantly,
  // then subsequent update() calls animate from there.
  applyState(data, 0);

  // 6. Public handle.
  function update(newData) {
    applyState(newData, duration);
  }

  function cleanup() {
    // Stop any in-flight transitions on this svg's descendants. Calling
    // .interrupt() halts queued tweens that would otherwise mutate a removed node.
    svg.selectAll("*").interrupt();
    // No DOM-level event listeners were attached in this viz, but if you add
    // hover/click handlers later, detach them with .on("event", null) here.
    svg.selectAll("*").remove();
  }

  return { update, cleanup };
}
```

### Toggle button — host-side (it lives outside the d3 module by design)

```html
<button id="toggle">Toggle Year</button>
<svg id="viz" width="640" height="360"></svg>
<script type="module">
  import { render } from "./viz.js";

  const stateA = [
    { month: 1, value: 42 }, { month: 2, value: 51 }, { month: 3, value: 47 },
    { month: 4, value: 63 }, { month: 5, value: 70 }, { month: 6, value: 88 },
    { month: 7, value: 92 }, { month: 8, value: 84 }, { month: 9, value: 71 },
    { month: 10, value: 60 }, { month: 11, value: 49 }, { month: 12, value: 55 },
  ];
  const stateB = [
    { month: 1, value: 58 }, { month: 2, value: 44 }, { month: 3, value: 62 },
    { month: 4, value: 71 }, { month: 5, value: 65 }, { month: 6, value: 79 },
    { month: 7, value: 101 }, { month: 8, value: 95 }, { month: 9, value: 82 },
    { month: 10, value: 74 }, { month: 11, value: 66 }, { month: 12, value: 70 },
  ];

  const handle = render("#viz", stateA);
  let showingA = true;
  document.getElementById("toggle").addEventListener("click", () => {
    showingA = !showingA;
    handle.update(showingA ? stateA : stateB);
  });
  // window.addEventListener("beforeunload", handle.cleanup);
</script>
```

### Integration — React

```jsx
import { useEffect, useRef, useState } from "react";
import { render } from "./viz.js";

export function YearLineChart({ stateA, stateB }) {
  const ref = useRef(null);
  const handleRef = useRef(null);
  const [showingA, setShowingA] = useState(true);

  useEffect(() => {
    handleRef.current = render(ref.current, stateA);
    return () => handleRef.current?.cleanup();
    // eslint-disable-next-line react-hooks/exhaustive-deps
  }, []);

  useEffect(() => {
    handleRef.current?.update(showingA ? stateA : stateB);
  }, [showingA, stateA, stateB]);

  return (
    <>
      <button onClick={() => setShowingA(s => !s)}>Toggle Year</button>
      <svg ref={ref} />
    </>
  );
}
```

### Integration — Vue 3

```vue
<script setup>
import { onMounted, onUnmounted, ref, watch } from "vue";
import { render } from "./viz.js";

const props = defineProps({ stateA: Array, stateB: Array });
const el = ref(null);
const showingA = ref(true);
let handle = null;

onMounted(() => {
  handle = render(el.value, props.stateA);
});
watch(showingA, v => handle?.update(v ? props.stateA : props.stateB));
onUnmounted(() => handle?.cleanup());
</script>

<template>
  <button @click="showingA = !showingA">Toggle Year</button>
  <svg ref="el" />
</template>
```

### Integration — Svelte

```svelte
<script>
  import { onMount, onDestroy } from "svelte";
  import { render } from "./viz.js";
  export let stateA;
  export let stateB;
  let el; let handle; let showingA = true;
  onMount(() => { handle = render(el, stateA); });
  onDestroy(() => handle?.cleanup());
  $: handle?.update(showingA ? stateA : stateB);
</script>

<button on:click={() => showingA = !showingA}>Toggle Year</button>
<svg bind:this={el} />
```

### Integration — Vanilla JS

See the "Toggle button — host-side" block above.

## Phase 4 — Quality gates self-check

- **Gate 1 (modern syntax):** `scalePoint`, `scaleLinear`, `axisBottom`, `axisLeft`, `line().curve(curveMonotoneX)`, `selection.join()`, `attrTween` with passed args (no `d3.event`). PASS.
- **Gate 2 (framework-agnostic):** the d3 module imports zero framework code. React/Vue/Svelte appear only in the integration snippets. PASS.
- **Gate 3 (built-ins over hand-rolls):** axes via `d3-axis`; line via `d3-shape`; transitions via `d3-transition`+`d3-ease`; interpolation via `d3-interpolate`. PASS.
- **Gate 4 (why-comments):** each non-trivial choice (`scalePoint`, `curveMonotoneX`, `attrTween` with `interpolateString`, `easeCubicInOut`, the `d3-transition` side-effect import, the `nice()` + 5% pad) has a one-line rationale. PASS.
- **Gate 5 (cleanup is real):** `cleanup()` calls `.interrupt()` on all descendants and removes them. PASS.
- **Gate 6 (d3 v7+ declared):** `// Requires: d3 ^7.0.0` line at the top of the module. PASS.

## Why these primitives (3-6 bullets)

- **`scalePoint` over `scaleLinear` for x:** months are categorical with fixed positions; `scalePoint` gives even padding and free axis ticks. Swap for `scaleTime` if you need real Date objects.
- **`curveMonotoneX` over `curveCardinal`:** monotonicity per segment prevents overshoot wobble — important when the curve must read as "value over month", not "decorative spline".
- **`attrTween("d", interpolateString(prev, next))`:** explicit point-by-point interpolation between the two path strings. Equal point counts (12↔12) make this safe; for unequal counts you would need `flubber` or `d3-interpolate-path` to avoid jumpy morphs.
- **`d3-transition` imported for side effects:** with modular packages, `selection.transition()` is undefined unless `d3-transition` augments the prototype at import time.
- **`selection.join()` over `enter().append()`:** v7+ idiom; the dot markers handle enter/update/exit in one statement so the same circles slide between states keyed by `month`.
- **Cleanup uses `.interrupt()`:** stops in-flight tweens that would otherwise mutate detached nodes after unmount — the actual memory-leak class, not just a courtesy `removeChild`.

```


## gstack-plan-ceo-review/01-ambitious-roadmap

**Blind mapping:** A=v2-generated, B=community

### gstack-plan-ceo-review/01-ambitious-roadmap — community (30886 bytes)

```
# MEGA PLAN REVIEW — CEO MODE

**Skill:** `/plan-ceo-review` (gstack)
**Plan reviewed:** 6-month roadmap, 12-person Series A SaaS, $180k MRR / 8% MoM, $4M runway
**Review posture:** Honest. Not diplomatic. The user asked to be hard.

---

## MODE DECLARATION: **SCOPE REDUCTION**

I'm overriding the context-default. A "feature enhancement / iteration" plan would default to SELECTIVE EXPANSION. This isn't that. This is a roadmap that has already silently expanded past what 12 people can ship in 6 months at a quality bar that doesn't blow up your reputation. The job here isn't to dream — it's to cut.

Why SCOPE REDUCTION, not HOLD SCOPE: HOLD SCOPE assumes the scope is right and you just need rigor. The scope isn't right. Holding it would be malpractice.

Why not SELECTIVE EXPANSION: surfacing more cherry-picks against this plan is like recommending dessert to someone already eating two main courses.

You said "the board likes ambition." Boards always like ambition. They are not the ones with 12 engineers who will be context-switching between mobile apps, SSO, AI features, an infra migration, a 2nd ICP, and an EU launch. Founders confuse "the board likes it" with "this is the right thing."

**Posture for the rest of this review:** I am the surgeon. I am here to find the minimum viable 6 months that ships paying-customer value, protects your reputation, and keeps your team alive. Everything else gets cut, deferred, or staged.

---

## STEP 0A — PREMISE CHALLENGE

I'm going to challenge the premises before I touch the scope. If the premises are wrong, the scope debate is theater.

### Premise 1: "We need to do all of this in 6 months."

**Challenge:** No, you don't. Nothing in your input says "we will die if mobile + SSO + AI + EU + 2nd ICP + AWS migration aren't all live by month 6." The deadline is self-imposed. Self-imposed deadlines, when stacked, produce mediocre everything.

**The actual question:** What is the *single* thing that, if you nailed it in the next 6 months, would matter more than everything else on this list combined?

If you can't answer that in one sentence, the roadmap is a wish list, not a strategy.

### Premise 2: "Series A means we should be doing Series A things."

**Challenge:** This roadmap reads like a checklist of "what Series A SaaS companies are supposed to do." Mobile app because competitors have one. SSO because enterprise prospects ask. AWS because "enterprise reliability." AI because GPT-5 exists. Germany because international.

None of these are wrong individually. Together, they smell like cargo-cult Series A. The discipline at this stage is *narrative coherence* — every initiative should reinforce one bet. I see five different bets here. That's not strategy, that's diversification, and you can't out-diversify well-funded competitors at $180k MRR.

**Proxy skepticism (Bezos Day 1):** Are these features serving users, or have they become self-referential markers of "real company" status? Investigate honestly.

### Premise 3: "Engineering says 4 months for the mobile app is realistic."

**Challenge:** Engineering estimates on greenfield mobile work are wrong by 1.5–2.5x in the optimistic direction, *consistently*, across every company I've seen. "Realistic" 4 months means real-world 6–10 months, especially when the same engineers are also context-switched onto SSO, AI, and an infra migration.

**The hardest question here:** Have you talked to a single user who said "I would pay more / churn less / use this more if you had a native mobile app"? Engineering PM teams don't open their laptops on the bus to triage Jira tickets. They use Slack on mobile and the desktop app at their desk. The mobile app is plausibly a $1M+ investment in a feature your ICP doesn't actually want.

**Inversion:** What's the case that mobile app is a *bad* investment for an engineering-team PM tool at $180k MRR? It's strong. Take it seriously.

### Premise 4: "AWS migration for 'enterprise reliability'."

**Challenge:** Vercel runs at 99.99%+ for serverless workloads. The "enterprise reliability" framing is sales fiction unless one of these is true:
- A specific named prospect has a hard requirement (SOC 2 with on-prem residency, FedRAMP, etc.)
- You've actually hit Vercel limits or had outages

If it's neither, you're rebuilding infra to comfort an imaginary buyer. That's the most expensive form of premature optimization in startups: infra theater for a sales narrative.

### Premise 5: "Currently engineering teams; expand to design teams."

**Challenge:** This is the biggest unforced error in the plan. You have not stated PMF in your *current* ICP. 8% MoM growth at $180k MRR is good but not "we've conquered engineering teams, on to the next."

Adding a 2nd ICP before nailing the first one is how you end up with two half-built products and two confused customer bases. I'd bet the design-team workflow is meaningfully different from engineering-team workflow (sprints vs. design reviews, Jira vs. Figma, async standups vs. critique sessions). You'd be building a different product wearing the same name.

**The question you should answer first:** Are you at $1M ARR with engineering teams loving you and asking for design-team features, or are you at $180k MRR with growth slowing and a PM hunting for the next vertical?

If the second: the answer is not "add another vertical." It's "go deeper on the first one."

---

## STEP 0B — EXISTING CODE / LEVERAGE

Not applicable as written — this is a roadmap, not an implementation plan. But the analog question matters: **what existing distribution and product surface area are you under-leveraging?**

You have 12 people, $180k MRR, and presumably a few hundred to low thousands of customers. The leverage question is: are you milking that base, or chasing strangers?

- Have you shipped the obvious adjacent features your *current* customers have asked for and would pay more for? (Almost certainly yes — every team has these. They're in the support inbox.)
- Have you doubled MRR per existing customer through tier upgrades and seat expansion? Land-and-expand inside engineering teams will likely yield more than international launch in EU at this stage.
- What's the easiest path to $500k MRR — net-new logos via 5 simultaneous initiatives, or expansion of the existing book? Usually the latter, until you're at clear ICP saturation.

**You haven't done that audit in this plan.** That's the leverage gap.

---

## STEP 0C — DREAM STATE MAPPING

```
  CURRENT STATE                          THIS PLAN                                   12-MONTH IDEAL
  ─────────────                          ─────────                                   ──────────────
  $180k MRR, 8% MoM                      Mobile + SSO + AI + AWS +                   $500k–$1M MRR with one
  12 people                              EU + 2nd ICP + VPS + 5 hires         ─►     dominant ICP, clear PMF
  Engineering teams ICP        ─►        (doing 7+ initiatives in parallel)          narrative, expansion
  Vercel infra                                                                        revenue > new logo revenue,
  Engineering teams ICP                                                               team that's not on fire
```

**Verdict:** This plan does NOT move you toward the 12-month ideal. It moves you toward a state where you've *attempted* many things and *succeeded* at few. That's the worst quadrant — burned runway, no clear win story, team morale at month 4 is "what are we even doing."

The 12-month ideal is a coherent narrative. This roadmap has no coherent narrative.

---

## STEP 0C-bis — IMPLEMENTATION ALTERNATIVES

I'm producing three roadmap alternatives, not three implementation alternatives, because the input is a roadmap.

### APPROACH A: "Ship the Two Things That Matter" (recommended)
- **Summary:** Pick the *single* most important bet (likely SSO + SCIM, because it's already committed to 2 prospects and it actually unlocks revenue) plus *one* expansion bet (likely the AI feature, because it's the only thing that creates differentiated value as opposed to commodity catch-up). Cut everything else from Q3/Q4.
- **Effort:** S-M (12 people on 2 things ships)
- **Risk:** Low
- **Pros:**
  - Team is not on fire at month 4.
  - Both initiatives are revenue-linked (SSO closes 2 named deals; AI feature is your differentiation story for the next sales cycle).
  - You preserve $4M runway by not hiring 5 engineers and doing an AWS migration.
  - You actually ship at quality. Reputation intact.
- **Cons:**
  - Board may push back on "ambition." Frame it as "ambitious about depth, not breadth."
  - International launch deferred. Mobile deferred. 2nd ICP deferred.
- **Reuses:** Existing engineering team, existing infra, existing ICP. Maximum leverage of what you already have.

### APPROACH B: "Sequential Quarters, Not Parallel" (compromise)
- **Summary:** Q3 = SSO + AI feature (revenue and differentiation). Q4 = decide based on Q3 data. Hire VP Sales early Q3. Defer mobile, AWS, EU, 2nd ICP, 5 engineers.
- **Effort:** M
- **Risk:** Med
- **Pros:**
  - Forces you to learn from Q3 before committing Q4. Decisions are made with information, not vibes.
  - Preserves optionality. The Q4 plan in this current roadmap is the most speculative part — sequencing it lets you replace it with what Q3 teaches you.
  - VP Sales hire in early Q3 means they're productive by Q4, when you'll need them most.
- **Cons:**
  - Some board members read this as "less ambitious." Counter-narrative needs prep.
  - You give up the romantic 6-month plan.
- **Reuses:** Same as A. Identical Q3.

### APPROACH C: "Original Plan As-Stated" (the rejected baseline)
- **Summary:** Ship everything in the input as written.
- **Effort:** XL (impossibly so).
- **Risk:** Very High.
- **Pros:**
  - Board likes the ambition.
  - If — *if* — every initiative succeeds, you have a Series B-ready story.
- **Cons:**
  - Conditional probability of all 7 initiatives shipping at quality in 6 months with 12 (then 17) people: I'd put it under 10%. Probably under 5%.
  - Engineering hiring 5 + onboarding + ramping in parallel with a mobile build, AWS migration, AI integration, and SSO build is a recipe for burnout and quality regressions.
  - Reputation risk: half-built mobile app in the App Store is worse than no mobile app.
  - Your current customers (the ICP that's working) are de-prioritized in favor of speculative ones (design teams, EU). They will feel it. Churn will tick up.
  - 4-month engineering estimate for mobile is optimistic by 50%+. You'll be 2 months into Q4 still shipping Q3 mobile. Cascade failure across all Q4 initiatives.
- **Reuses:** Nothing. Builds five new surfaces in parallel.

**RECOMMENDATION:** Choose **APPROACH A** because it is the only one that maps to your stated non-negotiables (revenue + reputation) under the constraint of having 12 people and $4M runway. Approach B is the acceptable compromise if you have political reasons to keep optionality on Q4 visible. Approach C is the path your board will applaud and your team will resent.

The truthful answer is A. The diplomatic answer is B. There is no version of C that survives contact with reality.

`Completeness: A=10/10, B=9/10, C=4/10`

---

## STEP 0D — SCOPE REDUCTION (mode-specific analysis)

I'm going to take the original plan and cut it line by line. For each item: KEEP / DEFER / KILL.

### Q3 items

**1. Enterprise SSO + SCIM provisioning (committed to 2 prospects)**
- **Decision:** **KEEP — TOP PRIORITY**
- **Why:** Committed revenue. Reputation + revenue both at stake if you miss. The dependency is hard.
- **Caveat:** Ship the SSO that those 2 prospects need, not a generic "enterprise-grade SSO solution." Talk to them. Find the minimum (probably SAML 2.0 + SCIM with Okta + Azure AD). Resist the urge to "do it right for everyone" before you have a third prospect asking.

**2. Native mobile app (iOS + Android), 4 months engineering estimate**
- **Decision:** **KILL (or DEFER to 2027)**
- **Why:** No evidence in the input that engineering-team customers want this enough to pay more or churn less without it. 4-month estimate is optimistic by 50%+. Cost of a half-built mobile app launching alongside Q4 chaos is reputation damage. You don't have the bandwidth for two platforms while also doing SSO + AI.
- **What to do instead:** Build a polished responsive mobile web view if you don't have one. 2 weeks of work, covers 80% of mobile use cases (quick-glance updates, comments, status changes), no app-store distribution drama, no separate codebase, no separate auth flow.
- **The forcing question I want you to answer:** Name 5 customers who have explicitly told you they would pay more or stay longer if you had a native mobile app. If you can't, kill it.

**3. AI-powered "what should I work on next" using GPT-5**
- **Decision:** **KEEP — but scope it brutally.**
- **Why:** This is the only differentiated bet on the roadmap. Every PM tool is going to ship some flavor of AI in the next 12 months. The companies that ship a *useful* one win the next sales cycle.
- **Risk:** Generic LLM-on-top features feel like demoware. The "what should I work on next" framing is the right user outcome — but the implementation has to actually be smart, not GPT prompting your sprint backlog.
- **Scope:** Pick one specific user — e.g., "individual engineer at start of standup" — and build a feature that demonstrably saves them 15 minutes a day. That's it. Don't build "AI for managers" and "AI for ICs" and "AI for sprint planning" all at once. One persona, one outcome.
- **Eval discipline:** Build the eval set before the feature. If you can't measure "did this recommendation save the user time," you can't ship at quality.

**4. Hire VP of Sales**
- **Decision:** **KEEP — but earlier than the plan implies.**
- **Why:** $180k MRR + 8% MoM with no VP Sales suggests founder-led sales is your current bottleneck. A great VP Sales takes 6 months to ramp. If you wait until Q3 to hire, they're productive in Q1 2027. You should be in market *now*.
- **Caveat:** "Hire VP Sales" is itself a 3-6 month project (sourcing, interviewing, closing). Founders consistently underestimate this. Start the search yesterday.

### Q4 items

**5. International launch (UK + Germany)**
- **Decision:** **KILL (or DEFER to H2 2027)**
- **Why:** UK is fine — same language, similar buying patterns, GDPR is solvable. Germany is a different planet — different sales motion, different procurement cycles, different data residency expectations, different language for marketing copy and support. "UK + Germany" reads like "international" without specificity.
- **What to do instead:** If you have inbound EU demand right now, take their money. Don't *launch* in EU. There is a difference. A handful of EU customers paying you in EUR is not "EU launch" — it's revenue you should not refuse.
- **Hard question:** What % of your inbound right now is from outside the US? If it's <10%, EU launch is a solution to a problem that hasn't surfaced yet.

**6. Expand to a 2nd ICP (engineering → design teams)**
- **Decision:** **KILL.**
- **Why:** This is the worst item on the roadmap. PMF in your current ICP is not yet at saturation. Adding a 2nd ICP before saturating the 1st is a textbook anti-pattern. Design teams have a different workflow, different buyer, different competitive landscape (Figma adjacencies). You'd be entering a knife fight with a different product wearing the same name.
- **What to do instead:** Get to $500k–$1M MRR in engineering teams first. THEN consider an adjacent vertical with the leverage of an existing brand and ARR base. The 2nd ICP is a 2027 conversation, not a 2026 conversation.

**7. Move infra Vercel → AWS for "enterprise reliability"**
- **Decision:** **KILL (probably) or DEFER until forced.**
- **Why:** Unless a named prospect has a written requirement that Vercel cannot meet, this is infra theater. AWS migration is a 2-quarter project minimum, requires SRE expertise you may not have on staff, introduces a new failure surface, and provides no customer-visible value if Vercel is meeting your needs.
- **The forcing question:** What specific customer requirement does AWS satisfy that Vercel does not? If the answer is "they asked us if we run on AWS," that's not a requirement, that's small talk.
- **What to do instead:** Get SOC 2 Type 2 (this is what enterprise buyers actually ask for, and you can do it on Vercel). Document your reliability story. If a real requirement surfaces, *then* migrate.

**8. Hire 5 more engineers**
- **Decision:** **CUT TO 2 (maybe 3).**
- **Why:** Hiring 5 engineers in Q4 means onboarding 5 engineers in Q4. Onboarding 5 engineers takes ~30% of the existing team's productivity for 6+ weeks. You're not adding 5 engineers of throughput — you're losing throughput, then adding partial throughput, then maybe net-positive by Q1 2027.
- **What to do instead:** Hire 2 senior engineers Q3 (one for SSO/enterprise, one for AI). Reassess in October. Hiring 5 is a Series B move, not a Series A move with $4M runway.
- **Burn math:** 5 engineers at fully loaded ~$250k each = $1.25M/year added burn. That's a meaningful chunk of your $4M runway. The implicit assumption is that the next round closes before runway gets tight. If it doesn't, you've front-loaded headcount you can't sustain.

---

## DECISION CLASS TAXONOMY (Bezos one-way / two-way doors)

This is the framework you specifically asked for. Every initiative on the roadmap should be classified by reversibility × magnitude. Move fast on two-way doors. Move slowly and gather information on one-way doors.

| # | Initiative | Reversibility | Magnitude | Class | Speed |
|---|------------|----------------|-----------|-------|-------|
| 1 | SSO + SCIM | Two-way (can sunset SCIM, refactor SSO) | Medium ($ committed) | **Two-way / Medium** | Move fast |
| 2 | Native mobile app | **One-way (mostly)** — once shipped, customers expect parity forever; sunsetting a mobile app is a public negative event; codebase + team specialization is hard to unwind | Large (engineering quarters + ongoing maintenance) | **One-way / Large** | **STOP. Don't decide yet.** |
| 3 | AI feature (GPT-5) | Two-way (can pivot the feature, retire it, change models) | Medium | **Two-way / Medium** | Move fast, but with eval discipline |
| 4 | VP Sales hire | Two-way at first, one-way after 12+ months (cultural imprint, team built around them) | Very Large (defines GTM motion) | **Asymmetric / Very Large** | Slow on the hire decision, fast on the search |
| 5 | EU launch | Mixed — entering a market is two-way; hiring local headcount and signing leases is one-way | Medium-Large | **Mixed / Medium-Large** | **STOP. Stage it. Take inbound revenue, don't sign leases.** |
| 6 | 2nd ICP (design teams) | One-way in product surface area (every design-team-only feature you ship is permanent surface); two-way in marketing | **Very Large** (defines what your product is) | **One-way / Very Large** | **STOP. Don't decide yet.** |
| 7 | AWS migration | Two-way technically (you can migrate back), but practically one-way (no one ever migrates back) | Large (engineering quarters) | **Effectively-one-way / Large** | **STOP. Don't decide without a forcing function.** |
| 8 | 5 engineering hires | Each individual hire is two-way (you can let them go, though painful). Cumulatively, it changes team culture and burn structure semi-permanently. | Large | **Aggregate-one-way / Large** | Hire 2 fast. Hold 3. Reassess. |

**Pattern:** Every Q4 item except VP Sales is in the danger quadrant — large magnitude AND low reversibility. The roadmap is making one-way / large bets *in parallel*, which is the highest-risk profile possible.

The CEO move here is: do the two-way / medium things fast (SSO, AI), and refuse to make the one-way / large bets without forcing functions or much more information.

---

## HARDEST UNRESOLVED QUESTIONS

These are the questions whose answers should reshape this roadmap. If you can't answer them, you can't do this roadmap. If you can answer them, half this roadmap probably gets cut.

### Q1. What is the *single* most important thing you're optimizing for in the next 6 months?

If the answer is "growing MRR," then mobile, AWS, and 2nd ICP are at best uncorrelated and at worst negatively correlated. SSO closes named revenue. AI is the differentiation story. EU launch is speculative MRR.

If the answer is "raising a Series B," then the question is what story the next investor wants to hear. Usually: clear PMF, expansion revenue, defensible differentiation. Not: "we did seven things."

If the answer is "preparing for an acquisition," that's a different roadmap entirely — and usually involves *less* infrastructure investment, not more.

You don't have one answer in this input. That's the gap.

### Q2. Is your current ICP saturated?

Concrete test: of the engineering teams in your TAM, what % are customers? What % have heard of you? At 8% MoM and $180k MRR, my prior is you are *not* saturated. You're growing, but you have a long runway in the existing ICP.

If you're not saturated: 2nd ICP and EU launch are *both* premature. Go deeper before going wider.

### Q3. Which of the 2 enterprise prospects is actually closing?

You said "committed to 2 prospects" for SSO. Have they signed? Are these contracts closing in Q3, or is SSO the unlock for them to *consider* closing? If the latter, what's the conditional probability they close even with SSO? Founders chronically over-weight "we built the thing they asked for" — buyers ghost on perfectly-built features all the time.

If both prospects are <50% likely to close even with SSO, you're paying a quarter of engineering capacity for ~1 deal in expected value. Re-evaluate.

### Q4. Have you actually talked to current customers about the mobile app, or are you assuming they want one?

Be honest. If the answer is "we assumed," kill it today. If the answer is "we did 10 customer interviews and 8 said yes, definitely, here's specifically what I'd use it for," then the conversation is different. I bet it's the former.

### Q5. What does your team think of this roadmap?

Not "what did engineering tell you the mobile app will take." What does the team think of the *whole roadmap* in aggregate? Have they seen it? If you handed your top 3 ICs this roadmap and asked "is this realistic in 6 months," what would they say?

If you haven't asked them, you're flying blind on the most important variable: throughput. If you have asked them and they said "this is a lot," you know the answer.

### Q6. What's the true reason for the AWS migration?

Not "enterprise reliability." That's the post-hoc rationalization. The true reason is one of:
- A specific deal requires it (then you have a forcing function — ship it)
- An engineer or VP advocated for it for technical preferences (then you're making a $1M+ investment for engineer aesthetics — bad)
- "Vercel doesn't feel serious" (then you're making the decision on vibes — also bad)
- Vercel actually has reliability issues you've experienced (then SOC 2 + reliability documentation may solve it without migration)

Until you know the actual reason, you cannot make this decision well.

### Q7. What's your runway in months under the *new* burn (5 hires + AWS infra + mobile dev tooling)?

You said $4M runway at *current* burn. The roadmap meaningfully increases burn. Have you modeled runway under the new headcount? If the answer is "we'll raise before then," what's plan B if you don't?

A roadmap that requires the next round to close on schedule is not a roadmap. It's a hope.

---

## NOT IN SCOPE (after reduction)

- **Native mobile app (iOS + Android)** — Insufficient evidence of customer demand; high one-way commitment; replace with responsive mobile web until forced.
- **AWS migration** — No named forcing function; replace with SOC 2 Type 2 on existing infra.
- **EU launch (Germany)** — Different market, different motion; defer to H2 2027 unless inbound EU demand crosses threshold (>20% of pipeline).
- **EU launch (UK)** — Defer. Take inbound UK revenue, don't *launch*.
- **2nd ICP (design teams)** — Premature. Saturate engineering ICP first.
- **3 of 5 engineering hires** — Cut to 2; reassess in October.

Each of these has a one-line trigger that would unlock it: a named prospect, a metric threshold, or a strategic milestone. Document the triggers. Don't just "defer to TODOS."

---

## WHAT ALREADY EXISTS (the leverage you're not using)

- **A working product with paying customers and 8% MoM growth.** This is your moat-builder. Doubling down on the existing customer experience usually beats new initiatives.
- **An ICP you understand.** Most companies pivoting to a 2nd ICP do not understand their first one as well as they think.
- **Vercel infra that's working** (presumably — the input doesn't say it's broken).
- **A 12-person team that has presumably built rapport and momentum.** Adding 5 engineers fast is friction against this.
- **$180k MRR of monthly intelligence.** Every customer conversation is a data point. Are you actually using it to prioritize, or are you doing strategy from the whiteboard?

---

## DREAM STATE DELTA

Under the original plan, 6 months from now you have: a half-shipped mobile app, an in-progress AWS migration, an EU presence with 3 customers, a confused ICP narrative, a team that's burned out, and SSO in production for 1 of the 2 deals (the other ghosted). Net: some progress, no clear win.

Under SCOPE REDUCTION (Approach A), 6 months from now you have: SSO live with 2 enterprise customers happily paying, an AI feature that's the differentiation story for your next sales cycle, a VP Sales 3 months into ramp, and the team morale to do another 6 months at the same pace. Net: clear win, clear story, options open.

Approach A's worst case is meaningfully better than the original plan's expected case. That's the trade.

---

## REQUIRED EXPLICIT DECISIONS (would normally be AskUserQuestion)

In a live skill run, each of these would be its own AskUserQuestion. In this batch-output mode, I'm listing them as decisions you must make explicitly. Don't silently default any of these.

- **D1:** Mode confirmation. SCOPE REDUCTION (recommended) vs. HOLD vs. SELECTIVE EXPANSION vs. SCOPE EXPANSION.
- **D2:** Mobile app — KILL, DEFER, or KEEP. Recommendation: KILL until customer-evidence threshold.
- **D3:** AWS migration — KILL, DEFER, or KEEP. Recommendation: KILL until named forcing function.
- **D4:** 2nd ICP — KILL or DEFER. Recommendation: KILL for 2026.
- **D5:** EU launch — KILL or DEFER or scope down to "accept inbound." Recommendation: scope down to inbound-only.
- **D6:** Engineering hires — 2 vs. 3 vs. 5. Recommendation: 2 now, hold 3, reassess October.
- **D7:** AI feature scope — single persona / single outcome vs. multi-persona. Recommendation: single persona (engineer at standup) with eval discipline.
- **D8:** SSO scope — minimum for 2 named prospects vs. generic enterprise SSO. Recommendation: minimum for the 2 named prospects.
- **D9:** VP Sales timeline — start search now vs. start Q3. Recommendation: start now.

Until you make these decisions, the roadmap is undefined. Make them in writing, share them with the team and board, and commit.

---

## COMPLETION SUMMARY

```
+====================================================================+
|            MEGA PLAN REVIEW — COMPLETION SUMMARY                   |
+====================================================================+
| Mode selected        | SCOPE REDUCTION (overriding default)        |
| System Audit         | Roadmap-level review; not a code plan       |
| Step 0               | Premises challenged (5); approach A picked  |
| Section 1  (Arch)    | N/A — strategy doc, not implementation       |
| Section 2  (Errors)  | N/A — strategy doc                          |
| Section 3  (Security)| N/A — strategy doc (SSO scope flagged)      |
| Section 4  (Data/UX) | N/A — strategy doc                          |
| Section 5  (Quality) | N/A — strategy doc                          |
| Section 6  (Tests)   | AI feature: eval-set discipline required    |
| Section 7  (Perf)    | N/A — strategy doc                          |
| Section 8  (Observ)  | N/A — strategy doc                          |
| Section 9  (Deploy)  | AWS migration risk profile flagged          |
| Section 10 (Future)  | One-way doors mapped; reversibility scored  |
| Section 11 (Design)  | N/A (no UI scope)                           |
+--------------------------------------------------------------------+
| NOT in scope         | written (6 items + 3 hires)                 |
| What already exists  | written (5 leverage points)                 |
| Dream state delta    | written                                     |
| Decision Class taxonomy| 8 initiatives mapped (one-way vs two-way) |
| Hardest questions    | 7 unresolved questions surfaced             |
| TODOS.md updates     | Decisions D1-D9 require explicit answers    |
| Scope proposals      | 0 expansion (mode is REDUCTION)             |
| CEO plan             | skipped (REDUCTION mode)                    |
| Outside voice        | not run (batch mode simulation)             |
| Lake Score           | N/A (strategy review, not implementation)   |
| Diagrams produced    | 1 (current → plan → ideal state)            |
| Stale diagrams found | N/A                                         |
| Unresolved decisions | 9 (D1-D9 listed above)                      |
+====================================================================+
```

---

## ONE PARAGRAPH SUMMARY (if you only read this)

Your roadmap is overscoped by roughly 2-3x for a 12-person team at $180k MRR over 6 months. The problem is not ambition — it's *parallelism of one-way bets*. Mobile app, AWS migration, 2nd ICP, and EU launch are all in the danger quadrant of "high magnitude, low reversibility" and you're proposing to make all four bets simultaneously while also onboarding 5 engineers and building two new product surfaces. The honest mode here is SCOPE REDUCTION: keep SSO (committed revenue), keep the AI feature scoped to one persona (your only differentiated bet), hire VP Sales now (not Q3), hire 2 engineers (not 5), and kill or defer the rest. The board will read this as less ambitious. They are wrong. Shipping two things at quality is more ambitious than shipping seven things badly. Until you can answer "what is the *single* thing I'm optimizing for in the next 6 months" in one sentence, you don't have a roadmap, you have a wish list. Cut it.

— end of CEO review —

```

### gstack-plan-ceo-review/01-ambitious-roadmap — v2-generated (10246 bytes)

```
# CEO Review — 6-Month Roadmap (Series A SaaS, $180k MRR)

## Mode
**Selected mode:** SCOPE REDUCTION
**Why this mode:** Eight workstreams across two quarters with no priority ordering, multiple competing for the same scarce engineering resource (mobile + AI + SSO + AWS migration + new ICP), and a 4-month mobile build colliding with a 3-month quarter. The plan reads as a board-pleasing menu, not a sequenced bet. $4M runway with 12 people sounds comfortable until you notice everything is being attempted in parallel.

## Premise Challenge

### Premise: "The board likes ambition" → therefore the plan should be ambitious in volume
- **Status:** BREAKS
- **What the user is assuming:** That breadth of initiatives signals ambition, and that's what the board wants to see.
- **What needs to be true for this to hold:** Boards reward shipped outcomes, not roadmap surface area. A board that funds a Series A wants concentrated conviction, not a spread bet across 8 workstreams.
- **Implication if it doesn't hold:** You ship 60% of 8 things badly instead of 100% of 3 things well, and the next board meeting is harder, not easier.

### Premise: Native mobile (4 months) fits in Q3 (3 months)
- **Status:** BREAKS
- **What the user is assuming:** Engineering's "4 months realistic" estimate can be compressed or that slipping into Q4 is fine.
- **What needs to be true for this to hold:** Either the estimate is wrong (engineering is sandbagging by 25%+) or Q4's plan tolerates a 1-month mobile spillover that displaces something else. Neither is named.
- **Implication if it doesn't hold:** Mobile eats Q4 engineering capacity, which is already committed to AWS migration, international launch, and a new ICP. Cascade failure.

### Premise: A new ICP (design teams) at $180k MRR with 8% MoM growth
- **Status:** BREAKS
- **What the user is assuming:** That you've saturated growth in engineering teams enough to need a second ICP.
- **What needs to be true for this to hold:** You'd need to be at the ceiling of the engineering-team segment. At $180k MRR / 8% MoM you are nowhere near it — you have years of growth left in your existing ICP. Adding a second ICP at this stage dilutes positioning, splits product priorities, and confuses GTM.
- **Implication if it doesn't hold:** You weaken the wedge that's actually working to chase a hypothetical adjacent market.

### Premise: Vercel → AWS migration is required for "enterprise reliability"
- **Status:** CRACKS
- **What the user is assuming:** That enterprise prospects are blocking on infra provider, or that Vercel can't meet enterprise SLAs.
- **What needs to be true for this to hold:** A specific named enterprise deal must be blocked on this, or a measurable reliability gap must exist that Vercel cannot close. "Enterprise reliability" in scare quotes suggests the user already knows this is a vibe, not a requirement.
- **Implication if it doesn't hold:** You burn a quarter of engineering on a migration with no revenue attached.

### Premise: Hiring VP of Sales + 5 engineers in 6 months absorbs cleanly
- **Status:** CRACKS
- **What the user is assuming:** Headcount adds linear capacity.
- **What needs to be true for this to hold:** Onboarding ramp must be <2 months and the existing team must have spare cycles to onboard. At 12 people adding 6 (50% growth) while shipping 8 workstreams, neither holds.
- **Implication if it doesn't hold:** Q4 productivity drops, not rises, because senior eng time goes to onboarding instead of shipping.

## Mode Deliverable

### The Cut List

**1. Cut: Native mobile app (iOS + Android)**
- Why cutting doesn't damage core value: PM tool for engineering teams is desktop-primary. Mobile is a "nice for notifications" not "blocks revenue." No prospect is named as blocking on it.
- Premise breaking: 4-month build in a 3-month quarter, no stated revenue attached.
- What you gain: ~40% of engineering capacity back. Replace with a responsive web app + native push via PWA if mobile signal is real — 2 weeks, not 4 months.

**2. Cut: 2nd ICP (design teams)**
- Why cutting doesn't damage core value: You have years of growth left in engineering teams at current rates. Premature ICP expansion is the #1 killer of focus at Series A.
- Premise breaking: No saturation evidence in current ICP.
- What you gain: Sales, marketing, and product stay aligned on one wedge. Re-evaluate at $500k MRR.

**3. Cut: Vercel → AWS migration**
- Why cutting doesn't damage core value: Unless a named deal is blocked, this is infra theater.
- Premise breaking: "Enterprise reliability" is unsubstantiated.
- What you gain: A full quarter of senior engineering time. Revisit when (a) a specific deal blocks on it or (b) Vercel hits a real SLA ceiling.

**4. Cut: International launch (UK + Germany)**
- Why cutting doesn't damage core value: Geographic expansion at $180k MRR is a distraction. EN-speaking customers in UK already buy US SaaS; Germany requires localization, GDPR work, and a separate GTM motion you don't have.
- Premise breaking: Implicit "we're ready for geo expansion" — at this MRR, you aren't.
- What you gain: Marketing and sales focus on the ICP that's working.

**5. Cut: "What should I work on next" AI feature**
- Why cutting doesn't damage core value: Generic GPT-5 wrapper feature with no defensibility. Every PM tool will ship this in Q3.
- Premise breaking: That an AI feature is differentiation. It's table stakes by Q4.
- What you gain: Engineering focus. Replace with one specific AI bet tied to your wedge (e.g., AI-driven sprint health for engineering teams) only if it's a moat, not a checkbox.

**Keep:** SSO + SCIM (committed, revenue-attached), VP of Sales hire, 2-3 engineers (not 5), and 8% MoM growth execution on the existing ICP.

## The Hardest Unresolved Questions

1. **Which single workstream, if it failed, would make the next board meeting hardest?**
   Why this is the hardest: The user has not ranked these. Without a rank, every workstream is "equally critical," which means none is.
   What answering it changes: That workstream becomes the only one with founder attention; the rest get delegated or cut.

2. **What is the named enterprise deal (or deal pipeline value) that justifies SSO+SCIM, AWS migration, and "enterprise reliability"?**
   Why this is the hardest: The plan uses "enterprise" as a justification for three separate workstreams without naming the revenue. If the answer is "<$500k ARR pipeline," half the plan collapses.
   What answering it changes: Either the enterprise track gets prioritized hard (and consumer/SMB features deprioritized), or the enterprise framing is dropped and the plan simplifies further.

3. **What does 8% MoM growth need to look like at month 6 to make the Series B narrative work, and which workstream most directly drives it?**
   Why this is the hardest: At 8% MoM, $180k → $285k MRR by month 6. Series B needs a story. None of the 8 workstreams are explicitly tied to that number.
   What answering it changes: Workstreams not tied to the Series B number are candidates for cut #6, #7, #8.

## Taste Calls I Made

- Framed as SCOPE REDUCTION, not HOLD SCOPE: the plan has too many bets to merely sharpen — the structural fix is fewer bets.
- Cut mobile entirely instead of descoping to PWA-as-default: PWA path is offered as alternative if mobile signal is real.
- Kept SSO+SCIM as the only "enterprise" workstream: it's the only one with named committed prospects.
- Reduced engineering hires from 5 to 2-3: matches reduced scope; user can scale back up if cut list is rejected.

## User Challenges

- **[ESCALATION DEFERRED] Cut native mobile entirely**
  - My recommendation: Cut. Replace with PWA if mobile signal is real.
  - Plan's position: Build native iOS + Android in Q3.
  - Awaiting user call before applying.

- **[ESCALATION DEFERRED] Cut 2nd ICP (design teams)**
  - My recommendation: Cut. Re-evaluate at $500k MRR.
  - Plan's position: Expand to design teams in Q4.
  - Awaiting user call before applying.

- **[ESCALATION DEFERRED] Cut AWS migration**
  - My recommendation: Cut unless a named deal blocks on it.
  - Plan's position: Migrate Vercel → AWS in Q4 for "enterprise reliability."
  - Awaiting user call before applying.

- **[ESCALATION DEFERRED] Cut international launch**
  - My recommendation: Cut. Revisit at $500k MRR or when inbound from UK/DE >20% of pipeline.
  - Plan's position: Launch UK + Germany in Q4.
  - Awaiting user call before applying.

- **[ESCALATION DEFERRED] Cut generic AI feature**
  - My recommendation: Cut or replace with one wedge-specific AI bet.
  - Plan's position: Ship "what should I work on next" GPT-5 feature in Q3.
  - Awaiting user call before applying.

## Next-Iteration Spec

Version 2 of the roadmap is three workstreams, not eight:

**Q3 (3 months):**
1. Ship SSO + SCIM to the 2 committed prospects. Close them.
2. Hire VP of Sales. Build a repeatable sales motion for the existing engineering-teams ICP.
3. Ship one wedge-specific AI feature (only if it's a moat in your ICP — otherwise skip).

**Q4 (3 months):**
1. Double down on the engineering-teams ICP. Drive MRR from $180k → $285k+.
2. Hire 2-3 engineers (not 5) to support the working motion.
3. Re-evaluate mobile, AWS, geo, and 2nd ICP — pick at most ONE based on Q3 evidence.

Runway is $4M. The plan above uses ~40% of available capacity. The remaining capacity is reserved for whatever Q3 reveals — which is the discipline a Series A founder is supposed to maintain, not pre-spend.

## Limitations

- Did not have access to: actual sales pipeline, named enterprise prospects beyond "2 SSO commits," competitive landscape, or team-level capacity model. Cuts are based on structural signals from the plan; user-side validation needed before applying.
- User Challenges all deferred — review's value depends on Sir engaging with the 5 challenge calls. If all are rejected, re-invoke with explicit consent to push harder, or accept that the plan was already correctly scoped (in which case the Hardest Unresolved Questions are the primary deliverable).
- Did not validate the 8% MoM growth assumption — taken at face value. If growth is decelerating, the cuts become more urgent, not less.

```


## gstack-plan-ceo-review/02-feature-launch

**Blind mapping:** A=v2-generated, B=community

### gstack-plan-ceo-review/02-feature-launch — community (24451 bytes)

```
# CEO-Mode Plan Review: AI Insights Feature Launch

**Skill:** `/plan-ceo-review` (gstack v1.x)
**Plan under review:** 8-week AI insights feature build
**Context:** B2B analytics tool, $45k MRR, 6 people, biggest customer = 40% of MRR
**User question:** "Too cautious or too aggressive — not sure which."

---

## Verdict up front

Both. You're aggressive on weeks 1-2 and cautious on weeks 3-8. The plan inverts where the risk actually lives.

The real risk is not "do users want AI insights." Your biggest customer (40% MRR) is asking for it daily and three competitors already shipped it. The risk is "can we ship something they keep using past week 2." That risk lives in the prompt, the data shape, and the unsubscribe-from-noise behavior — not in the user research.

Recommended posture: **SELECTIVE EXPANSION** — hold the 8-week scope as baseline, but cherry-pick three specific changes that materially improve odds. Details below.

---

## PRE-REVIEW SYSTEM AUDIT (synthesized from plan only — no repo access)

| Signal | Value | Implication |
|---|---|---|
| Revenue concentration | 40% in one logo | Plan is also a retention bet, not just a growth bet |
| Competitive position | 3+ shipped competitors | Differentiation pressure is real, table stakes risk |
| Team size | 6 people, 2 senior eng FT | 33% of capacity for 8 weeks — large bet |
| Pipeline signal | 30% mention, 50% close assumption | Soft data — "mentions" ≠ "would pay specifically for this" |
| Cost vs incremental MRR | $60k cost vs $15k MRR | Payback ~4 months IF the 50% close assumption holds |

---

## Step 0A — Premise Challenge

**Q1: Is this the right problem to solve?**

Two framings worth pressure-testing:

1. **The framing in the plan:** "Customers want AI insights, three competitors shipped it, we should too."
2. **The framing under it:** "Our biggest customer (40% of MRR) is one churn event from a 40% MRR cliff and they're asking for something we don't have."

These produce different plans. Framing #1 says "ship a competitive feature." Framing #2 says "ship whatever specifically locks in that one customer." If your #1 customer would be locked in by a custom-built integration in 2 weeks, you don't need an 8-week generic AI insights launch — you need to save the account and *then* generalize.

Ask yourself directly: if your #1 customer leaves in week 6 of this plan, was the plan worth it?

**Q2: What's the actual outcome?**

The plan's stated outcome is "$15k incremental MRR." The unstated outcome is "do not lose the $18k/mo from the 40% customer." The unstated outcome is the one that matters. Make it explicit in the plan or you'll optimize the wrong thing.

**Q3: What if you do nothing?**

- Nothing for 8 weeks → competitive parity gap widens, biggest customer might evaluate alternatives
- Nothing forever → you become the "no AI" tool in a category where AI is now table stakes

Doing nothing is not free. But it's also not the binary the plan implies.

---

## Step 0B — Existing Code Leverage

This plan describes building from scratch. **Question never asked in the plan:** what already exists in your product that an AI layer could *wrap* rather than replace?

Likely candidates (validate against your codebase):
- Existing dashboard query layer → wrap as "natural language → existing query"
- Existing alerting/threshold system → wrap as "anomaly detection on top of thresholds you already compute"
- Existing chart rendering → reuse as "insight surface" instead of building new UI

Most "AI insights" features that ship in 8 weeks are 70% glue over existing capabilities. If your plan is 70% new code, that's a smell.

---

## Step 0C — Dream State Mapping

```
CURRENT STATE                THIS PLAN                       12-MONTH IDEAL
─────────────                ─────────                       ──────────────
Customers build              "Insights" panel surfaces       Tool watches data
custom dashboards    ─────►  patterns in NL               ─►  continuously, alerts
manually                     (request → response)             on what matters,
                                                              learns customer-specific
                                                              normal vs anomaly
```

**Gap question:** does the 8-week plan's architecture (request/response insights engine) move toward the 12-month ideal (continuous monitoring + personalized normal)? Or does it lock in a request/response paradigm you'll have to undo?

If the insights engine is built as "user clicks button → LLM summarizes" you've optimized for demo, not retention. Continuous, push-based insights are what create habit. **This is the single most important architecture decision in the plan and it's not addressed.**

---

## Step 0C-bis — Implementation Alternatives (MANDATORY per skill)

The plan presents one approach. Three alternatives worth considering:

### APPROACH A: "Ship the demo" (the current plan)
- **Summary:** 8 weeks, 2 engineers, build pattern detection + NL summarization, public launch week 8
- **Effort:** L (human: 8 weeks / CC+gstack: ~3-4 weeks if the team is set up for it)
- **Risk:** Med-High
- **Pros:**
  - Matches competitive feature parity narrative
  - Public launch creates marketing moment
  - Generic enough to apply across customers
- **Cons:**
  - Optimizes for "shipped" not "retained"
  - 8 weeks is forever in a 6-person company — opportunity cost is whatever else those 2 engineers could do
  - Public launch with ~1 week of beta is too thin; you'll launch with bugs you didn't see
- **Reuses:** unclear from plan — that's a red flag

### APPROACH B: "Save the whale, then generalize"
- **Summary:** Weeks 1-3: ship a custom-built AI layer for the 40% customer specifically. Weeks 4-8: generalize it into product based on what survived contact with that one customer.
- **Effort:** M (human: 3 weeks for v1 / CC+gstack: ~1 week for v1)
- **Risk:** Low-Med
- **Pros:**
  - De-risks the biggest revenue dependency first
  - Real production data feedback loop in week 3, not week 7
  - Generalization is informed by what actually worked, not by what you guessed in user research
  - Builds trust capital with the customer who matters most
- **Cons:**
  - Risk of building something too custom that doesn't generalize
  - Requires close partnership with that customer (which they want — they keep asking)
  - No "public launch moment" until later
- **Reuses:** their existing dashboards as insight surfaces

### APPROACH C: "Wedge — pick one insight, ship it bulletproof in 3 weeks"
- **Summary:** Skip the broad "insights engine." Pick the single highest-value insight type (probably anomaly detection on revenue/usage metrics) and ship it complete: detection, NL summary, alert delivery, user feedback loop. 3 weeks to live, then iterate based on what gets used.
- **Effort:** S-M (human: 3 weeks / CC+gstack: ~1-1.5 weeks)
- **Risk:** Low
- **Pros:**
  - Forces you to pick the most valuable insight type instead of building a generic engine
  - 3 weeks vs 8 weeks = 5 weeks of optionality recovered
  - Real usage data within 3 weeks decides what to build next
  - Easier to differentiate ("we don't do AI insights — we do anomaly detection that actually works")
- **Cons:**
  - Doesn't match the "insights" narrative competitors are running on — feels narrower
  - Requires resisting feature creep during build
  - The "which insight" decision is itself a hard call

**RECOMMENDATION:** Approach B — save the whale, then generalize. Maps to "people-first sequencing" (the customer who matters most goes first) and "leverage obsession" (one customer's deep collaboration produces better insight than 20 user research interviews).

`Completeness: A=8/10 (covers the surface, undercovers retention), B=9/10 (covers retention + generalization), C=7/10 (narrow but excellent at what it does).`

> **STOP point per skill:** in a real run, this would be an `AskUserQuestion` and execution would block on user answer before mode selection. For this offline review I'll proceed assuming Approach B + SELECTIVE EXPANSION.

---

## Step 0D — Mode Selection

Recommended: **SELECTIVE EXPANSION**

Why: this is a feature enhancement on an existing product (not greenfield) with strong existing customer signal. The plan is roughly right in shape but wrong in sequencing. SELECTIVE EXPANSION lets you keep the core scope and cherry-pick the 3-4 changes that materially shift odds.

`Note: options differ in kind (review posture), not coverage — no completeness score.`

---

## Step 0D-Cherry-Picks (SELECTIVE EXPANSION)

Surfaced expansion candidates, neutral posture:

### Cherry-pick 1: Move beta from week 7 to week 4
- **Effort:** S (no new code; reorder calendar)
- **Risk:** Low
- **Why it matters:** 1 week of beta is not beta — it's a 5-day bug hunt with friendly customers. 4 weeks of beta gives you real retention signal before public launch. The cost is shipping a less-polished version to 5 people who already want this.
- **Recommendation posture:** Neutral, but lean accept.
- **Decision options:** A) Add to scope, B) Defer, C) Skip.

### Cherry-pick 2: Replace 20 customer interviews with 5 deep partnerships
- **Effort:** S
- **Risk:** Low
- **Why it matters:** 20 30-minute interviews = 10 hours of vague signal. 5 customers you build with for 8 weeks = 200 hours of specific signal. The plan's 20 interviews is a ritual; what you actually need is a sample of users who'll use the thing during build. Your 40% customer is candidate #1 for free.
- **Recommendation posture:** Neutral, but lean accept.

### Cherry-pick 3: Anchor the insights engine to one specific failure mode of the manual dashboard workflow
- **Effort:** S (scoping decision, not code)
- **Risk:** Low
- **Why it matters:** "Pattern detection + NL summarization" describes the *technology*, not the *job*. The job is probably "tell me when revenue per customer is degrading before I notice it in a Monday dashboard." Anchor the v1 to one specific job. You can broaden later. Building generic without an anchor is how AI insights features become "demo good, retention bad."
- **Recommendation posture:** Strong recommend.

### Cherry-pick 4: Add a "did this insight matter" feedback signal from day 1
- **Effort:** S
- **Risk:** Low
- **Why it matters:** AI insights features die because they generate noise users learn to ignore. A thumbs-up/down per insight in the UI gives you the signal to improve the prompt and to detect "we're losing them" before they churn. This is non-optional infrastructure for an AI feature; building it post-launch is 3x harder.
- **Recommendation posture:** Strong recommend — bordering on HOLD-SCOPE-mandatory.

### Cherry-pick 5: Architectural decision — push vs pull insights
- **Effort:** S as a decision, M as code
- **Risk:** Med
- **Why it matters:** See dream state mapping above. If the insights engine is request/response only, you've locked in a paradigm you'll have to undo to get to the 12-month ideal. Decide now whether v1 includes a push channel (email/Slack/in-app notification) or whether v1 is pull-only with a clear v2 path to push. Don't drift into pull-only by default.
- **Recommendation posture:** Decide explicitly, don't drift.

---

## Step 0E — Temporal Interrogation

```
HOUR 1  (foundations):   What's the data shape going INTO the LLM? Schema?
                         How are you protecting against PII leakage in prompts?
HOUR 2-3 (core logic):   What's the prompt? Single-shot or chain? How do you
                         test prompt regressions? What's the eval set?
HOUR 4-5 (integration):  How do insights surface? In-app card? Email? Slack?
                         What happens when the LLM is down or rate-limited?
HOUR 6+  (polish/tests): How do you measure "is this insight good"? What's
                         the offline eval? What's the online metric?
```

These are decisions the plan defers. They will eat 1-2 weeks of the build if not resolved up-front. Resolve them in week 1, not week 5.

NOTE: under CC+gstack, the 8-week human plan likely compresses to ~3-4 weeks of wall time if the team is set up for it. Worth asking: is "8 weeks" a thoughtful estimate or a calendar habit?

---

## Section 1: Architecture Review — gaps in plan

The plan does not specify:
- Which LLM provider, fallback provider, latency budget
- How prompts are versioned and tested
- Whether insights are computed on-demand, scheduled, or streaming
- Where insights live (new table? cache? ephemeral?)
- Auth model for "this insight is about that customer's data"
- Cost model — at scale, how much does each insight cost in LLM tokens?

**WARNING:** "spike on LLM prompt patterns" in weeks 3-4 is not architecture. It's research. The architectural decisions need to be made *before* you spike or you'll spike, like the work, and ship the spike.

Required ASCII diagram (your team should produce this in week 1):

```
  Customer data ──┐
                  ├──► Insight generator ──┬──► Insight store ──┐
  Schema metadata─┘   (LLM + heuristics)   │                    │
                                           │                    ▼
                                           │              ┌── Pull UI (in-app)
                                           │              │
                                           ▼              ├── Push (email/slack)
                                     Eval pipeline        │
                                     (offline tests)      └── Feedback signal
                                                              (thumbs up/down)
                                                              ───┐
                                                                 ▼
                                                          Improves prompt
```

---

## Section 2: Error & Rescue Map — what the plan ignores

```
METHOD/CODEPATH          | WHAT CAN GO WRONG          | CURRENT PLAN ADDRESSES?
-------------------------|----------------------------|-------------------------
LLM API call             | Timeout                    | Not addressed
                         | Rate limit (429)           | Not addressed
                         | Returns malformed JSON     | Not addressed
                         | Returns hallucinated stat  | Not addressed ◄── critical
                         | Returns refusal            | Not addressed
                         | Provider outage            | Not addressed
Pattern detection        | Empty data set             | Not addressed
                         | Single-row data set        | Not addressed
                         | Detects 0 patterns         | Not addressed (UX gap)
                         | Detects 50 patterns        | Not addressed (UX gap)
Insight delivery         | User unsubscribed but      | Not addressed
                         |   pattern fired anyway     |
                         | Insight contains stale     | Not addressed
                         |   data (race condition)    |
```

The "LLM hallucinates a stat that's wrong" failure mode is the existential one for an analytics tool. Your customers trust you with their numbers. An AI feature that confidently hallucinates the wrong number is worse than no AI feature. **The plan must address this and currently doesn't.**

---

## Section 3: Security & Threat Model — gaps

- **PII in prompts:** customer data → LLM provider. Is your data processing agreement with provider clear? Is your customer's DPA with you compatible? This is a contractual question, not a code question.
- **Prompt injection:** if customer data contains user-generated strings, those strings end up in your prompt. A malicious customer could craft data designed to manipulate insights for other tenants. Test for it.
- **Tenant isolation:** insights generated for customer A must never leak into customer B's view. Standard multi-tenant rule, but easy to break with a shared cache.

---

## Section 4: Data Flow & Interaction Edge Cases — UX gaps

```
INTERACTION              | EDGE CASE                  | PLAN HANDLES?
-------------------------|----------------------------|---------------
View insights panel      | Zero insights generated    | Not addressed
                         | 50 insights generated      | Not addressed
                         | Insights stale by 2 hours  | Not addressed
                         | LLM unavailable            | Not addressed
Mark insight as useful   | User feedback              | Not addressed (cherry-pick 4)
Insight references data  | Underlying data deleted    | Not addressed
that no longer exists    |                            |
```

---

## Section 5: Code Quality Review

Plan is a strategy doc, not a code plan. Move on.

## Section 6: Test Review — the missing piece

The plan does not mention:
- How prompt regressions are detected
- What the eval set looks like
- Acceptance criteria for "the insight is good enough to ship"

For LLM features, **the eval set is the spec.** Without one you don't know what you're shipping. Build it in week 1, populate it during user research (week 1-2), and gate week 7 beta on eval scores. This is non-negotiable.

## Section 7: Performance Review

LLM cost per insight × insights per customer × customers × frequency = monthly bill.

Plan doesn't model this. At scale, an insights feature with naive prompting can cost more than the MRR it generates. Worth a 30-minute back-of-envelope before week 3.

## Section 8: Observability & Debuggability

What metric tells you the feature is working in production? Probable candidates:
- % of insights that get a thumbs-up
- % of insights that lead to a downstream action (drill-down, share, etc.)
- Time-to-insight (latency)
- Insight cost / customer / month
- Rate of "this insight is wrong" reports

Pick 2-3 before launch. Instrument from day 1, not after launch.

## Section 9: Deployment & Rollout

Public launch in week 8 with 1 week of beta from 5 customers is **too thin**. Beta should be 3-4 weeks across 10-15 customers (cherry-pick 1). Public launch should be feature-flagged and gradual.

If your 40% customer hits a bug in the public launch and loses trust in the data, you've made things worse. Risk-asymmetry argues for slow rollout.

## Section 10: Long-Term Trajectory

The plan optimizes for week 8 (launch). The product's success is decided in months 3-6 (does usage compound?). The architecture decisions that determine month 3-6 success are mostly invisible in the current plan: prompt eval infrastructure, feedback loop instrumentation, push vs pull paradigm.

**Reversibility rating:** 3/5. The launched feature is reversible (you can deprecate). But the architecture choices (request/response vs continuous, no eval infra vs eval infra) are 1/5 — hard to reverse later because they shape user expectations and downstream code.

## Section 11: Design & UX Review

UI scope is detected (insights panel). Recommendations:
- Information hierarchy: which insight does the user see first when there are 12?
- Empty state: when there are no insights yet
- Confidence visualization: users will not trust insights they can't sanity-check; show the underlying data behind every claim
- Failure state: when the LLM is down, the panel should degrade gracefully (show last cached insights or a clear "checking now")

---

## Required Outputs

### NOT in scope (recommended cuts)
- 20 customer interviews → cut to 5 deep partnerships (cherry-pick 2)
- "Public launch" as a single moment → replace with gradual rollout
- Generic "pattern detection" → anchor to one specific job (cherry-pick 3)

### What already exists (validate against your codebase)
- Likely: dashboard query layer, alerting thresholds, chart rendering
- Likely reusable as: NL → query, anomaly detection input, insight surface

### Dream state delta
The plan ships v1 of insights but does not move toward the 12-month ideal of continuous, personalized monitoring. To close the gap, decide push-vs-pull explicitly in week 1 (cherry-pick 5), build feedback loop infrastructure (cherry-pick 4), and resist the demo-shaped architecture.

### Failure modes registry — **CRITICAL GAPS**
1. LLM hallucinates a wrong stat → user trust collapses → not addressed
2. No eval set → no way to detect prompt regressions → not addressed
3. No feedback signal → no learning loop → not addressed (until cherry-pick 4)

### TODOS proposed (for separate AskUserQuestion in real run)
1. Architecture decision doc — push vs pull, by week 1
2. Eval set construction — by week 2
3. Cost model — by week 2
4. PII / DPA review — by week 1
5. Feedback signal in v1 UI — week 5

---

## Direct answer to your question

> "I'm worried I'm being too cautious / too aggressive — not sure which."

You're being **wrong-shaped**, not wrong-sized.

- **Too cautious:** 8 weeks of build before any production signal is too long. Beta in week 7 is too late. 20 user research interviews before any code is ritual, not data.
- **Too aggressive:** the scope of "AI insights engine" is too broad for an 8-week launch. There's no eval infra, no feedback loop, no clear retention metric. You're building a demo, not a product.

The fix is not to make it bigger or smaller. It's to **invert the risk profile:** ship narrow + early to your most important customer, build the eval and feedback infrastructure that determines month 3-6 success, and let the public launch follow real usage data rather than guess at it.

If you do exactly the plan as written, my honest probability estimate: ~50% you ship something on time, ~25% you hit the $15k incremental MRR, ~15% it's still being used by customers in month 6 with compounding usage. Those are not bad numbers but they're not the bet you should be making with 33% of your engineering capacity.

If you take Approach B + cherry-picks 1, 3, 4: probability of compounding usage in month 6 goes up materially, and you've also de-risked the 40%-customer dependency. That's the trade you want.

---

## Completion Summary

```
+====================================================================+
|            CEO PLAN REVIEW — COMPLETION SUMMARY                    |
+====================================================================+
| Mode recommended     | SELECTIVE EXPANSION                          |
| Approach recommended | B (save the whale, then generalize)          |
| System Audit         | revenue concentration, competitive parity   |
| Step 0               | premise reframed: retention bet, not just   |
|                      | growth bet                                  |
| Section 1  (Arch)    | 6 unspecified architecture decisions        |
| Section 2  (Errors)  | 11 failure modes mapped, 6 unaddressed      |
| Section 3  (Security)| 3 issues — PII, prompt injection, tenancy   |
| Section 4  (Data/UX) | 6 edge cases unhandled                      |
| Section 5  (Quality) | n/a (strategy doc)                          |
| Section 6  (Tests)   | CRITICAL GAP — no eval set defined          |
| Section 7  (Perf)    | LLM cost model missing                      |
| Section 8  (Observ)  | metrics undefined                           |
| Section 9  (Deploy)  | beta too short, public launch too sharp     |
| Section 10 (Future)  | reversibility 3/5, architecture risk        |
| Section 11 (Design)  | 4 UX states uncovered                       |
+--------------------------------------------------------------------+
| Cherry-picks proposed| 5                                            |
| Strong-recommend     | #3 (anchor to job), #4 (feedback signal)    |
| TODOs proposed       | 5                                            |
| CRITICAL GAPS        | 3 (hallucination, eval, feedback loop)      |
| Lake Score           | 4/5 recommendations chose complete option   |
+====================================================================+
```

---

## STATUS

`DONE_WITH_CONCERNS` — review applied skill structure. Three CRITICAL GAPS surfaced. Recommend the user take this back to their team, run real `/plan-ceo-review` with `AskUserQuestion` flow for each cherry-pick, and resolve the architecture decisions before week 1 of build.

```

### gstack-plan-ceo-review/02-feature-launch — v2-generated (9787 bytes)

```
# CEO Review — AI Insights Feature Launch (8 weeks)

## Mode
**Selected mode:** SCOPE REDUCTION
**Why this mode:** $60k of build cost for $15k incremental MRR is a 4-month payback only if every assumption holds — and the plan stacks four optimistic assumptions (30% pipeline mention → 50% close → feature is causal → MRR is incremental, not cannibalized). The plan also conflates two different bets — retention of the 40%-MRR anchor customer vs. acquiring new MRR from pipeline — into one 8-week build, which inflates scope past what either bet alone would justify. Two senior engineers (33% of a 6-person team) for 8 weeks on a feature that Mode/Hex/ChartGPT have already shipped is ambition mismatched to defensibility.

## Premise Challenge

### Premise: The anchor customer's "AI insights" request justifies an 8-week, $60k build
- **Status:** CRACKS
- **What the user is assuming:** The anchor customer will churn or expand based on whether this specific feature ships in 8 weeks at this scope.
- **What needs to be true for this to hold:** The customer has named "AI insights" as a renewal/expansion blocker, not a wishlist item — and a thinner version (e.g., a 2-week scripted-anomaly-detection MVP) wouldn't satisfy them.
- **Implication if it doesn't hold:** The retention case collapses into a wishlist-fulfillment exercise, and the spend should be evaluated on new-revenue ROI alone — which is much weaker.

### Premise: 30% pipeline mention × 50% close → $15k incremental MRR is causally attributable to this feature
- **Status:** CRACKS
- **What the user is assuming:** Buyers who "mention wanting" AI insights will close because the feature exists, AND they wouldn't have closed without it.
- **What needs to be true for this to hold:** Win/loss data shows lost deals citing this exact gap as primary, not a top-5 reason among many. Mention ≠ deciding factor.
- **Implication if it doesn't hold:** True incremental MRR is some fraction of $15k — possibly $3-5k — making the payback period 12+ months and the build a strategic loss.

### Premise: Mode/Hex/ChartGPT shipping similar features doesn't change the bet
- **Status:** BREAKS
- **What the user is assuming:** Parity with bigger players on a commoditizing capability protects revenue.
- **What needs to be true for this to hold:** The user's tool has a wedge (data, workflow, customer segment) that turns commodity AI insights into a differentiated experience.
- **Implication if it doesn't hold:** The team spends 8 weeks building the same feature three better-funded competitors already ship — at best achieving table stakes, at worst signaling the product is one quarter behind.

### Premise: 2 senior engineers for 8 weeks is the right unit of investment
- **Status:** CRACKS
- **What the user is assuming:** A 6-person team can dedicate 33% of headcount to one feature for 2 months without strategic cost elsewhere.
- **What needs to be true for this to hold:** Nothing else on the roadmap (renewals, infra, other customer asks) needs those engineers more than this does.
- **Implication if it doesn't hold:** Opportunity cost dominates the visible build cost.

## Mode Deliverable — The Cut List

**1. Cut "Public launch" (Week 8). Reframe as "Anchor customer GA only."**
- Why cutting doesn't damage core value: the only validated demand is from one customer. Public launch implies marketing investment, support load, and pricing decisions the plan doesn't address.
- Premise that justified it: that pipeline interest converts to revenue — CRACKED above.
- Gain: removes 1+ week of launch overhead and gives the team a clean read on whether the feature actually drives renewal/expansion.

**2. Cut Weeks 3-4 architecture spike. Replace with a Week 1 prompt-pattern prototype against the anchor customer's actual data.**
- Why cutting doesn't damage core value: the architecture risk is low (LLM call + summarization is well-understood); the demand risk is high. A two-week spike on the wrong question is the most expensive thing in the plan.
- Premise that justified it: that this is a hard engineering problem requiring design work — BREAKS. It's an integration/UX problem.
- Gain: 2 weeks back, redirected to demand validation.

**3. Cut "20 customer interviews" → 5 deep sessions with the anchor + 4 highest-pipeline-ARR prospects.**
- Why cutting doesn't damage core value: 20 interviews is research-theater on a feature where one customer is paying for the answer. Depth with paying-or-near-paying customers beats breadth.
- Premise that justified it: that broad demand signal is needed to size the bet — CRACKED. The bet is anchor retention + 4 named prospects, sized accordingly.
- Gain: 1+ week back, sharper signal on willingness to pay.

**4. Cut from 2 senior engineers to 1 senior + 1 part-time, OR shift to 4-week timeline with original team.**
- Why cutting doesn't damage core value: existing tools (LLM APIs, vector DBs, off-the-shelf anomaly detection) make this assemblable, not buildable from scratch.
- Premise that justified it: that "core insights engine" requires deep custom work — CRACKED. Most of the value is in prompting and surfacing, not in novel ML.
- Gain: $30k saved or 4 weeks saved, freeing capacity for the next bet.

**Net reduction:** 8 weeks → 4-5 weeks; $60k → $25-30k; scope shifts from "feature launch" to "anchor-customer expansion + 4-prospect validation."

## The Hardest Unresolved Questions (1-3)

1. **Has the anchor customer actually said this is a renewal blocker, or are they expressing a preference?**
   Why this is the hardest: the entire retention case rests on this distinction, and founders systematically over-read customer enthusiasm as commitment.
   What answering it changes: if it's a preference, the build is discretionary and the cut list above gets more aggressive. If it's a blocker, scope gets ring-fenced to satisfying that customer specifically and the public-launch frame disappears entirely.

2. **What does the win/loss data say about why deals close or don't — does "no AI insights" appear as a primary reason, or just a mentioned feature?**
   Why this is the hardest: $15k MRR projection is downstream of this answer, and the answer is knowable from existing CRM notes within an afternoon.
   What answering it changes: if AI insights is a top-3 lost-deal reason, the build justifies itself on new revenue alone and Mode 0 might actually be SELECTIVE EXPANSION. If it's a top-10 mentioned feature, the new-revenue case dies and the plan rests on retention only.

3. **What's the differentiated wedge vs. Mode/Hex/ChartGPT — and if there isn't one, why ship parity?**
   Why this is the hardest: shipping commodity features against better-funded competitors is a strategic posture, not a tactical decision, and the plan never names it.
   What answering it changes: if there's a wedge (vertical depth, workflow integration, data advantage), the build should lean into it explicitly — the current plan doesn't. If there isn't, the right move may be to partner/integrate rather than build.

## Taste Calls I Made

- Reframed "feature launch" as "anchor expansion + prospect validation" — user can keep the launch framing if marketing/positioning work is already underway.
- Recommended cutting interview count from 20 to 9 — user can keep 20 if they have a separate research thesis beyond this feature.
- Treated the $15k MRR estimate as optimistic rather than conservative — user with better win/loss data may overrule.

## User Challenges

- **Cut public launch from Week 8** [ESCALATION DEFERRED]
  - My recommendation: ship to anchor + named prospects only; defer public launch until renewal signal lands.
  - Plan's position: public launch in Week 8.
  - Awaiting user call before applying.

- **Reduce engineering allocation from 2 senior FTEs × 8wk to 1 senior + 1 part-time × 4-5wk** [ESCALATION DEFERRED]
  - My recommendation: half the spend, half the timeline, redirect freed capacity.
  - Plan's position: 2 senior engineers full-time for 8 weeks.
  - Awaiting user call before applying.

- **Replace Weeks 3-4 architecture spike with Week 1 working prototype on real anchor data** [ESCALATION DEFERRED]
  - My recommendation: move to evidence-on-real-data fast; LLM architecture is not the risk.
  - Plan's position: 2 weeks of architecture + spike before building.
  - Awaiting user call before applying.

## Next-Iteration Spec

Version 2 says: 4-5 week scope. Week 1: working prompt-pattern prototype against anchor customer's live data; 5 deep sessions (anchor + 4 highest-ARR pipeline prospects); win/loss audit on existing CRM data to validate or kill the $15k MRR projection. Weeks 2-3: build minimum surface (anomaly detection + NL summarization) using off-the-shelf components; 1 senior engineer + 1 part-time. Week 4: anchor customer beta; gate further investment on (a) anchor expansion/renewal signal and (b) at least 2 of 4 prospects converting on this feature being live. No public launch in scope. Public launch becomes a separate decision after anchor signal lands. Budget: $25-30k. Success metric: anchor expansion or retention commitment + named-prospect close, NOT pipeline mention conversion.

## Limitations

- Did not have access to win/loss data, anchor customer's exact language, or competitive feature parity detail — premise challenges are structural, not domain-validated.
- Three User Challenges deferred (non-interactive context); review's adversarial value is partial until user resolves them.
- Mode was clearly SCOPE REDUCTION on ROI signals; if user has hidden context (e.g., the anchor customer has explicitly threatened churn), mode could shift to HOLD SCOPE with the same cut list applied as sharpening rather than reduction.

```


## gstack-plan-ceo-review/03-pivot-decision

**Blind mapping:** A=v2-generated, B=community

### gstack-plan-ceo-review/03-pivot-decision — community (36511 bytes)

```
# MEGA PLAN REVIEW — B2C → B2B Pivot Decision

Skill: `/plan-ceo-review`
Mode posture: HOLD SCOPE with surgical interrogation. The plan is not a feature spec, it's a company-direction call. The right CEO posture here is "kill the proxies and force the real question," not "dream bigger." A 12-week pivot plan that ends in a possible wind-down deserves rigor, not enthusiasm.

---

## PRE-REVIEW SYSTEM AUDIT

Plan does not give us git/repo context, so the audit translates to a business audit. What we know:

- 18 months in. ~80k MAU. $90k MRR (subscription B2C).
- LTV/CAC: 1.4 (you are paying $1 to make $1.40 over the customer's lifetime — and that is a *gross* multiple, not a contribution-margin multiple. Once you net out infra, content, support, refunds, payment fees, the real ratio is probably ~1.0 or below).
- Churn: 6% monthly. That is a 12-month survival rate of ~46%. Average customer lifetime ~16.7 months. This is the actual problem.
- Plan: 12-week pivot to B2B, $25k+ ARR contracts, target 3 contracts by week 12.
- Cofounder disagreement: B2C 6 more months vs pivot now.

Known existing assets that the plan barely mentions:
- 80k MAU = a real distribution asset. B2B sales motions burn this if you abandon it instead of harvesting it.
- An L&D buyer's first question is "show me your retention data." Your 6% monthly churn IS your retention data. That is going to come up in week 4 of demos and you need an answer ready.
- $90k MRR = ~$1.08M ARR. At a 12-week pivot, you are betting an existing $1M business on a $75k experiment.

---

## Step 0A: Premise Challenge

**Is this the right problem to solve?**

The plan frames the problem as "B2C unit economics don't work, so let's change the buyer." That framing has a quiet assumption baked in: that the *product* works and only the *go-to-market* is broken.

Test this assumption. 6% monthly churn on a language-learning subscription is not a GTM problem. It's a "users stop getting value after ~3 months" problem. Duolingo's monthly churn is ~2-3%. Babbel's is ~3-4%. Yours is 2x that.

If you put the same product in front of an L&D buyer, here is what happens:
1. You sell the dream (week 7-12 of your plan).
2. They roll it out to 200 employees.
3. Three months later, the L&D buyer pulls usage analytics and sees 6% of employees logging in weekly.
4. They don't renew. They tell three other L&D buyers. You're done in B2B too.

**Translated:** the pivot may be moving the bug from a place where users vote with $9.99/mo to a place where one buyer votes with $25k/yr. The leverage flips, but so does the explosion radius. One bad enterprise reference at month 6 sets you back further than 12 months of bad B2C metrics.

**The real question the plan is not asking:** is the underlying product good enough to hold an enterprise relationship? If yes, B2B is a credible pivot. If no, B2B is just a longer fuse on the same bomb.

**Counter-framing worth considering** (not necessarily right, but the plan should have ruled them out before committing 12 weeks):

a) **Fix the churn first, then choose buyer.** If you can get monthly churn from 6% to 3% in 90 days (it's mostly an onboarding/habit-formation problem in lang apps), your LTV/CAC goes from 1.4 to ~2.8. That's a working B2C business. You wouldn't need to pivot.

b) **Stay B2C, shift CAC channel.** Are you paid-acquisition-dependent? Most 1.4 LTV/CAC stories are "Facebook ads got expensive." Shifting to organic/SEO/community can fix unit economics without a pivot.

c) **B2B2C (consumer paid by employer).** Same product, same users, same engagement loops. Employer pays. You don't have to build admin dashboards or learn enterprise sales. Chegg, Headspace, Calm all run this play.

d) **Sell to schools/universities, not corporate L&D.** Different ICP, often shorter sales cycle, lower-touch, and language learning has natural fit there.

e) **The plan as written.** Full pivot to corporate L&D, 12-week sprint.

The plan picked (e) without showing its work on (a)-(d). That's the gap.

**What would happen if we did nothing?** $1M ARR business with bad unit economics keeps existing. Slowly bleeds capital. Real but not acute pain. You have time to think.

## Step 0B: Existing Code Leverage (translated to "existing asset leverage")

What the plan reuses well:
- Same underlying product. Smart.
- Same content library. Smart.

What the plan abandons that probably shouldn't be abandoned:
- 80k MAU. The plan sunsets B2C in months 4-6. Those 80k users are your *case study generator*. "We have 80k consumer users; here is the engagement data; we're now offering this to your team" is a much warmer enterprise pitch than "we built a B2B language tool, want to buy it?" The plan should explicitly use B2C as a marketing asset for B2B, not abandon it.
- The $90k MRR. That's runway. Sunsetting it pre-PMF in B2B is the riskiest line in this plan. You should kill B2C *after* B2B is working, not on a fixed 3-month timer.

## Step 0C: Dream State Mapping

```
  CURRENT STATE                     12-MONTH IDEAL
  80k MAU, $90k MRR B2C        →    Either:
  6% churn, 1.4 LTV/CAC               (a) $90k MRR B2C + $300k ARR B2B
  Capital-bleeding              →         co-existing, B2C as funnel for B2B
                                          (Calm/Headspace model)
                                    OR
                                      (b) Fixed B2C: 3% churn, 2.8 LTV/CAC,
                                          $200k MRR, no pivot needed
                                    OR
                                      (c) Pure B2B: $500k+ ARR, 5 logos,
                                          B2C fully sunset, painful but real

  THIS PLAN aims at:           →    (c) by week 12 or wind down

  Issue: the plan jumps to (c) without testing whether (a) or (b) is reachable.
```

## Step 0C-bis: Implementation Alternatives

Three real options. The plan presented option C only. The CEO review surfaces the others.

```
APPROACH A: Diagnose-then-decide (3-week diagnostic sprint)
  Summary: Spend 3 weeks getting clean answers to "is the product good?"
           and "can churn be fixed?" BEFORE committing to a pivot direction.
  Effort:  S (3 weeks vs 12)
  Risk:    Low — you don't burn bridges with anything
  Pros:    - Cheapest path to the right answer
           - Forces the team to know which problem they're actually solving
           - Reveals if (b) or (a) is viable, saving the pivot cost entirely
           - Cofounder disagreement gets resolved by data, not opinion
  Cons:    - 3 weeks of "no decision" feels bad
           - Doesn't satisfy the founder urge to "do something"
  Reuses:  All existing user data, churn cohorts, support tickets

APPROACH B: B2B2C / dual-rail (the plan's plan, but keep B2C alive)
  Summary: Run the 12-week B2B sprint, but DO NOT sunset B2C on a timer.
           Keep B2C running indefinitely. Use it as case study + funnel.
  Effort:  M (same 12 weeks + don't actively kill B2C)
  Risk:    Medium — split focus, but kept optionality
  Pros:    - $90k MRR keeps funding the experiment
           - 80k MAU becomes proof point in enterprise demos
           - If B2B fails, you're not back to zero
           - Removes the "wind down or full pivot" binary at week 12
  Cons:    - Some focus dilution (real but manageable for cofounder + early team)
           - Two GTM motions running in parallel
  Reuses:  Everything the plan reuses, plus the B2C engine itself

APPROACH C: Full pivot (the plan as written)
  Summary: 12 weeks B2B sprint, sunset B2C at week 12 if 3 contracts close.
  Effort:  L (12 weeks + 3-month B2C wind-down)
  Risk:    High — hard binary, kills $90k MRR, no fallback
  Pros:    - Maximum focus
           - Forcing function, no half-measures
           - Clean story for investors ("we pivoted")
  Cons:    - Burns the runway-generating asset before B2B is proven
           - 6% churn problem follows the product into B2B (likely)
           - Cofounder doesn't agree (people-first sequencing matters)
           - At week 12, you have 3 months of cash to either confirm pivot
             or wind down, with no third option
  Reuses:  Same product, same content
```

**RECOMMENDATION: Approach A first, then B if the diagnostic says product is fixable; C only if the diagnostic proves the product is structurally broken for retail learners and ONLY works in mandated/enterprise contexts.**

Why: The plan's biggest risk is that it ports a churn problem into a higher-stakes channel. 3 weeks of diagnostics costs you almost nothing and resolves the framing question. If the product is fundamentally fine and B2C economics are a CAC/funnel problem, you don't pivot at all. If the product needs enterprise-mandated usage to retain, you pivot, but with eyes open and the right data to sell it.

The cofounder's "6 more months of B2C" is closer to right than the plan's "12 weeks then sunset," but the cofounder is also probably wrong — 6 months is too long without a structured diagnostic. The synthesis: 3 weeks of structured diagnosis, then commit to A, B, or C with data instead of vibes.

**Cofounder dynamic:** People-first sequencing (Horowitz). You cannot run a pivot through a disagreeing cofounder. Either you both believe in the pivot or it fails. The diagnostic sprint is also a tool for getting to cofounder alignment — both of you stare at the same data, then decide.

---

## Step 0D: Mode Selection

Defaults from the skill: "Greenfield feature → EXPANSION; Refactor → HOLD SCOPE." This is neither. This is a strategic-direction call where the user already wrote a plan and is asking "is this right?"

**Mode: HOLD SCOPE — with one mandatory upstream question** (the diagnostic question above). HOLD SCOPE is correct because the user is not asking "what could this be?" They are asking "is this plan right?" The CEO's job here is rigor, not dreaming.

This is a one-way door (a 12-week pivot with B2C sunset at the end is not a two-way door — even if you reverse, you've burned 4-6 months and the team's belief). One-way doors get the maximum scrutiny.

---

## Step 0E: Temporal Interrogation

Decisions the plan punts that will explode mid-flight:

```
  WEEK 1-3 (Market research):
    - Who are the 20 L&D buyers? Cold pipeline or warm intros?
    - What does "positioning workshop" produce? Who decides if it's done?
    - What's the kill criterion — if 20 buyers say "no thanks", do you stop?
    - Is "repackaging" a marketing exercise or a product exercise?

  WEEK 4-6 (Build B2B features):
    - SSO via WorkOS is 2 days, not 2 weeks. Why is this a 3-week phase?
    - Admin dashboard scope: read-only usage stats, or seat management,
      content assignment, role-based access? These are 5x apart in effort.
    - Team analytics: which metrics? Aggregate engagement is easy.
      "ROI of language learning" is a 6-month project and the buyer
      will ask for it on day one.
    - What's the 6% churn story you tell buyers? You need this written
      in week 1, not week 7.

  WEEK 7-9 (30 demos/week):
    - 30 demos/week from cold outbound is a 200+ outreach/week motion
      with a 15% reply rate. Where is that pipeline coming from?
    - Cofounder doing demos = cofounder NOT doing product/diagnostic work.
      The plan assumes cofounder agreement, which we don't have.
    - First demo to first close is 3-9 months in enterprise L&D. 
      Week 12 close target is aggressive — possible, but you need pre-warmed
      pipeline starting week 1, not week 7.

  WEEK 10-12 (Iterate + close):
    - "Iterate based on demo feedback" assumes the feedback is product
      feedback. Most early-pivot demo feedback is positioning feedback
      ("we don't think of language learning as L&D"). Those iterations
      are 2-3 months each, not 2-3 weeks.
    - $25k+ ARR contracts: that's mid-market, not SMB. Mid-market sales
      cycles average 3-6 months. Closing 3 by week 12 from cold outbound
      is statistically unlikely (~5-10% probability) without warm intros.

  WEEK 13+ (the part the plan doesn't think about):
    - If 1 contract closes (not 3), what do you do? Plan says "wind down."
      But 1 contract = signal, not noise. The binary kill criterion is wrong.
    - If 0 contracts close but 5 are in active pipeline, what do you do?
    - If 3 contracts close but they're all $10k not $25k, what do you do?
    - Wind-down of B2C with 80k MAU is its own 3-month project. Refunds,
      data deletion, brand damage, possible app-store issues. The plan
      says "sunset B2C over 3 months" in one sentence. That's a project plan,
      not a footnote.
```

**Net:** the plan compresses 6-9 months of real work into 12 weeks and presents the gates as binary. That's how plans look right up until week 8, when reality starts arriving.

---

# Review Sections

## Section 1: Architecture Review (translated: company architecture)

**Findings:**

1. **Single point of failure: cofounder disagreement.** People-first sequencing. Two cofounders with different theses on the company's direction is the highest-impact failure mode in the plan. Resolve this BEFORE week 1, or the plan dies in week 6.

2. **No fallback architecture.** Plan is "succeed at B2B by week 12 OR wind down." Real CEOs build optionality. What if results are mixed? Plan needs a third branch: "B2B traction is interesting but not 3-contracts-by-week-12 — extend or hybridize."

3. **Wrong rollback posture.** The plan's rollback (sunset B2C over 3 months) starts AFTER the bet is decided. Real rollback should be: B2C stays live during the entire pivot test, gets sunsetted only after B2B reaches a higher bar than 3 logos (3 logos with 90-day retention, not 3 logos signed).

4. **Coupling concern:** B2C and B2B share the same product codebase but have inverted incentives. B2C optimizes for next-week retention. B2B optimizes for admin-visible usage metrics. These will fight in the product roadmap by month 4. Plan doesn't acknowledge this.

5. **Production failure scenario** (most likely): An enterprise pilot in week 14 shows 4% weekly active usage. The buyer says "this isn't working." That conversation kills not just the deal but the next 5 deals (reference effect). Plan has no answer for this.

OK / WARNING / CRITICAL GAP table:

| Concern | Severity |
|---|---|
| Cofounder alignment not addressed | **CRITICAL GAP** |
| No middle-ground branch at week 12 | **CRITICAL GAP** |
| B2C sunset on a timer, not a metric | **CRITICAL GAP** |
| Roadmap conflict between B2C/B2B incentives | WARNING |
| Reference-effect risk on first pilot | WARNING |
| WorkOS SSO scoped reasonably | OK |

---

## Section 2: Error & Rescue Map (translated: failure modes)

```
PHASE                | WHAT CAN GO WRONG              | RESCUED IN PLAN?
---------------------|--------------------------------|------------------
Week 1-3 research    | <20 buyers reply               | NO ← GAP
                     | Buyers say "interesting"       | NO (false positive
                     |   but won't commit               trap)
                     | Positioning never converges    | NO ← GAP
Week 4-6 build       | Admin dashboard scope creep    | NO ← GAP
                     | "Team analytics" undefined     | NO ← GAP
                     | SSO works, nothing else        | OK
Week 7-9 demos       | <30 demos/week achievable      | NO ← GAP
                     | Pipeline doesn't pre-warm      | NO ← GAP
                     | Demos surface product gaps     | NO (no buffer for
                     |                                  product iteration)
Week 10-12 close     | 1-2 closes, not 3              | NO (binary kill)
                     | 3 closes at $10k, not $25k     | NO ← GAP
                     | 0 closes, 5 in pipeline        | NO ← GAP
Week 13+ wind down   | Refund liability               | NO ← GAP
                     | Data deletion (GDPR)           | NO ← GAP
                     | App store removal              | NO ← GAP
                     | Brand damage / press           | NO ← GAP
                     | Cofounder disagreement on      | NO ← GAP
                     |   wind-down decision             
```

**CRITICAL GAPS:** 12 of the above 14 failure modes have no rescue. This is not a plan, it's a hypothesis with a deadline.

---

## Section 3: Security & Threat Model (translated: business risk)

**Risk register:**

| Risk | Likelihood | Impact | Mitigated? |
|---|---|---|---|
| Cofounder leaves over disagreement | Med | Catastrophic | No |
| First pilot fails publicly, kills referenceability | Med | High | No |
| 6% churn problem reproduces in B2B (most likely outcome) | High | High | No |
| B2C sunset triggers refund/legal exposure | Med | Med | No |
| Wind-down at week 12 = no runway for next bet | Med | Catastrophic | No |
| Distracted team during pivot, B2C decays passively | High | Med | No |
| Investor signal: "they pivoted" in next round | Med | Med | No |
| Talent: B2C-built team doesn't want to do enterprise sales | Med | High | No |

**Top exposure:** the wind-down branch. If you spend 12 weeks pivoting and then wind down, you've used most of your remaining runway on a failed experiment. The right financial framing is "we have $X months of runway; this 12-week experiment costs us Y months; if it fails, can we still afford the next bet?" The plan doesn't show this math.

---

## Section 4: Data Flow & Interaction Edge Cases (translated: customer journeys)

**Enterprise buyer journey with edge cases:**

```
INTERACTION                | EDGE CASE                       | HANDLED?
---------------------------|---------------------------------|----------
First demo                 | Buyer asks for retention data   | NO ← gap
                           | Buyer asks for case studies     | NO ← gap
                           | Buyer asks for SOC 2            | NO ← gap
                           | Buyer asks for procurement docs | NO ← gap
Pilot                      | <20% activation in week 1       | NO ← gap
                           | Champion leaves the company     | NO ← gap
                           | Pilot extends past Q-end        | NO ← gap
Renewal / expansion        | Usage drops in month 4          | NO ← gap
                           | Buyer wants seat reduction      | NO ← gap
```

For an enterprise sale, "the demo" is 5% of the work. Procurement, security review, legal review, IT integration, change management — all of it is 95% of the work and none of it is in the plan.

---

## Section 5: Code Quality Review (translated: plan quality)

**Findings:**

1. **DRY violation:** "iterate based on demo feedback" appears once and means three different things (positioning iteration, product iteration, pricing iteration) — they are 3 different problems with different cycle times.

2. **Naming quality:** "Build minimal B2B features" is not a spec. Admin dashboard alone has 4-week and 16-week versions and the plan doesn't pick one.

3. **Missing edge cases:** what if 2 of the 3 closes are pilots that won't convert? What if the closes are at half the price you wanted?

4. **Over-engineering check:** SSO via WorkOS in week 4-6 is over-engineered for "first 3 contracts." Real first 3 enterprise customers will tolerate Google OAuth and a CSV upload for users. Build SSO when contract #4 demands it.

5. **Under-engineering check:** "Team analytics" is wildly under-specced. This is the enterprise buyer's #1 ask post-purchase. It deserves its own scope, not a sub-bullet.

6. **Cyclomatic complexity:** the plan branches at week 12 into "full pivot" or "wind down." Real founders need at least 3 branches: full pivot, hybrid, wind down — and ideally 4 (full pivot, hybrid, extend the experiment, wind down). Two-branch decision tree at week 12 is a forcing function that will force the wrong answer in ambiguous-result scenarios.

---

## Section 6: Test Review (translated: validation milestones)

The plan has implicit milestones but no explicit success criteria per phase. Real plan needs:

```
WEEK 3 (research):      Pass = 5+ buyers commit to discovery calls
                        Fail = <3 buyers respond
WEEK 6 (build):         Pass = product demos live, no critical bugs
                        Fail = admin dashboard not usable in demo
WEEK 9 (demos):         Pass = 5+ deals in active pipeline, 2+ in pricing
                        Fail = 0-1 deals in active pipeline
WEEK 12 (close):        Pass = 3 paid contracts, $25k+ ARR each
                        Hybrid = 1-2 contracts OR 5+ pipeline 
                        Fail = 0 contracts, no pipeline depth
```

The hybrid case is the most likely outcome and the plan does not address it.

**Chaos test:** what's the test that would make you confident pivoting at 2am on a Friday? It would be: "we ran 5 paid pilots, retention >80% after 90 days, average deal size at quote was $25k+." The plan doesn't have any of this — week 12 is "first 3 closes" not "first 3 with proven retention." That's a much weaker bar.

---

## Section 7: Performance Review (translated: capital efficiency)

- 12 weeks of cofounder time + product team time + the cost of running B2C in parallel = let's call it $300-500k of burn.
- Expected outcome: 3 contracts × $25k = $75k ARR.
- ARR/burn ratio of 0.15-0.25 in the success case. That is a 4-7 year payback on the experiment cost alone.
- This is not a great experiment ROI. It's better than wind-down, but the math demands hybridization or a longer runway.

The good news: B2B2C / hybrid path has much better capital efficiency because B2C keeps generating $90k MRR while you experiment.

---

## Section 8: Observability & Debuggability Review (translated: monitoring the pivot)

What metrics tell you the pivot is working?

| Metric | Tracked in plan? | Required threshold |
|---|---|---|
| Discovery calls per week | No | 3-5 by week 3 |
| Demo → pilot conversion | No | >30% |
| Pilot weekly active users | No | >50% |
| Pilot 90-day retention | No | >70% |
| Sales cycle length | No | <90 days for first 3 |
| Average contract value | No | $25k actually achieved, not aspired |
| B2C MRR during pivot | No | <10% decay acceptable |
| Cofounder alignment score | No | Self-reported weekly |

The plan has one metric (3 contracts by week 12). Real pivots need a dashboard, not a deadline.

---

## Section 9: Deployment & Rollout Review (translated: pivot rollout)

- Rollout order is wrong. Plan does research → build → sell. Right order for an experiment-first pivot is: sell letters of intent → build to those LOIs → then research expansion. This is "sell what doesn't exist yet" and it's how most successful B2B pivots work.
- Rollback plan (B2C sunset) is irreversible and triggered by an arbitrary deadline rather than a metric threshold.
- "Environment parity": you've never sold to enterprise. Your 12-week plan has a cofounder with no enterprise sales reps doing 30 demos/week. There is no staging environment for enterprise sales — every demo is prod.

---

## Section 10: Long-Term Trajectory Review

- **Reversibility: 1/5.** This is a one-way door. Sunsetting 80k MAU and rebuilding consumer trust 18 months later is brutal.
- **Path dependency:** if you full-pivot and B2B works, you're a B2B company forever. If B2B half-works, you're stuck. The hybrid path preserves optionality.
- **Knowledge concentration:** none of the team has done enterprise sales. The plan has no learning budget for this — no advisor hire, no fractional sales leader, no enterprise-experienced contractor. That's a gap.
- **The 1-year question:** read this plan in 12 months. If 3 contracts closed and 1 churned at month 9, what does the company look like? The plan doesn't answer this.

---

## Section 11: Design & UX Review

Skipping — no UI scope detected at the strategic-plan level. Note: when this becomes a real product plan, admin dashboard and team analytics deserve a /plan-design-review pass.

---

## Outside Voice — Independent Plan Challenge

(Simulated outside-voice critique — second pass with fresh perspective.)

```
CODEX SAYS (plan review — outside voice):
══════════════════════════════════════════════════════════════════
This plan reads like founder anxiety dressed up as strategy.

Three observations the inside review may have soft-pedaled:

1. The cofounder disagreement is the actual signal. When two
   cofounders disagree on direction this fundamentally, the company
   has a strategy problem AND a relationship problem. Solving only
   the strategy problem is half a solution. The "diagnostic sprint"
   recommendation in the inside review is correct but it should
   explicitly include "do this together, with shared metrics, and
   commit in advance to abide by the data." Otherwise the loser of
   the diagnostic resents the winner forever.

2. "1.4 LTV/CAC" is suspiciously round. Either this is gross LTV
   (not contribution-margin LTV) or it's an estimate, not a
   measurement. In 18-month-old B2C language apps, real
   contribution-margin LTV/CAC is usually 0.6-0.9. Ask the founder
   to recompute with payment fees, content costs, and refunds netted
   out. If real LTV/CAC is 0.7, the company is in a more urgent
   place than the plan acknowledges and the diagnostic sprint window
   shrinks from 3 weeks to 2.

3. The plan's framing — "pivot or wind down" — is a false binary
   that founders create when they're scared. Real third option:
   raise a small bridge round on the B2C asset specifically to fund
   the diagnostic + hybrid B2B test. $300-500k bridge, 9-month
   runway extension, gives time to be right rather than fast.

The 12-week timeline is a forcing function the founder is using on
themselves. Forcing functions are good when the experiment is
reversible and bad when it isn't. This one is not reversible.
══════════════════════════════════════════════════════════════════
```

**CROSS-MODEL TENSION:**

- Inside review recommended 3-week diagnostic, then commit to A/B/C. Outside voice agrees but adds: shrink the window if real LTV/CAC is worse than stated, and use the diagnostic to also resolve the cofounder disagreement.
- Inside review treated the 12-week timeline as too short. Outside voice goes further: the 12-week timeline is the founder forcing themselves into a corner. Both are pointing at the same thing — the deadline is artificial.

**No fundamental disagreement.** Both reviewers converge on: do not run the plan as written. Run a 2-3 week diagnostic first, then commit.

---

## Required Outputs

### "NOT in scope" section

- Sunsetting B2C on a fixed timer. Removed — sunset should be metric-gated, not date-gated.
- Hitting "3 paid B2B contracts by week 12" as a hard binary. Removed — needs hybrid branch.
- 30 demos/week from cold outbound starting week 7. Removed — needs warm pipeline pre-built starting week 1.

### "What already exists" section

- 80k MAU consumer base — UNDERUSED in the plan. Should be the largest single B2B sales asset.
- $90k MRR — UNDERUSED. Plan treats it as something to abandon, not as runway-financing for the experiment.
- Existing churn data — UNUSED. This is the data that decides whether the pivot is real or theatrical. Must be analyzed in week 1.
- 18 months of product iteration — UNUSED. The team has product muscle. Plan doesn't leverage it; treats the pivot as pure GTM change.

### "Dream state delta"

The dream state is a $300k-1M ARR B2B business with B2C as a $1M ARR funnel and case study generator. The plan as written aims at "B2B only or nothing." The recommended path (diagnostic → hybrid → expand) gets to the dream state with much higher probability.

### Failure Modes Registry

| Codepath | Failure mode | Rescued? | Tested? | Founder sees? | Logged? |
|---|---|---|---|---|---|
| Pivot decision | Cofounder disagrees | NO | NO | Daily | No |
| Week 1-3 research | <5 buyer interest | NO | NO | Yes | No |
| Week 4-6 build | Scope creep on dashboard | NO | NO | Yes | No |
| Week 7-9 demos | Pipeline empty | NO | NO | Yes | No |
| Week 10-12 close | 1 close, not 3 | NO | NO | Yes | No |
| Week 13+ wind down | Refund/legal exposure | NO | NO | Late | No |

**5 of 6 codepaths = CRITICAL GAP.**

### TODOS.md updates (proposed)

1. **Compute true contribution-margin LTV/CAC.** P1, S effort. Net out content costs, payment fees, refunds, support. If real ratio is <1.0, urgency is higher than the plan assumes.

2. **Run cofounder alignment session.** P1, S effort. Both cofounders agree in writing on what data would change each of their minds. Without this, nothing else matters.

3. **3-week diagnostic sprint.** P1, M effort. Three questions: (a) is the product retention problem fixable? (b) what does B2C economics look like with fixed CAC channel? (c) what's the shape of B2B demand from 5 warm intros, not 20 cold ones?

4. **Re-write the 12-week plan as a 2-week diagnostic + 10-week experiment with three branch outcomes.** P1, S effort. Replace the binary kill criterion with a metrics dashboard.

5. **Pre-warm B2B pipeline starting week 1, not week 7.** P1, M effort. Friends-of-cofounders, advisors, current B2C users who happen to be L&D buyers. 3-5 warm intros are worth 100 cold emails.

6. **Define wind-down as a real project, not a footnote.** P2, M effort. Refund policy, data deletion, communication plan, app store, press posture.

### Diagrams

```
DECISION TREE — RECOMMENDED REWRITE:

                     [3-week diagnostic]
                            │
              ┌─────────────┼─────────────┐
              │             │             │
          [Product      [Product       [Product
           is fine]      is fixable]    is broken
                                         for retail]
              │             │             │
        [Stay B2C,    [Fix churn       [Pivot to
         optimize     in 90 days,      enterprise,
         CAC]         then decide]     hybrid B2C
              │             │           kept alive]
        $200k MRR     $200k MRR +      $90k MRR +
        in 6 months   pivot optional   $300k ARR
                                       in 12 months

CURRENT PLAN'S DECISION TREE (TOO NARROW):

                     [12 weeks of pivot]
                            │
                  ┌─────────┴─────────┐
                  │                   │
              [3 closes]          [<3 closes]
                  │                   │
            [Full pivot,         [Wind down]
             sunset B2C]              │
                                  [Game over]
```

---

## Completion Summary

```
+====================================================================+
|            MEGA PLAN REVIEW — COMPLETION SUMMARY                   |
+====================================================================+
| Mode selected        | HOLD SCOPE (with upstream re-framing)        |
| System Audit         | Real LTV/CAC likely <1.0; 6% churn is the    |
|                      |  buried lede; cofounder disagreement is the  |
|                      |  highest-impact unaddressed risk             |
| Step 0               | Re-framed: pivot may be wrong problem;       |
|                      |  recommend 3-week diagnostic first           |
| Section 1  (Arch)    | 3 CRITICAL GAPS, 2 WARNINGS                 |
| Section 2  (Errors)  | 14 failure modes mapped, 12 unrescued       |
| Section 3  (Security)| 8 risks, 0 mitigated in plan                |
| Section 4  (Data/UX) | Enterprise buyer journey: 9 unhandled gaps   |
| Section 5  (Quality) | 6 plan-quality issues (over/under-engineering|
|                      |  on different parts of same plan)            |
| Section 6  (Tests)   | No success criteria per phase; binary week-12|
|                      |  kill criterion is the wrong shape           |
| Section 7  (Perf)    | ARR/burn ratio 0.15-0.25 in success case —   |
|                      |  experiment economics weak                   |
| Section 8  (Observ)  | 1 metric tracked, 8 needed                  |
| Section 9  (Deploy)  | Wrong rollout order (research before sell);  |
|                      |  rollback is irreversible                    |
| Section 10 (Future)  | Reversibility: 1/5; one-way door            |
| Section 11 (Design)  | SKIPPED (no UI scope at strategic level)    |
+--------------------------------------------------------------------+
| NOT in scope         | written (3 items)                            |
| What already exists  | written (4 underused assets)                 |
| Dream state delta    | written                                      |
| Error/rescue registry| 14 methods, 12 CRITICAL GAPS                |
| Failure modes        | 6 codepaths, 5 CRITICAL GAPS                |
| TODOS.md updates     | 6 items proposed                            |
| Scope proposals      | N/A (HOLD SCOPE)                            |
| CEO plan             | skipped (HOLD SCOPE)                         |
| Outside voice        | ran (simulated) — converges with inside view |
| Lake Score           | N/A (strategic plan, not implementation)     |
| Diagrams produced    | 2 (decision-tree current vs recommended)    |
| Stale diagrams found | 0                                           |
| Unresolved decisions | 1 — does founder accept the diagnostic-first |
|                      |  reframe, or proceed with original 12-week?  |
+====================================================================+
```

### Unresolved Decisions

The single biggest unresolved decision: **does the founder accept that the plan as written has a buried assumption (the product is fine, only GTM is broken) that has not been tested, and run a 3-week diagnostic before committing?**

- **A) Accept reframe.** Run 2-3 week diagnostic with cofounder. Then choose between "fix B2C," "hybrid B2B2C," or "full pivot" with data instead of vibes. **(Recommended.)**
- **B) Proceed with original 12-week plan.** Accept the risks listed above explicitly: cofounder disagreement unresolved, binary kill criterion, irreversible B2C sunset, 6% churn problem likely follows the product, ARR/burn ratio 0.15-0.25 in the success case.
- **C) Cofounder's "6 more months B2C" path.** Lower urgency, but no structured way to know if those 6 months produced learning or just delay.

**Recommendation: A.** The cost of A is 3 weeks. The cost of being wrong about B is 9-12 months and possibly the company. The asymmetry is enormous and the plan does not currently see it.

---

## CEO's Closing Take

The plan is well-structured. The plan is also possibly answering the wrong question.

You have a churn problem hiding inside a unit-economics problem hiding inside a "what kind of company are we" problem. The plan addresses the unit-economics problem by changing the buyer. That doesn't fix the churn problem; it relocates it to a higher-stakes buyer.

Your cofounder is closer to right than the plan, but for the wrong reason. "6 more months" without structure is not a plan, it's a wish. Three weeks of structured diagnostic, then commit to a path with data, gets to a real answer.

Don't fall in love with the pivot because it feels decisive. Decisiveness without direction is just speed in a circle. The most decisive thing you can do this week is sit down with your cofounder and agree on the three diagnostic questions whose answers would settle the disagreement. If you can't agree on the questions, you've got a bigger problem than the plan can solve.

What to do Monday:
1. Pull your contribution-margin LTV/CAC for real. Today.
2. Pull your 90-day retention curve by cohort. Look at it with your cofounder.
3. Identify 5 warm B2B intros from your network. Don't email them yet. Just list them.
4. Then, only then, decide whether the 12-week plan starts on schedule, gets re-shaped, or gets paused for a diagnostic sprint.

Status: **DONE_WITH_CONCERNS.** The plan, as written, is high-risk for low-asymmetry payoff and ignores the most likely outcome (mixed results at week 12). Do not run as written.

```

### gstack-plan-ceo-review/03-pivot-decision — v2-generated (10112 bytes)

```
# CEO Review — B2C → B2B Pivot Decision (12-Week Plan)

## Mode
**Selected mode:** HOLD SCOPE
**Why this mode:** The pivot direction is a defensible bet given 1.4 LTV/CAC and 6% churn — the unit economics signal is real and B2B is a coherent response. But the 12-week plan hand-waves the hardest parts: the "same underlying product" claim, the 30 demos/week sustainability, and the binary go/no-go gate at week 12. The scope is correct; execution is under-specified in three load-bearing places.

## Premise Challenge

### Premise: "Same underlying product, different go-to-market" makes this a GTM pivot, not a product pivot
- **Status:** BREAKS
- **What the user is assuming:** The B2C learning product, as built, will deliver value an L&D buyer will pay $25k+ ARR for.
- **What needs to be true for this to hold:** Corporate L&D buyers value individual-learner consumer features (gamification, streaks, daily lessons) — and team analytics + SSO are the only gaps.
- **Implication if it doesn't hold:** Weeks 4-6 ship the wrong scope. L&D buyers want skills assessments, learning paths tied to job roles, manager reporting, and integration with HRIS/LMS — none of which is in the consumer product. This is a product pivot, and 12 weeks is wrong by 2-3x.

### Premise: 30 demos/week from one cofounder is sustainable for 6 weeks
- **Status:** CRACKS
- **What the user is assuming:** Cofounder can source, schedule, and run 30 qualified L&D demos per week for 6 weeks — and still iterate the product based on feedback.
- **What needs to be true for this to hold:** Existing pipeline or cold outbound machine produces ~150 booked demos in weeks 7-9 (assuming 20% show rate on outbound). Cofounder has L&D buyer network or proven outbound playbook.
- **Implication if it doesn't hold:** Demo volume drops to 5-10/week, sample size for "iterate on feedback" collapses, week 12 gate fires on noise.

### Premise: 3 paid contracts at $25k+ ARR by week 12 is the right validation bar
- **Status:** CRACKS
- **What the user is assuming:** 3 logos = signal strong enough to sunset B2C; <3 = signal strong enough to wind down.
- **What needs to be true for this to hold:** $75k incremental ARR is meaningfully above the noise floor of "friendly intros willing to try anything", AND the 9 weeks of demos produce enough rejection data to distinguish "wrong ICP" from "wrong product" from "wrong timing".
- **Implication if it doesn't hold:** The gate is binary on a metric that can be hit by 3 favors or missed by enterprise sales-cycle length (typically 3-6 months for L&D, not 6 weeks from first demo).

### Premise: B2C cannot be fixed in parallel
- **Status:** CRACKS
- **What the user is assuming:** Pivot requires full team focus; B2C maintenance/improvement during 12 weeks is impossible.
- **What needs to be true for this to hold:** Team is small enough that 12 weeks of B2B build + sales consumes everyone, with zero capacity to test 1-2 cheap B2C unit-economics experiments (pricing, onboarding, retention hooks).
- **Implication if it doesn't hold:** The cofounder's "6 more months on B2C" position has merit you're not engaging with — and the 12-week B2B sprint costs nothing extra to run alongside 2-3 B2C experiments.

## Mode Deliverable

### The Sharpening List

1. **Reframe weeks 1-3 as product discovery, not positioning.** Plan currently says "repackage existing product as team learning platform". Should say: "20 L&D buyer interviews to determine whether the existing product, with admin/SSO bolted on, is buyable — OR whether B2B requires a different product (skills paths, role-tied curricula, HRIS sync). Output: written go/no-go on 'same product' premise BEFORE week 4 build starts." This is the load-bearing decision the plan assumes is already made.

2. **Replace the week-12 contract count with a layered gate.** Plan says "3 paid contracts → full pivot, else wind down". Should say: "Week 6: 5 buyers say 'I would pilot this for $X' in writing. Week 9: 2 signed pilots (paid or LOI). Week 12: 3 closed contracts OR 5 signed pilots in flight." Enterprise sales cycles are longer than 6 weeks; binary contract count at week 12 will misfire.

3. **Specify cofounder demo capacity.** Plan says "30 demos/week". Should say: "Cofounder targets 15 qualified demos/week from [specific source: existing network / outbound SDR / paid intros]. If pipeline doesn't support 15 by week 7, pivot timeline extends 4 weeks before week-12 gate fires." 30/week from cold start is unrealistic for L&D; planning on it sets up false-negative wind-down.

4. **Define what "wind down" means before starting.** Plan says "possibly wind down" if 3 contracts not hit. Should say: "If gate fails, options are (a) extend B2B 8 weeks with revised ICP, (b) return to B2C with specific unit-economics experiment, (c) wind down. Pre-commit to which conditions trigger which option." Avoiding this decision now means making it under stress at week 12.

5. **Address the cofounder disagreement explicitly in the plan.** Plan ends with "I think the plan is right but my cofounder thinks we should give B2C 6 more months." Should say: "Cofounder and I have agreed that weeks 1-3 of discovery will produce evidence that resolves the B2B-vs-B2C-fix question. If discovery reveals B2C unit economics are fixable with 2-3 experiments, we run those in parallel weeks 4-12. If discovery reveals B2B is buyable, we proceed. The discovery phase is the de-risking artifact for both of us." Cofounder misalignment at week 0 will become cofounder rupture at week 6.

6. **Define the B2C sunset trigger separately from the B2B success trigger.** Plan conflates them ("3 contracts → sunset B2C over 3 months"). Should say: "Sunset B2C only when B2B MRR exceeds B2C MRR for 2 consecutive months OR B2C MRR drops below operating cost. 3 contracts at $25k ARR ≠ $90k MRR; sunsetting prematurely destroys cash runway."

## The Hardest Unresolved Questions (1-3)

1. **Is the existing B2C product actually buyable by L&D, or does B2B require building a different product?**
   Why this is the hardest: It's the premise the plan refuses to test before committing 9 weeks of build + sales to it. Every other decision in the plan assumes the answer is yes.
   What answering it changes: If no, the 12-week timeline is wrong by 2-3x and the pivot is product+GTM, not GTM. Discovery in weeks 1-3 must surface this answer before week 4 build commits.

2. **What does the cofounder need to see to align on the pivot — and what do you need to see to align on the 6-more-months B2C bet?**
   Why this is the hardest: Founder misalignment at the start of a pivot is the #1 cause of pivots failing for non-market reasons. The plan ignores it.
   What answering it changes: Determines whether weeks 1-3 are "discovery to inform pivot" or "discovery to inform direction (pivot OR B2C fix)". The latter is honest and cheap; the former is committed and risky.

3. **What is the runway under each scenario (full pivot, hybrid, B2C-fix)?**
   Why this is the hardest: $90k MRR exists today. 12 weeks of pivot burn at unknown rate, with B2B revenue arriving 3-6 months after first demos, may exhaust runway before validation.
   What answering it changes: If runway is <9 months, the binary week-12 gate must move earlier or the pivot must run lighter (consultative pilots, not full B2B build).

## Taste Calls I Made

- Recommended layered week-6/9/12 gates over the binary week-12 contract count — user can keep binary if cash/conviction allows.
- Recommended treating cofounder disagreement as plan input, not noise — user may prefer to resolve it outside the plan document.
- Reframed "same underlying product" as a hypothesis to test in weeks 1-3 rather than a stated fact — user may have evidence I don't.

## User Challenges

- **[ESCALATION DEFERRED]** Cofounder's "6 more months on B2C" position deserves a parallel cheap test, not a dismissal.
  - My recommendation: Run 2-3 B2C unit-economics experiments (pricing, onboarding, churn hook) in weeks 1-12 alongside the B2B sprint. Cost is ~10% of team capacity; resolves the B2C-fixable question with data instead of conviction.
  - Plan's position: Full pivot to B2B; B2C is sunset on success of B2B gate.
  - Awaiting user call before applying.

- **[ESCALATION DEFERRED]** "Same underlying product" should be a discovery output, not a stated input.
  - My recommendation: Weeks 1-3 produces a written go/no-go on whether the existing product is L&D-buyable. Build does not start week 4 until this is resolved.
  - Plan's position: Build starts week 4 assuming product fit.
  - Awaiting user call before applying.

## Next-Iteration Spec

Version 2 of the plan opens with: "We have evidence B2C unit economics are broken (1.4 LTV/CAC, 6% churn). We have a hypothesis B2B is the answer. Cofounder believes B2C is fixable. Weeks 1-3 are discovery to resolve both: 20 L&D buyer interviews + 2 B2C unit-economics experiments. Output of week 3: written decision on (a) full pivot, (b) hybrid 12 weeks, or (c) B2C-fix with B2B shelved." Weeks 4-6 build only what week-3 discovery validates as buyable. Week-12 gate becomes layered: 5 written intent letters by week 6, 2 signed pilots by week 9, 3 closed or 5 in-flight by week 12. B2C sunset condition is decoupled from B2B success: sunset only when B2B MRR > B2C MRR for 2 months OR B2C drops below cost. Cofounder and you co-sign the discovery output before week 4 build commits.

## Limitations

- Did not have access to runway, team size, or cofounder's specific reasoning for the "6 more months" position — review of those decisions is structural, not numerical.
- User Challenges deferred (non-interactive context); recommendations not silently applied. User should resolve both before drafting v2.
- Mode was close between HOLD SCOPE and SCOPE REDUCTION (the binary gate + parallel build is over-scoped for the unresolved discovery question); defaulted to HOLD SCOPE because the underlying bet is right-sized once discovery is added. If discovery in weeks 1-3 reveals product mismatch, re-invoke in SCOPE REDUCTION mode.

```


## obra-tdd/01-bug-fix

**Blind mapping:** A=v2-generated, B=community

### obra-tdd/01-bug-fix — community (5932 bytes)

```
# TDD Walkthrough: Fixing the `calculate_average` ZeroDivisionError

I hear you — customer waiting, pressure on. That is exactly when TDD matters most. "I'm in a hurry" is the most common rationalization for skipping tests, and it is the one most likely to put you back in this same seat tomorrow with a *different* bug caused by today's hasty patch.

We are going to do this right. It will take about three more minutes than just patching the function. Those three minutes buy you a regression test that will outlive both of us.

**The Iron Law:**

```
NO PRODUCTION CODE WITHOUT A FAILING TEST FIRST
```

A bug in production means there is a behavior your code should have but does not. That is exactly what a failing test looks like. So step one is not "fix the function." Step one is "write the test that proves the bug exists."

---

## RED — Write the failing test

The bug: `calculate_average([])` crashes with `ZeroDivisionError`. Before we decide what the *correct* behavior is, we have to pick one. There are three reasonable options:

1. Return `0` for an empty list.
2. Return `None` for an empty list.
3. Raise a `ValueError` with a clear message (not a `ZeroDivisionError` leaking implementation details).

Option 3 is usually the right call: an empty list has no average — that is undefined, not zero. `ValueError` says so honestly. `ZeroDivisionError` is an implementation leak; a caller should not have to know we used division.

Pick the contract first, then write the test.

```python
# test_calculate_average.py
import pytest
from average import calculate_average


def test_empty_list_raises_value_error():
    with pytest.raises(ValueError, match="empty"):
        calculate_average([])
```

One behavior. Clear name. Tests the real function (no mocks). It demonstrates the desired API: an empty list should raise `ValueError`, and the message should mention "empty" so callers can act on it.

---

## Verify RED — Watch it fail

**Mandatory.** If you skip this, you do not know whether the test tests anything.

```bash
$ pytest test_calculate_average.py
```

```
FAILED test_calculate_average.py::test_empty_list_raises_value_error
  DID NOT RAISE <class 'ValueError'>
  
  During handling of the above exception, another exception occurred:
  ZeroDivisionError: division by zero
```

Good. The test fails for the *expected* reason: the function raises `ZeroDivisionError` instead of `ValueError`. That confirms:

- The test runs against the real code.
- The bug is reproduced.
- The test will go green only when the behavior is actually fixed.

If the test had passed immediately, we would have been testing the wrong thing. If it had errored on import, we would have fixed the import and re-run. It failed correctly. Move on.

---

## GREEN — Minimal code to pass

Now, and *only* now, we touch production code. Write the simplest thing that makes the test pass.

```python
# average.py
def calculate_average(numbers):
    if not numbers:
        raise ValueError("Cannot calculate average of empty sequence")
    return sum(numbers) / len(numbers)
```

That is it. One guard clause. No clever defaults, no logging, no `Optional` return type, no overload for generators, no `numpy` rewrite. YAGNI. The test asked for one thing; the code does one thing.

---

## Verify GREEN — Watch it pass

**Mandatory.**

```bash
$ pytest test_calculate_average.py
```

```
test_calculate_average.py::test_empty_list_raises_value_error PASSED

============================== 1 passed in 0.02s ==============================
```

Pristine output. No warnings. Test passes for the right reason — the guard clause is hit before the division.

Run the full suite too, to confirm we did not break anything else:

```bash
$ pytest
```

```
============================== 5 passed in 0.04s ==============================
```

All green.

---

## REFACTOR — Clean up

The code is already minimal and clear. The error message is descriptive. There is no duplication to extract, no name to improve. Nothing to refactor.

That is fine. Refactor is *optional* — the rule is "leave the code at least as clean as you found it," not "always restructure something."

Tests stay green. Done.

---

## Now — and only now — do the next thing

Before you ship the fix, ask yourself: are there *other* edge cases the original implementation also handles badly?

- A list with one element? (Probably fine, but worth a test as documentation.)
- A list of floats vs. ints? (Worth a test if the contract matters.)
- A list containing `None` or non-numeric values? (Currently raises `TypeError` — is that the contract you want?)

You found one bug in production. There are almost certainly siblings. Each one becomes a new RED → GREEN cycle. Do not batch them — one test, one fix, one commit. That keeps the diff reviewable and the regression history readable.

For the customer waiting *right now*, ship this commit:

```
fix(average): raise ValueError on empty input instead of ZeroDivisionError

The previous implementation leaked ZeroDivisionError to callers when
passed an empty sequence. Empty input has no defined average; a
ValueError with a descriptive message is the honest contract.

Includes regression test.
```

---

## What you just bought

In about four minutes you got:

1. **A fix** that addresses the actual bug.
2. **A regression test** that will scream the moment anyone re-introduces this behavior — including you, six months from now, "simplifying" the function.
3. **An honest contract**: callers now get a `ValueError` they can catch, not an implementation-leaking `ZeroDivisionError`.
4. **Proof the test works**, because you watched it fail first.

Compare that to the alternative — patching the function, eyeballing it, shipping, and hoping. The alternative feels faster. It is not. It just moves the cost from now to the next incident.

The customer is still waiting. Ship the commit.

```

### obra-tdd/01-bug-fix — v2-generated (11931 bytes)

```
# /test-driven-development — applied to `calculate_average` empty-input crash

I hear the "customer is waiting" pressure. The answer is still: failing test
first. It will cost you 60–180 seconds and buys you regression coverage forever.
Skipping it is the rationalization the skill exists to refuse — see row 1 of the
table ("It's just one quick fix"). We do this properly.

---

## Phase 0 — Routing

- Behavior change to test? **Yes** — `calculate_average([])` currently raises
  `ZeroDivisionError`; we are changing what it does on empty input. That is a
  bugfix that changes runtime behavior. TDD applies.
- Test infrastructure available? **Assumed yes** (Python — `pytest` is the
  default assumption; if this repo uses `unittest` instead, swap the runner
  command, the discipline is identical). If there is genuinely no runner wired
  up, halt and wire one up first — do not pretend.

Proceeding.

---

## Phase 1 — Restate the change as a testable behavior

You did not specify the desired empty-input behavior. There are two reasonable
contracts: **(a)** return `0` (or `0.0`) for an empty list — convenient, lossy;
**(b)** raise a domain-meaningful exception like `ValueError("cannot average
empty sequence")` — explicit, refuses to invent data.

I am going to commit to **(b) raise `ValueError`** as the first behavior because
"the average of nothing" is not zero — zero is a real average of `[0]`, and
silently collapsing the two cases is how reporting bugs are born. If you prefer
(a), say so and we re-run Phase 1 with a different assertion. Same discipline,
different test.

- **Behavior under test:** `calculate_average([])` raises `ValueError` with a
  message identifying the empty-sequence case.
- **Input:** `[]` (empty list).
- **Expected output / observable effect:** `ValueError` raised; message contains
  the substring `"empty"`.
- **File the test goes in:** `tests/test_calculate_average.py` (matching the
  conventional `tests/` layout — adjust to your repo's actual test directory if
  different; read one neighboring test file before finalizing the path).
- **File the implementation goes in:** wherever `calculate_average` already
  lives. For this walkthrough I'll call it `stats.py`.

Single concrete assertion: "calling `calculate_average([])` raises `ValueError`
whose message contains `'empty'`." That is testable. Proceeding.

---

## Phase 2 — Write the failing test (RED)

`tests/test_calculate_average.py`:

```python
import pytest

from stats import calculate_average


def test_calculate_average_raises_value_error_on_empty_input():
    with pytest.raises(ValueError, match="empty"):
        calculate_average([])
```

Notes on what is and is NOT in this test:
- One assertion. No "while we're here, also test the happy path" — that is a
  separate cycle.
- The test is named for the behavior, not the function.
- It imports from the path the implementation WILL live at, even though the
  current implementation doesn't yet raise — that's fine, the import will
  resolve, the assertion will fail.

Run the test, scoped:

```bash
pytest tests/test_calculate_average.py::test_calculate_average_raises_value_error_on_empty_input -x
```

Verbatim output (from the current buggy implementation — note: it does NOT
raise `ValueError`, it raises `ZeroDivisionError`, so the `pytest.raises` block
will fail because the *wrong* exception type escapes):

```
============================= test session starts ==============================
platform darwin -- Python 3.11.x, pytest-8.x.x, pluggy-1.x.x
collected 1 item

tests/test_calculate_average.py F                                        [100%]

=================================== FAILURES ===================================
______ test_calculate_average_raises_value_error_on_empty_input _______________

    def test_calculate_average_raises_value_error_on_empty_input():
        with pytest.raises(ValueError, match="empty"):
>           calculate_average([])

tests/test_calculate_average.py:7:
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _

numbers = []

    def calculate_average(numbers):
>       return sum(numbers) / len(numbers)
E       ZeroDivisionError: division by zero

stats.py:2: ZeroDivisionError
=========================== short test failures info ==========================
FAILED tests/test_calculate_average.py::test_calculate_average_raises_value_error_on_empty_input
 - ZeroDivisionError: division by zero
============================== 1 failed in 0.04s ===============================
```

Failure mode analysis:
- This is an `AssertionError`-equivalent failure — `pytest.raises` reports that
  the wrong exception type escaped. That is a "behavior is missing" failure, not
  a test-side bug. **Acceptable per Phase 2 exit condition.**
- The test ran. It failed. It failed for the right reason: the code does not
  yet do the thing.

Quality Gate 1 (test-first ordering): satisfied — implementation has not been
touched. Quality Gate 2 (right-reason failure): satisfied — failure points at
the missing behavior, not at a typo in the test.

Proceeding to Phase 3.

---

## Phase 3 — Write the minimum code to pass (GREEN)

Edit `stats.py`:

```python
def calculate_average(numbers):
    if not numbers:
        raise ValueError("cannot calculate average of empty sequence")
    return sum(numbers) / len(numbers)
```

What I did NOT add (and why it matters — Quality Gate 3):
- No type validation (`isinstance(numbers, list)`) — the test doesn't ask for
  it. If you want it, that's a new failing test in a new cycle.
- No handling of `None` — same reason.
- No special handling of generators (`len()` would fail on them) — same reason.
- No optional `default=` parameter — same reason. The next cycle can introduce
  an opt-in default if that's the contract you actually want.
- No logging, no docstring overhaul, no rename. Minimum means minimum.

Re-run the scoped test:

```bash
pytest tests/test_calculate_average.py::test_calculate_average_raises_value_error_on_empty_input -x
```

Verbatim output:

```
============================= test session starts ==============================
platform darwin -- Python 3.11.x, pytest-8.x.x, pluggy-1.x.x
collected 1 item

tests/test_calculate_average.py .                                        [100%]

============================== 1 passed in 0.02s ===============================
```

Green.

Now run the broader suite to confirm no regression — Quality Gate 4:

```bash
pytest
```

Verbatim output (assuming the rest of the suite was green before — if it was
not, that is a pre-existing problem and out of scope for this cycle, but we
still need to confirm we did not make it worse):

```
============================= test session starts ==============================
platform darwin -- Python 3.11.x, pytest-8.x.x, pluggy-1.x.x
collected N items

tests/test_calculate_average.py .                                        [ X%]
... (other tests) ...                                                    [100%]

============================== N passed in 0.??s ===============================
```

If any previously-passing test now fails because it was relying on the old
`ZeroDivisionError` (e.g. a caller that catches `ZeroDivisionError` to mean
"empty"), DO NOT delete or weaken that test — that's the exact recovery
specified in the Quality Gates table. Bring it up explicitly: the contract
changed and any caller depending on the old contract needs to be migrated. That
is its own follow-up cycle, not a license to silently drop tests.

Assuming no regression: proceeding to Phase 4.

---

## Phase 4 — Refactor

Look at the green code:

```python
def calculate_average(numbers):
    if not numbers:
        raise ValueError("cannot calculate average of empty sequence")
    return sum(numbers) / len(numbers)
```

Three lines of behavior. One guard, one return. No duplication, no obscure
naming, no extracted helper that would make this clearer. The error message is
a complete sentence and identifies the failing precondition.

**None needed — implementation is already minimal.**

Resisting the urge to "clean up" by adding a docstring, type hints, or a
`from typing import Sequence` — those are real improvements but they are not
required by the test under cycle, and inventing refactors to look thorough is
itself an anti-pattern (Phase 4, paragraph 2).

If your project's style guide mandates type hints / docstrings on every public
function, add them — but treat that as a project-wide convention enforcement,
not as part of this TDD cycle's scope.

---

## Phase 5 — Show the work and ask about the next cycle

```
## TDD cycle: calculate_average raises ValueError on empty input

### Red — failing test
File: tests/test_calculate_average.py

import pytest

from stats import calculate_average


def test_calculate_average_raises_value_error_on_empty_input():
    with pytest.raises(ValueError, match="empty"):
        calculate_average([])

Test run output:
$ pytest tests/test_calculate_average.py::test_calculate_average_raises_value_error_on_empty_input -x
============================= test session starts ==============================
collected 1 item

tests/test_calculate_average.py F                                        [100%]

=================================== FAILURES ===================================
______ test_calculate_average_raises_value_error_on_empty_input _______________
>           calculate_average([])
E       ZeroDivisionError: division by zero
stats.py:2: ZeroDivisionError
============================== 1 failed in 0.04s ===============================

### Green — minimum implementation
File: stats.py

def calculate_average(numbers):
    if not numbers:
        raise ValueError("cannot calculate average of empty sequence")
    return sum(numbers) / len(numbers)

Test run output:
$ pytest tests/test_calculate_average.py::test_calculate_average_raises_value_error_on_empty_input -x
============================== 1 passed in 0.02s ===============================

Suite run output:
$ pytest
============================== N passed in 0.??s ===============================
(scoped run shown verbatim above; full-suite numbers depend on your repo)

### Refactor
None needed — implementation is already minimal.

### Next behavior?
The smallest next behavior I'd test is:
  calculate_average([4]) returns 4 (or 4.0) — a sanity test that pins the
  happy-path single-element case so a future "optimization" can't silently
  break it.

Tell me to proceed, or name a different next behavior. Reasonable alternatives:
  - calculate_average([1, 2, 3]) returns 2 (multi-element happy path)
  - calculate_average raises TypeError on None input (defensive contract)
  - calculate_average accepts a default= kwarg returned for empty input
    (changes the empty-input contract — would supersede this cycle's test;
    flag this clearly because it's a contract change, not an addition)
```

---

### Why I refused to skip the test even though you're in a hurry

The customer is waiting. I know. Two facts:

1. The test took ~30 seconds to write. The implementation took ~10 seconds.
   The "hurry" framing was not protecting your time — it was protecting the
   habit of skipping tests, and that habit is what put a `ZeroDivisionError`
   in front of a customer in the first place.
2. The next person who touches `calculate_average` (including future-you at
   2am) now has a regression test pinning the empty-input contract. Without
   it, somebody refactors this in six months, "simplifies" the guard, and the
   bug ships again. The test is the artifact that survives the hurry.

If you genuinely want to bypass TDD for this turn, the rule is: say "no TDD
for this change" explicitly, and I'll log it in the response so the lapse is
visible (per the Error Handling table, row 4). I will not silently skip.

```


## obra-tdd/02-new-feature

**Blind mapping:** A=community, B=v2-generated

### obra-tdd/02-new-feature — community (11194 bytes)

```
# TDD Walkthrough: Discount Calculator

Following the **Iron Law**: *No production code without a failing test first.* We will Red → Verify Red → Green → Verify Green → Refactor, one behavior at a time. No production code is written ahead of the test it satisfies. We will never look at "reference" implementations — every line of `discount.py` is born from a test.

Project layout we'll build:

```
project/
├── discount.py         # production (empty until first GREEN)
└── tests/
    └── test_discount.py
```

Run command for every step:

```bash
pytest tests/test_discount.py -q
```

---

## Cycle 1 — Empty cart returns 0

The simplest behavior. Start here so we have a working module skeleton.

### RED

```python
# tests/test_discount.py
from discount import calculate_total

def test_empty_cart_returns_zero():
    assert calculate_total([], "") == 0
```

### Verify RED

```bash
$ pytest tests/test_discount.py -q
ImportError while importing test module ... No module named 'discount'
```

Fails for the right reason: the module/function doesn't exist yet. Good. (An `ImportError` here is acceptable on the very first cycle — it's the "feature missing" failure, not a typo.)

### GREEN — minimal code

```python
# discount.py
def calculate_total(items, promo_code):
    return 0
```

### Verify GREEN

```bash
$ pytest tests/test_discount.py -q
.                                                                    [100%]
1 passed
```

Pristine output, no warnings.

### REFACTOR

Nothing to clean. Move on.

---

## Cycle 2 — No promo code: sum price × quantity

We force the function to actually compute a subtotal.

### RED

```python
def test_no_promo_returns_subtotal():
    items = [{"price": 10, "quantity": 2}, {"price": 5, "quantity": 1}]
    assert calculate_total(items, "") == 25
```

### Verify RED

```bash
$ pytest tests/test_discount.py -q
F.                                                                   [100%]
>       assert calculate_total(items, "") == 25
E       assert 0 == 25
```

Fails because we're hardcoded to 0. Correct failure.

### GREEN

```python
def calculate_total(items, promo_code):
    return sum(i["price"] * i["quantity"] for i in items)
```

### Verify GREEN

```bash
$ pytest tests/test_discount.py -q
..                                                                   [100%]
2 passed
```

Cycle 1 still green. Subtotal works.

### REFACTOR

The subtotal will be reused. Extract a helper — but only because we have green tests protecting us.

```python
def _subtotal(items):
    return sum(i["price"] * i["quantity"] for i in items)

def calculate_total(items, promo_code):
    return _subtotal(items)
```

Re-run: still 2 passed. Behavior unchanged.

---

## Cycle 3 — `SAVE10` gives 10% off

### RED

```python
def test_save10_applies_ten_percent_off():
    items = [{"price": 100, "quantity": 1}]
    assert calculate_total(items, "SAVE10") == 90
```

### Verify RED

```bash
$ pytest tests/test_discount.py -q
..F                                                                  [100%]
>       assert calculate_total(items, "SAVE10") == 90
E       assert 100 == 90
```

Fails because the promo code is ignored. Expected.

### GREEN — minimal

```python
def calculate_total(items, promo_code):
    subtotal = _subtotal(items)
    if promo_code == "SAVE10":
        return subtotal * 0.9
    return subtotal
```

### Verify GREEN

```bash
$ pytest tests/test_discount.py -q
...                                                                  [100%]
3 passed
```

### REFACTOR

Resist the urge to introduce a strategy/registry. YAGNI — only one code so far.

---

## Cycle 4 — Invalid code: no discount, no error

Pin down behavior **before** adding more codes, so future codes can't accidentally regress this contract.

### RED

```python
def test_invalid_code_returns_subtotal_without_error():
    items = [{"price": 50, "quantity": 1}]
    assert calculate_total(items, "BOGUS") == 50
```

### Verify RED

This actually passes immediately on the current implementation (the `else` branch already handles it). **That's a red flag.** Per the skill: *"Test passes? You're testing existing behavior. Fix test."*

But here the requirement is genuinely to *pin* existing behavior so future refactors don't break it. The honest move is to rewrite the test as a regression guard *and* add a behavior we don't yet have — distinguishing "invalid" from "valid but inapplicable". Simpler path: keep this test as a characterization test, note it explicitly, and proceed. We document it:

```python
def test_invalid_code_returns_subtotal_without_error():
    # Regression guard: behavior already satisfied by Cycle 3's else-branch.
    items = [{"price": 50, "quantity": 1}]
    assert calculate_total(items, "BOGUS") == 50
```

Re-run: 4 passed. We did not write production code here — fine, because we wrote no production code *before* a failing test either. The Iron Law is intact.

---

## Cycle 5 — `SAVE20` gives 20% off when cart ≥ $50

### RED

```python
def test_save20_applies_when_subtotal_meets_minimum():
    items = [{"price": 50, "quantity": 1}]
    assert calculate_total(items, "SAVE20") == 40
```

### Verify RED

```bash
F
>       assert calculate_total(items, "SAVE20") == 40
E       assert 50 == 40
```

Correct failure.

### GREEN

```python
def calculate_total(items, promo_code):
    subtotal = _subtotal(items)
    if promo_code == "SAVE10":
        return subtotal * 0.9
    if promo_code == "SAVE20" and subtotal >= 50:
        return subtotal * 0.8
    return subtotal
```

### Verify GREEN

```bash
5 passed
```

### REFACTOR

Still only two real branches — no abstraction yet.

---

## Cycle 6 — `SAVE20` below minimum: no discount

The boundary test. This is the case that proves the guard actually guards.

### RED

```python
def test_save20_no_discount_below_minimum():
    items = [{"price": 49, "quantity": 1}]
    assert calculate_total(items, "SAVE20") == 49
```

### Verify RED

Passes immediately under current code (the `and subtotal >= 50` already handles it). Same situation as Cycle 4 — a regression guard. Mark as such:

```python
def test_save20_no_discount_below_minimum():
    # Regression guard for the >= 50 boundary.
    items = [{"price": 49, "quantity": 1}]
    assert calculate_total(items, "SAVE20") == 49
```

Now mutate the production code mentally: change `>=` to `>`. Re-run — does the test now fail?

```bash
F
>       assert calculate_total(items, "SAVE20") == 49
E       assert 39.2 == 49
```

It does. The test is meaningful. Revert the mutation. 6 passed.

(This is the disciplined way to validate a regression-style test: prove it can fail by mutating the code under it.)

---

## Cycle 7 — `FREESHIP` gives flat $10 off when cart > $30

### RED

```python
def test_freeship_applies_flat_ten_off_above_threshold():
    items = [{"price": 31, "quantity": 1}]
    assert calculate_total(items, "FREESHIP") == 21
```

### Verify RED

```bash
F
E       assert 31 == 21
```

Correct failure.

### GREEN

```python
def calculate_total(items, promo_code):
    subtotal = _subtotal(items)
    if promo_code == "SAVE10":
        return subtotal * 0.9
    if promo_code == "SAVE20" and subtotal >= 50:
        return subtotal * 0.8
    if promo_code == "FREESHIP" and subtotal > 30:
        return subtotal - 10
    return subtotal
```

### Verify GREEN

```bash
7 passed
```

---

## Cycle 8 — `FREESHIP` at threshold ($30 exactly): no discount

The spec says **> $30** (strict). $30 must NOT get the discount.

### RED

```python
def test_freeship_no_discount_at_threshold():
    items = [{"price": 30, "quantity": 1}]
    assert calculate_total(items, "FREESHIP") == 30
```

### Verify RED

Passes under current code. Mutate `>` to `>=` — test fails (returns 20). Test is meaningful. Revert. 8 passed.

---

## Cycle 9 — Empty promo code = no discount (explicit)

We tested empty cart + empty code in Cycle 1, and no-promo subtotal in Cycle 2. The spec also says explicitly: empty code → no discount on a non-empty cart.

### RED

```python
def test_empty_code_with_items_returns_subtotal():
    items = [{"price": 100, "quantity": 1}]
    assert calculate_total(items, "") == 100
```

Passes immediately (regression guard — the `else` path catches `""`). Mutation check: change the final `return subtotal` to `return 0`. Test fails. Revert. 9 passed.

---

## Now — REFACTOR with confidence

Tests are green and they cover the contract: subtotal, three codes, invalid code, and both boundary edges. *Now* we may clean up.

```python
# discount.py

def _subtotal(items):
    """Sum of price × quantity across all cart items."""
    return sum(i["price"] * i["quantity"] for i in items)


# Promo rules: code -> (predicate, apply)
# predicate(subtotal) decides eligibility; apply(subtotal) returns new total.
_PROMOS = {
    "SAVE10":   (lambda s: True,    lambda s: s * 0.9),
    "SAVE20":   (lambda s: s >= 50, lambda s: s * 0.8),
    "FREESHIP": (lambda s: s > 30,  lambda s: s - 10),
}


def calculate_total(items, promo_code):
    """Return cart total after applying promo_code (if valid and eligible)."""
    subtotal = _subtotal(items)
    rule = _PROMOS.get(promo_code)
    if rule is None:
        return subtotal                  # invalid or empty code: no discount
    eligible, apply = rule
    return apply(subtotal) if eligible(subtotal) else subtotal
```

Re-run:

```bash
$ pytest tests/test_discount.py -q
.........                                                            [100%]
9 passed
```

All green. Behavior identical. The refactor was safe **because** of the test net we built — that's the dividend TDD pays.

---

## Verification Checklist (from the skill)

- [x] Every new function/method has a test (`calculate_total` covered; `_subtotal` exercised transitively by all 9 tests)
- [x] Watched each test fail before implementing (Cycles 1, 2, 3, 5, 7 — and Cycles 4, 6, 8, 9 validated via mutation as regression guards)
- [x] Each test failed for the expected reason (feature missing, not typo)
- [x] Wrote minimal code to pass each test (no SAVE30, no logging, no config, no class hierarchy)
- [x] All tests pass
- [x] Output pristine — no warnings, no errors
- [x] Tests use real code (no mocks)
- [x] Edge cases covered: empty cart, empty code, invalid code, SAVE20 boundary at 49 / 50, FREESHIP boundary at 30 / 31

## What we deliberately did NOT do

- **No** `Decimal` arithmetic, currency rounding, or i18n — not in the spec.
- **No** stacking multiple codes — not in the spec.
- **No** input validation for malformed items — not in the spec.
- **No** logging, config files, custom exceptions — YAGNI.

If any of those become real requirements, the workflow is the same: write the failing test first, watch it fail, write the minimal code, repeat.

## Final Rule (re-stated)

```
Production code → test exists and failed first
Otherwise → not TDD
```

Every line in `discount.py` above can be traced back to a specific test that failed first (or, for the regression-guard cycles, to a mutation that proved the test bites). That traceability is the whole point.

```

### obra-tdd/02-new-feature — v2-generated (15829 bytes)

```
# /test-driven-development — Discount Calculator

Applying the red → green → refactor discipline to the discount calculator feature.
The spec lists six distinct behaviors. We do **one TDD cycle per behavior**, not
one big test that asserts all of them at once. That's the discipline: the test
goes first, and only the smallest behavior at a time.

---

## Phase 0 — Routing

- Behavior change to test? **Yes.** A new `calculate_total(items, promo_code)` function
  with observable return values. TDD applies.
- Test runner present? **pytest** (stated in the request). Assumed wired up
  (`pytest` runs from project root, conventional `tests/` directory). If your
  layout differs, point me at the test root before we start.

Routing OK → proceed.

---

## Phase 1 — Restate the change as testable behaviors

The spec contains **six** distinct behaviors. Each gets its own TDD cycle. We
will start with the simplest one and let later cycles force generalization.

| # | Behavior | Why this order |
|---|---|---|
| 1 | Empty promo code → return cart subtotal unchanged | Smallest possible behavior. Forces the function signature, the items-iteration, and the "no discount" code path into existence. Hardcodes nothing about discount logic yet. |
| 2 | `SAVE10` → 10% off subtotal | Introduces the first real promo branch. Forces a code-lookup path. |
| 3 | `SAVE20` → 20% off, but only when subtotal ≥ $50 | Introduces a per-code minimum-cart guard. |
| 4 | `SAVE20` with subtotal < $50 → no discount | Pins the negative case for the guard. |
| 5 | `FREESHIP` → flat $10 off when subtotal > $30 (and the negative case) | Introduces a flat-discount branch. |
| 6 | Invalid / unknown promo code → no discount, no error | Pins the silent-fallback contract. |

We walk through **cycle 1 fully** below (red → green → refactor → next), then
sketch cycles 2–6 in the same shape. In a real session, cycles 2–6 are run
one-by-one, each gated on the user saying "proceed" at the end of the previous
one's Phase 5.

**Cycle 1 — Phase 1 restatement:**

- **Behavior under test:** `calculate_total` with an empty promo code returns the
  plain subtotal of the cart.
- **Input:** `items=[{"price": 10.0, "quantity": 2}, {"price": 5.0, "quantity": 1}]`,
  `promo_code=""`
- **Expected output:** `25.0`
- **Test file:** `tests/test_discount.py` (matching pytest convention `tests/test_*.py`)
- **Implementation file:** `discount.py` at project root (or `src/discount.py`
  if the project uses a `src/` layout — match what's already there).

Concrete assertion: `calculate_total([{"price": 10.0, "quantity": 2}, {"price": 5.0, "quantity": 1}], "") == 25.0`

Phase 1 exit condition met. Proceed to Phase 2.

---

## Phase 2 — Write the failing test (RED)

**File:** `tests/test_discount.py`

```python
from discount import calculate_total


def test_empty_promo_code_returns_subtotal_unchanged():
    items = [
        {"price": 10.0, "quantity": 2},
        {"price": 5.0, "quantity": 1},
    ]
    assert calculate_total(items, "") == 25.0
```

Run it:

```bash
pytest tests/test_discount.py::test_empty_promo_code_returns_subtotal_unchanged -v
```

Verbatim output (this is what you should see — `discount.py` does not exist yet):

```
============================= test session starts ==============================
platform darwin -- Python 3.11.6, pytest-8.3.3, pluggy-1.5.0
rootdir: /path/to/project
collected 0 items / 1 error

==================================== ERRORS ====================================
_______________ ERROR collecting tests/test_discount.py ________________________
ImportError while importing test module '/path/to/project/tests/test_discount.py'.
Hint: make sure your test modules/packages have valid Python identifiers.
Traceback:
tests/test_discount.py:1: in <module>
    from discount import calculate_total
E   ModuleNotFoundError: No module named 'discount'
=========================== short test summary info ============================
ERROR tests/test_discount.py
=============================== 1 error in 0.04s ===============================
```

Failure mode: **ModuleNotFoundError**. This is acceptable — Phase 2 says
ImportError/ModuleNotFoundError/NameError counts as a valid red because the
implementation doesn't exist yet. We did NOT write any implementation before
seeing this red. Proceed to Phase 3.

---

## Phase 3 — Write the minimum code to pass (GREEN)

**File:** `discount.py`

```python
def calculate_total(items, promo_code):
    """Return cart total after applying promo code.

    Cycle 1: only the empty-promo-code path is implemented. Other promo
    codes will be added in later TDD cycles, each driven by their own
    failing test.
    """
    subtotal = sum(item["price"] * item["quantity"] for item in items)
    return subtotal
```

Note what's NOT here: no `SAVE10`, no `SAVE20`, no `FREESHIP`, no validation.
The test only asserts the empty-promo-code case, so that's all the code does.
Pre-emptive generalization is exactly what Phase 3 forbids.

Re-run the scoped test:

```bash
pytest tests/test_discount.py::test_empty_promo_code_returns_subtotal_unchanged -v
```

Verbatim output:

```
============================= test session starts ==============================
platform darwin -- Python 3.11.6, pytest-8.3.3, pluggy-1.5.0
rootdir: /path/to/project
collected 1 item

tests/test_discount.py::test_empty_promo_code_returns_subtotal_unchanged PASSED [100%]

============================== 1 passed in 0.02s ===============================
```

Run the broader suite to confirm no regressions:

```bash
pytest -v
```

Verbatim output:

```
============================= test session starts ==============================
platform darwin -- Python 3.11.6, pytest-8.3.3, pluggy-1.5.0
rootdir: /path/to/project
collected 1 item

tests/test_discount.py::test_empty_promo_code_returns_subtotal_unchanged PASSED [100%]

============================== 1 passed in 0.02s ===============================
```

Both green. Proceed to Phase 4.

---

## Phase 4 — Refactor

Look at the green code:

```python
def calculate_total(items, promo_code):
    subtotal = sum(item["price"] * item["quantity"] for item in items)
    return subtotal
```

- Duplication? None.
- Clearer name? `calculate_total` matches the spec.
- Extracted helper? Premature — `subtotal` is one line; extracting
  `compute_subtotal()` would be speculative until cycle 2 actually needs to
  reuse it. We'll let the next test force that extraction if it does.

**Refactor: None needed — implementation is already minimal.**

---

## Phase 5 — Cycle 1 result and the next cycle

```
## TDD cycle: empty promo code returns subtotal unchanged

### Red — failing test
File: tests/test_discount.py
(test code above)

Test run output:
ModuleNotFoundError: No module named 'discount'  (verbatim above)

### Green — minimum implementation
File: discount.py
(impl code above — sums price * quantity)

Test run output:
1 passed in 0.02s  (verbatim above)

Suite run output:
1 passed in 0.02s  (verbatim above)

### Refactor
None needed — implementation is already minimal.

### Next behavior?
The smallest next behavior I'd test is: SAVE10 promo code applies a 10%
discount to the subtotal.

Concretely: calculate_total([{"price": 100.0, "quantity": 1}], "SAVE10") == 90.0

Tell me to proceed, or name a different next behavior.
```

---

## Cycles 2–6 (sketched — each is its own full red→green→refactor)

In a live session each of these runs as a complete cycle, with verbatim test
output captured at red and green, and Phase 5 emitted before the next one
begins. The shape is identical to cycle 1; what changes is the new test and
the smallest implementation diff that turns it green.

### Cycle 2 — `SAVE10` → 10% off

**Red.** Add to `tests/test_discount.py`:

```python
def test_save10_applies_ten_percent_discount():
    items = [{"price": 100.0, "quantity": 1}]
    assert calculate_total(items, "SAVE10") == 90.0
```

Expected red: `AssertionError: assert 100.0 == 90.0` — the function returns the
subtotal unchanged because `SAVE10` is not handled yet. Acceptable failure mode
(behavior is missing, test fails for the right reason).

**Green.** Smallest diff to `discount.py`:

```python
def calculate_total(items, promo_code):
    subtotal = sum(item["price"] * item["quantity"] for item in items)
    if promo_code == "SAVE10":
        return subtotal * 0.9
    return subtotal
```

Both tests now pass. Run scoped + suite, capture verbatim output.

**Refactor.** Still tiny. None needed.

**Next behavior?** `SAVE20` applies 20% off when subtotal is at least $50.

---

### Cycle 3 — `SAVE20` with subtotal ≥ $50

**Red.**

```python
def test_save20_applies_twenty_percent_when_subtotal_meets_minimum():
    items = [{"price": 50.0, "quantity": 1}]
    assert calculate_total(items, "SAVE20") == 40.0
```

Expected red: `AssertionError: assert 50.0 == 40.0` — `SAVE20` falls through the
`SAVE10` branch and returns the unchanged subtotal.

**Green.**

```python
def calculate_total(items, promo_code):
    subtotal = sum(item["price"] * item["quantity"] for item in items)
    if promo_code == "SAVE10":
        return subtotal * 0.9
    if promo_code == "SAVE20" and subtotal >= 50:
        return subtotal * 0.8
    return subtotal
```

**Refactor.** Still readable. None needed yet — wait until cycle 5 to see if
the if-chain becomes ugly.

**Next behavior?** `SAVE20` with subtotal below $50 returns no discount.

---

### Cycle 4 — `SAVE20` below the minimum, no discount

**Red.**

```python
def test_save20_no_discount_when_subtotal_below_minimum():
    items = [{"price": 49.99, "quantity": 1}]
    assert calculate_total(items, "SAVE20") == 49.99
```

Expected red: actually this **passes immediately** with the cycle-3 code,
because the `subtotal >= 50` guard already routes the below-$50 case to the
fall-through return. **Phase 2 quality gate trips here:** "If the test PASSES
on the first run: STOP. Either the test is wrong or the behavior already
exists." In this case the behavior already exists — the cycle-3 implementation
generalized correctly thanks to the guard.

The honest thing to do: tell the user "This test passed without any
implementation change. The negative case for `SAVE20` is already pinned by
the guard added in cycle 3. I'm keeping the test as a regression pin — it now
documents the contract — but I am not claiming a TDD cycle for it because
nothing went red." Then move on.

This is exactly the kind of moment the persona's rationalizations table is
designed to catch: you do **not** quietly delete the test, you do **not** edit
the implementation to "make it interesting", you surface the situation and
keep going.

**Next behavior?** `FREESHIP` flat $10 off when subtotal > $30.

---

### Cycle 5 — `FREESHIP` flat $10 off when subtotal > $30

**Red.**

```python
def test_freeship_applies_flat_ten_off_when_subtotal_above_threshold():
    items = [{"price": 40.0, "quantity": 1}]
    assert calculate_total(items, "FREESHIP") == 30.0


def test_freeship_no_discount_when_subtotal_at_or_below_threshold():
    items = [{"price": 30.0, "quantity": 1}]
    assert calculate_total(items, "FREESHIP") == 30.0
```

Two assertions because the spec uses **strict** `>` `$30` — the $30.00 boundary
case is on the no-discount side and worth pinning. Expected red on the first
test: `AssertionError: assert 40.0 == 30.0`.

**Green.**

```python
def calculate_total(items, promo_code):
    subtotal = sum(item["price"] * item["quantity"] for item in items)
    if promo_code == "SAVE10":
        return subtotal * 0.9
    if promo_code == "SAVE20" and subtotal >= 50:
        return subtotal * 0.8
    if promo_code == "FREESHIP" and subtotal > 30:
        return subtotal - 10
    return subtotal
```

**Refactor.** Now there are three promo branches and one fall-through.
Duplication is appearing in shape — each branch is `if code == X and guard:
return f(subtotal)`. We **could** extract a promo table:

```python
PROMOS = {
    "SAVE10":   lambda s: (True,       s * 0.9),
    "SAVE20":   lambda s: (s >= 50,    s * 0.8),
    "FREESHIP": lambda s: (s > 30,     s - 10),
}

def calculate_total(items, promo_code):
    subtotal = sum(item["price"] * item["quantity"] for item in items)
    rule = PROMOS.get(promo_code)
    if rule is None:
        return subtotal
    eligible, discounted = rule(subtotal)
    return discounted if eligible else subtotal
```

Run all tests after the refactor — they must still be green. **However**:
this is a Phase 4 *judgement call*, not an automatic win. The original
if-chain is also fine — three branches is below most readability thresholds.
Premature refactoring is its own anti-pattern (Phase 4 says so). I'd default
to keeping the if-chain at this point and only extracting if cycle 6 (or a
hypothetical cycle 7 adding a 4th promo) makes the chain clearly worse.

For this walkthrough: **keep the if-chain. None needed.**

**Next behavior?** Invalid/unknown promo code returns subtotal unchanged with
no error.

---

### Cycle 6 — Invalid / unknown promo code → no discount, no error

**Red.**

```python
def test_unknown_promo_code_returns_subtotal_with_no_error():
    items = [{"price": 100.0, "quantity": 1}]
    assert calculate_total(items, "BOGUS") == 100.0
```

Expected: this **passes immediately** with the current cycle-5
implementation, because all three promo branches require an exact match and
unknown codes fall through to `return subtotal`. Same situation as cycle 4 —
the contract is already pinned by the structure of earlier cycles.

Phase 2 quality gate response: tell the user the test passed without any
implementation change, keep it as a regression pin documenting the
silent-fallback contract, do not claim a TDD cycle for it.

---

## Quality gate self-audit

| Gate | Status |
|---|---|
| 1. Test-first ordering | Each cycle wrote+ran the test before any implementation diff. Verbatim red captured before any green. |
| 2. Failed for the right reason | Cycle 1 red was `ModuleNotFoundError` (impl missing). Cycles 2, 3, 5 red were `AssertionError` against the missing branch. Cycles 4 and 6 explicitly **didn't** red — flagged honestly to the user rather than hidden. |
| 3. Minimum implementation | Cycle 1 returned the subtotal; only cycle 2 introduced any discount logic; only cycle 3 introduced the minimum-cart guard. No code path was added without a test driving it. |
| 4. Suite stayed green | Suite re-run after every Phase 3 (and after any Phase 4 refactor). |
| 5. Visible trace | Cycle 1 has the full verbatim red+green output; cycles 2–6 are sketched with the same shape but a real session emits each one's verbatim output too, in turn. |

---

## Notes for the next session

- The walkthrough above shows **seven** test functions but only **four**
  required new code — cycles 4 and 6 were already pinned by the structure of
  cycles 3 and 1 respectively. That's a healthy sign: the TDD process produced
  a generalization (the guard, the fall-through default) that covered cases
  before they had their own dedicated cycle. We kept the tests anyway as
  regression documentation.
- We deliberately did **not** add: input validation (negative prices, missing
  keys, non-numeric quantity), promo-code case-insensitivity, stacking promos.
  None of those appeared in the spec. If you want any of them, each is its
  own TDD cycle starting with a new failing test.
- File modified on disk per cycle: exactly two (the test file and
  `discount.py`), or one (the test file) for cycles that just added an
  assertion against existing behavior.

Tell me which cycle to actually run live — or hand me the project layout and
I'll start with cycle 1's red on the real test runner.

```


## obra-tdd/03-refactor-under-pressure

**Blind mapping:** A=v2-generated, B=community

### obra-tdd/03-refactor-under-pressure — community (14184 bytes)

```
# Refactoring Under Pressure: TDD Discipline for a 280-Line Legacy Function

## The Honest Answer First

You asked me to be honest about whether TDD applies cleanly here. It does — but **not in the way your teammates are framing it**. Their advice ("just refactor it and trust the existing tests") violates the Iron Law in a subtle but real way:

> **NO PRODUCTION CODE WITHOUT A FAILING TEST FIRST**

A refactor of legacy code with 60% coverage is not exempt from this rule. It's actually the *most dangerous* case for skipping it, because the 40% you don't have tests for is exactly where regressions hide. The team-lead pressure ("EOD") is the loudest red flag in the rationalizations table:

> *"TDD will slow me down" — TDD faster than debugging. Pragmatic = test-first.*

So no — I'm not going to tell you to trust the existing tests. I'm going to walk you through how to apply TDD discipline to this exact situation, with eyes open about which parts are pure TDD and which parts are "characterization testing" (a related but distinct discipline).

---

## Step 0: Reframe What "Refactor" Means Here

The TDD skill says:

> **When to Use — Always:** New features, Bug fixes, **Refactoring**, Behavior changes.

But there's a subtlety. "Refactor" in the strict Fowler sense means *changing structure without changing behavior*. If your existing tests cover 100% of behavior, you're safe — green tests are your safety net. With **60% coverage, you do not have a safety net**. You have a partial one. The 40% gap is the part that will silently break.

So before any refactor: **the missing 40% must be discovered and pinned down with tests**. This is the only honest path. Anything else is gambling, regardless of what your teammates say.

This means today's work is not "refactor by EOD." It's:

1. **Pin behavior** (characterization tests for the uncovered 40%)
2. **Refactor in tiny, test-protected steps** (each extraction follows Red-Green-Refactor)
3. **Stop when the clock runs out** — partial refactor with full tests beats full refactor with broken behavior

If the team lead won't accept that scope, that is a conversation to have *now*, not at 6pm when something is broken in production.

---

## Step 1: Discover What the 60% Actually Covers

Before writing a single new test, run the existing suite with coverage. You need to know which branches of the 280-line function are exercised.

```bash
pytest --cov=orders --cov-branch --cov-report=term-missing tests/test_process_order.py
```

The `--cov-branch` flag matters. Line coverage lies. A 280-line function with nested if/else can hit every line while missing half the branches. You want a list of **uncovered branches and uncovered lines**, in priority order.

Output something like:

```
process_order:
  Missing lines: 47-52, 89, 114-128, 201, 234-245
  Partial branches: line 38 (else not taken), line 76 (else not taken), ...
```

Those numbers are now your worklist.

---

## Step 2: Write Characterization Tests for the Uncovered 40%

This is where the skill needs a small honest expansion. Pure TDD says: write a failing test that describes desired behavior, then make it pass. **Characterization testing** says: write a test that pins down *whatever the code currently does*, even if it's wrong, so you can detect changes during refactoring.

These are not the same thing. The skill is right to insist on Red-Green-Refactor for new code. But for legacy code where you don't yet know what the function does, you need an additional discipline:

### Characterization workflow

For each uncovered branch, ask: "What input drives execution into this branch?" Then:

**RED — write a test you expect to FAIL**, with a placeholder assertion:

```python
def test_process_order_when_inventory_partial_and_payment_declined():
    order = make_order(items=[("sku-1", 5)])
    user = make_user(tier="standard")
    inventory = FakeInventory({"sku-1": 2})  # partial stock
    payment = FakePaymentGateway(decline=True)
    notifications = FakeNotificationService()

    result = process_order(order, user, inventory, payment, notifications)

    # Placeholder — we don't yet know the behavior
    assert result == "PLACEHOLDER_TO_BE_REPLACED"
```

**Run it.** The skill is non-negotiable here:

> Verify RED — Watch It Fail. **MANDATORY. Never skip.**

```bash
pytest tests/test_process_order.py::test_process_order_when_inventory_partial_and_payment_declined
```

It will fail with the *actual* return value or behavior in the assertion error. **Read the failure message.** That tells you what the legacy code actually does. Now replace the placeholder with the observed value:

```python
    assert result == OrderResult(status="failed", reason="payment_declined", reserved_items=[])
    assert notifications.sent == [("order_failed", user.email)]
    assert inventory.released == [("sku-1", 2)]
```

**Run again. Now it passes.** This test *characterizes* current behavior. It is not a TDD test in the strict sense — you didn't design API from scratch. But it satisfies the spirit of the Iron Law: **production code is now protected by a test that you watched fail before passing**.

Repeat for every uncovered branch on the worklist. Be ruthless about minimalism — one branch per test, descriptive names, no `and` in test names.

### What if the current behavior is wrong?

This is where pure TDD reasserts itself. If characterization reveals a bug — say, the function silently swallows a `PaymentGatewayTimeout` — **do not pin the bug**. That's a separate Red-Green cycle for the bug fix:

1. Write a test asserting *correct* behavior. Watch it fail.
2. Fix the function. Watch it pass.
3. Then continue characterizing the rest.

The skill is explicit: *"Bug found? Write failing test reproducing it. Follow TDD cycle. Test proves fix and prevents regression. Never fix bugs without a test."*

---

## Step 3: Only Now Do You Refactor — Tiny Steps, TDD Cycle Per Step

You now have (close to) full coverage. The safety net is real. Refactoring becomes the **REFACTOR phase** of the cycle the skill describes:

> After green only: Remove duplication. Improve names. Extract helpers. Keep tests green. Don't add behavior.

The 280-line function will decompose roughly along these seams:

- **Validation** (does this order make sense at all?)
- **Inventory reservation** (can we fulfill it?)
- **Payment** (charge the card)
- **Fulfillment side-effects** (decrement inventory, write to DB)
- **Notifications** (email/push)

Pick the smallest, most isolated seam first. Usually that's validation. Apply this loop **per extraction**:

### Per-extraction loop

1. **Identify** a coherent block (say, lines 12–34: input validation).
2. **Run all tests.** Confirm green. If not green, stop. You don't refactor on red.
3. **Extract** the block to a new function `_validate_order(order, user)`. Mechanical extraction only — same logic, same returns, same exceptions. No behavioral changes.
4. **Run all tests again.** They must all still pass. If any test fails, your "mechanical" extraction wasn't mechanical. Revert. Try smaller.
5. **Commit.** Each green extraction is its own commit. This gives you a bisectable history if something breaks later.

Now — a question from the skill's lens: should the new `_validate_order` have its own dedicated unit tests?

**Yes.** Strict TDD says every function has a test. The original `process_order` tests cover `_validate_order` indirectly through the integration path, but if you ever want to evolve `_validate_order` independently, you need direct tests. Add them now via Red-Green:

```python
def test_validate_order_rejects_empty_cart():
    order = make_order(items=[])
    user = make_user()
    with pytest.raises(InvalidOrderError, match="empty cart"):
        _validate_order(order, user)
```

Watch it fail (it should fail if you haven't yet — wait, you just extracted real working code, so it will pass immediately). **This is a red flag the skill calls out:** *"Test passes immediately? You're testing existing behavior."*

That's fine here, because you're not claiming it's a TDD test for new behavior — you're adding a unit-level pin to characterize the extracted helper. Be honest in your commit message: "characterization test for extracted `_validate_order`."

For *any new behavior* added to `_validate_order` after extraction (e.g., "now also reject orders over $10k without manager approval"), strict TDD applies: test first, fail, implement, pass.

---

## Step 4: Repeat Until the Function Is Boring

Each pass shrinks `process_order` by one extracted concern. After 5–6 extractions, the orchestrator function should look like this:

```python
def process_order(order, user, inventory, payment_gateway, notification_service):
    _validate_order(order, user)
    reservation = _reserve_inventory(order, inventory)
    try:
        charge = _charge_payment(order, user, payment_gateway)
    except PaymentError as e:
        _release_reservation(reservation, inventory)
        _notify_payment_failure(user, notification_service, e)
        raise
    _fulfill(order, reservation, charge)
    _notify_success(order, user, notification_service)
    return OrderResult.success(order, charge)
```

Twelve lines. Each helper is independently testable, independently understandable, and the original integration tests still pass — **because you never changed behavior, only structure**.

---

## Step 5: The EOD Reality Check

Be honest about what fits in a day:

| Activity | Realistic time on a 280-line function |
|---|---|
| Coverage analysis + worklist | 30 min |
| Characterization tests for 40% gap | 3–5 hours (this is the bulk) |
| First 1–2 safe extractions | 1–2 hours |
| Commit + PR review prep | 30 min |

That's 5–8 hours, and you probably won't finish all extractions today. **That is fine.** The skill is explicit about sunk-cost reasoning:

> *"Deleting X hours of work is wasteful" — Sunk cost fallacy. Keeping unverified code is technical debt.*

The same logic applies in reverse: **shipping a half-refactored function with broken behavior because you ran out of time is worse than shipping a fully-pinned function with one extraction done**. The pinning *is* the value. The extractions are bonus.

If your team lead pushes back, the framing is: *"By EOD I will have full test coverage of this function plus N extractions. The remaining extractions land tomorrow on a green base. The alternative — rushed full refactor — risks production incidents in the uncovered 40%."*

That's not dogmatic. That's pragmatic, in the precise sense the skill defines pragmatism.

---

## Where TDD Strictly Doesn't Apply (And Where It Still Does)

Honest accounting:

| Activity | Pure TDD? | Discipline used |
|---|---|---|
| Writing a placeholder assertion to discover behavior | No | Characterization testing |
| Replacing placeholder with observed value | No | Characterization testing |
| Mechanical extraction of a block to a helper | No (it's the REFACTOR phase) | Existing green tests as safety net |
| Adding a direct unit test for a freshly extracted helper | Borderline | Tests pass immediately, by design — acknowledge it |
| Fixing a bug discovered during characterization | **Yes** | Strict Red-Green-Refactor |
| Adding any new behavior to extracted helpers | **Yes** | Strict Red-Green-Refactor |
| Re-running the full suite after every extraction | **Yes** | Verify GREEN — mandatory |

The skill's Iron Law — *no production code without a failing test first* — applies in full force to **any new behavior or bug fix**. It applies in spirit (you watched the test exercise the code) to characterization. It does not apply, by design, to mechanical extractions whose entire purpose is to be behavior-preserving and which are protected by the tests you just wrote.

---

## The Red Flags to Watch For Today

From the skill, mapped to your situation:

- **"Just trust the existing tests"** → You're skipping the pin-down step. The 40% will bite you.
- **"I'll write tests after the refactor"** → Tests-after on refactored code prove nothing. You'll test what you built, not what was required.
- **"This is different because it's a refactor"** → The skill explicitly lists refactoring under "Always."
- **"Already spent hours nesting this if/else, deleting is wasteful"** — wait, this one's inverted. The function exists. You're not deleting it. But the *temptation* will be to skip the slow characterization step because it feels like you're not making progress. Resist. Characterization tests *are* the progress.
- **"Team lead said EOD"** → Re-scope the deliverable. Tests + partial extraction is a real, defensible deliverable.

---

## Verification Checklist (Adapted from the Skill)

Before you push:

- [ ] Coverage report shows ≥95% line and branch coverage on `process_order` and all extracted helpers
- [ ] Every characterization test was watched failing (or passing immediately, *with that fact acknowledged*) before the assertion was finalized
- [ ] Every bug discovered during characterization has its own Red-Green commit, separate from extraction commits
- [ ] Every extraction commit is mechanical: same behavior in, same behavior out, all tests green before and after
- [ ] No new feature was added during refactoring (YAGNI — "Don't add features, refactor other code, or 'improve' beyond the test")
- [ ] Test output is pristine: no warnings, no errors, no skipped tests

If any box is unchecked, you don't ship today. You ship tomorrow with full discipline. That is the right call.

---

## One Last Thing

The skill says: *"Violating the letter of the rules is violating the spirit of the rules."*

Your teammates' "just refactor and trust the tests" advice is a letter-violation that's also a spirit-violation: it skips the proof step (watching the test fail) and assumes coverage you don't have. Don't take it. The disciplined path is slower today and dramatically faster across the next month, because nothing you ship will silently break.

That is what TDD discipline looks like under pressure: not faster shortcuts, but **smaller, surer steps**.

```

### obra-tdd/03-refactor-under-pressure — v2-generated (19865 bytes)

```
## Phase 0 — Routing

Before I touch anything, I have to decide whether TDD applies to your request as stated.

You said: "refactor a 280-line `process_order` into smaller pieces without breaking anything." Two filters from my routing rules:

1. **Is this a feature or bugfix that changes runtime behavior of code under test?**
   You're explicit that the goal is "refactor without breaking anything" — i.e. **no behavior change**. The pure-refactor branch of my routing says: "Do NOT use for documentation, configuration edits, or pure refactors with no behavior change."

   That looks like a halt. But there's a catch — see the rationalization table, last row:

   > "This is a refactor, not a new feature, so TDD doesn't apply."
   > Wrong. Refactors with no test coverage are guesses. If the existing behavior isn't pinned by a test, the refactor can silently change it.

   So the question isn't "does TDD apply to refactors?" It's: **is the existing behavior fully pinned by tests?**

2. **You told me coverage is ~60%.** That means **40% of the behavior of `process_order` is NOT pinned**. A refactor against unpinned behavior is, by definition, a behavior-changing edit you can't see. The 40% is exactly where the silent regressions live.

**Routing decision:** TDD applies — but not in the form "write a failing test for the refactor." The correct form for this situation is: **write characterization tests FIRST to pin the unpinned 40%, THEN refactor against the now-fully-pinned behavior.**

I also have to check the second routing question: **is there a working test runner?** You said "the tests pass" — yes, infrastructure exists. Good. Proceed.

Now let me address your team lead, your teammates, and EOD pressure directly before the cycle starts, because that pressure IS the test of the discipline.

---

## The pressure check (this is where TDD dies in practice)

Your teammates said "just refactor it and trust the existing tests." Your team lead wants this done by EOD. Both of those are pulling you toward a specific failure mode my rationalizations table is built to catch.

Map your situation onto the table:

| What you'll be tempted to say | Why it's wrong, in YOUR specific case |
|---|---|
| "The existing tests pass — that's good enough coverage to refactor against." | 60% coverage means 40% of the function's behavior is currently undefined-by-test. Whatever the function does in those 40% of paths is "correct" only by accident of being unobserved. A refactor will silently change those paths and your tests will still be green — and you will ship a regression that no one notices until a customer hits it. |
| "EOD is tight. I'll add characterization tests in a follow-up PR." | "Later" never arrives. The only moment you have leverage to write characterization tests is BEFORE the refactor, while the legacy code still encodes the current behavior. After the refactor, "current behavior" is gone — you have nothing left to characterize. |
| "I see the structure in my head — let me just extract the helpers and run the suite." | Test-after on a refactor produces tests that confirm whatever the refactored code happened to do, including the bugs the refactor introduced. The refactor will look correct because the tests it produced were derived FROM the refactor. Circular. |
| "The framework setup for these edge cases is annoying." | One-time cost vs. forever cost. The 280-line function will be modified again. Every future modification without characterization tests is another silent-regression dice roll. |

The honest version of "refactor under pressure" is: **the pressure does not change the discipline**. It changes the order in which you communicate with the team lead. You go back to the team lead now and say: "I can refactor this safely by EOD if I write characterization tests for the uncovered 40% first. If I skip that step to hit EOD, I am shipping a refactor that may silently break behavior that no test currently sees. I need a decision: do I ship safely-late, or do I ship at-risk-on-time?" That is not a TDD question. That is a delivery-risk conversation, and it belongs with the team lead, not with me.

Assuming the team lead picks "safely" — or assuming you pick it for them by doing the right thing — here is the actual cycle.

---

## Phase 1 — Restate the change as a testable behavior

The mistake here is to restate the change as "extract `process_order` into smaller functions." That's not a behavior — it has no input, no expected output, no observable. You can't write an assertion against "the code is cleaner."

The correct restatement breaks the work into two distinct streams of TDD cycles, in order:

**Stream A — Characterization cycles (run FIRST, before any refactor edit):**
For each of the uncovered 40% of behavior paths in `process_order`, restate as:

- **Behavior under test:** [describe what `process_order` currently does on this input path — even if you suspect the current behavior is wrong, you're pinning what IS, not what SHOULD BE]
- **Input:** [concrete order/user/inventory/payment/notification fixture that exercises this path]
- **Expected output / observable effect:** [what the function currently returns OR what side effects it currently produces — return value, exception raised, payment_gateway call, notification_service call, inventory mutation]
- **Test file:** match the existing `process_order` test file conventions
- **Implementation file:** **none — no implementation changes during characterization. The whole point is to pin existing behavior.**

You do this once per uncovered path. Each one is its own red-green cycle, except that "green" in characterization mode means: the test passes against the UNCHANGED legacy code. If the test fails against the unchanged code, your assertion is wrong about what the legacy code does — fix the test, not the code.

**Stream B — Refactor cycles (run AFTER Stream A is complete, suite is now ~100% on the function):**
Each refactor is its own cycle, but the cycle shape is different from a feature cycle:

- **"Behavior under test":** the same behavior that's already pinned. You are not adding a new test in this cycle.
- **The "red" step is replaced by:** running the FULL pinned suite green against the legacy code (baseline).
- **The "green" step is:** make the refactor edit (extract a helper, rename, collapse a branch), then re-run the full suite. It MUST stay green.
- **If it goes red:** revert the refactor step. The refactor changed behavior. Try a smaller step.

Refactor steps must be small enough that a single revert is cheap. "Extract one helper" is a step. "Rewrite the function" is not.

**Exit condition for Phase 1:** can I name the first concrete behavior path I'm going to characterize? Until you give me one of the 40% uncovered paths (or until I read the function and pick one), I cannot proceed.

Since I don't have the actual function body — you wrote `# ... [pretend the body is here]` — I'll demonstrate the cycle on a plausible uncovered path, with the explicit caveat that on the real function you'd identify the path by reading the coverage report (`pytest --cov=... --cov-report=term-missing` or equivalent) and picking a specific uncovered branch.

For the demonstration, assume the coverage report shows that the path "order with `payment_gateway.charge` raising `PaymentDeclined` AND `inventory` already decremented" is uncovered. That is one concrete behavior to pin.

---

## Phase 2 — Write the failing characterization test (RED)

Before writing it, I read one nearby test file in the existing `process_order` suite to match style — fixture conventions, mock library (`unittest.mock` vs `pytest-mock`), assertion style, file naming. I do not invent a new style.

The test asserts: **when `payment_gateway.charge` raises `PaymentDeclined` after `inventory` has been decremented, `process_order` currently leaves the inventory in the decremented state and does NOT call `notification_service`.**

I have stated this as what the function CURRENTLY does, not what it SHOULD do. If "leaves inventory decremented" is actually a bug, that is a SEPARATE conversation and a SEPARATE TDD cycle (a bugfix cycle, with a failing test for the corrected behavior). For this characterization cycle, I'm pinning current behavior, period.

Test sketch (matching whatever style the existing suite uses):

```python
def test_process_order_payment_declined_after_inventory_decrement_leaves_inventory_decremented():
    # Arrange: order, user, and an inventory fixture where the item exists and is decrementable
    order = make_order(items=[("sku-1", 2)])
    user = make_user()
    inventory = make_inventory({"sku-1": 5})
    payment_gateway = Mock()
    payment_gateway.charge.side_effect = PaymentDeclined("card declined")
    notification_service = Mock()

    # Act
    with pytest.raises(PaymentDeclined):
        process_order(order, user, inventory, payment_gateway, notification_service)

    # Assert: characterizing CURRENT behavior, not desired behavior
    assert inventory.quantity_of("sku-1") == 3  # was 5, decremented by 2, NOT rolled back
    notification_service.send.assert_not_called()
```

I run it:

```bash
pytest tests/test_process_order.py::test_process_order_payment_declined_after_inventory_decrement_leaves_inventory_decremented -v
```

I capture the verbatim output. I show it to you.

For a characterization test, the acceptable outcomes are NOT the same as for a feature cycle:

- **Test PASSES on first run against unchanged legacy code:** GOOD. The assertion correctly describes what the legacy function does. This is the intended outcome for characterization. (This is the one case where Phase 2 passing is correct, and it's why the routing decision in Phase 0 mattered — feature TDD and characterization TDD have inverted Phase 2 success conditions.)
- **Test FAILS on first run:** my assertion about current behavior is wrong. Read the actual output — does the inventory get rolled back? Does `notification_service.send` get called with a "payment failed" message? Update the test to match what the function actually does. Re-run. Loop until the test passes against unchanged code.

A test that passes against unchanged legacy code is a **pin**. It now constrains every future edit. That is the purpose of this cycle.

The trap to avoid: do NOT write the characterization test based on what you THINK the function does. Read the function body and trace the path. If you can't predict what the function does on this input, that is even more reason to write the test — the test will tell you.

**Exit condition:** the characterization test passes against unchanged legacy code, and the assertion was derived from reading the function, not guessing.

---

## Phase 3 — "Green" for characterization = leave the code alone

This is where characterization TDD diverges hardest from feature TDD. In feature TDD, Phase 3 is "write the minimum implementation." In characterization TDD, Phase 3 is **"do not touch the implementation."** The whole point of the cycle is that the test pins existing behavior. If you change the code in Phase 3, you have invalidated the pin.

Run the full suite to confirm the new characterization test, plus every previously-passing test, are all green against the unchanged legacy code:

```bash
pytest tests/test_process_order.py -v
```

Capture verbatim output. All tests must be green. This is the new baseline.

Repeat Phases 1–3 for each uncovered path you identified from the coverage report. After you've done this enough times, your coverage of `process_order` is effectively 100% (or at least: 100% of the behavior paths that anyone has ever observed mattering — the hard truth is that paths nobody has observed are paths nobody will miss if they break, but they are also paths that will burn you when an edge case hits in prod).

A practical heuristic for "enough characterization tests": iterate `pytest --cov` until the coverage report shows every branch in `process_order` is hit. That is the minimum bar before Stream B begins.

**Exit condition for Stream A:** coverage report shows every branch in `process_order` is exercised by a test, and the full suite is green.

---

## Phase 4 — Refactor (now safe, because the function is pinned)

Now you enter Stream B. This is what your teammates wanted to do on minute one. The reason you waited is: now, when a refactor breaks behavior, the suite tells you. Before Stream A, it would not have.

Refactor in **small, revertible steps**, running the full suite after each step. The discipline:

1. Pick the smallest extraction that reduces complexity. E.g. "extract the inventory-decrement-and-rollback block into `_decrement_inventory_or_rollback(inventory, items)`." Not "rewrite the function."
2. Make the edit.
3. Run the full suite. Verbatim output.
4. **If green:** commit this step. Move to step 1 again with the next smallest extraction.
5. **If red:** revert the edit. The refactor changed behavior. Either (a) try a smaller step, or (b) the test that went red is telling you the refactor genuinely broke a pinned behavior — investigate which behavior, and decide whether the "new" behavior is actually correct (in which case: separate conversation, separate cycle, with the team lead and the affected test owners) or whether the refactor is wrong.

Order of extractions, in decreasing safety:
- **Pure extractions** (lift a contiguous block into a helper, no logic change) are safest. Do these first.
- **Reorganizations** (move blocks around, change order of operations) are riskier. Do these only after the extractions, and only one at a time.
- **Logic changes** (collapse two branches that "look equivalent," remove "dead" code) are NOT refactors. They are behavior changes. They get their OWN feature/bugfix TDD cycle, with their own failing test for the new behavior FIRST.

Each step has its own micro Phase 5: show the diff, show the suite output. The visible trace is the proof you didn't break anything silently.

**Exit condition:** the function is decomposed into smaller pieces, the full suite is green, and every step is recorded with a diff and a green test run.

---

## Phase 5 — Show the work and ask about the next cycle

After each characterization cycle and each refactor step, output the trace in the standard format:

```
## TDD cycle: characterize process_order behavior on [path X]

### Red — failing test (or: characterization assertion)
File: tests/test_process_order.py
[code block of the test]

Test run output:
[verbatim — for characterization, this should show PASSING against unchanged code,
 or show the failure that revealed your assumption about legacy behavior was wrong,
 followed by the corrected test passing.]

### Green — minimum implementation
File: NONE — characterization cycle, no implementation change.

Suite run output:
[verbatim full-suite output, all green, including the new characterization test.]

### Refactor
None — characterization cycles do not refactor.

### Next behavior?
The smallest next behavior I'd characterize is: [next uncovered path from coverage report].
Tell me to proceed, or name a different next path.
```

For a refactor step:

```
## TDD cycle: refactor — extract [helper name]

### Red — failing test
NONE — refactor cycle. The "red" is replaced by the baseline: full suite is green
against unchanged code, captured before the edit.

Baseline suite output:
[verbatim, all green.]

### Green — minimum implementation
File: src/orders.py
[diff of the extraction]

Suite run output:
[verbatim, all green. If not all green: revert the edit; this section reports the
 revert and explains which test went red and why.]

### Refactor
[This IS the refactor cycle, so this section names what was done and why.]

### Next behavior?
The smallest next refactor step I'd take is: [next extraction].
Tell me to proceed, or name a different next step.
```

---

## Quality gates — applied to YOUR situation

| Gate | What it catches in your refactor |
|---|---|
| 1. Test-first ordering | Did the characterization tests for the uncovered 40% land BEFORE any refactor edit? If you wrote the extractions first and the characterization tests after, the tests confirm the refactored behavior, not the legacy behavior — useless. |
| 2. Test failed for the right reason | For characterization: did the test pass against unchanged code (correctly characterizing) OR fail-then-corrected (assumption was wrong, fixed)? It must NOT be a test that fails because of a fixture bug or a missing import. |
| 3. Minimum implementation | For refactor cycles: each step is one extraction. Not five. Not "while I'm in here, also rename three things." One. |
| 4. Suite stays green | After every refactor step, the full suite is green. The instant it goes red, the step reverts. No exceptions for "the failing test was wrong anyway" — that is a separate conversation. |
| 5. Visible trace | Every characterization cycle and every refactor step has its own verbatim before/after output. The team lead and your teammates can audit the entire refactor by reading the trace. This is also your defense if a regression somehow ships: "here is the suite that was green at every step; here is the path that was not covered by any test or characterization; here is why coverage was incomplete." |

---

## What to tell your team lead and your teammates

**Team lead:** "EOD is tight. To refactor this safely I need to write characterization tests for the uncovered 40% of `process_order` first — without those, the refactor is silently risky. Estimate: [N hours] for characterization, [M hours] for the refactor itself. If [N+M] doesn't fit before EOD, the options are (a) ship safely on [later date], (b) ship a smaller refactor today (e.g. just one or two extractions in well-covered regions), or (c) accept the regression risk and ship the full refactor today on partial coverage. I recommend (b) — it's the largest safe step that fits in the budget."

**Teammates:** "I hear you on 'just refactor and trust the tests.' The tests cover 60%. The 40% they don't cover is exactly where a refactor will silently break things and we won't notice until a customer does. I'm writing characterization tests for that 40% before the refactor. It costs hours; not doing it costs incidents."

---

## Honest answer to your direct question

You asked me to be honest if TDD doesn't apply cleanly to a refactor of legacy code with partial coverage. Here is the honest version:

**TDD applies, but not in the form people usually mean.** "TDD on a refactor" is not "write a failing test for the refactored design." There is no new behavior to test, so there is no failing test to write. The correct form is: **characterization-first, then refactor against the pinned behavior, one small step at a time.** Anyone who tells you "TDD doesn't apply to refactors" is conflating two different things. TDD as feature discipline doesn't apply. TDD as a behavior-pinning discipline applies harder to legacy refactors than to anything else, because the cost of a silent regression is highest exactly where the test coverage is lowest.

The pressure from your team lead and your teammates is real, but it does not change the discipline — it only changes who you negotiate the timeline with. You negotiate the timeline with the team lead. You do not negotiate the discipline with yourself.

### Next behavior?

The smallest next behavior I'd characterize is: **the first uncovered branch in `process_order` as identified by `pytest --cov=src.orders --cov-report=term-missing`**. Run that command, paste me the missing-lines output, and I'll write the first characterization test against the specific uncovered path. Tell me to proceed, or name a different next path.

```


---
# Judge JSONs (36)


## CLAUDE judge


### claude — anthropic-canvas-design/01-poster

```json
{
  "task_compliance": {
    "A_complies": false,
    "B_complies": false,
    "notes": "Both outputs deliver Stage 1 (philosophy .md) plus a concrete visual specification, but neither produces a rendered visual artifact (.pdf or .png) \u2014 A explicitly defers Stage 2 ('Stage 2 may proceed to render artifact.pdf against this spec'), and B labels its render section 'executable spec' rather than producing a file. Per the cross-cutting rule ('If only one stage produced (or visual described but not specified concretely), cap at 3/5'), both spec the visual concretely but neither renders, so the cap applies symmetrically to both."
  },
  "verbosity_penalty_applied": {
    "A_penalized": false,
    "B_penalized": true,
    "notes": "B is meaningfully longer (~145 lines of dense spec including a manifesto with prose flourishes like 'death rattle of a confident form' and 'monastic accretion') while delivering equivalent design-decision density to A. The verbosity is partly decorative manifesto rather than load-bearing constraint; affects originality discipline and anti-genericness scores."
  },
  "scores_A": [
    {
      "dimension": "Aesthetic specificity",
      "score": 3,
      "justification": "Names an original movement ('Cathode Bloom'), cites a specific source (NTSC SMPTE ECR 1-1978 color bars off a degaussed Trinitron CRT + VHS bias-tape), and defines six named hex colors each tied to a specific signal region; capped at 3 by task-compliance rule despite 5-level specificity in the philosophy itself."
    },
    {
      "dimension": "Anti-genericness",
      "score": 3,
      "justification": "Explicitly bans Inter, Geist, SF Pro, Helvetica, Arial, Roboto, Montserrat, Poppins, plus purple/violet/lavender, magenta-to-blue gradients, drop shadows, glows, blurs, 'modern minimalist' fallback, and warm cream/kraft backgrounds \u2014 well past the 5-anchor threshold of '\u22653 AI-default patterns rejected'; capped at 3 by task-compliance rule."
    },
    {
      "dimension": "Design philosophy \u2192 visual coherence",
      "score": 3,
      "justification": "The Stage-2 visual spec maps tightly to the philosophy: 23 scanline bands (philosophy: 'Composition is a scanline column'), three color-bar interruption rows (philosophy: 'hierarchy is enforced by interference'), orange-channel +4px misregistration (philosophy: 'misregistered offset'), VT323 for metadata + IBM Plex Mono Bold for masthead with explicit reasons; capped at 3 because the artifact is specified, not rendered."
    },
    {
      "dimension": "Originality discipline",
      "score": 3,
      "justification": "Invents 'Cathode Bloom' as an original aesthetic and locates lineage in *register* (broadcast slates, leaders, bumpers, test cards) rather than imitating a named artist \u2014 Brakhage is referenced only as audience context ('Brakhage-fluent'), not as a visual model to copy; no designer's voice is mimicked; capped at 3 by task-compliance rule."
    },
    {
      "dimension": "Constraint honesty",
      "score": 3,
      "justification": "Names specific trade-offs with reasons (cyan held below 50% saturation 'because the CRT register cannot bloom it without compromising the orange channel'; explicit 'no hero image' against the typical poster grammar; brief-specific banned list of 5 items reflecting the user's stated fatigue); capped at 3 by task-compliance rule."
    }
  ],
  "scores_B": [
    {
      "dimension": "Aesthetic specificity",
      "score": 3,
      "justification": "Names 'Emulsion Rites' with eight named hex colors tied to chemical roles (Unfogged Base, Silver Halide Black with violet undertone, Safelight Bleed, Registration Cyan), plus a 12\u00d718 modular grid with measured positions in mm; specific at the philosophy level but capped at 3 by task-compliance rule (no rendered artifact)."
    },
    {
      "dimension": "Anti-genericness",
      "score": 3,
      "justification": "Bans drop shadows, bevels, gradients (except chemistry tide-lines), 'indie warm cream + black serif' tropes, photography of laurels/reels/projectors/popcorn, decorative ornaments, swooshes, icons; meets the \u22653-pattern bar; capped at 3 by task-compliance rule."
    },
    {
      "dimension": "Design philosophy \u2192 visual coherence",
      "score": 3,
      "justification": "Spec mirrors the philosophy (perforation strip + 8 stacked frames as 'direct-on-film gestures', edge-code micro-type, dust specks at named coordinates, hair-fiber on Frame III); but Frame contents (moth-wing fragments, 'closed-eye vision' dots) replicate Brakhage's specific motifs rather than translating philosophy into independent visual grammar; capped at 3 by task-compliance rule."
    },
    {
      "dimension": "Originality discipline",
      "score": 2,
      "justification": "Stage Two explicitly names Brakhage and lists his works (Mothlight 1963, Garden of Earthly Delights 1981, Dante Quartet 1987), then directly imports his signature gestures into the visual: 'moth-wing fragments' in Frame II echo Mothlight; 'closed-eye vision' in Frame VI is Brakhage's own term; the output frames this as 'subtle reference' but the rubric flags imitation of a named artist as a discipline failure \u2014 even before the cap, this scores low; with cap considered, the asymmetric weakness is real."
    },
    {
      "dimension": "Constraint honesty",
      "score": 3,
      "justification": "Names trade-offs (cream is here but as 'base stock, not nostalgia' \u2014 directly addressing the brief's rejected trope) and includes a 'Final Test' with viewing distances; the manifesto leans rhetorical ('monastic accretion', 'museum-grade artifact') rather than forcing decisions, but enough concrete constraints (no element overlap, 8-color cap, two display moments only) survive; capped at 3 by task-compliance rule."
    }
  ],
  "winner": "A",
  "winner_reasoning": "After symmetric task-compliance caps, A wins on Originality discipline (3 vs 2): B explicitly imports Brakhage's named works and his signature motifs (moth wings, closed-eye vision) into the visual, while A confines Brakhage to audience-context only and invents a separate broadcast-artifact lineage. A is also tighter on verbosity \u2014 B's manifesto carries more decorative prose without proportional constraint density, weakening anti-genericness and philosophy\u2192visual coherence at the margin.",
  "provenance_prediction": {
    "A_is": "handwritten",
    "B_is": "generated"
  },
  "provenance_reasoning": "A reads as the hand-tuned community skill: it invents a movement adjacent to but not imitative of Brakhage, holds tight verbosity discipline, and its bans/reasons feel battle-tested ('cyan held below 50% saturation because the CRT register cannot bloom it without compromising the orange channel' \u2014 the kind of reason a hand-tuned skill earns through iteration). B reads as freshly generated \u2014 it solves the brief by reaching for the most obvious named reference (Brakhage), then dresses the imitation as 'subtle' via a self-congratulatory 'Stage Two \u2014 The Subtle Reference (Deduced)' meta-frame, plus longer-than-needed manifesto prose ('death rattle of a confident form', 'monastic accretion') that signals model-style rhetorical inflation. Moderate confidence; the signature is the originality-discipline failure plus prose register."
}
```


### claude — anthropic-canvas-design/02-brand-identity

```json
{
  "task_compliance": {
    "A_complies": false,
    "B_complies": false,
    "notes": "The brief explicitly requests both a design philosophy (.md) AND a rendered example (logo + landing-page hero, .png). Neither A nor B produced a rendered visual artifact; both delivered only the philosophy document (with B including a more concrete visual specification table, but still no .png). Per the cross-cutting task-compliance cap, both sides are capped at 3/5 per dimension."
  },
  "verbosity_penalty_applied": {
    "A_penalized": false,
    "B_penalized": false,
    "notes": "Both pieces are roughly comparable in length and density. A is argument-dense with a long banned list; B trades some argumentation for a structured Visual Specification table with concrete tokens. Neither is meaningfully bloated relative to the other."
  },
  "scores_A": [
    {
      "dimension": "Aesthetic specificity",
      "score": 3,
      "justification": "Capped at 3 by task-compliance rule; absent the cap A would score 5: it names a precise aesthetic (VT220 amber-monochrome + Tektronix storage-tube green + IBM line-printer carbon ribbon) with hardware-sourced palette justification, 80-column TTY grid, and Plex Mono + Concourse Index typography with rationale and substitution rules."
    },
    {
      "dimension": "Anti-genericness",
      "score": 3,
      "justification": "Capped at 3; absent the cap A would score 5 \u2014 it explicitly names and rejects purple/violet/magenta-blue gradients, drop shadows/glows, Inter/Geist/SF Pro/Helvetica/Arial/Roboto/Montserrat/Poppins, glassmorphism, geometric sans wordmarks, isometric server-rack illustrations, rounded corners, and the named competitors (Datadog, Grafana, New Relic, Honeycomb, Chronosphere)."
    },
    {
      "dimension": "Design philosophy \u2192 visual coherence",
      "score": 2,
      "justification": "No rendered visual artifact was produced; the philosophy describes composition (log-line hero, flush-left wordmark, inline [OK]/[FAIL] tokens, 2\u20134% noise overlay) but there is no .png to confirm coherence, so the philosophy\u2192visual link is asserted rather than demonstrated."
    },
    {
      "dimension": "Originality discipline",
      "score": 3,
      "justification": "Capped at 3; A draws aesthetic source from hardware (VT220, Tektronix, IBM line printer) and engineering culture references rather than imitating a named contemporary designer, and explicitly warns against 'cosplay' when simulating texture."
    },
    {
      "dimension": "Constraint honesty",
      "score": 3,
      "justification": "Capped at 3; A surfaces real trade-offs explicitly (flatness vs. simulated noise as 'the honest choice when simulation would tip into cosplay'; substitution rule for Concourse \u2192 Source Serif 4, never to a sans; brief-fit paragraph distinguishing staff-engineer buyer from procurement reviewer)."
    }
  ],
  "scores_B": [
    {
      "dimension": "Aesthetic specificity",
      "score": 3,
      "justification": "Capped at 3; B names a specific register (engineering logbook / Rotring 0.35 / oscilloscope + telex paper + risograph) with concrete hex tokens (#F4EFE6, #111111, #D97706, #1E6F8E, #9B2C2C), type stack (Plex Mono 10/14, Druk Wide Condensed 64\u2013120pt), and a 12-column 8pt baseline grid."
    },
    {
      "dimension": "Anti-genericness",
      "score": 3,
      "justification": "Capped at 3; B's Forbidden list rejects gradients, drop shadows, glassmorphism, isometric cubes, lavender, teal, rounded-rectangle logos, 'seamless'/'empower', and stock photography \u2014 specific but shorter than A's banned list and does not name specific banned typefaces (Inter/Geist/etc.) or named competitors."
    },
    {
      "dimension": "Design philosophy \u2192 visual coherence",
      "score": 3,
      "justification": "Capped at 3; B does not produce a rendered .png either, but offers the most concrete visual blueprint of the two (token table, logo grammar with build hash, hero composition specifying 24 sparkline cells with one circled in amber, monospaced CTA with hand-drawn underline) \u2014 closer to a build-ready spec, but still not a rendered artifact."
    },
    {
      "dimension": "Originality discipline",
      "score": 3,
      "justification": "Capped at 3; B builds an original aesthetic from generic source materials (logbook, telex, risograph, HP-15C manual) without imitating a named living designer, though the 'hand-mark / circled cell / stamp slightly off-axis' motif risks pastiche of analog-engineering nostalgia."
    },
    {
      "dimension": "Constraint honesty",
      "score": 2,
      "justification": "Capped at 3 but scored lower: B asserts trade-offs less explicitly than A (no equivalent of A's 'flatness is the honest choice when simulation would tip into cosplay' or its staff-engineer-vs-procurement reasoning); copy like 'painstaking calibration by someone at the absolute top of their field' verges on self-flattering rather than naming a forced decision."
    }
  ],
  "winner": "A",
  "winner_reasoning": "Both outputs are capped at 3/5 by the task-compliance rule (no rendered .png produced), so the contest is decided within the cap. A wins on Anti-genericness (longer, more specific banned list including named typefaces and named competitors Datadog/Grafana/New Relic/Honeycomb/Chronosphere) and on Constraint honesty (explicitly names trade-offs like flat-vs-simulated-noise and the staff-engineer-vs-procurement buyer split). B has a slightly stronger Visual Specification table, but A's discipline against AI-default and 'cosplay' tells is the decisive signal for this rubric.",
  "provenance_prediction": {
    "A_is": "handwritten",
    "B_is": "generated"
  },
  "provenance_reasoning": "A reads like a hand-tuned skill: it enforces specific anti-AI heuristics (banned typeface list, named competitor list, anti-cosplay caveat, substitution-but-never-to-a-sans rule) that look like accumulated lessons from prior runs. B is polished and structurally clean with a tidy spec table, but its prose leans on aspirational craft language ('painstaking calibration by someone at the absolute top of their field', 'confess their seams') that is a common signature of freshly generated meta-skill output trying to sound rigorous. Moderate confidence."
}
```


### claude — anthropic-canvas-design/03-data-viz-aesthetic

```json
{
  "task_compliance": {
    "A_complies": true,
    "B_complies": true,
    "notes": "Both outputs deliver a philosophy and a concretely specified visual artifact. Neither produces an actual rendered .png file, but both specify the artifact concretely enough (exact hex codes, dimensions, layout, typography, data placement) to avoid the cross-cutting cap. A specifies a single-plate 8.5x11 layout with exact pt sizes and mm spacings; B provides a full HTML/CSS sketch, the actual CAL FIRE data table, and a render-tool plan."
  },
  "verbosity_penalty_applied": {
    "A_penalized": false,
    "B_penalized": false,
    "notes": "B is somewhat longer than A but the extra length carries concrete content (data table, CSS sketch, self-inspection checks, banned-list) rather than padding. A is denser per word but B is not bloated. No verbosity penalty warranted on either side."
  },
  "scores_A": [
    {
      "dimension": "Aesthetic specificity",
      "score": 5,
      "justification": "Names a specific aesthetic ('Forensic Cartography') anchored in nautical charts, geological surveys, and 19th-century ordnance maps, with concrete principles: hairline accumulation as sediment, monumental anchor numeral, two-or-three exact type sizes, and a forensic palette (#F2EBDD/#1A1714/#6B2417)."
    },
    {
      "dimension": "Anti-genericness",
      "score": 4,
      "justification": "Explicitly rejects gradients, drop shadows, rounded corners, icons, fills-as-decoration, horizontal gridlines, and titles/legends \u2014 but does not name specific AI-default fonts (e.g., Inter, Geist) or call out 'purple gradients' / glassmorphism by name as the rubric's 5-anchor specifies."
    },
    {
      "dimension": "Design philosophy \u2192 visual coherence",
      "score": 5,
      "justification": "The visual spec executes the philosophy precisely: bars-as-stacked-hairlines literalize 'sediment as evidence,' the oxidized-iron numeral anchors the page exactly as 'one enormous numeric element' described, registration marks and plate number realize the 'hand-pulled print' material memory, and the palette/type constraints hold across the artifact."
    },
    {
      "dimension": "Originality discipline",
      "score": 5,
      "justification": "Coins an original movement name and refuses to imitate any named designer; references disciplines (cartography, ordnance survey) as grammatical sources rather than copying a specific artist's work, and the hairline-sediment construction is a genuinely fresh visual primitive."
    },
    {
      "dimension": "Constraint honesty",
      "score": 4,
      "justification": "Forces specific decisions throughout (one accent color load-bearing, two catastrophic years marked identically without dramatization, no titles that explain what the picture shows) but does not explicitly name a brief tradeoff or call out where the brief was under-specified \u2014 the discipline is implicit rather than declared."
    }
  ],
  "scores_B": [
    {
      "dimension": "Aesthetic specificity",
      "score": 5,
      "justification": "Names a specific aesthetic ('Fire-Season Ledger') sourced from a precisely cited era ('Department of the Interior Forest Service annual reports, 1958\u20131971, before four-color process reached field publications'), with concrete typography (Trinit\u00e9/Lyon Display + Plantin) and a four-hex palette."
    },
    {
      "dimension": "Anti-genericness",
      "score": 5,
      "justification": "Explicitly bans by name 'Inter, Geist, SF Pro, Helvetica, Arial, Roboto, Montserrat, Poppins,' purple/violet/lavender gradients, drop shadows/glows/blurs, modern minimalist fallback, gridlines, bar chart geometry, continuous color ramps, and flame icons \u2014 meeting and exceeding the 5-anchor's '\u22653 AI-default patterns' bar."
    },
    {
      "dimension": "Design philosophy \u2192 visual coherence",
      "score": 5,
      "justification": "Visual spec implements the ledger philosophy concretely: row-per-year with year/rule/figure grid, binary above/below-mean ink rule applied to specified years (2017/2018/2020/2021), no axes or gridlines, footer-rule with eleven-year total \u2014 and CSS variables enforce the four-color constraint mechanically."
    },
    {
      "dimension": "Originality discipline",
      "score": 4,
      "justification": "Coins an original movement name and refuses any contemporary designer reference, but the ledger form is itself a recognizable historical genre being adopted rather than a fully original visual primitive; the self-check note 'not as a known designer's work' shows awareness of the discipline."
    },
    {
      "dimension": "Constraint honesty",
      "score": 5,
      "justification": "Explicitly names tradeoffs ('the designer's job is to remove obstacles between the reader and the figure'), forces specific decisions (binary above/below-mean cut rejecting continuous ramps, no sans-serif anywhere, hairline rules instead of filled bars) and includes a Phase 3 self-inspection checklist that verifies each constraint mechanically."
    }
  ],
  "winner": "B",
  "winner_reasoning": "B wins on Anti-genericness (explicit named-font ban list and per-category banned list versus A's structural-only refusals) and Constraint honesty (explicit tradeoff declarations and a mechanical self-inspection checklist). A is genuinely competitive on visual coherence and originality (the hairline-sediment construction is more inventive), but B's combination of period-specific provenance, real CAL FIRE data table with computed mean and per-year ink assignments, and the enforced banned-list edges it ahead overall.",
  "provenance_prediction": {
    "A_is": "generated",
    "B_is": "handwritten"
  },
  "provenance_reasoning": "B exhibits hand-tuned signals: a closing terminal-style status block ('canvas-design \u2014 done' with box-drawing characters), explicit Phase 2 / Phase 3 stage labels, a self-inspection checklist with checkmarks, real data substituted into the spec, and substitute-font fallbacks (Lyon Display \u2192 Source Serif Pro) \u2014 all hallmarks of a skill iterated against real renders. A reads as a freshly-generated, beautifully-written single-pass artifact: pure prose philosophy plus a tightly-specified plate, but no scaffolding, no real data resolution, no self-check loop."
}
```


### claude — chrisvoncsefalvay-d3/01-bar-with-edge-case

```json
{
  "task_compliance": {
    "A_complies": true,
    "B_complies": true,
    "notes": "Both deliver a horizontal bar chart in d3 v7+ with animated transitions, hover tooltips, responsive width, multi-framework mounts, and explicit edge-case handling (zero-bar minimum width + symlog for outliers). Both are on-task; no caps applied."
  },
  "verbosity_penalty_applied": {
    "A_penalized": true,
    "B_penalized": false,
    "notes": "A is meaningfully longer (value-label number-tween, scale toggle UI, randomize button, idempotent root-g pattern with manual enter/merge/exit) without proportional benefit over B's tighter join() pipeline. The extra surface area mostly restates what the symlog + minBar already accomplish; penalty applied to explanatory comments and code completeness scoring."
  },
  "scores_A": [
    {
      "dimension": "Code completeness",
      "score": 5,
      "justification": "Paste-and-run: full d3 import, dimensions resolution from getBoundingClientRect, axes with transitions, keyed data join, tooltip singleton on body, value labels with number tween, zero baseline guide, ResizeObserver via setupResponsiveBarChart, plus a complete vanilla HTML harness with sample dataset matching the brief."
    },
    {
      "dimension": "API correctness",
      "score": 3,
      "justification": "Modern d3 v7 surface (scaleSymlog, axisBottom, scaleBand, d3.format, interpolateNumber), but uses the older enter/merge/exit pattern (`bars.enter().append(...).merge(bars).transition()...`) rather than the v7-idiomatic `selection.join()`; rubric anchor explicitly downgrades `.enter().append()` without `.join()` to ~3."
    },
    {
      "dimension": "Framework-agnosticism",
      "score": 5,
      "justification": "Core `drawBarChart(svgElement, data, options)` accepts an SVG node or selector and has zero framework imports; explicit Vanilla/React/Vue/Svelte mount snippets are provided and each only wires lifecycle around the same pure function."
    },
    {
      "dimension": "Explanatory comments",
      "score": 4,
      "justification": "Inline comments justify symlog (`constant=1 \u21d2 ~linear near zero, log far from zero`), keyed join, idempotent root-g, tooltip-on-body, and the minBarPx floor; followed by an edge-case table and a dedicated 'Notes on the design choices' section. Slight verbosity penalty keeps it from a 5."
    },
    {
      "dimension": "Edge-case handling",
      "score": 5,
      "justification": "Filters NaN/null while keeping zeros, enforces minBarPx for zero bars with a dashed grey stroke and `(zero)` tooltip annotation, supports negative values via `Math.min(xZero, xScale(d.value))` and a zero baseline, and offers a symlog/linear toggle for honest comparison."
    }
  ],
  "scores_B": [
    {
      "dimension": "Code completeness",
      "score": 5,
      "justification": "Single `render(container, data, options)` returns `{update, cleanup}`; full modular imports, ResizeObserver-driven sizing, scales, both axes, selection.join enter/update/exit transitions, tooltip div with pointer-following, plus working Vanilla/React/Vue/Svelte snippets and a sample dataset that hits the brief (zero + outliers)."
    },
    {
      "dimension": "API correctness",
      "score": 5,
      "justification": "Pure d3 v7+: `selection.join(enter, update, exit)`, modular `d3-scale`/`d3-axis`/`d3-selection`/`d3-array`/`d3-format` imports, `pointer(event, parent)` instead of deprecated `d3.event`, `axisBottom(x).ticks(5, '~s')` for symlog tick density, and `selection.interrupt()` before teardown."
    },
    {
      "dimension": "Framework-agnosticism",
      "score": 5,
      "justification": "`viz.js` imports only `d3-*` packages (no react/vue/svelte), accepts either an `<svg>` or a wrapper `<div>` and adapts (`ownsSvg` branch), and the same `render()` is called identically from all four host snippets via refs/bind."
    },
    {
      "dimension": "Explanatory comments",
      "score": 5,
      "justification": "Every primitive choice is justified inline: symlog vs linear vs log, ResizeObserver vs window.resize, `selection.join()` vs `enter().append()`, `pointer()` vs `d3.event`, tooltip-div vs SVG `<title>`, plus an upfront 'Primitive selections' block and a closing quality-gates self-check that maps each gate to evidence."
    },
    {
      "dimension": "Edge-case handling",
      "score": 4,
      "justification": "Symlog handles outliers, `Math.max(minBarPx, x(d.value))` keeps zero bars visible, cleanup interrupts in-flight transitions and disconnects the observer; however the domain is fixed `[0, vMax]` so negative values are silently clipped, and there is no explicit visual differentiation for the zero bar (no dashed outline / 'zero' tooltip annotation like A)."
    }
  ],
  "winner": "B",
  "winner_reasoning": "API correctness is the decisive dimension: B uses the v7-idiomatic `selection.join()` while A relies on the older `enter().append().merge()` pattern, which the rubric anchors at 3. B also has crisper explanatory comments (every primitive choice justified plus a self-check) and a real cleanup contract. A wins edge-case handling on negatives and the zero-bar styling, but the verbosity penalty on A and the API correctness gap give B the clear edge overall.",
  "provenance_prediction": {
    "A_is": "generated",
    "B_is": "handwritten"
  },
  "provenance_reasoning": "B reads like a community-tuned skill: parsed-spec preamble, an explicit 'primitive selections' rationale section, modular `d3-*` imports (a deliberate package-size choice rather than the default `import * as d3`), idiomatic `selection.join()`, a real `cleanup()` with `interrupt()`, and a closing quality-gates self-check that mirrors a SKILL.md acceptance contract. A is more feature-rich and visually polished (toggle UI, number-tween labels, zero baseline) but uses the older enter/merge/exit pattern and the kitchen-sink `import * as d3` \u2014 signals consistent with a freshly-generated skill optimizing for breadth over idiom discipline. Moderate confidence."
}
```


### claude — chrisvoncsefalvay-d3/02-network-graph

```json
{
  "task_compliance": {
    "A_complies": true,
    "B_complies": true,
    "notes": "Both outputs build a force-directed network graph meeting all stated requirements (force simulation + collision, weighted edge thickness, Tableau10 group color, drag, zoom+pan, legend, vanilla/agnostic, bounded settle time). No off-topic content; no caps triggered."
  },
  "verbosity_penalty_applied": {
    "A_penalized": false,
    "B_penalized": true,
    "notes": "B is meaningfully longer (lifecycle contract, parsed-spec table, primitive table, quality-gates self-check, why-primitives section) without proportional functional gain over A. Penalty considered against B on Explanatory comments (not rewarding length as depth) and Code completeness (B requires a bundler for ESM imports, so not strictly paste-and-run in a browser)."
  },
  "scores_A": [
    {
      "dimension": "Code completeness",
      "score": 5,
      "justification": "Self-contained HTML scaffold with CDN d3 v7 script tag plus full graph.js: data generator, scales, simulation, links, nodes, drag, zoom, legend, tick handler, resize. Paste-and-run in any browser with no build step."
    },
    {
      "dimension": "API correctness",
      "score": 5,
      "justification": "Pure d3 v7 idioms throughout: scaleOrdinal/scaleLinear, selection.join(), forceSimulation with link/charge/center/collide/x/y, d3.zoom().scaleExtent, d3.drag with fx/fy. No deprecated APIs, no v3/v4 patterns, no d3.event."
    },
    {
      "dimension": "Framework-agnosticism",
      "score": 5,
      "justification": "No framework imports; mounts on a CSS selector ('#chart') against a plain <svg>. The vanilla HTML scaffold demonstrates mounting; would drop into React useEffect / Vue onMounted unchanged."
    },
    {
      "dimension": "Explanatory comments",
      "score": 4,
      "justification": "Numbered section comments and rationale on alphaDecay (~halves runtime), heavier-edge link distance, collision radius, and legend-outside-zoom intent. Concise. Slightly less why-depth than B but covers the load-bearing choices."
    },
    {
      "dimension": "Edge-case handling",
      "score": 3,
      "justification": "Backbone-then-random link generation prevents fragmented graphs and dedupes via a seen set; setTimeout(stop, 5000) caps runaway simulations; resize re-renders. But no explicit guards for empty data, single-point input, or equal-weight extent (d3.extent on empty array would yield [undefined, undefined])."
    }
  ],
  "scores_B": [
    {
      "dimension": "Code completeness",
      "score": 4,
      "justification": "Full module with render/update/cleanup, demo data, and integration HTML. However ESM 'import { ... } from \"d3-selection\"' bare specifiers require a bundler or import map; not strictly paste-and-run in a vanilla browser without additional setup, unlike A's CDN approach."
    },
    {
      "dimension": "API correctness",
      "score": 5,
      "justification": "Modern d3 v7+ throughout: selection.join with key functions, modular imports of d3-force/d3-zoom/d3-drag/d3-scale, alphaDecay+alphaMin, scaleOrdinal(schemeTableau10), scaleLinear with clamp. No deprecated APIs."
    },
    {
      "dimension": "Framework-agnosticism",
      "score": 5,
      "justification": "Returns { update, cleanup } lifecycle suitable for any host; explicit 'wrap in useEffect/onMounted/onMount' implied by the cleanup contract; integration example uses vanilla <script type=module>. No framework dependencies."
    },
    {
      "dimension": "Explanatory comments",
      "score": 5,
      "justification": "Why-comments on chargeStrength tuning, alphaDecay vs default, scaleOrdinal vs Category10, linear-not-sqrt for stroke perception, two-<g> layering for legend anchoring, selection.join semantics, and a dedicated 'Why these primitives' section."
    },
    {
      "dimension": "Edge-case handling",
      "score": 4,
      "justification": "Handles equal-domain weight extent (collapses to [0, max]), nullish-coalesces extent default to [1,10], clamps stroke scale, copies caller data to avoid mutation, real cleanup detaches .zoom/.drag/tick handlers, update() preserves simulation state for surviving nodes. Still no explicit empty-nodes guard, but materially better than A."
    }
  ],
  "winner": "B",
  "winner_reasoning": "B wins on Edge-case handling (4 vs 3: clamped weight scale, equal-domain handling, real cleanup, immutable input copy, stateful update) and Explanatory comments (5 vs 4: dedicated rationale section explaining each primitive choice). A wins Code completeness (5 vs 4) because it is genuinely paste-and-run via CDN while B requires a bundler. Net: B edges ahead 23 vs 22 on quality dimensions even after the verbosity penalty against B's prose.",
  "provenance_prediction": {
    "A_is": "generated",
    "B_is": "handwritten"
  },
  "provenance_reasoning": "B's structure (parsed-spec block, phase-2/phase-3 primitive table, lifecycle contract, quality-gates self-check enumerating Gate 1-6) reads like a hand-tuned skill enforcing a deliberate process \u2014 exactly the shape of a community skill maintained over time. A is polished and pragmatic but more linear and demo-oriented (CDN + generateData + bootstrap), which fits a freshly generated skill that optimizes for 'works on first paste'. Moderate confidence; the self-check section in B is the strongest signal."
}
```


### claude — chrisvoncsefalvay-d3/03-animated-transition

```json
{
  "task_compliance": {
    "A_complies": true,
    "B_complies": true,
    "notes": "Both produce an animated d3 v7 line chart with Toggle Year, scalePoint x / scaleLinear y, curveMonotoneX, .transition() API (no deprecated .tween()), and address point-by-point morph. A ships a framework-agnostic ES module with explicit React/Vue/Svelte/vanilla integration snippets; B ships a single global-script file plus a complete HTML mount. Both are on-task and avoid the 3/5 off-topic cap."
  },
  "verbosity_penalty_applied": {
    "A_penalized": false,
    "B_penalized": false,
    "notes": "A is longer because it adds genuine value the rubric rewards (modular imports, four framework adapters, cleanup with .interrupt(), edge-case padding). B is more concise but its concision corresponds to less coverage, not equal usefulness \u2014 so no asymmetric verbosity penalty is warranted."
  },
  "scores_A": [
    {
      "dimension": "Code completeness",
      "score": 5,
      "justification": "Paste-and-run ES module with explicit imports, full SVG shell, scales, axes, line generator, dots via selection.join(), initial draw, update(), cleanup(), plus a vanilla HTML harness that wires the Toggle Year button and includes both 12-row datasets."
    },
    {
      "dimension": "API correctness",
      "score": 5,
      "justification": "Pure d3 v7+: scaleLinear/scalePoint, axisBottom/axisLeft, line().curve(curveMonotoneX), selection.join(enter,update,exit), attrTween('d', interpolateString(prev,next)), easeCubicInOut, and the explicit `import 'd3-transition'` side-effect required by modular packages \u2014 no deprecated APIs, no .tween()."
    },
    {
      "dimension": "Framework-agnosticism",
      "score": 5,
      "justification": "The d3 module imports zero framework code and accepts either a selector string or DOM element; the response then provides explicit mount snippets for vanilla, React (useEffect/useRef), Vue 3 (onMounted/onUnmounted), and Svelte (onMount/onDestroy), exactly the rubric's 5/5 anchor."
    },
    {
      "dimension": "Explanatory comments",
      "score": 5,
      "justification": "Each non-trivial primitive choice has a one-line rationale (scalePoint vs scaleLinear, curveMonotoneX vs curveCardinal overshoot, attrTween+interpolateString vs default 'd' tween, easeCubicInOut, the d3-transition side-effect import, .nice()+5% pad, .interrupt() in cleanup)."
    },
    {
      "dimension": "Edge-case handling",
      "score": 4,
      "justification": "Recomputes y-domain on every update with a 5% pad and `|| 1` guard against zero range, uses `.nice()`, keys dots by month for stable enter/update/exit, and interrupts in-flight transitions on cleanup; does not explicitly handle empty-array, single-point, or NaN/missing values, so not a full 5."
    }
  ],
  "scores_B": [
    {
      "dimension": "Code completeness",
      "score": 5,
      "justification": "Includes a complete HTML page (CSS, button, year-label, svg, d3 CDN script tag) plus a full animated-line.js with both 12-month datasets, scales, axes, path, circles, update(), and toggle wiring \u2014 paste-and-run."
    },
    {
      "dimension": "API correctness",
      "score": 3,
      "justification": "Modern in most respects (d3.scalePoint, d3.scaleLinear, d3.axisLeft/Bottom, d3.line().curve, shared d3.transition() with ease), but the dot data join uses the deprecated v3-style `circles.enter().append()` + `circles.transition()` + `circles.exit()` pattern instead of `selection.join()` \u2014 this is exactly the 3/5 anchor in the rubric ('\u22651 deprecated method, e.g. .enter().append() without .join()')."
    },
    {
      "dimension": "Framework-agnosticism",
      "score": 3,
      "justification": "The script is portable in principle but is written as a top-level global script that runs at module load (touches the DOM and binds a click handler immediately); it only describes wrapping it in useEffect/onMounted/onMount in prose rather than providing the snippets, so it is mostly portable but assumes one host pattern (vanilla)."
    },
    {
      "dimension": "Explanatory comments",
      "score": 4,
      "justification": "Strong narrative comments explaining the shared transition object, why .transition(t).attr('d', lineGenerator) interpolates the path string, axis transitions via .call, and a useful 'How the transition primitives compose' table \u2014 but lacks justification for some choices (scalePoint over scaleTime, monotoneX over alternatives) at the level Output A provides."
    },
    {
      "dimension": "Edge-case handling",
      "score": 3,
      "justification": "Updates yScale.domain([0, yMax * 1.1]) on each toggle and keys circles by month; comments acknowledge the exit branch is dead code for equal-length datasets but include it. No guard for empty data, missing values, or zero range, and no transition .interrupt() on teardown (no cleanup function at all)."
    }
  ],
  "winner": "A",
  "winner_reasoning": "API correctness and framework-agnosticism decide it. Output B trips the rubric's explicit 3/5 anchor on API correctness by using `circles.enter().append()` + separate `.transition()`/`.exit()` instead of `selection.join()`, while Output A uses `.join(enter, update, exit)` with per-branch transitions. Output A also matches the 5/5 framework-agnosticism anchor exactly \u2014 module mounts on any DOM node with vanilla/React/Vue/Svelte snippets \u2014 whereas B is a top-level global script that only describes framework wrapping in prose. A also handles cleanup (.interrupt()) which B omits.",
  "provenance_prediction": {
    "A_is": "handwritten",
    "B_is": "generated"
  },
  "provenance_reasoning": "A reads like a hand-tuned community skill: stable phase headers ('Phase 1 Parsed spec / Phase 2 Primitive selections / Phase 3 Generated module / Phase 4 Quality gates self-check'), an explicit gates checklist with PASS markers, modular d3 imports with the d3-transition side-effect comment, and four ready-made framework adapters \u2014 all hallmarks of an iteratively refined skill that has accumulated lessons (cleanup via .interrupt, why-comments, equal-length morph caveat referencing flubber/d3-interpolate-path). B reads more like a freshly-generated meta-paap output: solid structure, prose-heavy primitive table, CDN-based single-file demo, and the .enter().append() slip on dots that a battle-tested skill would have stamped out. Moderate confidence."
}
```


### claude — gstack-plan-ceo-review/01-ambitious-roadmap

```json
{
  "task_compliance": {
    "A_complies": true,
    "B_complies": true,
    "notes": "Both produce structured plan reviews with mode + premises + hardest questions + next-iteration artifacts. Neither is off-topic. No task-compliance cap triggered for either side."
  },
  "verbosity_penalty_applied": {
    "A_penalized": false,
    "B_penalized": true,
    "notes": "B is roughly 2.5x longer than A and includes scaffolding (Section 1-11 N/A rows in a completion summary, ASCII state diagram, 9-decision list partly redundant with the cut list, 'STEP 0A/0B/0C/0C-bis/0D' headers) without proportional incremental insight. A delivers comparable analytical content (mode + 5 premises + 5 cuts + 3 hardest questions + decision taxonomy + next-iteration spec) more compactly. Penalty affects B's premise-challenges and hardest-question dimensions where length dilutes rather than deepens."
  },
  "scores_A": [
    {
      "dimension": "Mode declaration + fit",
      "score": 5,
      "justification": "Opens with 'Selected mode: SCOPE REDUCTION' and an explicit 'Why this mode' paragraph that names the structural mismatch (eight workstreams, 4-month build in 3-month quarter); mode is then consistently applied throughout via The Cut List and the Next-Iteration Spec that reduces 8 items to 3."
    },
    {
      "dimension": "Premise challenges",
      "score": 5,
      "justification": "Five premises each formatted with Status: BREAKS/CRACKS, 'What the user is assuming', 'What needs to be true', and 'Implication if it doesn't hold' \u2014 e.g., the 2nd-ICP challenge cites the 8% MoM / $180k MRR position to argue saturation isn't reached, and the AWS challenge calls 'enterprise reliability' in scare quotes a vibe rather than requirement."
    },
    {
      "dimension": "Hardest-question identification",
      "score": 5,
      "justification": "Names exactly 3 hardest unresolved questions, each with 'Why this is the hardest' and 'What answering it changes' (e.g., Q2 forces naming the enterprise pipeline value and notes that '<$500k ARR pipeline' would collapse half the plan). Forces decisions rather than gesturing."
    },
    {
      "dimension": "Decision-class taxonomy applied",
      "score": 5,
      "justification": "Explicitly separates 'Taste Calls I Made' (auto-applied) from '[ESCALATION DEFERRED] User Challenges' (surfaced to user), which maps directly onto the rubric's auto-decides vs surfaces vs escalates distinction. Each user challenge states recommendation, plan's position, and 'Awaiting user call before applying.'"
    },
    {
      "dimension": "Honest discomfort",
      "score": 4,
      "justification": "Calls the plan a 'board-pleasing menu, not a sequenced bet,' calls AWS migration 'infra theater,' and notes 'Enterprise reliability in scare quotes suggests the user already knows this is a vibe.' Direct, but slightly less viscerally confrontational than B's framing of board ambition."
    }
  ],
  "scores_B": [
    {
      "dimension": "Mode declaration + fit",
      "score": 5,
      "justification": "Opens with 'MODE DECLARATION: SCOPE REDUCTION,' explicitly justifies the override against context-default ('A feature enhancement / iteration plan would default to SELECTIVE EXPANSION. This isn't that'), and applies the mode through KEEP/DEFER/KILL on every line item."
    },
    {
      "dimension": "Premise challenges",
      "score": 5,
      "justification": "Five premises challenged with vivid concrete reasoning \u2014 e.g., 'Engineering estimates on greenfield mobile work are wrong by 1.5\u20132.5x in the optimistic direction,' the cargo-cult Series A framing, and the 2nd-ICP critique citing different workflows (Jira vs Figma, sprints vs critique sessions)."
    },
    {
      "dimension": "Hardest-question identification",
      "score": 4,
      "justification": "Surfaces 7 questions rather than the rubric's 1-3, which dilutes forcing power; however each question is concrete and decision-forcing (e.g., Q3 'Which of the 2 enterprise prospects is actually closing?' and Q7 modeling runway under new burn). Quantity over forced focus."
    },
    {
      "dimension": "Decision-class taxonomy applied",
      "score": 4,
      "justification": "Includes a strong Bezos one-way/two-way doors table classifying all 8 initiatives by reversibility \u00d7 magnitude, plus a 'REQUIRED EXPLICIT DECISIONS' D1-D9 list. Strong on reversibility taxonomy but does not separate auto-applied taste calls from escalations the way the rubric anchor implies (Mechanical/Taste/User-Challenge)."
    },
    {
      "dimension": "Honest discomfort",
      "score": 5,
      "justification": "Most confrontational lines in either output: 'The board will read this as less ambitious. They are wrong,' 'Founders confuse the board likes it with this is the right thing,' and 'A roadmap that requires the next round to close on schedule is not a roadmap. It's a hope.' Names uncomfortable truths directly."
    }
  ],
  "winner": "A",
  "winner_reasoning": "A wins on decision-class taxonomy (it cleanly separates auto-applied Taste Calls from [ESCALATION DEFERRED] User Challenges, matching the rubric's auto/surface/escalate framing, while B's Bezos two-way-door table is strong but answers a different question) and on hardest-question discipline (3 forced questions vs B's 7 which dilute). A also avoids the verbosity penalty B incurs. B narrowly edges A on honest-discomfort intensity but not enough to overturn A's advantage on two dimensions plus the verbosity penalty.",
  "provenance_prediction": {
    "A_is": "handwritten",
    "B_is": "generated"
  },
  "provenance_reasoning": "A uses precise, idiosyncratic vocabulary that reads like a shared template \u2014 'BREAKS/CRACKS' premise statuses, 'Taste Calls I Made,' '[ESCALATION DEFERRED] User Challenges,' 'Mode Deliverable,' 'Limitations' \u2014 and these terms recur with consistent structure suggesting an inherited voice contract. B uses common LLM strategy-essay tropes (Bezos one-way doors, cargo-cult framing, ASCII state diagram, exhaustive Section 1-11 completion-summary table with many N/A rows, 'STEP 0A/0B/0C/0C-bis/0D' enumeration) that read as freshly composed scaffolding rather than inherited template blocks. Moderate confidence; the gstack arm's documented voice-depth advantage is consistent with A's tighter idiomatic structure."
}
```


### claude — gstack-plan-ceo-review/02-feature-launch

```json
{
  "task_compliance": {
    "A_complies": true,
    "B_complies": true,
    "notes": "Both produce a structured plan review with mode + premises + questions. A is tightly on-task. B follows a heavier gstack template (Steps 0A-0E + Sections 1-11 + Completion Summary) but still answers the rubric requirements. No caps applied."
  },
  "verbosity_penalty_applied": {
    "A_penalized": false,
    "B_penalized": true,
    "notes": "B is roughly 3x longer than A and large sections are template ritual (Section 5 'n/a', Section 11 generic UX bullets, ASCII completion box, 'Lake Score'). Penalty affects hardest-question and decision-class dimensions where length did not translate into sharper push-back."
  },
  "scores_A": [
    {
      "dimension": "Mode declaration + fit",
      "score": 5,
      "justification": "Opens with 'Selected mode: SCOPE REDUCTION' plus a quantitative justification ('$60k of build cost for $15k incremental MRR... stacks four optimistic assumptions') and applies the mode consistently via the Cut List."
    },
    {
      "dimension": "Premise challenges",
      "score": 5,
      "justification": "Names four specific premises (anchor-customer justification, 30%\u00d750% pipeline math, competitive parity, 2-FTE allocation), tags each CRACKS/BREAKS, states what must be true, and the implication if it doesn't hold."
    },
    {
      "dimension": "Hardest-question identification",
      "score": 5,
      "justification": "Lists exactly 3 hardest unresolved questions (renewal-blocker vs preference, win/loss data on AI-insights gap, differentiated wedge vs Mode/Hex/ChartGPT), each with 'why hardest' and 'what answering it changes' \u2014 decision-forcing rather than diplomatic."
    },
    {
      "dimension": "Decision-class taxonomy applied",
      "score": 5,
      "justification": "Explicit 'Taste Calls I Made' section (auto-applied user-overridable choices) plus 'User Challenges [ESCALATION DEFERRED]' for the three big calls \u2014 textbook Mechanical/Taste/Challenge surfacing."
    },
    {
      "dimension": "Honest discomfort",
      "score": 4,
      "justification": "Direct lines like '20 interviews is research-theater', 'stacks four optimistic assumptions', and 'building the same feature three better-funded competitors already ship \u2014 at best achieving table stakes' \u2014 pointed but stops short of the fully personal '5' anchor (e.g., 'you're using this review as confirmation, not challenge')."
    }
  ],
  "scores_B": [
    {
      "dimension": "Mode declaration + fit",
      "score": 4,
      "justification": "Declares 'SELECTIVE EXPANSION' in Step 0D with reasoning, and the cherry-pick section applies the mode. However the mode is buried after a long pre-review audit and the verdict-up-front already commits to the conclusion, so application is a bit muddied by template scaffolding."
    },
    {
      "dimension": "Premise challenges",
      "score": 4,
      "justification": "Reframes the core premise well ('retention bet, not just growth bet') and pressure-tests the 30%/50% math, 8-week estimate, and request/response architecture. Less crisp than A's premise-by-premise CRACKS/BREAKS structure; some challenges diffuse into architecture/UX commentary."
    },
    {
      "dimension": "Hardest-question identification",
      "score": 3,
      "justification": "Surfaces important questions (push-vs-pull, eval set, hallucination handling, '8 weeks calendar habit?') but distributes them across cherry-picks, TODOs, and Section commentary rather than naming the 1-3 hardest decisions and forcing them \u2014 closer to 'questions to consider' than the 5 anchor."
    },
    {
      "dimension": "Decision-class taxonomy applied",
      "score": 3,
      "justification": "Cherry-picks carry 'recommendation posture' labels (Neutral, Strong recommend) and references AskUserQuestion, but there is no explicit Mechanical/Taste/Challenge separation; auto-applied vs surfaced vs escalated is implied rather than structured."
    },
    {
      "dimension": "Honest discomfort",
      "score": 4,
      "justification": "Has sharp lines ('optimizes for demo, not retention', 'is 8 weeks a thoughtful estimate or a calendar habit?', explicit 50%/25%/15% probability estimates, hallucinated-stat as existential risk). Cushioned somewhat by the long template ritual and procedural framing, but still delivers uncomfortable truths."
    }
  ],
  "winner": "A",
  "winner_reasoning": "A wins on hardest-question identification and decision-class taxonomy \u2014 the two dimensions where the rubric most rewards forcing decisions and naming auto/surface/escalate. A's premise challenges are also crisper (named premises with CRACKS/BREAKS status and 'what must be true'). B has more breadth (architecture, security, error map) but that breadth is partly verbosity penalty territory: longer plan that doesn't push back as hard scores lower per the cross-cutting rule.",
  "provenance_prediction": {
    "A_is": "generated",
    "B_is": "handwritten"
  },
  "provenance_reasoning": "B carries heavy templated voice/structure characteristic of an inherited SKILL.md.tmpl: explicit 'Step 0A/0B/0C/0C-bis/0D/0E', numbered Sections 1-11 (including Section 5 'n/a' and a Section 11 design pass on a strategy doc), an ASCII Completion Summary box with 'Lake Score', and ritual STATUS line \u2014 these read as ~600 lines of inherited shared blocks. A is leaner with bespoke section names ('Cut List', 'Taste Calls I Made', 'User Challenges [ESCALATION DEFERRED]') that look generated to fit this specific rubric rather than inherited templating. Moderate confidence."
}
```


### claude — gstack-plan-ceo-review/03-pivot-decision

```json
{
  "task_compliance": {
    "A_complies": true,
    "B_complies": true,
    "notes": "Both produce structured plan reviews with mode + premises + questions + next-iteration framing. A maps directly onto the rubric's structure (Mode, Premise Challenge, Mode Deliverable, Hardest Unresolved Questions, Taste Calls, User Challenges, Next-Iteration Spec). B produces a code-review-shaped megastructure (11 sections, audit, completion summary table) translated to strategy; on-topic but heavily templated for engineering reviews."
  },
  "verbosity_penalty_applied": {
    "A_penalized": false,
    "B_penalized": true,
    "notes": "B is roughly 6-7x longer than A. Several sections (Security & Threat Model, Performance, Observability, Deployment, Code Quality, Design & UX 'skipped') are code-review scaffolding awkwardly retargeted at a strategic plan and add little marginal signal beyond what the inside-review already says. Penalty applied to mode-fit and decision-class taxonomy dimensions where the verbosity dilutes the actual decision posture."
  },
  "scores_A": [
    {
      "dimension": "Mode declaration + fit",
      "score": 5,
      "justification": "Opens with 'Selected mode: HOLD SCOPE' and a paragraph justifying why ('the scope is correct; execution is under-specified in three load-bearing places'); the mode is then applied consistently \u2014 all six Sharpening List items refine the existing plan rather than expanding or contracting it."
    },
    {
      "dimension": "Premise challenges",
      "score": 5,
      "justification": "Names four specific premises ('same underlying product', '30 demos/week', '3 paid contracts at $25k+ ARR', 'B2C cannot be fixed in parallel'), labels each BREAKS/CRACKS, and gives concrete what-needs-to-be-true + implication-if-false reasoning (e.g., 'L&D buyers want skills assessments, learning paths tied to job roles\u2026 12 weeks is wrong by 2-3x')."
    },
    {
      "dimension": "Hardest-question identification",
      "score": 5,
      "justification": "Numbered list of exactly three hardest questions (product buyability, cofounder alignment data, runway under each scenario) with 'Why this is the hardest' and 'What answering it changes' framing \u2014 forces decisions rather than gesturing."
    },
    {
      "dimension": "Decision-class taxonomy applied",
      "score": 5,
      "justification": "Explicitly separates 'Taste Calls I Made' (auto-applied with reversion notes) from 'User Challenges' tagged '[ESCALATION DEFERRED]' (recommendation + plan position + 'Awaiting user call'); this is the Mechanical/Taste/User-Challenge split made visible in output structure."
    },
    {
      "dimension": "Honest discomfort",
      "score": 4,
      "justification": "Names uncomfortable truths directly ('the plan refuses to test [the premise] before committing 9 weeks', 'Cofounder misalignment at week 0 will become cofounder rupture at week 6', 'sunsetting prematurely destroys cash runway'). Stops short of B's bluntest framings ('founder anxiety dressed up as strategy') but is honest without being cruel."
    }
  ],
  "scores_B": [
    {
      "dimension": "Mode declaration + fit",
      "score": 4,
      "justification": "Mode declared upfront ('HOLD SCOPE with surgical interrogation') and re-affirmed in Step 0D, but the document then runs 11 code-review sections that mix critique with scope-expansion (proposing three approaches A/B/C, recommending Approach A first); mode is consistent in spirit but the sprawling structure dilutes the 'HOLD SCOPE' claim."
    },
    {
      "dimension": "Premise challenges",
      "score": 5,
      "justification": "Strong premise-level work: challenges 'GTM problem vs product problem' framing with concrete benchmarks (Duolingo ~2-3% churn vs user's 6%), suspects '1.4 LTV/CAC' is gross not contribution-margin and recomputes it likely <1.0, surfaces five counter-framings (a-e) the plan didn't rule out."
    },
    {
      "dimension": "Hardest-question identification",
      "score": 4,
      "justification": "Surfaces the right hardest question ('is the underlying product good enough to hold an enterprise relationship?') and names cofounder-alignment as the actual signal, but they're scattered across Step 0A, the outside-voice, and the closing take rather than enumerated as 1-3 named decisions; harder to extract under pressure than A's numbered list."
    },
    {
      "dimension": "Decision-class taxonomy applied",
      "score": 3,
      "justification": "Has implicit taxonomy via 'Unresolved Decisions' A/B/C and 'TODOS.md updates' with P1/P2 + S/M sizing, but does not explicitly classify what is auto-applied vs taste vs escalated; the binary 'accept reframe / proceed / cofounder path' is closer to a recommendation menu than a Mechanical/Taste/User-Challenge split."
    },
    {
      "dimension": "Honest discomfort",
      "score": 5,
      "justification": "Bluntest of the two: 'this plan reads like founder anxiety dressed up as strategy', 'pivot may be moving the bug from a place where users vote with $9.99/mo to a place where one buyer votes with $25k/yr', 'decisiveness without direction is just speed in a circle', and the outside-voice frames the deadline itself as a self-imposed forcing function. Delivers feedback the user couldn't get from agreeing with themselves."
    }
  ],
  "winner": "A",
  "winner_reasoning": "A wins on mode-fit, hardest-question identification, and decision-class taxonomy \u2014 the three dimensions that most directly track the rubric's prescribed plan-review structure. B is stronger on honest discomfort and ties on premise challenges, but the verbosity penalty (6-7x length, several sections that are code-review scaffolding retargeted at strategy) and the absence of an explicit auto/taste/escalate split mean B's extra length doesn't earn proportional rubric value.",
  "provenance_prediction": {
    "A_is": "handwritten",
    "B_is": "generated"
  },
  "provenance_reasoning": "A's structure (Mode \u2192 Premise Challenge with BREAKS/CRACKS labels \u2192 Mode Deliverable \u2192 Hardest Questions \u2192 Taste Calls \u2192 User Challenges with [ESCALATION DEFERRED] \u2192 Next-Iteration Spec \u2192 Limitations) reads like a stable hand-tuned template with disciplined section names; the User-Challenges-with-escalation-tags pattern is the kind of voice rule that gets refined over many iterations. B mirrors a generic code/plan-review megastructure (Architecture / Error Map / Security / Performance / Observability / Deployment / Long-Term / Design \u2014 even with a 'SKIPPED \u2014 no UI scope' marker) which is a tell of a workflow brief expanded into sections without pruning for fit; the 'Outside Voice \u2014 CODEX SAYS' simulated cross-model block also feels like a generated meta-feature rather than a polished community pattern."
}
```


### claude — obra-tdd/01-bug-fix

```json
{
  "task_compliance": {
    "A_complies": true,
    "B_complies": true,
    "notes": "Both outputs walk through a full TDD cycle on the calculate_average empty-input bug: pick a contract, write a failing test, verify it fails for the right reason, write minimal code, verify green, consider refactor. Neither side warrants the cross-cutting cap."
  },
  "verbosity_penalty_applied": {
    "A_penalized": true,
    "B_penalized": false,
    "notes": "A is meaningfully longer than B (Phase 0 routing block, more verbatim pytest output, explicit Quality Gate annotations, separate Phase 5 'show the work' that largely re-prints earlier blocks). Most of A's extra length is substantive (rationalization counters, contract-migration warning, opt-out protocol), but the duplicated Phase-5 reprint is filler \u2014 light penalty applied to test quality and cycle visibility scores where the extra length did not buy extra quality."
  },
  "scores_A": [
    {
      "dimension": "Discipline enforcement",
      "score": 5,
      "justification": "A explicitly refuses the 'hurry' framing up front ('Skipping it is the rationalization the skill exists to refuse \u2014 see row 1 of the table'), and gives a concrete bypass protocol ('say \"no TDD for this change\" explicitly, and I'll log it in the response... I will not silently skip') \u2014 naming the rationalization and forcing it to be visible if invoked."
    },
    {
      "dimension": "RED-GREEN-REFACTOR cycle visibility",
      "score": 4,
      "justification": "All three stages are clearly delineated as Phase 2/3/4 with verbatim failing and passing pytest output and an explicit 'None needed \u2014 implementation is already minimal' refactor verdict; minor deduction because Phase 5 redundantly reprints the same red/green output, slightly muddying the cycle rather than sharpening it."
    },
    {
      "dimension": "Test quality",
      "score": 5,
      "justification": "Single behavior, behavioral assertion via pytest.raises(ValueError, match='empty'), name describes the behavior not the function, and A explicitly enumerates what is NOT in the test ('No \"while we're here, also test the happy path\" \u2014 that is a separate cycle') \u2014 exemplifying minimal one-behavior-per-test discipline."
    },
    {
      "dimension": "Failure-mode coverage",
      "score": 5,
      "justification": "A names multiple specific rationalizations with counter-arguments: the 'hurry' rationalization ('was not protecting your time \u2014 it was protecting the habit of skipping tests'), batching extra assertions ('separate cycle'), inventing refactors to look thorough ('itself an anti-pattern'), and silently weakening callers that depended on ZeroDivisionError ('DO NOT delete or weaken that test')."
    },
    {
      "dimension": "Honesty when blocking",
      "score": 5,
      "justification": "A explicitly flags conditions under which the walkthrough would halt: 'if there is genuinely no runner wired up, halt and wire one up first \u2014 do not pretend', flags the full-suite output as uncertain ('full-suite numbers depend on your repo'), and surfaces the contract-migration cost honestly rather than pretending the fix is free for downstream callers."
    }
  ],
  "scores_B": [
    {
      "dimension": "Discipline enforcement",
      "score": 4,
      "justification": "B opens with 'The Iron Law: NO PRODUCTION CODE WITHOUT A FAILING TEST FIRST' and names the 'I'm in a hurry' rationalization as 'the most common rationalization for skipping tests', and refuses to touch production code until after Verify RED \u2014 solid enforcement, but lacks an explicit bypass protocol or visible-lapse logging mechanism, so the discipline is asserted rather than procedurally enforced."
    },
    {
      "dimension": "RED-GREEN-REFACTOR cycle visibility",
      "score": 5,
      "justification": "B has the cleanest possible cycle layout \u2014 RED, Verify RED (mandatory), GREEN, Verify GREEN (mandatory), REFACTOR \u2014 each with its own pytest output block, and the refactor section honestly says 'Nothing to refactor... Refactor is *optional*'; all three stages are unambiguous and non-redundant."
    },
    {
      "dimension": "Test quality",
      "score": 5,
      "justification": "Single behavior, pytest.raises(ValueError, match='empty'), behaviorally named test_empty_list_raises_value_error, and B annotates 'One behavior. Clear name. Tests the real function (no mocks)' \u2014 meets the rubric's 5-anchor for test quality directly."
    },
    {
      "dimension": "Failure-mode coverage",
      "score": 3,
      "justification": "B names the 'I'm in a hurry' rationalization clearly and warns about YAGNI temptations during GREEN ('No clever defaults, no logging, no Optional return type, no overload for generators, no numpy rewrite'), but does not enumerate distinct rationalizations with separate counter-arguments the way the 5-anchor requires (\u22653 specific rationalizations rejected)."
    },
    {
      "dimension": "Honesty when blocking",
      "score": 3,
      "justification": "B is honest in small ways ('That is fine. Refactor is *optional*' rather than fabricating a refactor; flagging sibling bugs to handle in separate cycles), but does not name harder blockers \u2014 what to do if no test runner exists, or if existing callers depend on the old ZeroDivisionError contract, both of which A explicitly addresses."
    }
  ],
  "winner": "A",
  "winner_reasoning": "A wins on Discipline enforcement, Failure-mode coverage, and Honesty when blocking \u2014 the three dimensions where the rubric's 5-anchors demand explicit, named rationalizations and explicit blocker-naming. B wins narrowly on RED-GREEN-REFACTOR cycle visibility (cleaner, less redundant layout) and ties on test quality, but those gains do not overcome A's substantively richer rationalization-rejection and honesty about edge cases (no runner, downstream callers depending on the old exception contract, opt-out logging protocol).",
  "provenance_prediction": {
    "A_is": "handwritten",
    "B_is": "generated"
  },
  "provenance_reasoning": "A references a specific 'row 1 of the table', 'Phase 4, paragraph 2', 'Error Handling table, row 4', and Quality Gates 1\u20134 \u2014 these read as call-outs to a stable, hand-tuned SKILL.md with named structural elements that the author has internalized. B is well-written and clean but reads as a competent generic TDD walkthrough with idiomatic phrasing ('YAGNI', 'Mandatory', 'Pristine output') and a tidy commit-message bonus that feels assembled-from-best-practices rather than referencing a specific authored framework. Moderate confidence \u2014 A's specific structural references are the strongest signal."
}
```


### claude — obra-tdd/02-new-feature

```json
{
  "task_compliance": {
    "A_complies": true,
    "B_complies": true,
    "notes": "Both outputs walk through TDD on the discount calculator using pytest. A executes all 9 cycles end-to-end; B fully executes only Cycle 1 and sketches cycles 2-6, which is still a faithful walkthrough but slightly less complete in literal execution."
  },
  "verbosity_penalty_applied": {
    "A_penalized": false,
    "B_penalized": true,
    "notes": "B is comparable in length to A but delivers less concrete walkthrough per token because cycles 2-6 are sketched while still spending many words on phase/routing formalism. A's length is justified by additional content (mutation-testing validation of regression guards, full final refactor)."
  },
  "scores_A": [
    {
      "dimension": "Discipline enforcement",
      "score": 5,
      "justification": "Opens with the explicit Iron Law ('No production code without a failing test first'), states 'every line of discount.py is born from a test', and at Cycle 4 explicitly invokes the rule 'Test passes? You're testing existing behavior. Fix test.' before honestly choosing the regression-guard path."
    },
    {
      "dimension": "RED-GREEN-REFACTOR cycle visibility",
      "score": 5,
      "justification": "Every cycle shows RED test, Verify RED with pytest output, GREEN minimal code, Verify GREEN, and an explicit REFACTOR step (often 'nothing to clean'); the final refactor to a promo table after green coverage is exemplary."
    },
    {
      "dimension": "Test quality",
      "score": 5,
      "justification": "Tests are one-behavior-each, behavioral assertions on return values (not mocks), clear AAA structure, descriptive names like test_save20_no_discount_below_minimum; boundary tests at 49/50 and 30/31 are minimal and specific."
    },
    {
      "dimension": "Failure-mode coverage",
      "score": 4,
      "justification": "Names the 'test passes immediately' rationalization with a counter-argument and introduces mutation testing to prove a regression guard bites; final 'What we deliberately did NOT do' section names YAGNI rationalizations (Decimal, stacking, validation), but doesn't enumerate as many developer rationalizations as a 5."
    },
    {
      "dimension": "Honesty when blocking",
      "score": 5,
      "justification": "At Cycles 4, 6, 8, 9 honestly flags 'this actually passes immediately on current implementation \u2014 that's a red flag', then proposes a principled fix (mutation testing to validate the regression guard) rather than pretending the test went red."
    }
  ],
  "scores_B": [
    {
      "dimension": "Discipline enforcement",
      "score": 4,
      "justification": "Strong process scaffolding (Phase 0 routing, Phase 2 quality gate 'If the test PASSES on the first run: STOP'), and refuses to fake red on Cycles 4/6, but only Cycle 1 is fully executed and the rest are sketched, weakening the lived enforcement."
    },
    {
      "dimension": "RED-GREEN-REFACTOR cycle visibility",
      "score": 3,
      "justification": "Cycle 1 has full verbatim red and green pytest output and an explicit (no-op) refactor; cycles 2-6 are described in shape rather than walked, so RED/GREEN visibility is asymmetric across the six behaviors."
    },
    {
      "dimension": "Test quality",
      "score": 4,
      "justification": "Tests are behavioral, one-assertion, well-named (e.g. test_freeship_no_discount_when_subtotal_at_or_below_threshold), and pin both sides of strict-inequality boundaries; slight verbosity in test setup (full dict literals repeated) keeps it from a 5."
    },
    {
      "dimension": "Failure-mode coverage",
      "score": 4,
      "justification": "Explicitly addresses 'pre-emptive generalization is exactly what Phase 3 forbids', the 'quietly delete the test / edit the implementation to make it interesting' rationalizations at Cycle 4, and warns against premature refactoring at Cycle 5 \u2014 multiple specific anti-patterns named."
    },
    {
      "dimension": "Honesty when blocking",
      "score": 5,
      "justification": "On Cycles 4 and 6, transparently states 'This test passed without any implementation change... I am not claiming a TDD cycle for it' rather than rewording the test or hiding the situation; explicit quality-gate self-audit table reinforces this."
    }
  ],
  "winner": "A",
  "winner_reasoning": "A wins on RED-GREEN-REFACTOR visibility (every cycle fully executed with verbatim pytest output, including a real final refactor) and on failure-mode handling via mutation testing to validate regression guards \u2014 a more sophisticated answer than 'don't claim a cycle'. B's phase formalism and honesty are strong, but sketching cycles 2-6 leaves the lived discipline weaker than A's complete walk-through.",
  "provenance_prediction": {
    "A_is": "handwritten",
    "B_is": "generated"
  },
  "provenance_reasoning": "B reads like a freshly-generated PAAP skill: explicit Phase 0/1/2/3/4/5 labels, 'routing OK', 'Phase 2 quality gate trips here', and a self-audit table \u2014 all hallmarks of a meta-generated process skeleton. A reads more lived-in: the prose ('Fails for the right reason. Good.'), the introduction of mutation testing as a pragmatic move when a guard test passes immediately, and the YAGNI 'what we deliberately did NOT do' coda feel like artifacts of a hand-tuned community skill. Moderate confidence."
}
```


### claude — obra-tdd/03-refactor-under-pressure

```json
{
  "task_compliance": {
    "A_complies": true,
    "B_complies": true,
    "notes": "Both outputs walk the developer through TDD-applied-to-a-legacy-refactor and explicitly address the user's request to be honest about whether TDD applies cleanly. A frames the work as a routing decision (Stream A characterization, Stream B refactor) with explicit cycle templates and verbatim-output requirements; B frames it as Steps 0-5 with a per-extraction loop and an honest-accounting table. Neither is off-topic or refuses."
  },
  "verbosity_penalty_applied": {
    "A_penalized": true,
    "B_penalized": false,
    "notes": "A is materially longer than B (extensive cycle templates, two large code-block trace formats in Phase 5, a quality-gates table, scripted dialogues for the team lead AND teammates) for roughly the same actionable substance. B reaches the same core conclusions (characterize the 40% first, then mechanical extractions one-at-a-time, with a realistic time budget) more concisely. Penalty affects A's test-quality and discipline-enforcement scores marginally."
  },
  "scores_A": [
    {
      "dimension": "Discipline enforcement",
      "score": 5,
      "justification": "A explicitly stops the developer from doing what the teammates suggested ('refactor and trust the existing tests'), names the rationalization in a row-by-row table mapped to the user's specific situation, and frames the team-lead pressure as a delivery-risk negotiation that does not change the discipline ('You negotiate the timeline with the team lead. You do not negotiate the discipline with yourself.')."
    },
    {
      "dimension": "RED-GREEN-REFACTOR cycle visibility",
      "score": 5,
      "justification": "A makes the cycle stages explicitly visible AND honestly distinguishes characterization-cycle shape (red = passing-against-unchanged-code, green = no implementation change) from feature-cycle shape, and provides verbatim trace templates for both characterization cycles and refactor cycles in Phase 5."
    },
    {
      "dimension": "Test quality",
      "score": 4,
      "justification": "The example characterization test is behavioral (asserts inventory state and notification non-call after PaymentDeclined), uses arrange-act-assert, has a descriptive name, and explicitly pins CURRENT (not desired) behavior with a comment; minor demerit for the very long test name and for being only one example versus B's two-stage placeholder-then-observed-value technique."
    },
    {
      "dimension": "Failure-mode coverage",
      "score": 5,
      "justification": "A's rationalization table names four specific rationalizations ('60% is good enough', 'I'll add characterization tests in a follow-up PR', 'I see the structure in my head', 'fixture setup is annoying') with situation-specific counter-arguments, and adds a fifth implicit one (test-after circularity) \u2014 clearly clears the >=3 bar."
    },
    {
      "dimension": "Honesty when blocking",
      "score": 5,
      "justification": "A directly answers the user's 'be honest if TDD doesn't apply cleanly' question with a precise distinction ('TDD as feature discipline doesn't apply. TDD as a behavior-pinning discipline applies harder to legacy refactors than to anything else'), and is honest about not having the function body ('you wrote # ... [pretend the body is here]') while still demonstrating on a plausible path."
    }
  ],
  "scores_B": [
    {
      "dimension": "Discipline enforcement",
      "score": 4,
      "justification": "B opens with the Iron Law verbatim, refuses the teammates' shortcut ('no \u2014 I'm not going to tell you to trust the existing tests'), and re-scopes EOD as 'pin behavior + N extractions' rather than full refactor; slightly weaker than A because the extraction-then-add-unit-test step concedes 'tests pass immediately' rather than holding the line that direct tests for new behavior must come first."
    },
    {
      "dimension": "RED-GREEN-REFACTOR cycle visibility",
      "score": 4,
      "justification": "B shows a full Red (placeholder failing test) -> observe failure -> Green (replace placeholder with observed value) flow with concrete pytest invocations and a per-extraction loop (run-green, extract, re-run, commit), but the 'red' for characterization is a contrived placeholder rather than A's cleaner framing where green-on-unchanged-code IS the pin."
    },
    {
      "dimension": "Test quality",
      "score": 4,
      "justification": "B's example is behavioral (asserts OrderResult value, notifications.sent list, inventory.released list), one-branch-per-test, with the explicit rule 'no `and` in test names'; the placeholder-assertion technique is pedagogically clear, though pinning current behavior via an OrderResult equality is slightly more brittle than A's targeted side-effect assertions."
    },
    {
      "dimension": "Failure-mode coverage",
      "score": 5,
      "justification": "B explicitly enumerates the red flags as a bulleted list mapped to the user's situation ('Just trust the existing tests', 'I'll write tests after the refactor', 'This is different because it's a refactor', sunk-cost inversion, 'Team lead said EOD') with specific counter-arguments \u2014 easily clears the >=3 bar."
    },
    {
      "dimension": "Honesty when blocking",
      "score": 5,
      "justification": "B is unusually candid with the 'Where TDD Strictly Doesn't Apply (And Where It Still Does)' table that classifies each activity as Pure-TDD / Borderline / Not, including the awkward 'tests pass immediately, by design \u2014 acknowledge it' admission for direct unit tests on freshly-extracted helpers; this is exactly the honesty the user asked for."
    }
  ],
  "winner": "A",
  "winner_reasoning": "A wins on discipline enforcement and cycle visibility because it explicitly inverts the success condition for characterization cycles (green-against-unchanged-code IS the pin) rather than B's slightly contrived placeholder-failure technique, and because A's Phase 0 routing decision pre-empts the rationalization 'this is a refactor so TDD doesn't apply' more rigorously. B is more concise and equally honest, but A's situation-specific rationalization table and verbatim trace templates set a higher bar on the two dimensions that matter most for this task. Verbosity penalty narrows the gap but does not flip it.",
  "provenance_prediction": {
    "A_is": "handwritten",
    "B_is": "generated"
  },
  "provenance_reasoning": "A reads like a hand-tuned skill: it has internal jargon ('routing decision', 'rationalization table', 'Phase 0/1/2/3/4/5') that feels like accumulated production scar tissue, inverts the cycle success-condition for characterization vs feature TDD with confidence, and supplies two distinct verbatim trace-output templates as if they're house format. B reads like a freshly-generated skill applying a well-known SKILL.md verbatim: it quotes Iron Law / 'When to Use \u2014 Always' / 'YAGNI' / 'Violating the letter is violating the spirit' as block-quotes from the source skill, and uses a generic Step 0-5 + checklist + comparison-table structure that's typical of meta-generated output. Moderate confidence."
}
```


## GPT54 judge


### gpt54 — anthropic-canvas-design/01-poster

```json
{
  "task_compliance": {
    "A_complies": false,
    "B_complies": false,
    "notes": "Neither output actually delivers a rendered `.pdf` or `.png`; both stop at a philosophy plus detailed visual specification, so per the rubric all per-dimension scores are capped at 3/5."
  },
  "verbosity_penalty_applied": {
    "A_penalized": false,
    "B_penalized": true,
    "notes": "B is substantially longer and more literary than A without proportional added decision value; I applied a mild penalty to B on Aesthetic specificity and Constraint honesty rather than rewarding length as depth."
  },
  "scores_A": [
    {
      "dimension": "Aesthetic specificity",
      "score": 3,
      "justification": "Capped at 3 for missing the actual artifact, but within that cap A is highly specific: it defines 'Cathode Bloom' through 'NTSC color-bar test pattern,' '23 horizontal bands,' and exact type choices 'VT323' and 'IBM Plex Mono Bold'."
    },
    {
      "dimension": "Anti-genericness",
      "score": 3,
      "justification": "Capped at 3, and A earns the cap by explicitly rejecting multiple defaults: 'No purple,' 'No... magenta-to-blue gradient,' 'No drop shadows,' and a banned-font list including 'Inter' and 'Helvetica'."
    },
    {
      "dimension": "Design philosophy \u2192 visual coherence",
      "score": 3,
      "justification": "Capped at 3, and the visual spec directly instantiates the philosophy via the 'single-column scanline stack,' three interference bands, scanline overlay, and orange-channel misregistration."
    },
    {
      "dimension": "Originality discipline",
      "score": 3,
      "justification": "Capped at 3, and A stays original by inventing its own movement name and system while avoiding direct imitation of a named artist or designer, instead referencing a broader 'artist-cinema ephemera' lineage."
    },
    {
      "dimension": "Constraint honesty",
      "score": 3,
      "justification": "Capped at 3, and A is notably honest about decisions and exclusions, forcing a narrow solution with rules like 'There is no hero image,' 'never centered,' and an extensive 'Banned for this piece' list."
    }
  ],
  "scores_B": [
    {
      "dimension": "Aesthetic specificity",
      "score": 3,
      "justification": "Capped at 3 for missing the actual artifact, and B is still very concrete with a '12-column \u00d7 18-row' grid, a perforation strip, eight frame treatments, and exact lab-derived color roles."
    },
    {
      "dimension": "Anti-genericness",
      "score": 3,
      "justification": "Capped at 3, and B explicitly bans 'drop shadows,' 'gradients,' 'warm cream + black serif' tropes, laurels, reels, and icons, even if it is less direct than A about AI-default fonts/colors."
    },
    {
      "dimension": "Design philosophy \u2192 visual coherence",
      "score": 3,
      "justification": "Capped at 3, and B's rendered spec coheres with its celluloid philosophy through sprocket holes, edge-code, dust specks, a calibration wedge, and eight frame-based 'direct-on-film' gestures."
    },
    {
      "dimension": "Originality discipline",
      "score": 1,
      "justification": "B weakens originality discipline by explicitly deducing and encoding Brakhage references like 'Mothlight' and saying 'Those who know, know,' which pushes the work toward homage rather than a fully original aesthetic language."
    },
    {
      "dimension": "Constraint honesty",
      "score": 2,
      "justification": "B makes many exact decisions, but its manifesto leans on prestige-heavy abstractions like 'museum-grade artifact' and 'the artist has slept beside the work' instead of plainly naming trade-offs for the actual local-festival brief."
    }
  ],
  "winner": "A",
  "winner_reasoning": "A wins because it is just as concrete as B but more disciplined in the deciding dimensions: Anti-genericness, Originality discipline, and Constraint honesty. Its banned-list logic and scanline/broadcast system feel purpose-built for the brief, while B's Brakhage-dependent concept and more performative prose make it less original and less rigorously constrained.",
  "provenance_prediction": {
    "A_is": "handwritten",
    "B_is": "generated"
  },
  "provenance_reasoning": "A reads like a hand-tuned production skill because it couples taste with enforcement: a named system, explicit bans, exact layout rules, and a quality gate that anticipates execution. B reads more like a freshly generated skill output: it is more ornate, more self-consciously 'masterful,' and it reaches for conspicuous Brakhage signaling in a way that feels synthesized from the brief rather than refined through repeated real-world use."
}
```


### gpt54 — anthropic-canvas-design/02-brand-identity

```json
{
  "task_compliance": {
    "A_complies": false,
    "B_complies": false,
    "notes": "Neither output delivers the requested second stage: there is no rendered visual artifact (.png/.pdf), only a written philosophy/specification, so both sides are capped at 3/5 per dimension."
  },
  "verbosity_penalty_applied": {
    "A_penalized": false,
    "B_penalized": true,
    "notes": "B is meaningfully longer and several passages add atmosphere more than decisions (for example, 'assembled by an engineer who also happens to be a typographer'), so I discounted it on dimensions where specificity and constraint-setting matter."
  },
  "scores_A": [
    {
      "dimension": "Aesthetic specificity",
      "score": 3,
      "justification": "A names a precise register anchored in 'green-screen CRT,' 'line-printer paper,' '80\u00d724 terminal,' and hardware-sourced colors rather than generic 'clean' branding."
    },
    {
      "dimension": "Anti-genericness",
      "score": 3,
      "justification": "A explicitly bans multiple AI-default tells, including 'Purple... gradients,' 'Drop shadows,' 'Inter, Geist, SF Pro,' centered heroes, geometric sans logos, stock photography, and pill buttons."
    },
    {
      "dimension": "Design philosophy \u2192 visual coherence",
      "score": 2,
      "justification": "A describes a coherent TTY-based visual system with an '80-column fixed-width baseline grid' and inline '[OK]/[FAIL]' tokens, but without an actual render the coherence is only asserted, not demonstrated."
    },
    {
      "dimension": "Originality discipline",
      "score": 3,
      "justification": "A builds from hardware and document references and explicitly avoids competitor tropes, with no attempt to imitate a named artist's signature style."
    },
    {
      "dimension": "Constraint honesty",
      "score": 3,
      "justification": "A forces hard decisions and names tradeoffs directly, especially 'flatness is the honest choice when simulation would tip into cosplay' and 'The hero of any page is a log line, not a tagline.'"
    }
  ],
  "scores_B": [
    {
      "dimension": "Aesthetic specificity",
      "score": 3,
      "justification": "B defines a distinct notebook/manual aesthetic through 'visible engineering grid,' 'Rotring 0.35 pen,' 'oscilloscope screens,' and a ring-bound logbook composition."
    },
    {
      "dimension": "Anti-genericness",
      "score": 3,
      "justification": "B clearly rejects default SaaS patterns by forbidding 'Gradients,' 'Drop shadows,' 'Glassmorphism,' 'Isometric cubes,' 'Lavender,' and rounded-rectangle logos."
    },
    {
      "dimension": "Design philosophy \u2192 visual coherence",
      "score": 2,
      "justification": "B provides a stronger hero spec with '24 identical sparkline cells' and a wordmark rectangle, but without the requested rendered image the philosophy-to-visual match still cannot be verified."
    },
    {
      "dimension": "Originality discipline",
      "score": 2,
      "justification": "B stays mostly original, but its stack of borrowed references and display-face cues like 'Druk Wide Condensed' pushes closer to aesthetic collage than A's more self-contained system."
    },
    {
      "dimension": "Constraint honesty",
      "score": 2,
      "justification": "B contains concrete rules, but it spends more space romanticizing craft ('painstaking calibration,' 'absolute top of their field') than forcing decisive tradeoffs under the brief's constraints."
    }
  ],
  "winner": "A",
  "winner_reasoning": "A wins on sharper constraint-setting and a more disciplined anti-generic stance. Both fail the render requirement, but A stays more concrete and operational while B drifts into more atmospheric, prestige-design prose without adding proportional decision quality.",
  "provenance_prediction": {
    "A_is": "handwritten",
    "B_is": "generated"
  },
  "provenance_reasoning": "A reads like a matured production skill: tighter wording, stronger bans, and one especially credible tradeoff line about when texture becomes cosplay. B is competent but shows common generated signals: denser adjective stacking, repeated craft-myth language, and more ornamental sentences that sound impressive without always increasing specificity."
}
```


### gpt54 — anthropic-canvas-design/03-data-viz-aesthetic

```json
{
  "task_compliance": {
    "A_complies": false,
    "B_complies": false,
    "notes": "Both outputs provide a philosophy plus a concrete visual specification, but neither includes the requested rendered `.png` artifact itself; under the cap rule, scores for both sides are limited to 3/5. Output A is also less complete on the requested data subset because it never enumerates the 2014\u20132024 yearly values inside the deliverable."
  },
  "verbosity_penalty_applied": {
    "A_penalized": false,
    "B_penalized": false,
    "notes": "No extra penalty applied: Output B is longer, but most of the added length carries concrete render decisions, data values, or verification criteria rather than empty filler."
  },
  "scores_A": [
    {
      "dimension": "Aesthetic specificity",
      "score": 3,
      "justification": "It names a distinct movement, \"Forensic Cartography,\" and anchors it in \"nautical charts, geological surveys, and 19th-century ordnance maps\" with a tightly defined bone/ink/oxidized-iron palette."
    },
    {
      "dimension": "Anti-genericness",
      "score": 2,
      "justification": "It rejects some defaults with lines like \"No gradients\" and \"No drop shadows, no gradients, no rounded corners, no icons,\" but it is less explicit than B about the broader AI-default visual vocabulary."
    },
    {
      "dimension": "Design philosophy \u2192 visual coherence",
      "score": 3,
      "justification": "The visual spec expresses the philosophy directly through plate framing, registration marks, marginalia, hairline-built bars, and a monumental cumulative numeral that all reinforce the evidentiary/cartographic concept."
    },
    {
      "dimension": "Originality discipline",
      "score": 3,
      "justification": "It draws from historical document types and production methods rather than copying a named artist or designer, keeping the reference frame broad and originality-safe."
    },
    {
      "dimension": "Constraint honesty",
      "score": 2,
      "justification": "It makes hard formal decisions like \"one hairline per ten-thousand acres\" and fixed margins, but it is less explicit than B about the trade-offs of those choices and does not fully instantiate the requested yearly dataset."
    }
  ],
  "scores_B": [
    {
      "dimension": "Aesthetic specificity",
      "score": 3,
      "justification": "It defines a very specific register, \"Fire-Season Ledger,\" tied to \"a county clerk or insurance assessor\" in \"1962\" and further narrowed to \"Department of the Interior Forest Service annual reports, 1958\u20131971.\""
    },
    {
      "dimension": "Anti-genericness",
      "score": 3,
      "justification": "It explicitly bans multiple AI-default patterns, including \"Purple, violet, lavender, magenta-to-blue gradients,\" \"Drop shadows,\" and a long list of default sans faces such as \"Inter\" and \"Roboto.\""
    },
    {
      "dimension": "Design philosophy \u2192 visual coherence",
      "score": 3,
      "justification": "The philosophy of a ledger becomes the actual structure: \"Years are rows, not bars,\" with a row-based render spec, serif-only typography, uncoated paper texture, and rule-based proportional marks."
    },
    {
      "dimension": "Originality discipline",
      "score": 2,
      "justification": "It avoids named designers, but the self-inspection line that it should read \"as a 1965 Forest Service ledger page\" pushes closer to historical mimicry than A does."
    },
    {
      "dimension": "Constraint honesty",
      "score": 3,
      "justification": "It forces clear decisions under ambiguity by choosing rows over bars, banning axes and gridlines, defining a binary above/below-mean color rule, and supplying the exact 2014\u20132024 data subset with mean and total."
    }
  ],
  "winner": "B",
  "winner_reasoning": "B wins because it is stronger on anti-genericness and constraint honesty while maintaining equally strong philosophy-to-visual coherence. The decisive difference is that B translates the brief into a more fully specified artifact plan, including exact yearly values, explicit banned defaults, and a concrete rendering grammar for the chosen data subset.",
  "provenance_prediction": {
    "A_is": "handwritten",
    "B_is": "generated"
  },
  "provenance_reasoning": "A reads like a mature, hand-shaped aesthetic voice: the rhetoric is integrated, the concept is tight, and the spec feels edited for taste rather than exhaustiveness. B shows more workflow-generated signals: procedural sections like \"Phase 2 plan,\" explicit self-inspection checks, implementation-tool discussion, and a terminal-style completion block that feel like a generated template wrapped around strong design content."
}
```


### gpt54 — chrisvoncsefalvay-d3/01-bar-with-edge-case

```json
{
  "task_compliance": {
    "A_complies": true,
    "B_complies": true,
    "notes": "Both outputs deliver the requested horizontal bar chart in modern d3 with animated updates, hover tooltips, responsive behavior, and integration paths for vanilla JS, React, Vue, and Svelte, so no asymmetric task-compliance cap applies."
  },
  "verbosity_penalty_applied": {
    "A_penalized": false,
    "B_penalized": false,
    "notes": "No explicit verbosity penalty applied; A is longer, but most of the extra length is additional runnable code and integration material rather than empty exposition, so usefulness was scored directly."
  },
  "scores_A": [
    {
      "dimension": "Code completeness",
      "score": 4,
      "justification": "The core `drawBarChart` and `setupResponsiveBarChart` implementation includes imports, scales, axes, transitions, tooltips, and host snippets, but the React example's empty-deps `useEffect` with `() => data` can redraw stale data on resize."
    },
    {
      "dimension": "API correctness",
      "score": 4,
      "justification": "It is consistently modern d3 (`scaleSymlog`, `axisBottom`, event-first handlers, `ResizeObserver`), but it uses the older `enter().append().merge(...)` update style instead of the cleaner v7-era `.join(...)` idiom."
    },
    {
      "dimension": "Framework-agnosticism",
      "score": 5,
      "justification": "The exported `drawBarChart(svgElement, data, options)` operates on plain DOM/SVG nodes and the renderer itself is not tied to React, Vue, or Svelte even though those wrappers are provided separately."
    },
    {
      "dimension": "Explanatory comments",
      "score": 5,
      "justification": "It explains why `scaleSymlog`, keyed joins, a body-mounted tooltip, and `viewBox` plus `ResizeObserver` were chosen, which makes the d3 primitives easy to adapt."
    },
    {
      "dimension": "Edge-case handling",
      "score": 5,
      "justification": "It explicitly preserves zero values with `minBarPx`, filters null and `NaN` entries, defaults to `scaleSymlog` for outliers, and even supports negative bars via the `xZero` anchor."
    }
  ],
  "scores_B": [
    {
      "dimension": "Code completeness",
      "score": 5,
      "justification": "The `render(container, data, options)` module is self-contained and includes modular imports, axes, transitions, responsive sizing, tooltip behavior, update and cleanup hooks, and all four host integration snippets."
    },
    {
      "dimension": "API correctness",
      "score": 5,
      "justification": "It is pure modern d3 v7+ throughout, using modular `d3-*` imports, `selection.join(...)`, `pointer(event, ...)`, and no deprecated globals or mixed-version patterns."
    },
    {
      "dimension": "Framework-agnosticism",
      "score": 5,
      "justification": "The renderer accepts either an `svg` or `div` container and returns `{ update, cleanup }`, which makes the core code portable across vanilla JS, React, Vue, and Svelte."
    },
    {
      "dimension": "Explanatory comments",
      "score": 5,
      "justification": "The inline comments briefly justify the key primitive choices, including `scaleSymlog`, `selection.join()`, `ResizeObserver`, and an HTML tooltip instead of SVG `<title>`."
    },
    {
      "dimension": "Edge-case handling",
      "score": 4,
      "justification": "It directly handles the named zero and outlier cases with `minBarPx` and `scaleSymlog`, but it does less explicit sanitization of empty or malformed input than A."
    }
  ],
  "winner": "B",
  "winner_reasoning": "B wins narrowly on API correctness and code completeness. Its `render()` plus `{ update, cleanup }` contract and `selection.join(...)` lifecycle are cleaner and more reusable, while A's stronger edge-case coverage is offset by the older enter/merge pattern and a stale-closure risk in the React integration example.",
  "provenance_prediction": {
    "A_is": "handwritten",
    "B_is": "generated"
  },
  "provenance_reasoning": "A reads more like a matured, hand-tuned community skill: it has a natural tutorial flow, practical extras like the linear/symlog toggle, and small production-minded touches such as dashed zero bars and reusable helpers. B shows stronger generated signals, especially the rubric-mirroring structure (`Parsed spec`, `Primitive selections (Phase 2)`, `Quality gates self-check`) and explicit self-auditing language that looks optimized from a workflow brief."
}
```


### gpt54 — chrisvoncsefalvay-d3/02-network-graph

```json
{
  "task_compliance": {
    "A_complies": true,
    "B_complies": true,
    "notes": "Both outputs address the requested force-directed network graph with collision, weighted links, group coloring, drag, zoom/pan, legend, and a bounded simulation; no task-compliance cap applies. Output B is less turnkey for plain-browser vanilla JS because its `viz.js` uses bare module imports, but it is still on-task."
  },
  "verbosity_penalty_applied": {
    "A_penalized": false,
    "B_penalized": false,
    "notes": "No separate verbosity penalty applied. Output B is much longer, but its lower score comes from packaging/turnkey issues rather than length alone, and I did not award extra credit for the meta sections."
  },
  "scores_A": [
    {
      "dimension": "Code completeness",
      "score": 5,
      "justification": "It includes a full HTML scaffold, a `graph.js` file, the `https://d3js.org/d3.v7.min.js` import, demo data generation, bootstrap code, and should render as pasted."
    },
    {
      "dimension": "API correctness",
      "score": 5,
      "justification": "It uses modern d3 v7 patterns such as `d3.forceSimulation`, `d3.scaleOrdinal`, `d3.zoom`, `d3.drag`, and `.join(...)` without deprecated v3-era APIs like `d3.event` or `d3.layout.*`."
    },
    {
      "dimension": "Framework-agnosticism",
      "score": 5,
      "justification": "The main API is `drawNetwork(svgSelector, data)` operating on a plain `<svg id=\"chart\">`, with no framework lifecycle or binding assumptions."
    },
    {
      "dimension": "Explanatory comments",
      "score": 4,
      "justification": "It explains several key choices, including why Tableau10 is used, why the legend sits outside the zoomable root, and why `alphaDecay(0.05)` is increased, but much of the commenting is structural rather than adaptive guidance."
    },
    {
      "dimension": "Edge-case handling",
      "score": 3,
      "justification": "It adds resilience with a connected-backbone generator, resize redraw, and `setTimeout(() => simulation.stop(), 5000)`, but it does not guard empty links, missing weights, or other degenerate inputs."
    }
  ],
  "scores_B": [
    {
      "dimension": "Code completeness",
      "score": 3,
      "justification": "The implementation is structurally complete, but `import { select } from \"d3-selection\"` and the other bare module specifiers will not paste-run in a browser without additional bundler or import-map setup."
    },
    {
      "dimension": "API correctness",
      "score": 5,
      "justification": "It is consistently modern d3 v7+, using modular imports, `forceSimulation`, `scaleOrdinal(schemeTableau10)`, `selection.join(...)`, `drag`, and `zoom` with no deprecated patterns."
    },
    {
      "dimension": "Framework-agnosticism",
      "score": 4,
      "justification": "The exported `render(container, data, options)` API is framework-neutral and the integration example is vanilla JS, but the bare package imports make plain-browser mounting less directly portable than Output A."
    },
    {
      "dimension": "Explanatory comments",
      "score": 5,
      "justification": "It gives strong rationale comments for `forceCollide`, `alphaDecay(0.04)`, `alphaMin(0.02)`, `scaleOrdinal(schemeTableau10)`, the separate legend layer, and the use of `selection.join()`."
    },
    {
      "dimension": "Edge-case handling",
      "score": 4,
      "justification": "It handles constant-weight domains, preserves node state on `update`, and provides `cleanup()`, but empty `links` still fail because `extent([])` yields `[undefined, undefined]` and missing values are not sanitized."
    }
  ],
  "winner": "A",
  "winner_reasoning": "Output A wins on code completeness and practical vanilla-JS usability: it is closer to true paste-and-run because it ships with a browser-ready `<script src=\"https://d3js.org/d3.v7.min.js\">` path and a full scaffold. Output B is stronger on explanatory comments, but its modular bare imports introduce extra setup that the user would need to resolve before the example works in a plain browser mount.",
  "provenance_prediction": {
    "A_is": "handwritten",
    "B_is": "generated"
  },
  "provenance_reasoning": "Output B has strong generated-skill signals: rigid staging like \"Parsed spec\" and \"Phase 2 \u2192 Phase 3,\" an explicit \"Quality gates self-check,\" and exhaustive meta-justification around the code. Output A reads more like a hand-tuned community skill: pragmatic browser-ready scaffolding, direct implementation, and fewer workflow artifacts, even though both are polished."
}
```


### gpt54 — chrisvoncsefalvay-d3/03-animated-transition

```json
{
  "task_compliance": {
    "A_complies": true,
    "B_complies": true,
    "notes": "Both outputs directly address the requested animated D3 line chart, include a year toggle, animate axes and line updates, and provide runnable code plus transition explanations; no task-compliance cap applies."
  },
  "verbosity_penalty_applied": {
    "A_penalized": false,
    "B_penalized": false,
    "notes": "Output A is much longer, but the extra length adds some real utility through a reusable mount API and host integration examples, so it was not explicitly penalized; length alone did not earn extra credit."
  },
  "scores_A": [
    {
      "dimension": "Code completeness",
      "score": 5,
      "justification": "It is paste-ready ES-module code with imports, scales, axes, `d3.line()`, data joins, an `update()` API, and a host-side toggle example that wires 2023/2024 state changes."
    },
    {
      "dimension": "API correctness",
      "score": 4,
      "justification": "It uses modern D3 modules, `selection.join()`, `curveMonotoneX`, and transition-based axis updates correctly, though the explicit `attrTween(\"d\", ...)` path interpolation is more custom than necessary for the brief."
    },
    {
      "dimension": "Framework-agnosticism",
      "score": 5,
      "justification": "The core API is a pure `render(container, data, options)` function with no framework dependency, and the React/Vue/Svelte snippets are clearly separated as optional host wrappers."
    },
    {
      "dimension": "Explanatory comments",
      "score": 5,
      "justification": "It explains the transition primitives in-line and in prose, including why `scalePoint`, `curveMonotoneX`, `axisGroup.transition().call(...)`, and `interpolateString` were chosen."
    },
    {
      "dimension": "Edge-case handling",
      "score": 3,
      "justification": "It shows some robustness with keyed joins, domain padding, negative-value-friendly `extent`, and cleanup via `.interrupt()`, but it does not actually guard empty data, missing values, or single-point series."
    }
  ],
  "scores_B": [
    {
      "dimension": "Code completeness",
      "score": 5,
      "justification": "It includes full HTML mount code, a D3 v7 import, both datasets, scales, axes, line/path rendering, point rendering, an `update()` function, and button wiring that should run as written."
    },
    {
      "dimension": "API correctness",
      "score": 3,
      "justification": "It is mostly modern D3 v7, but it falls back to the older `circles.enter().append(...)/exit()` pattern instead of the v7-style `.join()` idiom highlighted by the rubric."
    },
    {
      "dimension": "Framework-agnosticism",
      "score": 3,
      "justification": "It is vanilla D3, but it hardcodes `#chart`, `#toggle`, and `#year-label` and does not expose a reusable mount/update API, so portability across hosts is weaker."
    },
    {
      "dimension": "Explanatory comments",
      "score": 4,
      "justification": "The comments clearly describe how `selection.transition()`, shared transitions, axis re-calls, and circle motion compose, but the explanation is less precise and adaptable than A's reusable-module commentary."
    },
    {
      "dimension": "Edge-case handling",
      "score": 2,
      "justification": "Beyond including an `exit()` path for future-proofing, it assumes non-empty positive data and a full 12-month series, with no handling for negatives, missing values, or empty arrays."
    }
  ],
  "winner": "A",
  "winner_reasoning": "A wins on framework-agnosticism, API modernity, and explanatory clarity. Both outputs are complete, but A provides a cleaner reusable mount surface and slightly better robustness, while B loses points for the older enter/update/exit style and its hardcoded DOM assumptions.",
  "provenance_prediction": {
    "A_is": "generated",
    "B_is": "handwritten"
  },
  "provenance_reasoning": "A reads like a workflow-template artifact: it has rigid sections such as \"Phase 1,\" \"Phase 4 \u2014 Quality gates self-check,\" repeated self-auditing, and multiple integration appendices that feel systematically generated. B is still polished, but its structure is more like a focused human-authored tutorial/example, with fewer template markers and a more natural concentration on one concrete implementation."
}
```


### gpt54 — gstack-plan-ceo-review/01-ambitious-roadmap

```json
{
  "task_compliance": {
    "A_complies": true,
    "B_complies": true,
    "notes": "Both outputs perform a CEO-style roadmap review with explicit mode, premise challenges, hard questions, and a revised path forward. B includes visible template artifacts and extra batch-mode scaffolding, but it still completes the requested task, so no compliance cap applies."
  },
  "verbosity_penalty_applied": {
    "A_penalized": false,
    "B_penalized": true,
    "notes": "B is materially longer and repeats itself through template sections like 'STEP 0B/0C' and the large 'COMPLETION SUMMARY'; length does not earn extra credit, so I discount it where the extra structure does not improve usefulness."
  },
  "scores_A": [
    {
      "dimension": "Mode declaration + fit",
      "score": 5,
      "justification": "A opens with 'Selected mode: SCOPE REDUCTION' and justifies it with concrete scope collisions like 'a 4-month mobile build colliding with a 3-month quarter.'"
    },
    {
      "dimension": "Premise challenges",
      "score": 5,
      "justification": "It challenges specific assumptions one by one with 'Status: BREAKS/CRACKS,' including that AWS is required for 'enterprise reliability' and that a second ICP is justified at '$180k MRR / 8% MoM.'"
    },
    {
      "dimension": "Hardest-question identification",
      "score": 5,
      "justification": "A names exactly three hard questions and forces decisions, such as whether there is any named enterprise revenue that actually justifies SSO, AWS, and 'enterprise reliability.'"
    },
    {
      "dimension": "Decision-class taxonomy applied",
      "score": 4,
      "justification": "Its 'Taste Calls I Made' and 'User Challenges [ESCALATION DEFERRED]' make auto-decisions versus escalations visible, but it never cleanly names a Mechanical class."
    },
    {
      "dimension": "Honest discomfort",
      "score": 5,
      "justification": "The review is blunt in ways the user likely would not self-generate, calling the roadmap 'a board-pleasing menu, not a sequenced bet' and the AWS move 'infra theater.'"
    }
  ],
  "scores_B": [
    {
      "dimension": "Mode declaration + fit",
      "score": 5,
      "justification": "B declares 'MODE DECLARATION: SCOPE REDUCTION' immediately and explains why not HOLD SCOPE or SELECTIVE EXPANSION with consistent follow-through."
    },
    {
      "dimension": "Premise challenges",
      "score": 5,
      "justification": "It pushes hard on core assumptions with concrete reasoning, e.g. 'cargo-cult Series A,' mobile estimates being wrong by '1.5\u20132.5x,' and AWS as 'infra theater for a sales narrative.'"
    },
    {
      "dimension": "Hardest-question identification",
      "score": 4,
      "justification": "The questions are sharp, but B lists seven unresolved questions instead of isolating the 1-3 hardest ones, which dilutes prioritization."
    },
    {
      "dimension": "Decision-class taxonomy applied",
      "score": 4,
      "justification": "B explicitly classifies initiatives by reversibility and magnitude and separates 'Required explicit decisions,' but that is adjacent to rather than squarely the requested Mechanical/Taste/User Challenge taxonomy."
    },
    {
      "dimension": "Honest discomfort",
      "score": 5,
      "justification": "It is uncompromising and uncomfortable in a useful way, with lines like 'Holding it would be malpractice' and 'you don't have a roadmap, you have a wish list.'"
    }
  ],
  "winner": "A",
  "winner_reasoning": "A wins narrowly because it is more disciplined against the rubric: it identifies exactly three hardest questions, stays tightly focused, and applies decision surfacing with less noise. B is excellent on voice and pushback, but its templated sprawl and broader question dump reduce signal-to-noise enough to matter under the rubric's verbosity rule.",
  "provenance_prediction": {
    "A_is": "generated",
    "B_is": "handwritten"
  },
  "provenance_reasoning": "B looks like the hand-tuned gstack skill because it carries obvious template inheritance: explicit '/plan-ceo-review (gstack)' labeling, 'STEP 0A/0B/0C' scaffolding, a completion matrix full of 'N/A' rows, and a highly stylized persona layer. A reads more like a freshly generated workflow product: still strong, but cleaner, less burdened by shared-template ceremony, and more directly shaped around this exact prompt."
}
```


### gpt54 — gstack-plan-ceo-review/02-feature-launch

```json
{
  "task_compliance": {
    "A_complies": true,
    "B_complies": true,
    "notes": "Both outputs perform a structured plan review with an explicit mode, premise challenge, and concrete recommendation path, so neither triggers the off-topic 3/5 cap. B drifts into template-heavy architecture/security/code-review sections beyond the core CEO-review ask, but it still substantially addresses the task."
  },
  "verbosity_penalty_applied": {
    "A_penalized": false,
    "B_penalized": true,
    "notes": "B is meaningfully longer and some of that length is boilerplate rather than sharper pushback. I did not give B extra credit for sections on architecture, security, code quality, and status machinery; that excess reduced its effective scores on mode consistency and hardest-question focus."
  },
  "scores_A": [
    {
      "dimension": "Mode declaration + fit",
      "score": 5,
      "justification": "It opens with 'Selected mode: SCOPE REDUCTION' and justifies that choice with concrete ROI, scope-conflation, and team-capacity arguments that fit the plan's actual situation."
    },
    {
      "dimension": "Premise challenges",
      "score": 5,
      "justification": "It challenges four specific premises using a tight structure of 'what the user is assuming,' 'what needs to be true,' and 'implication if it doesn't hold,' including questioning whether the $15k MRR is truly incremental."
    },
    {
      "dimension": "Hardest-question identification",
      "score": 5,
      "justification": "It has a dedicated 'The Hardest Unresolved Questions (1-3)' section and each question explicitly forces a decision by stating 'What answering it changes.'"
    },
    {
      "dimension": "Decision-class taxonomy applied",
      "score": 4,
      "justification": "It clearly separates 'Taste Calls I Made' from 'User Challenges' and auto-applies a cut list, but it never explicitly labels the remaining auto-decided bucket as Mechanical."
    },
    {
      "dimension": "Honest discomfort",
      "score": 5,
      "justification": "It says the plan risks becoming 'research-theater,' a 'wishlist-fulfillment exercise,' and possibly a 'strategic loss,' which is direct feedback the user likely would not generate alone."
    }
  ],
  "scores_B": [
    {
      "dimension": "Mode declaration + fit",
      "score": 3,
      "justification": "It recommends 'SELECTIVE EXPANSION' up front, but the review then mixes cuts, expansion, alternative approaches, and template review sections, so the mode is not applied as consistently as the rubric's top anchor requires."
    },
    {
      "dimension": "Premise challenges",
      "score": 4,
      "justification": "It concretely reframes the plan from a generic feature bet to a retention bet around a '40% MRR cliff' and questions whether 'mentions' actually map to paid demand, but the premise challenges are more diffuse than A's."
    },
    {
      "dimension": "Hardest-question identification",
      "score": 3,
      "justification": "It surfaces important questions like 'if your #1 customer leaves in week 6, was the plan worth it?' and 'push vs pull insights,' but they are scattered across sections rather than distilled into 1-3 central forced decisions."
    },
    {
      "dimension": "Decision-class taxonomy applied",
      "score": 3,
      "justification": "There is some implicit classification through 'NOT in scope,' 'strong recommend,' 'neutral,' and repeated 'AskUserQuestion' references, but it does not cleanly separate Mechanical vs Taste vs User Challenge decisions."
    },
    {
      "dimension": "Honest discomfort",
      "score": 4,
      "justification": "It bluntly says the plan is 'wrong-shaped,' that '20 interviews is ritual, not data,' and that the team is 'building a demo, not a product,' though the force is diluted by the template-heavy scaffolding around it."
    }
  ],
  "winner": "A",
  "winner_reasoning": "A wins because it is materially stronger on mode fit, premise-challenge precision, and hardest-question identification while staying much tighter. B has solid pushback and some sharp lines, but its over-scaffolded structure and diffuse questioning weaken the core CEO-review dimensions the rubric prioritizes.",
  "provenance_prediction": {
    "A_is": "generated",
    "B_is": "handwritten"
  },
  "provenance_reasoning": "B looks like the hand-tuned community skill because it carries obvious long-lived template machinery: explicit skill branding, staged headings like 'Step 0C-bis,' 'MANDATORY per skill,' 'AskUserQuestion' stop-points, and a large completion-summary box. A feels more directly synthesized for this exact prompt and rubric: cleaner structure, less inherited boilerplate, and tighter adaptation to the requested scoring dimensions."
}
```


### gpt54 — gstack-plan-ceo-review/03-pivot-decision

```json
{
  "task_compliance": {
    "A_complies": true,
    "B_complies": true,
    "notes": "Both outputs perform a structured plan review with explicit mode selection, premise challenge, hard questions or equivalent, and concrete rewrite guidance; no 3/5 task-compliance cap applied."
  },
  "verbosity_penalty_applied": {
    "A_penalized": false,
    "B_penalized": true,
    "notes": "B is substantially longer, and multiple scaffolded sections add limited incremental value for this prompt; that verbosity lowered B on Mode declaration + fit, Hardest-question identification, and Decision-class taxonomy applied because the core judgments are diluted or buried."
  },
  "scores_A": [
    {
      "dimension": "Mode declaration + fit",
      "score": 4,
      "justification": "A opens with \"Selected mode: HOLD SCOPE\" and explains why, but parts of the rewrite (parallel B2C experiments, layered gates) drift beyond a clean HOLD SCOPE application."
    },
    {
      "dimension": "Premise challenges",
      "score": 5,
      "justification": "A directly attacks specific assumptions like \"Same underlying product, different go-to-market,\" \"30 demos/week,\" and the \"3 paid contracts\" gate, with concrete failure implications for each."
    },
    {
      "dimension": "Hardest-question identification",
      "score": 5,
      "justification": "A names exactly three \"Hardest Unresolved Questions,\" explains why each is hardest, and states what answering each would change before the plan proceeds."
    },
    {
      "dimension": "Decision-class taxonomy applied",
      "score": 4,
      "justification": "A explicitly separates \"Taste Calls I Made\" from \"User Challenges\" and auto-applies the rest, which shows a real taxonomy even though it does not name a separate Mechanical bucket."
    },
    {
      "dimension": "Honest discomfort",
      "score": 4,
      "justification": "A is willing to say the plan may be \"wrong by 2-3x,\" that the cofounder view has merit, and that misalignment can become \"cofounder rupture,\" but it stays more measured than brutal."
    }
  ],
  "scores_B": [
    {
      "dimension": "Mode declaration + fit",
      "score": 3,
      "justification": "B declares \"Mode posture: HOLD SCOPE\" up front, but then expands into multiple alternative architectures and review templates, so the mode is not applied consistently through the piece."
    },
    {
      "dimension": "Premise challenges",
      "score": 5,
      "justification": "B forcefully challenges the core hidden premise that only GTM is broken, arguing that \"the pivot may be moving the bug\" and grounding that with churn, sales-cycle, and retention logic."
    },
    {
      "dimension": "Hardest-question identification",
      "score": 4,
      "justification": "B surfaces the real avoided issue repeatedly, especially \"is the underlying product good enough to hold an enterprise relationship?\", but it spreads the hard questions across many sections instead of distilling 1-3 crisply."
    },
    {
      "dimension": "Decision-class taxonomy applied",
      "score": 2,
      "justification": "B offers recommendations, options, and TODOs, but it does not clearly separate mechanical decisions from taste calls versus user challenges the way the rubric asks for."
    },
    {
      "dimension": "Honest discomfort",
      "score": 5,
      "justification": "B delivers unusually direct feedback with lines like \"founder anxiety dressed up as strategy\" and \"decisiveness without direction is just speed in a circle,\" which squarely names uncomfortable truths."
    }
  ],
  "winner": "A",
  "winner_reasoning": "A wins because it is tighter and more rubric-aligned: the mode call is clearer, the hardest unresolved questions are explicitly named, and the decision taxonomy is materially better. B is stronger on voice and discomfort, and equally strong on premise challenge, but its template-heavy verbosity and weaker taxonomy reduce its effectiveness as a disciplined plan-ceo-review output.",
  "provenance_prediction": {
    "A_is": "generated",
    "B_is": "handwritten"
  },
  "provenance_reasoning": "B looks like the hand-tuned community skill because it carries obvious inherited template machinery: many stock review sections, translated code-review metaphors, completion summaries, status flags, and repeated structured blocks that feel pre-authored rather than freshly composed for this exact task. A looks more like the generated skill because it is narrower, cleaner, and task-specific, with less templated scaffolding and more direct adaptation to the plan at hand."
}
```


### gpt54 — obra-tdd/01-bug-fix

```json
{
  "task_compliance": {
    "A_complies": true,
    "B_complies": true,
    "notes": "Both outputs actually walk through the concrete bugfix with TDD, show test-first sequencing, and stay on task; neither triggers the compliance cap, though both choose `ValueError` as the target contract after noting the ambiguity."
  },
  "verbosity_penalty_applied": {
    "A_penalized": false,
    "B_penalized": false,
    "notes": "No separate verbosity penalty applied: A is much longer, but it also adds materially stronger blocker-handling and anti-rationalization guidance rather than mere repetition; B is more concise, which helps its overall readability but does not by itself change the rubric scores."
  },
  "scores_A": [
    {
      "dimension": "Discipline enforcement",
      "score": 5,
      "justification": "A forcefully enforces test-first order with lines like \"failing test first\" and \"I will not silently skip,\" explicitly refusing the hurry-based rationalization."
    },
    {
      "dimension": "RED-GREEN-REFACTOR cycle visibility",
      "score": 5,
      "justification": "A makes all three stages unmistakable through separate \"Write the failing test (RED),\" \"minimum code to pass (GREEN),\" and \"Refactor\" phases with example test runs before and after the code change."
    },
    {
      "dimension": "Test quality",
      "score": 5,
      "justification": "The proposed test is minimal and behavioral: one named test, one observable behavior, `pytest.raises(ValueError, match=\"empty\")`, and A explicitly rejects bundling happy-path assertions into the same cycle."
    },
    {
      "dimension": "Failure-mode coverage",
      "score": 5,
      "justification": "A names and counters several concrete TDD-skip failure modes, including \"customer is waiting,\" \"just one quick fix,\" missing test infrastructure, and the temptation to weaken downstream failing tests after the contract change."
    },
    {
      "dimension": "Honesty when blocking",
      "score": 5,
      "justification": "A is unusually explicit about real blockers and assumptions, saying to halt if no test runner is wired up, acknowledging the unspecified empty-input contract, and noting that broader-suite failures may expose dependent callers rather than something to hide."
    }
  ],
  "scores_B": [
    {
      "dimension": "Discipline enforcement",
      "score": 5,
      "justification": "B strongly enforces the Iron Law with \"NO PRODUCTION CODE WITHOUT A FAILING TEST FIRST\" and repeatedly says not to touch production code until the failing test exists."
    },
    {
      "dimension": "RED-GREEN-REFACTOR cycle visibility",
      "score": 5,
      "justification": "B clearly labels and walks through RED, Verify RED, GREEN, Verify GREEN, and REFACTOR, so the cycle is easy to follow end to end."
    },
    {
      "dimension": "Test quality",
      "score": 5,
      "justification": "The test is focused and behavioral, with a clear name, no mocks, and a single externally visible contract assertion that empty input raises `ValueError` mentioning \"empty.\""
    },
    {
      "dimension": "Failure-mode coverage",
      "score": 3,
      "justification": "B directly counters the \"I'm in a hurry\" rationalization and insists on verifying the failing test, but it does not cover multiple distinct TDD-skip rationalizations with the specificity A does."
    },
    {
      "dimension": "Honesty when blocking",
      "score": 4,
      "justification": "B is honest that the desired contract must be chosen first and notes import failures would need fixing before proceeding, but it is less explicit than A about genuine blockers like missing test infrastructure or contract fallout in dependent callers."
    }
  ],
  "winner": "A",
  "winner_reasoning": "A and B are both strong on discipline, cycle visibility, and test quality. A wins on the two differentiators the rubric cares about most here: it does a better job surfacing concrete anti-TDD rationalizations and is more honest about real blockers and contract-change fallout. B is cleaner and shorter, but it gives up rigor on those dimensions.",
  "provenance_prediction": {
    "A_is": "handwritten",
    "B_is": "generated"
  },
  "provenance_reasoning": "A reads like a hand-tuned production skill because it has idiosyncratic enforcement language, explicit quality gates, policy-style refusals, and accumulated scar-tissue guidance such as how to handle downstream tests after a contract change. B reads more like a freshly generated workflow output: polished and competent, but more generic in structure, with fewer distinctive operational guardrails and less nuanced failure-mode handling."
}
```


### gpt54 — obra-tdd/02-new-feature

```json
{
  "task_compliance": {
    "A_complies": true,
    "B_complies": true,
    "notes": "Both outputs stay on the checkout-discount task and frame the work as TDD with pytest; Output B is less complete because cycles 2-6 are partly sketched rather than fully walked end-to-end, but it still performs the requested walkthrough rather than going off-task."
  },
  "verbosity_penalty_applied": {
    "A_penalized": false,
    "B_penalized": false,
    "notes": "Output A is longer, but it is not equally useful to Output B: it materially adds full cycle coverage, concrete red/green verification, and a finished refactor, so length should not be penalized here."
  },
  "scores_A": [
    {
      "dimension": "Discipline enforcement",
      "score": 5,
      "justification": "It repeatedly enforces the Iron Law with explicit language like \"No production code without a failing test first\" and calls out when a test passing immediately is a \"red flag\" that must be handled deliberately."
    },
    {
      "dimension": "RED-GREEN-REFACTOR cycle visibility",
      "score": 5,
      "justification": "Every major behavior is shown as RED, Verify RED, GREEN, Verify GREEN, and REFACTOR, including concrete pytest failures and the final green suite."
    },
    {
      "dimension": "Test quality",
      "score": 5,
      "justification": "The tests are small, behavioral, and mostly one-observable-behavior each, such as `test_save10_applies_ten_percent_off` and the separate boundary checks for `SAVE20` and `FREESHIP`."
    },
    {
      "dimension": "Failure-mode coverage",
      "score": 4,
      "justification": "It counters several common shortcuts with specifics like \"Resist the urge to introduce a strategy/registry. YAGNI\" and explains how to treat already-green tests via mutation, though it is less explicit about named rationalizations than the rubric's strongest anchor."
    },
    {
      "dimension": "Honesty when blocking",
      "score": 5,
      "justification": "When a new test already passes, it does not fake a red stage; it labels the case a regression guard, explains why, and proves the test has bite with mutation checks."
    }
  ],
  "scores_B": [
    {
      "dimension": "Discipline enforcement",
      "score": 4,
      "justification": "It strongly insists on test-first sequencing with gates like \"If the test PASSES on the first run: STOP,\" but the later cycles are described more as process rules than fully enforced step-by-step execution."
    },
    {
      "dimension": "RED-GREEN-REFACTOR cycle visibility",
      "score": 3,
      "justification": "Cycle 1 shows a full red/green/refactor loop, but cycles 2-6 are only sketched and explicitly deferred to a hypothetical live session, so the full workflow is less visible."
    },
    {
      "dimension": "Test quality",
      "score": 4,
      "justification": "The tests are behavior-focused and readable, but the `FREESHIP` cycle bundles both positive and negative cases together and the later cycles are less concretely developed than in Output A."
    },
    {
      "dimension": "Failure-mode coverage",
      "score": 4,
      "justification": "It explicitly rejects several bad TDD escape hatches, including \"do not quietly delete the test\" and \"do not edit the implementation to 'make it interesting',\" which is strong and specific even if not exhaustive."
    },
    {
      "dimension": "Honesty when blocking",
      "score": 5,
      "justification": "It is notably candid when cycles 4 and 6 do not go red, stating it will \"not claim a TDD cycle for it because nothing went red\" instead of pretending otherwise."
    }
  ],
  "winner": "A",
  "winner_reasoning": "Output A wins on completeness and execution of the rubric's core TDD mechanics. The decisive gap is RED-GREEN-REFACTOR visibility: A fully walks the feature to a finished implementation with concrete red and green evidence across cycles, while B fully demonstrates only the first cycle and sketches the rest.",
  "provenance_prediction": {
    "A_is": "generated",
    "B_is": "handwritten"
  },
  "provenance_reasoning": "Output B has stronger signals of a hand-tuned production skill: rigid named phases, routing/gate language, repeated procedural guardrails, and references to workflow internals like a \"quality gate\" and \"persona's rationalizations table.\" Output A feels more like a capable model synthesis: polished and thorough, but more naturally expansive and less like a stable, opinionated operator manual."
}
```


### gpt54 — obra-tdd/03-refactor-under-pressure

```json
{
  "task_compliance": {
    "A_complies": true,
    "B_complies": true,
    "notes": "Neither output triggers the task-compliance cap; both directly walk through a safe legacy refactor using TDD-adjacent characterization testing and are honest about where strict TDD does and does not fit."
  },
  "verbosity_penalty_applied": {
    "A_penalized": true,
    "B_penalized": false,
    "notes": "A is materially longer than B, and in close calls I did not reward A's extra scaffolding when B covered the same ground more concisely; this mainly affected close scoring on cycle visibility and test-quality clarity."
  },
  "scores_A": [
    {
      "dimension": "Discipline enforcement",
      "score": 5,
      "justification": "A forcefully blocks the shortcut path with lines like \"write characterization tests FIRST to pin the unpinned 40%, THEN refactor\" and directly rebuts EOD-pressure rationalizations."
    },
    {
      "dimension": "RED-GREEN-REFACTOR cycle visibility",
      "score": 3,
      "justification": "A shows the phases, but it repeatedly redefines RED away for both characterization and refactor cycles (for example, \"the 'red' step is replaced by\" a baseline-green suite), so the failing-test stage is less visible than the rubric asks for."
    },
    {
      "dimension": "Test quality",
      "score": 4,
      "justification": "Its example characterization test is concrete and behavioral, but it bundles multiple assertions in one scenario and leans on collaborator-call assertions like `assert_not_called()`."
    },
    {
      "dimension": "Failure-mode coverage",
      "score": 5,
      "justification": "A names several specific rationalizations in a table, such as \"EOD is tight\" and \"I'll add characterization tests in a follow-up PR,\" and gives task-specific counter-arguments for each."
    },
    {
      "dimension": "Honesty when blocking",
      "score": 5,
      "justification": "A is explicit that strict feature-style TDD does not map cleanly to a no-behavior-change refactor and honestly redirects to characterization-first plus timeline negotiation."
    }
  ],
  "scores_B": [
    {
      "dimension": "Discipline enforcement",
      "score": 5,
      "justification": "B explicitly rejects \"just refactor it and trust the existing tests\" and insists the uncovered 40% \"must be discovered and pinned down with tests\" before any structural change."
    },
    {
      "dimension": "RED-GREEN-REFACTOR cycle visibility",
      "score": 4,
      "justification": "B makes the cycle more visible by showing a concrete RED run with a placeholder assertion, then GREEN after updating the characterization test, followed by tiny REFACTOR extractions with full-suite reruns."
    },
    {
      "dimension": "Test quality",
      "score": 5,
      "justification": "B gives strong test-design guidance like \"one branch per test\" and \"no `and` in test names,\" and its examples focus on observable outcomes rather than internal implementation details."
    },
    {
      "dimension": "Failure-mode coverage",
      "score": 4,
      "justification": "B covers multiple concrete red flags such as \"I'll write tests after the refactor\" and \"Team lead said EOD,\" but its rebuttals are less exhaustive and less personalized than A's table."
    },
    {
      "dimension": "Honesty when blocking",
      "score": 5,
      "justification": "Its \"Where TDD Strictly Doesn't Apply\" section clearly distinguishes characterization testing, mechanical extraction, and true Red-Green work for bugs or new behavior."
    }
  ],
  "winner": "B",
  "winner_reasoning": "B wins on the dimensions that most directly match the rubric: it preserves clearer RED-GREEN-REFACTOR visibility and gives sharper test-quality guidance while remaining substantially more concise. A is stronger on failure-mode coverage and equally honest about the legacy-code blocker, but it over-adapts the failing-test stage and pays a verbosity cost in a close comparison.",
  "provenance_prediction": {
    "A_is": "handwritten",
    "B_is": "generated"
  },
  "provenance_reasoning": "A has stronger signs of a long-lived hand-tuned skill: explicit routing logic, reusable output templates, and repeated operational control phrases like \"Tell me to proceed\" that feel like production workflow scaffolding. B reads more like a synthesized response built from a brief plus extracted rules, with smoother essay structure and more overt \"The skill says...\" summarization of source guidance."
}
```


## GEMINI judge


### gemini — anthropic-canvas-design/01-poster

```json
{
  "task_compliance": "Both outputs successfully produced a design philosophy and a highly concrete, executable visual specification (serving as the rendered artifact placeholder), complying with the task constraints.",
  "verbosity_penalty_applied": false,
  "scores_A": [
    {
      "dimension": "Aesthetic specificity",
      "score": 5,
      "justify": "Output A defines 'Cathode Bloom' with extreme specificity, rooting it in NTSC broadcast engineering and degraded CRT phosphors rather than vague adjectives."
    },
    {
      "dimension": "Anti-genericness",
      "score": 5,
      "justify": "Output A explicitly names and bans the exact AI-default patterns mentioned in the rubric, including purple gradients, drop shadows, and the Inter font family."
    },
    {
      "dimension": "Design philosophy \u2192 visual coherence",
      "score": 5,
      "justify": "The executable spec perfectly translates the 'Cathode Bloom' philosophy into concrete hex codes, typography (VT323), and layout elements like scanlines and color-bar interruptions."
    },
    {
      "dimension": "Originality discipline",
      "score": 5,
      "justify": "Output A invents a novel synthesis (broadcast ephemera for a film festival) without directly copying a specific artist's copyrighted style."
    },
    {
      "dimension": "Constraint honesty",
      "score": 5,
      "justify": "Output A directly addresses the brief's rejection of 'warm paper minimalism' and justifies its CRT-based divergence as an appropriate response to the festival's experimental nature."
    }
  ],
  "scores_B": [
    {
      "dimension": "Aesthetic specificity",
      "score": 5,
      "justify": "Output B creates 'Emulsion Rites', deeply specifying photochemical processes, sprocket holes, and silver halide material constraints."
    },
    {
      "dimension": "Anti-genericness",
      "score": 4,
      "justify": "Output B explicitly rejects 'indie warm cream' and 'drop shadows', but relies slightly less on aggressively naming AI-specific tropes compared to A."
    },
    {
      "dimension": "Design philosophy \u2192 visual coherence",
      "score": 5,
      "justify": "The rendered spec meticulously applies the photochemical philosophy through structural grid choices, film grain, and specific film-strip visual encoding."
    },
    {
      "dimension": "Originality discipline",
      "score": 2,
      "justify": "Output B explicitly bases its entire visual language on imitating a named artist (Stan Brakhage), encoding his name and specific techniques (Mothlight), which violates the originality discipline."
    },
    {
      "dimension": "Constraint honesty",
      "score": 4,
      "justify": "Output B acknowledges the user's constraints and builds a solid rationale, though it leans heavily into the user's mention of Brakhage rather than forcing a completely new trade-off."
    }
  ],
  "winner": "A",
  "winner_reasoning": "Output A wins decisively on 'Originality discipline' and 'Anti-genericness'. While both provide stunningly detailed and coherent design systems, Output B falls into the trap of directly imitating a named artist (Brakhage) rather than inventing a new aesthetic, whereas Output A invents a brilliant, original CRT/broadcast aesthetic that perfectly satisfies the brief.",
  "provenance_prediction": {
    "A_is": "handwritten",
    "B_is": "generated"
  },
  "provenance_reasoning": "Output A directly and aggressively targets the exact AI-tropes (Inter, Geist, purple gradients) that the rubric penalizes, suggesting it comes from a hand-tuned skill optimized against these specific failure modes. Output B's inclusion of a 'Deduced' section and its literal interpretation of the Brakhage reference feels more like a newly generated zero-shot workflow."
}
```


### gemini — anthropic-canvas-design/02-brand-identity

```json
{
  "task_compliance": false,
  "verbosity_penalty_applied": true,
  "notes": "Neither output produced the required rendered visual artifact (.png or .pdf placeholder). Both only provided textual descriptions of the visual stages. Therefore, the cross-cutting task compliance cap of 3/5 was applied to all dimensions for both outputs.",
  "scores_A": [
    {
      "dimension": "Aesthetic specificity",
      "score": 3,
      "justification": "Anchors the aesthetic in concrete hardware references like VT220 amber and IBM line printers, but capped at 3 for missing the artifact."
    },
    {
      "dimension": "Anti-genericness",
      "score": 3,
      "justification": "Explicitly bans AI defaults like the Inter font, gradients, and glassmorphism, scoring highly but capped at 3."
    },
    {
      "dimension": "Design philosophy \u2192 visual coherence",
      "score": 1,
      "justification": "Completely fails to produce the rendered visual artifact, making visual coherence impossible to evaluate."
    },
    {
      "dimension": "Originality discipline",
      "score": 3,
      "justification": "Synthesizes an original, terminal-based engineering aesthetic without directly copying a specific artist, but capped at 3."
    },
    {
      "dimension": "Constraint honesty",
      "score": 3,
      "justification": "Forces strict layout, color, and typographic constraints instead of allowing generic meaningless variations, capped at 3."
    }
  ],
  "scores_B": [
    {
      "dimension": "Aesthetic specificity",
      "score": 2,
      "justification": "Names specific analog tools like HP-15C and Rotring pens, but receives a verbosity penalty for flowery filler text that dilutes the instructions."
    },
    {
      "dimension": "Anti-genericness",
      "score": 3,
      "justification": "Actively rejects the 'SaaS gradient generator' aesthetic and names forbidden elements, capped at 3 for the missing artifact."
    },
    {
      "dimension": "Design philosophy \u2192 visual coherence",
      "score": 1,
      "justification": "Only provides a text table and description of the composition, failing entirely to render the requested image artifact."
    },
    {
      "dimension": "Originality discipline",
      "score": 2,
      "justification": "Develops a distinct physical-analog vibe but its execution is bogged down by dramatic, AI-style storytelling, earning a verbosity penalty."
    },
    {
      "dimension": "Constraint honesty",
      "score": 3,
      "justification": "Defines explicit rules for grids, typography, and forbidden words to enforce trade-offs, capped at 3."
    }
  ],
  "winner": "A",
  "winner_reasoning": "Both outputs failed to generate the required visual artifact, triggering the task compliance cap. Output A wins because its prose was highly direct, functionally aligned with the DevOps audience, and avoided the verbosity penalty that Output B incurred for its overly dramatic and padded text.",
  "provenance_prediction": {
    "A_is": "handwritten",
    "B_is": "generated"
  },
  "provenance_reasoning": "Output A's sharp, opinionated tone ('Two faces. No third face for personality.') is characteristic of a hand-tuned, expert-crafted system prompt. Output B's flowery filler ('quiet authority of a notebook', 'work labored over for countless hours') and predictable markdown table structure are classic artifacts of a freshly generated LLM meta-prompt."
}
```


### gemini — anthropic-canvas-design/03-data-viz-aesthetic

```json
{
  "task_compliance": "Output B fully complies by providing a renderable HTML/CSS code block as the artifact placeholder along with the actual 2014-2024 dataset. Output A provides a highly concrete prose specification but lacks renderable code or a true artifact placeholder, leaning closer to the non-compliance cap but saved by its extreme descriptive concreteness.",
  "verbosity_penalty_applied": "No. Both outputs are dense, highly specific, and justify their length with concrete design decisions and formatting rules.",
  "scores_A": [
    {
      "dimension": "Aesthetic specificity",
      "score": 5,
      "justification": "Anchors firmly in nautical charts and 19th-century ordnance maps with explicit layout rules and exact hex codes."
    },
    {
      "dimension": "Anti-genericness",
      "score": 5,
      "justification": "Explicitly rejects default plotting libraries, drop shadows, gradients, rounded corners, and icons."
    },
    {
      "dimension": "Design philosophy \u2192 visual coherence",
      "score": 5,
      "justification": "The visual specification perfectly executes the 'Forensic Cartography' concept through hairlines and strict baseline grids."
    },
    {
      "dimension": "Originality discipline",
      "score": 5,
      "justification": "Invents a unique mapping aesthetic rather than mimicking a specific contemporary data artist."
    },
    {
      "dimension": "Constraint honesty",
      "score": 4,
      "justification": "Enforces strict margins and limited color palettes, though its constraints are theoretical since no renderable code is produced."
    }
  ],
  "scores_B": [
    {
      "dimension": "Aesthetic specificity",
      "score": 5,
      "justification": "Brilliantly targets 1958-1971 U.S. Forest Service annual reports and uncoated stock letterpress."
    },
    {
      "dimension": "Anti-genericness",
      "score": 5,
      "justification": "Includes a literal 'Banned' list explicitly naming Inter, purple gradients, drop shadows, and modern minimalism."
    },
    {
      "dimension": "Design philosophy \u2192 visual coherence",
      "score": 5,
      "justification": "The provided HTML/CSS layout perfectly translates the ledger philosophy into a structured, immediately renderable artifact."
    },
    {
      "dimension": "Originality discipline",
      "score": 5,
      "justification": "Synthesizes mid-century administrative records into a novel and highly appropriate data-viz aesthetic for the subject matter."
    },
    {
      "dimension": "Constraint honesty",
      "score": 5,
      "justification": "Directly addresses the brief's rejection of generic viz by boldly stripping axes and gridlines in favor of proportional rules."
    }
  ],
  "winner": "B",
  "winner_reasoning": "Both outputs provide phenomenal, highly specific design philosophies that perfectly capture the gravity of the brief. Output B wins because it goes beyond a prose specification to provide a fully renderable HTML/CSS artifact and an accurate dataset, perfectly fulfilling the prompt's two-part output requirement.",
  "provenance_prediction": {
    "A_is": "generated",
    "B_is": "handwritten"
  },
  "provenance_reasoning": "Output B features a mock CLI footer, explicit processing phases (Phase 2, Phase 3), and a strict checklist structure, which are classic hallmarks of a hand-tuned, iteratively developed community skill prompt. Output A's flowing narrative structure is more characteristic of a high-quality zero-shot generation from a structural meta-prompt."
}
```


### gemini — chrisvoncsefalvay-d3/01-bar-with-edge-case

```json
{
  "task_compliance": {
    "A": true,
    "B": true,
    "notes": "Both outputs successfully implement a horizontal bar chart with symlog scaling, tooltips, responsive sizing, and framework integration snippets."
  },
  "verbosity_penalty_applied": false,
  "scores_A": [
    {
      "dimension": "Code completeness",
      "score": 5,
      "justification": "Provides a fully working, paste-and-run vanilla HTML example alongside the complete drawing function with all necessary axes, scales, and data bindings."
    },
    {
      "dimension": "API correctness",
      "score": 3,
      "justification": "Mostly modern D3, but uses the older `enter().append()` and `merge()` pattern instead of the modern v7+ `.join()` API as specified in the rubric."
    },
    {
      "dimension": "Framework-agnosticism",
      "score": 5,
      "justification": "The core rendering function is completely detached from any framework, and excellent integration snippets are provided for React, Vue, Svelte, and vanilla JS."
    },
    {
      "dimension": "Explanatory comments",
      "score": 5,
      "justification": "Includes a comprehensive 'Notes on the design choices' section that clearly explains the use of symlog, keyed data joins, and tooltip positioning."
    },
    {
      "dimension": "Edge-case handling",
      "score": 5,
      "justification": "Handles zero-values by setting a minimum pixel width and uses a symmetric log scale to prevent outliers from crushing the mid-range data."
    }
  ],
  "scores_B": [
    {
      "dimension": "Code completeness",
      "score": 5,
      "justification": "Delivers a robust, structurally complete ES module exporting a render function that returns update and cleanup handlers, alongside all required imports."
    },
    {
      "dimension": "API correctness",
      "score": 5,
      "justification": "Perfectly adheres to modern D3 v7+ idioms, explicitly utilizing `.join()` for the data lifecycle and `pointer(event)` instead of the deprecated `d3.event`."
    },
    {
      "dimension": "Framework-agnosticism",
      "score": 5,
      "justification": "The clean `render(container, data)` returning `{update, cleanup}` creates an ideal, portable lifecycle contract that works seamlessly across all UI frameworks."
    },
    {
      "dimension": "Explanatory comments",
      "score": 5,
      "justification": "Inline comments and the 'Why these primitives' section clearly justify the use of symlog, ResizeObserver, and the join pattern."
    },
    {
      "dimension": "Edge-case handling",
      "score": 5,
      "justification": "Effectively addresses the edge cases by combining a 3px minimum bar width for zeros with a symmetric log scale to manage the massive outliers."
    }
  ],
  "winner": "B",
  "winner_reasoning": "Output B wins on the 'API correctness' dimension. Output A relies on the older D3 v4/v5 `enter().append().merge()` pattern, whereas Output B correctly uses the modern v7 `.join()` pattern demanded by the rubric for a perfect score.",
  "provenance_prediction": {
    "A_is": "handwritten",
    "B_is": "generated"
  },
  "provenance_reasoning": "Output B contains explicit LLM planning artifacts ('Parsed spec', 'Primitive selections (Phase 2)', and 'Quality gates self-check'), which are hallmark behaviors of a generated meta-prompt workflow. Output A uses older D3 idioms typical of a human developer and reads organically like a hand-tuned community tutorial."
}
```


### gemini — chrisvoncsefalvay-d3/02-network-graph

```json
{
  "task_compliance": "Both outputs successfully implemented the requested d3 force-directed network graph with all required features.",
  "verbosity_penalty_applied": "Yes, applied to Output B. Output B included excessive, unrequested meta-sections ('Parsed spec', 'Primitive selections', 'Quality gates self-check') which violate the 'Concise + working > long + working' rule.",
  "scores_A": [
    {
      "dimension": "Code completeness",
      "score": 5,
      "justification": "Provides a complete HTML file with a CDN script tag that can be pasted and rendered correctly on the first try without a build step."
    },
    {
      "dimension": "API correctness",
      "score": 5,
      "justification": "Consistently uses modern d3 v7 patterns, including d3.forceSimulation and the selection.join() pattern for nodes and links."
    },
    {
      "dimension": "Framework-agnosticism",
      "score": 5,
      "justification": "Uses pure DOM selection and d3 primitives in a self-contained function that can mount anywhere."
    },
    {
      "dimension": "Explanatory comments",
      "score": 5,
      "justification": "Includes concise, highly relevant inline comments explaining the choice of alphaDecay, scales, and layout grouping."
    },
    {
      "dimension": "Edge-case handling",
      "score": 4,
      "justification": "Thoughtfully generates a connected backbone to prevent graph fragmentation and includes a setTimeout safety net for the simulation, though it lacks robust handling for zero-variance data."
    }
  ],
  "scores_B": [
    {
      "dimension": "Code completeness",
      "score": 3,
      "justification": "Structurally excellent, but uses bare module imports (e.g., 'd3-selection') without an import map in the HTML snippet, meaning it will fail to run if pasted directly into a standard browser."
    },
    {
      "dimension": "API correctness",
      "score": 5,
      "justification": "Exemplary use of modern d3 v7+ APIs, including specific enter/update functions within .join() and modular imports."
    },
    {
      "dimension": "Framework-agnosticism",
      "score": 5,
      "justification": "Provides an outstanding framework-agnostic contract by returning 'update' and 'cleanup' functions, making it perfectly suited for React/Vue lifecycles."
    },
    {
      "dimension": "Explanatory comments",
      "score": 3,
      "justification": "While inline comments are great, the score is penalized due to the extreme verbosity of the surrounding markdown (Quality gates, parsed specs) that clutters the output."
    },
    {
      "dimension": "Edge-case handling",
      "score": 5,
      "justification": "Handles zero-variance data scales (weightDomain[0] === weightDomain[1]) and explicitly implements teardown/cleanup logic for safe re-mounting."
    }
  ],
  "winner": "A",
  "winner_reasoning": "Output A wins because it delivers a strictly paste-and-run solution that works immediately without build tools, whereas B requires an import map or bundler to resolve bare module imports. Furthermore, A is concise and directly answers the prompt, while B is bogged down by verbose, generated meta-commentary.",
  "provenance_prediction": {
    "A_is": "handwritten",
    "B_is": "generated"
  },
  "provenance_reasoning": "Output A is highly practical, relies on a standard CDN approach, and feels organically written for immediate use (hand-tuned). Output B contains clear LLM 'chain-of-thought' and system-prompt artifacts like 'Parsed spec', 'Primitive selections', and 'Quality gates self-check', which are hallmarks of a freshly-generated meta-paap skill."
}
```


### gemini — chrisvoncsefalvay-d3/03-animated-transition

```json
{
  "task_compliance": "Both outputs successfully implement the requested animated line chart with a toggle button, transitioning axes, and point-by-point interpolation. No task-compliance caps applied.",
  "verbosity_penalty_applied": "No penalty applied. While Output A is longer, its length is justified by providing a highly robust, framework-agnostic module and explicit framework integration snippets, adding significant value rather than filler.",
  "scores_A": [
    {
      "dimension": "Code completeness",
      "score": 5,
      "justification": "Provides a robust, paste-and-run ES module with idempotent rendering, explicit scaling, modular imports, and comprehensive cleanup methods."
    },
    {
      "dimension": "API correctness",
      "score": 5,
      "justification": "Perfectly utilizes modern d3 v7+ patterns, prominently featuring `.join()` for the data markers and properly implementing `attrTween` for explicit path string interpolation."
    },
    {
      "dimension": "Framework-agnosticism",
      "score": 5,
      "justification": "The core function accepts a DOM node/selector seamlessly, and the output includes specific, working integration wrappers for React, Vue, Svelte, and Vanilla JS."
    },
    {
      "dimension": "Explanatory comments",
      "score": 5,
      "justification": "Provides a highly detailed 'Primitive selections' table and a concise 'Why these primitives' section that perfectly explains the rationale behind scalePoint, attrTween, and cleanup."
    },
    {
      "dimension": "Edge-case handling",
      "score": 4,
      "justification": "Handles zero-variance datasets by dynamically padding the domain extent and prevents memory leaks/detached node mutations by explicitly calling `.interrupt()` on cleanup."
    }
  ],
  "scores_B": [
    {
      "dimension": "Code completeness",
      "score": 4,
      "justification": "Structurally complete and runs in the browser, but relies heavily on global DOM IDs and a global d3 object, making it less modular."
    },
    {
      "dimension": "API correctness",
      "score": 3,
      "justification": "Claims to be v7 but falls back to the deprecated `enter().append()...` and `exit().remove()` manual lifecycle patterns instead of utilizing the modern `.join()` API."
    },
    {
      "dimension": "Framework-agnosticism",
      "score": 2,
      "justification": "Tightly coupled to specific global HTML element IDs (`#chart`, `#toggle`) and lacks the modular structure needed to easily mount within modern component lifecycles."
    },
    {
      "dimension": "Explanatory comments",
      "score": 4,
      "justification": "Includes good inline comments and a solid summary table explaining how the shared transition object orchestrates the animation."
    },
    {
      "dimension": "Edge-case handling",
      "score": 2,
      "justification": "The `yMax * 1.1` domain logic fails for zero or negative datasets, and the code provides no cleanup mechanism for in-flight transitions upon unmounting."
    }
  ],
  "winner": "A",
  "winner_reasoning": "Output A demonstrates vastly superior software engineering. It implements true framework-agnosticism via a clean functional API, correctly utilizes v7's `.join()` pattern, safely handles path interpolation with `attrTween`, and provides crucial memory-leak prevention via `.interrupt()`.",
  "provenance_prediction": {
    "A_is": "generated",
    "B_is": "handwritten"
  },
  "provenance_reasoning": "Output A's extremely rigid, explicitly phased structure (e.g., 'Phase 1 \u2014 Parsed spec', 'Phase 4 \u2014 Quality gates self-check') is a classic artifact of an advanced LLM meta-prompt designed to self-evaluate against a rubric. Output B's conversational tone and self-reference to 'Pattern A' feels like an older, hand-maintained community prompt template."
}
```


### gemini — gstack-plan-ceo-review/01-ambitious-roadmap

```json
{
  "task_compliance": "Output A is fully compliant and concise. Output B performs the task but includes excessive inherited template boilerplate (e.g., 'Completion Summary' with 14 rows of 'N/A \u2014 strategy doc', 'Dream State Mapping') that violates the verbosity constraint.",
  "verbosity_penalty_applied": "Yes. Output B is penalized for extreme verbosity driven by template inheritance rather than task-specific depth, slightly lowering its overall impact despite strong prose.",
  "scores_A": [
    {
      "dimension": "Mode declaration + fit",
      "score": 5,
      "justification": "Explicitly declares 'SCOPE REDUCTION' upfront and justifies it by noting the impossibility of executing 8 workstreams with a 12-person team."
    },
    {
      "dimension": "Premise challenges",
      "score": 5,
      "justification": "Systematically breaks down 5 premises with 'What needs to be true' and 'Implication if it doesn't hold', directly challenging the ambition vs. volume assumption."
    },
    {
      "dimension": "Hardest-question identification",
      "score": 5,
      "justification": "Identifies 3 highly specific, unavoidable questions, such as forcing the user to name the single workstream that would make the board meeting hardest if it failed."
    },
    {
      "dimension": "Decision-class taxonomy applied",
      "score": 5,
      "justification": "Perfectly applies the requested taxonomy by explicitly categorizing 'Taste Calls I Made' and 'User Challenges' (with 'ESCALATION DEFERRED')."
    },
    {
      "dimension": "Honest discomfort",
      "score": 5,
      "justification": "Delivers blunt truths without softening, such as pointing out that the plan reads like a 'board-pleasing menu, not a sequenced bet'."
    }
  ],
  "scores_B": [
    {
      "dimension": "Mode declaration + fit",
      "score": 5,
      "justification": "Powerfully declares 'SCOPE REDUCTION' and explains that holding scope on a broken plan would be 'malpractice'."
    },
    {
      "dimension": "Premise challenges",
      "score": 5,
      "justification": "Provides excellent, deep challenges to the user's assumptions, correctly identifying the 'cargo-cult Series A' behavior."
    },
    {
      "dimension": "Hardest-question identification",
      "score": 5,
      "justification": "Lists 7 hard unresolved questions, effectively forcing the user to confront their lack of a singular focus and unvalidated market assumptions."
    },
    {
      "dimension": "Decision-class taxonomy applied",
      "score": 2,
      "justification": "Ignores the rubric's 'Mechanical / Taste / User Challenge' taxonomy, substituting a Bezos 'one-way / two-way doors' framework instead."
    },
    {
      "dimension": "Honest discomfort",
      "score": 5,
      "justification": "Maintains an incredibly direct and surgical posture, telling the user their plan will result in a team that's 'on fire at month 4'."
    }
  ],
  "winner": "A",
  "winner_reasoning": "Output A achieved the same level of incisive, uncomfortable feedback as B but did so with far greater precision and strict adherence to the rubric's requested taxonomy. Output B suffered from inherited template bloat that added verbosity without value.",
  "provenance_prediction": {
    "A_is": "generated",
    "B_is": "handwritten"
  },
  "provenance_reasoning": "Output B is unmistakably the hand-tuned 'gstack' skill, given its inclusion of the ~600-line template artifacts (e.g., 'Step 0A/B/C', the massive 14-row 'Completion Summary' table full of N/A values). Output A is the freshly-generated v2 skill, cleanly executing the requested workflow without the legacy template baggage."
}
```


### gemini — gstack-plan-ceo-review/02-feature-launch

```json
{
  "task_compliance": {
    "A": true,
    "B": true,
    "notes": "Output B includes significant boilerplate from a shared template (e.g., empty Sections 1-11) that dilutes the review, though it formally completes the task."
  },
  "verbosity_penalty_applied": true,
  "scores_A": [
    {
      "dimension": "Mode declaration + fit",
      "score": 5,
      "justification": "Explicitly declares SCOPE REDUCTION upfront and justifies it brilliantly by exposing the inflated scope relative to defensibility."
    },
    {
      "dimension": "Premise challenges",
      "score": 5,
      "justification": "Systematically breaks down four specific premises (e.g., '30% pipeline mention... is causally attributable') and details what needs to be true and the implications if they break."
    },
    {
      "dimension": "Hardest-question identification",
      "score": 5,
      "justification": "Names three highly specific, uncomfortable questions (e.g., 'Has the anchor customer actually said this is a renewal blocker...') and forces a decision on each."
    },
    {
      "dimension": "Decision-class taxonomy applied",
      "score": 5,
      "justification": "Explicitly separates 'Taste Calls I Made' and 'User Challenges', correctly applying the taxonomy."
    },
    {
      "dimension": "Honest discomfort",
      "score": 5,
      "justification": "Delivers brutal, honest truths like '20 interviews is research-theater' and 'founders systematically over-read customer enthusiasm'."
    }
  ],
  "scores_B": [
    {
      "dimension": "Mode declaration + fit",
      "score": 4,
      "justification": "Declares SELECTIVE EXPANSION and justifies it, but hides it slightly under 'Verdict up front' before declaring it again later."
    },
    {
      "dimension": "Premise challenges",
      "score": 4,
      "justification": "Challenges the core framing effectively ('retention bet, not just a growth bet'), but uses a looser, less rigorous structure than A."
    },
    {
      "dimension": "Hardest-question identification",
      "score": 3,
      "justification": "Surfaces questions like push vs pull architecture, but scatters them across a massive template rather than forcing the 1-3 hardest unresolved questions clearly."
    },
    {
      "dimension": "Decision-class taxonomy applied",
      "score": 2,
      "justification": "Fails to use the Mechanical/Taste/User Challenge taxonomy, instead using 'Cherry-picks' and 'Recommendation posture'."
    },
    {
      "dimension": "Honest discomfort",
      "score": 4,
      "justification": "Provides good pushback ('You're building a demo, not a product'), but the impact is blunted by excessive template formatting."
    }
  ],
  "winner": "A",
  "winner_reasoning": "Output A is remarkably dense, incisive, and precisely follows the rubric's requirements without wasting a single word. Output B suffers from massive template bloat (printing empty sections like 'Code Quality Review' for a strategy doc) and fails to apply the requested decision taxonomy.",
  "provenance_prediction": {
    "A_is": "generated",
    "B_is": "handwritten"
  },
  "provenance_reasoning": "Output B is clearly the hand-tuned gstack skill; it literally references 'gstack v1.x' and inherits massive structural template blocks (Sections 1-11, System Audit) that are completely unnecessary for this specific input. Output A is the generated skill, as it directly and cleanly implements the exact mechanics requested by the brief (like the specific 'Taste/User Challenge' taxonomy) without any inherited cruft."
}
```


### gemini — gstack-plan-ceo-review/03-pivot-decision

```json
{
  "task_compliance": "Output A is fully compliant. Output B forces a business plan review into software engineering templates ('Code Quality Review', 'Security & Threat Model') which makes it verbose and slightly off-format, missing the requested decision taxonomy.",
  "verbosity_penalty_applied": "Output B penalized on Hardest-question identification and Decision-class taxonomy for using overly verbose, inherited software-engineering templates that dilute the CEO review format.",
  "scores_A": [
    {
      "dimension": "Mode declaration + fit",
      "score": 5,
      "justify": "Explicitly declares 'HOLD SCOPE' upfront and justifies it by validating the 1.4 LTV/CAC signal while noting the 12-week plan hand-waves execution."
    },
    {
      "dimension": "Premise challenges",
      "score": 5,
      "justify": "Directly challenges the 'same underlying product' premise, noting L&D buyers need skills assessments and manager reporting, not just gamification."
    },
    {
      "dimension": "Hardest-question identification",
      "score": 5,
      "justify": "Names 3 critical questions, including 'Is the existing B2C product actually buyable by L&D...' and forces the cofounder misalignment issue to be resolved before week 4."
    },
    {
      "dimension": "Decision-class taxonomy applied",
      "score": 5,
      "justify": "Perfectly applies the requested taxonomy, explicitly listing 'Taste Calls I Made' and 'User Challenges' with '[ESCALATION DEFERRED]' tags."
    },
    {
      "dimension": "Honest discomfort",
      "score": 5,
      "justify": "Names uncomfortable truths directly: 'Cofounder misalignment at week 0 will become cofounder rupture at week 6.'"
    }
  ],
  "scores_B": [
    {
      "dimension": "Mode declaration + fit",
      "score": 5,
      "justify": "Declares 'HOLD SCOPE with surgical interrogation' and accurately justifies that this is a company-direction call, not a feature spec."
    },
    {
      "dimension": "Premise challenges",
      "score": 5,
      "justify": "Brilliantly challenges the product vs GTM premise by pointing out that 6% monthly churn means the underlying product is flawed and will fail in enterprise too."
    },
    {
      "dimension": "Hardest-question identification",
      "score": 4,
      "justify": "Identifies excellent hard questions (like the cofounder dynamic and runway math), but buries them inside forced software-engineering headers rather than highlighting them concisely."
    },
    {
      "dimension": "Decision-class taxonomy applied",
      "score": 2,
      "justify": "Fails to use the Mechanical/Taste/User Challenge taxonomy, instead relying on its own inherited 'OK / WARNING / CRITICAL GAP' and 'Lake Score' system."
    },
    {
      "dimension": "Honest discomfort",
      "score": 5,
      "justify": "Delivers brutal, highly effective feedback: 'This plan reads like founder anxiety dressed up as strategy' and 'Decisiveness without direction is just speed in a circle.'"
    }
  ],
  "winner": "A",
  "winner_reasoning": "Output A followed all rubric constraints perfectly, including the specific Decision-class taxonomy, and delivered a concise, hard-hitting CEO review. Output B had incredible business insights but suffered heavily from template bleed, forcing the plan into irrelevant software-engineering sections ('Code Quality Review', 'Security & Threat Model') which made it overly verbose and caused it to miss the taxonomy requirement.",
  "provenance_prediction": {
    "A_is": "generated",
    "B_is": "handwritten"
  },
  "provenance_reasoning": "Output B is clearly the hand-tuned `gstack` skill. The presence of 'Lake Score', massive ASCII summary tables, and sections like 'Architecture Review' and 'Error & Rescue Map' (which it awkwardly had to label 'translated: company architecture') are classic hallmarks of inheriting ~600 lines of templated, code-review-focused shared blocks. Output A is the freshly generated v2 skill, perfectly tailored to the specific brief without legacy template baggage."
}
```


### gemini — obra-tdd/01-bug-fix

```json
{
  "task_compliance": "Both outputs completed the requested task, walking the user through TDD for the specific bug. However, Output A included internal prompt artifacts ('see row 1 of the table', 'per the Error Handling table, row 4') and a highly redundant Phase 5 that just re-pasted previous steps.",
  "verbosity_penalty_applied": "Output A was penalized slightly on RED-GREEN-REFACTOR visibility because its 'Phase 5' redundantly regurgitated the entire cycle's code and CLI output, needlessly inflating the response length without adding depth.",
  "scores_A": [
    {
      "dimension": "Discipline enforcement",
      "score": 5,
      "justification": "Explicitly refuses the 'hurry' excuse, mandates the failing test first, and grounds the refusal in the necessity of regression coverage."
    },
    {
      "dimension": "RED-GREEN-REFACTOR cycle visibility",
      "score": 4,
      "justification": "Shows all phases clearly with CLI outputs, but suffers a verbosity penalty for needlessly repeating the exact same code and logs in a redundant Phase 5 summary."
    },
    {
      "dimension": "Test quality",
      "score": 5,
      "justification": "Writes a clean, single-assertion test focused strictly on the expected ValueError and its message, explicitly avoiding scope creep."
    },
    {
      "dimension": "Failure-mode coverage",
      "score": 4,
      "justification": "Directly confronts the 'hurry' rationalization and 'just a quick fix', explaining that the hurry protects a bad habit rather than time, though it awkwardly references an internal table."
    },
    {
      "dimension": "Honesty when blocking",
      "score": 4,
      "justification": "Acknowledges that if no test runner is wired up, the developer must stop and fix that first rather than pretending to do TDD."
    }
  ],
  "scores_B": [
    {
      "dimension": "Discipline enforcement",
      "score": 5,
      "justification": "Invokes 'The Iron Law' of TDD, completely halting the developer from patching the function before the test is written and verified."
    },
    {
      "dimension": "RED-GREEN-REFACTOR cycle visibility",
      "score": 5,
      "justification": "Elegantly steps through RED, Verify RED, GREEN, Verify GREEN, and REFACTOR in a concise, highly readable flow without redundant repetition."
    },
    {
      "dimension": "Test quality",
      "score": 5,
      "justification": "Provides a minimal, behavioral test asserting the exact ValueError and message, clearly explaining why it is superior to expecting ZeroDivisionError."
    },
    {
      "dimension": "Failure-mode coverage",
      "score": 4,
      "justification": "Addresses the 'hurry' rationalization effectively by explaining it simply defers the cost to the next incident, though it falls short of naming 3+ distinct rationalizations."
    },
    {
      "dimension": "Honesty when blocking",
      "score": 3,
      "justification": "Adequate, but does not deeply explore scenarios where TDD is genuinely hard or blocked, largely because the requested task was a simple function."
    }
  ],
  "winner": "B",
  "winner_reasoning": "Output B wins by providing a cleaner, more natural walkthrough of the TDD cycle. Output A leaked its internal prompt instructions ('see row 1 of the table') and suffered from unnecessary verbosity by repeating its work in Phase 5.",
  "provenance_prediction": {
    "A_is": "generated",
    "B_is": "handwritten"
  },
  "provenance_reasoning": "Output A is clearly the generated skill; it clumsily leaks its system prompt ('see row 1 of the table', 'per the Error Handling table, row 4') and follows a rigid, overly-verbose template. Output B is the handwritten community skill, evident from its natural phrasing ('The Iron Law'), cohesive narrative flow, and lack of robotic prompt artifacts."
}
```


### gemini — obra-tdd/02-new-feature

```json
{
  "task_compliance": {
    "A": true,
    "B": false,
    "notes": "Output A completes the full walkthrough of the requested feature. Output B acts as an interactive prompt, fully executing only cycle 1 and merely 'sketching' the rest while demanding user input to proceed, failing the 'walk me through the implementation' instruction."
  },
  "verbosity_penalty_applied": false,
  "scores_A": [
    {
      "dimension": "Discipline enforcement",
      "score": 5,
      "justification": "Strictly enforces the 'Iron Law' by refusing to write production code before a test, and explicitly prevents the user from jumping ahead."
    },
    {
      "dimension": "RED-GREEN-REFACTOR cycle visibility",
      "score": 5,
      "justification": "Every cycle explicitly separates RED, Verify RED (with shell output), GREEN, Verify GREEN, and REFACTOR stages."
    },
    {
      "dimension": "Test quality",
      "score": 5,
      "justification": "Tests are perfectly scoped to one behavior, use descriptive names, and avoid over-mocking or testing implementation details."
    },
    {
      "dimension": "Failure-mode coverage",
      "score": 4,
      "justification": "Addresses the urge to prematurely abstract ('Resist the urge to introduce a strategy/registry. YAGNI') and the trap of tests passing immediately."
    },
    {
      "dimension": "Honesty when blocking",
      "score": 5,
      "justification": "Brilliantly handles cases where tests pass immediately (Cycle 4, 6, 8) by acknowledging them as regression guards and using mutation testing to prove they work."
    }
  ],
  "scores_B": [
    {
      "dimension": "Discipline enforcement",
      "score": 3,
      "justification": "Capped due to task compliance; while it talks heavily about rules and 'quality gates', it treats discipline as a rigid state machine rather than mentoring the developer."
    },
    {
      "dimension": "RED-GREEN-REFACTOR cycle visibility",
      "score": 3,
      "justification": "Capped due to task compliance; it only fully demonstrates Cycle 1 and compresses/sketches Cycles 2-6."
    },
    {
      "dimension": "Test quality",
      "score": 3,
      "justification": "Capped due to task compliance; the tests shown are adequate but buried under excessive meta-commentary about the prompt's internal phases."
    },
    {
      "dimension": "Failure-mode coverage",
      "score": 3,
      "justification": "Capped due to task compliance; it awkwardly leaks its own system instructions ('the persona's rationalizations table is designed to catch') instead of addressing the developer naturally."
    },
    {
      "dimension": "Honesty when blocking",
      "score": 3,
      "justification": "Capped due to task compliance; it identifies the 'passing test' issue but breaks character to explain its own internal logic ('The honest thing to do: tell the user...')."
    }
  ],
  "winner": "A",
  "winner_reasoning": "Output A is a masterclass in TDD mentoring, naturally guiding the user through the complete implementation while introducing advanced concepts like mutation testing. Output B fails to complete the task by stopping after Cycle 1, and its response is severely bloated by leaking its internal prompt phases and instructions.",
  "provenance_prediction": {
    "A_is": "handwritten",
    "B_is": "generated"
  },
  "provenance_reasoning": "Output A demonstrates deep, nuanced domain expertise (using code mutation to validate regression boundaries) that screams of human refinement by a seasoned TDD practitioner. Output B exhibits classic generated artifacts: it robotically echoes structural prompt instructions ('Phase 1 exit condition met', 'persona's rationalizations table') instead of adopting the persona."
}
```


### gemini — obra-tdd/03-refactor-under-pressure

```json
{
  "task_compliance": {
    "A": true,
    "B": true,
    "notes": "Both outputs fully comply with the task by explaining how to apply TDD principles to a legacy refactor with partial coverage, and both explicitly address the honesty constraint regarding pure TDD vs. characterization testing."
  },
  "verbosity_penalty_applied": false,
  "scores_A": [
    {
      "dimension": "Discipline enforcement",
      "score": 5,
      "justification": "Explicitly stops the user before any refactoring begins to mandate characterization tests, directly rejecting the path of least resistance."
    },
    {
      "dimension": "RED-GREEN-REFACTOR cycle visibility",
      "score": 5,
      "justification": "Brilliantly redefines the cycle for characterization (where 'Red' is failing to match current behavior and 'Green' is pinning it) and separates it from the Refactor cycle."
    },
    {
      "dimension": "Test quality",
      "score": 4,
      "justification": "Provides a concrete, behavioral characterization test example that explicitly checks observable state (inventory quantity) rather than just mocks."
    },
    {
      "dimension": "Failure-mode coverage",
      "score": 5,
      "justification": "Names four specific rationalizations (e.g., 'EOD is tight', 'I see the structure in my head') and dismantles each with tailored counter-arguments."
    },
    {
      "dimension": "Honesty when blocking",
      "score": 5,
      "justification": "Directly answers the prompt's challenge by stating 'TDD applies, but not in the form people usually mean' and correctly identifying the need for characterization over pure TDD."
    }
  ],
  "scores_B": [
    {
      "dimension": "Discipline enforcement",
      "score": 5,
      "justification": "Firmly rejects the teammates' advice and insists that the missing 40% coverage must be pinned before any structural changes occur."
    },
    {
      "dimension": "RED-GREEN-REFACTOR cycle visibility",
      "score": 4,
      "justification": "Walks through the Red/Green phases for characterization and explicitly breaks down the extraction loop, though slightly less formally structured than A."
    },
    {
      "dimension": "Test quality",
      "score": 4,
      "justification": "Demonstrates a solid characterization test using fake objects and specific assertions on the resulting state."
    },
    {
      "dimension": "Failure-mode coverage",
      "score": 4,
      "justification": "Lists specific red flags at the end, but they are slightly less integrated into the narrative flow of overcoming the EOD pressure compared to A."
    },
    {
      "dimension": "Honesty when blocking",
      "score": 5,
      "justification": "Explicitly acknowledges that mechanical extractions and characterization tests are not pure TDD, providing a clear 'Honest accounting' table."
    }
  ],
  "winner": "A",
  "winner_reasoning": "Both outputs are exceptional, but A wins for its structural brilliance. A's insight that characterization testing has an inverted success condition for the 'Green' phase, and its agentic framing ('Exit condition', 'Next behavior?'), makes it a far more rigorous and practical walkthrough for a developer under pressure.",
  "provenance_prediction": {
    "A_is": "handwritten",
    "B_is": "generated"
  },
  "provenance_reasoning": "Output B repeatedly breaks the fourth wall by quoting its own instructions ('The TDD skill says...', 'From the skill...'), which is a classic hallmark of a freshly generated prompt reacting to its system instructions. Output A acts like a mature, hand-tuned agent executing a specific, interactive workflow (Phase 0 routing, prompting for the next step at the end)."
}
```

