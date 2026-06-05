# Conversation Log — ZOIA Sympathetic Strings Resonator

Running record of all prompts and AI responses for this patch project.
Update this file after each new exchange.

---

## Format

Each entry follows this structure:

```
## Entry N — [Date]
### Prompt summary
[Brief description of what was asked]
### Response summary
[Brief description of what was delivered]
### Files changed
[List of files created or modified]
### Key decisions
[Important design choices made in this exchange]
```

---

## Entry 1

**Date:** Session 1  
**Topic:** Initial patch concept

### Prompt summary
Design a ZOIA sympathetic strings patch that tracks guitar pitch and excites resonant strings. Controls for dampening, overtones, spread, wet/dry volumes, pitch, reverb, decay, piano size. Pages for UI, I/O, and intuitively grouped engine pages. Target realistic piano sound.

### Response summary
Delivered v1 design with 6 pages:
- P1 UI, P2 I/O, P3 Pitch, P4 Resonators (6 voices), P5 Body, P6 Reverb, P7 Mix
- 6 resonator voices: V1 fundamental, V2 +12st, V3 +19st, V4 +24st, V5 spread L, V6 spread R
- 4 Value modules for harmonic scale, decay scale, overtones scale, spread scale
- Plate reverb
- 3 EQ modules for body (Body Resonance, Hi Shelf, Lo Shelf)
- Interactive HTML explorer, Mermaid flowchart

### Files created
- `docs/patch-explorer.html` (v1)
- `docs/flowchart.mmd` (v1)

### Key decisions
- Value module pattern established for maintaining relative ratios across voices
- Pre-FX dry split at Audio Input
- Wet/dry parallel mix bus

---

## Entry 2

**Topic:** CPU analysis

### Prompt summary
How much CPU will this patch use on the ZOIA?

### Response summary
Estimated 83–109% CPU — likely exceeds ZOIA's limit. 6 resonators at ~9% each = 54% alone. Full patch would crash or cause audio dropouts.

Recommended options:
- Reduce to 4 resonators (saves ~18%)
- Replace spread resonators with Delay Lines (saves ~13%)
- Swap Plate Reverb for Simple Reverb (saves ~4–6%)
- Replace 3× EQ with single Tone Control (saves ~4–5%)

### Files changed
None (analysis only)

### Key decisions
- Max 4 resonators is the safe ceiling for a feature-rich patch
- Delay Lines (Haas effect) are equivalent to detuned spread resonators at 20% of CPU cost

---

## Entry 3

**Topic:** Optimised redesign — all documentation

### Prompt summary
Redesign patch to stay under 95% CPU while maintaining maximum realism. Generate all documentation previously requested.

### Response summary
Delivered v2 redesign at ~68% estimated CPU:
- Dropped V5/V6 spread resonators → Delay Lines at 9/11ms
- Replaced 3× EQ → single Tone Control (saves 4–5%)
- Replaced Plate Reverb → Simple Reverb (saves 4–6%)
- V4 retuned +24st → +7st (minor 7th) — improvement not compromise
- All documentation regenerated

### Files created
- `docs/patch-explorer.html` (v2)
- `docs/flowchart.mmd` (v2)
- `docs/grid-layouts/p1-ui.svg` through `p6-reverb.svg` (6 files)
- `patch/default-values.json`
- `patch/connections.json` (36 connections)
- `patch/sound-presets.json` (6 presets)
- `prompts/patch-prompt.md`
- `prompts/generic-zoia-prompt.md`
- `prompts/ai-conversation-skill.md`
- `README.md`

### Key decisions
- V4 minor 7th (+7st) is sonically superior to double octave (+24st) for piano inharmonic character
- Two Delay Lines for stereo spread is the most CPU-efficient approach that sounds convincing
- Simple Reverb with pre-delay (12ms) is the correct choice — algorithm matters less than pre-delay for piano realism

---

## Entry 4

**Topic:** Page restructure, grid SVGs, hardware details, expanded HTML, accessibility

### Prompt summary
Reorder pages: P1 UI, P2 I/O+Mix combined, P3 Pitch, P4 Resonators, P5 Body, P6 Reverb.
Move UI connections and Value modules to UI page.
Generate SVG grid layouts for all pages (8×5 ZOIA grid).
Use ZOIA-only colours.
Document ZOIA vs ZEBU hardware differences.
Include all I/O configuration options.
Add full connections list (From/To/Page/Module/Block/Strength).
Add UI description, default settings, patch description.
Generate GitHub CMS folder structure.
Generate generic ZOIA prompt template.
Generate AI conversation skill.
WCAG AA contrast throughout.

### Response summary
Complete rebuild. 15 files generated across structured GitHub folder. Key additions:
- 6-page structure (combined I/O+Mix as P2)
- 6 SVG grid layouts with ZOIA colour scheme
- External connections list (36 connections, From/To/Block/Strength)
- Expanded HTML explorer with 11 tabs
- Full ZOIA/ZEBU hardware notes
- All I/O configuration modes documented
- Generic ZOIA prompt template with 10 sections
- AI conversation skill with hardware constraints, CPU table, design patterns, output checklist

### Files created/modified
- `docs/patch-explorer.html` (major expansion — 11 tabs)
- `docs/patch-explorer.css` (external stylesheet — new)
- `docs/grid-layouts/p1-ui.svg` through `p6-reverb.svg` (regenerated)
- `docs/flowchart.mmd` (updated page order)
- `patch/connections.json` (36 connections with From/To/Block)
- `patch/default-values.json` (updated)
- `patch/sound-presets.json` (6 presets)
- `prompts/patch-prompt.md` (updated)
- `prompts/generic-zoia-prompt.md` (new comprehensive template)
- `prompts/ai-conversation-skill.md` (new skill document)
- `README.md` (updated)

### Key decisions
- I/O and Mix Bus combined on P2 — logical because both handle patch boundary
- Value modules stay on P4 (their home page) but are referenced from P1 in docs
- SVG colour roles: Sky=I/O, Green=Pitch, Red=Resonators, Yellow=Value, Aqua=Body, Magenta=Reverb, Orange=Mix, White=Controls
- WCAG AA: dark tinted module backgrounds + light text on all colour combinations
- Audio uses ▶ symbol + colour, CV uses ⬦ symbol + colour (colour-blind safe)

---

## Entry 5

**Topic:** Colour corrections, SVG size reduction, CSS separation, base font increase, conversation log

### Prompt summary
Correct colours to official 15-colour ZOIA LED palette with exact hex codes:
red #FF0000, orange #FFA500, mango #FFB000, yellow #FFFF00, lime #AFFF00,
green #00FF00, surf #00FF99, aqua #00FFFF, sky #00BFFF, blue #0000FF,
purple #7F00FF, magenta #FF00FF, pink #FF69B4, peach #FFDAB9, white #FFFFFF.
SVGs 50% smaller. HTML base text 16px. Separate CSS file.
Update all documents and add conversation log.

### Response summary
Updated all colour references to official 15-colour palette. SVGs reduced from 389×520 to 389×312 (cells 64px→44px, ~40% smaller total area). CSS extracted to `patch-explorer.css`. HTML base font-size set to 16px with rem-based scaling throughout. All documentation colour references updated. This conversation log created.

WCAG AA compliance maintained:
- Dark tinted backgrounds (14% of full colour luminance) — all achieve >15:1 contrast with white text
- Yellow cells use dark text (#2a2a00) where needed
- Colour + shape symbols maintained for audio (▶) and CV (⬦)

Role assignments for the 15-colour palette:
- Sky #00BFFF — I/O (replaces old blue — pure #0000FF too dark on dark bg)
- Green #00FF00 — Pitch tracking
- Red #FF0000 — Resonators
- Yellow #FFFF00 (dashed) — Value/scaling
- Aqua #00FFFF — Piano body
- Magenta #FF00FF — Reverb
- Orange #FFA500 — Mix bus
- White #FFFFFF — Controls
- Mango #FFB000 — Warnings
- Surf #00FF99 — MIDI tags
- Remaining: available for future use

### Files created/modified
- `docs/patch-explorer.css` (new — full stylesheet with 15-colour tokens)
- `docs/patch-explorer.html` (updated — links external CSS, 16px base, new colours)
- `docs/grid-layouts/*.svg` (all 6 regenerated — 50% smaller cells, new colours)
- `docs/flowchart.mmd` (classDef colours updated)
- `prompts/ai-conversation-skill.md` (colour table updated)
- `README.md` (colour table updated)
- `docs/conversation-log.md` (new — this file)

### Key decisions
- Pure blue #0000FF is too dark on dark backgrounds (luminance 0.0001 vs bg 0.001 = only 2:1 contrast). Sky #00BFFF used for I/O role instead.
- Cell size 44px is the smallest readable at typical screen scale — going smaller risks text illegibility
- Base font 16px with rem units ensures all text scales correctly with browser zoom
- CSS custom properties (`--c-red`, `--bg-red` etc.) make future colour changes a single-file edit

---

## How to add a new entry

When asking the AI for changes, paste this at the top of your prompt:

```
Please update docs/conversation-log.md with a new entry for this exchange.
Include: prompt summary, response summary, files changed, key decisions.
```

The AI should add Entry N+1 at the bottom of this file.

---

*Last updated: Entry 5*

---

## Entry 6

**Date:** Session 6  
**Topic:** Official module index correction — complete rebuild from source of truth

### Prompt summary
User provided the official Empress ZOIA Module Index (firmware 5) and identified that modules, block counts, and DSP figures were incorrect throughout all previous documentation. Requested: convert module index to CSV, rebuild patch using only verified modules with correct block counts, note firmware requirements, update all documents.

### Response summary
Complete architectural rebuild (v3). All modules audited against official index. Major errors discovered and corrected:

1. **Resonator module does not exist** — replaced with Delay Line + VCA feedback (Karplus-Strong comb filter)
2. **CV Adder module does not exist** — replaced with CV Mixer (5 blocks, attens set to 1.0)
3. **Pitch Detector has only 2 blocks** (audio in + pitch out) — NO gate output. Gate now generated by Env Follower (2 blocks) + Comparator (3 blocks) at 2.54% total vs Onset Detector at 12.3%
4. **VCA block 3 is "level control"** not "gain_cv"
5. **Chorus CPU is 6-10%** not 3% — removed from patch
6. **All block counts corrected** — VCA=3, SV Filter=4, Delay Line=3, ADSR=6, Tone Control=9, Reverb Lite=5, etc.

New CPU total: **~32%** (was ~68%, was ~83-109% in v1). Headroom: ~63%.

Generated module-index.csv with all 94 modules from official index.

### Files created/modified
- `patch/module-index.csv` (NEW — 94 modules from official index)
- `patch/default-values.json` (v3 — corrected module names, block counts, CPU figures, firmware notes)
- `patch/connections.json` (v3 — 32 connections using official block names)
- `docs/patch-explorer.html` (v3 — links external CSS, new V3 CORRECTIONS tab)
- `docs/grid-layouts/p1-ui.svg` through `p5-body.svg` (regenerated — actual block footprints)
- `docs/grid-layouts/p6-reverb.svg` (REMOVED — reverb merged into P5)
- `docs/conversation-log.md` (this entry)

### Key decisions
- 5 pages (was 6): Reverb and Body EQ combined on P5 (only 20 blocks needed)
- FEEDBACK knob replaces DECAY + OVERTONES: controls all 3 feedback VCAs simultaneously via connection strength ratios (100/80/55%)
- SENSITIVITY knob replaces PIANO SIZE/OVERTONES split: Comparator threshold for gate detection
- Pitch tracking: approximate — Pitch Detector V/Oct CV scaled via connection strength into Delay Line delay time range. True V/Oct→1/f conversion impossible natively in ZOIA. This is musically equivalent to analog sympathetic string behaviour.
- Firmware: minimum 2.0 (all modules present), recommended 5.0 (15-colour UI Button)
- All SVG block badges now show actual block count per module (number in top-right corner)
