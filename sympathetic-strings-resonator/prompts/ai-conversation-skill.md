# AI Conversation Skill: ZOIA / ZEBU Patch Designer

**Skill version:** 2.0
**Trigger:** Use this skill when asked to design, document, or modify a ZOIA or ZEBU patch.

---

## Skill Purpose

This skill guides an AI assistant through a complete ZOIA/ZEBU patch design
and documentation workflow. It encodes verified hardware constraints, module
facts, design patterns, CPU budget rules, and documentation standards developed
through iterative real-world patch building.

**Load this skill before starting any ZOIA/ZEBU patch work.**

---

## Step 1 — Elicit Requirements (ask before building anything)

Confirm all of the following before generating any design. If missing, ask:

1. **Effect goal** — what should it sound like? (Reference: hardware, plugin, track)
2. **Hardware** — ZOIA, ZEBU, or both?
3. **Signal path** — mono in / stereo out? Other?
4. **Controls** — what's on the UI page? How many knobs/stomps? MIDI needed?
5. **CPU ceiling** — maximum acceptable % (recommend targeting ≤75%)
6. **Output format** — which deliverables? (HTML, flowchart, JSON, markdown)

Do not proceed until effect goal and hardware target are confirmed.

---

## Step 2 — Verified Hardware Constraints

### ZOIA / ZEBU grid
- **8 columns × 5 rows = 40 blocks per page**
- Modules occupy their official block count (see table below) — not always 1
- A module spanning N blocks uses N consecutive grid positions in its row
- Never overflow a page — always verify total blocks fit ≤ 40 before finalising
- Leave empty cells between functional groups for navigation clarity

### ZOIA hardware (stompbox)
- 3 stomp switches (left/middle/right) · configurable latching or momentary
- 2 auxiliary buttons
- 1 control port: expression pedal or external CV in (set in Config Menu)
- MIDI in/out via 3.5mm TRS (included dongles)
- 2 inputs: left = TS unbalanced, right = TRS balanced (can use as TS)
- 2 outputs: left = TS, right = TRS
- Up to 64 patches on SD card (FAT32 format only)
- Audio: 48kHz · 24-bit ADC/DAC · 32-bit internal processing
- Latency: 3.21ms bypassed · +1.33ms per audio module in series

### ZEBU / Euroburo (Eurorack module)
- **No stomp switches** — must map stomp functions to CV inputs or aux buttons
- 2 auxiliary buttons (same as ZOIA)
- 4 CV inputs (±5V or 0–5V, configurable)
- 4 CV outputs (±5V)
- Same audio I/O, grid, and module set as ZOIA
- Recommended CV mapping: CV In 1 = most-used expression param, etc.

### Audio I/O configurations (ZOIA supports all of these)
- Mono in → mono out
- Mono in → stereo out ← most common for effects
- Stereo in → stereo out
- Mono in → dry/wet split outputs (dry to amp, wet to PA)
- Mono in → stereo with aux send/return
- Parallel mono → parallel mono
- Self-generating (no input required)
- Sample playback from SD card (FAT32, `/samples/`, WAV 48kHz)

### ZOIA LED colour palette (15 official colours, firmware 5+)

| Hex | Name | Recommended role |
|---|---|---|
| `#00BFFF` | Sky | I/O modules (Audio In/Out) |
| `#00FF00` | Green | Pitch tracking, analysis |
| `#FF0000` | Red | Resonators, core audio processing |
| `#FFFF00` | Yellow | Value / scaling modules (dashed border) |
| `#00FFFF` | Aqua | Body EQ, shaping |
| `#FF00FF` | Magenta | Reverb, time-based effects |
| `#FFA500` | Orange | Mix bus (VCAs, mixers) |
| `#FFFFFF` | White | UI controls (knobs, stomps) |
| `#FFB000` | Mango | Warnings, critical annotations |
| `#00FF99` | Surf | MIDI tags |
| `#AFFF00` | Lime | Secondary positive status |
| `#FF69B4` | Pink | Stomp switch references |
| `#7F00FF` | Purple | CV accent highlights |
| `#FFDAB9` | Peach | Label pixels, annotations |
| `#0000FF` | Blue | Available — avoid as primary text (too dark on dark bg) |

**WCAG contrast note:** Pure blue `#0000FF` has near-zero luminance contrast on
dark backgrounds. Use Sky `#00BFFF` for the I/O role instead.

---

## Step 3 — Verified Module Index

All DSP figures from official Empress Module Index, firmware 5.
Block counts are minimum blocks unless stereo/optional blocks are enabled.

### Interface modules
| Module | Blocks | DSP | Key blocks |
|---|---|---|---|
| Audio Input | 2 | 0.3% | pedal input L (1), R (2) |
| Audio Output | 2–3 | 1.0% | pedal output L (1), R (2), gain* (3) |
| Stompswitch | 1 | 0.1% | cv output (1) |
| Pushbutton | 1 | 0.02% | switch (1) |
| UI Button | 1–2 | 0.04% | in (1), cv output* (2) |
| Pixel | 1 | 0.01% | cv/audio in (1) |
| Midi CC In | 1 | 0.1% | cc value (1) |
| Midi Notes In | 2–4 | 0.1% | note out (1), gate out (2) |
| Midi Clock In | 1–4 | 0.1% | quarter out (1) |
| Cport Exp/CV In | 1 | 0.1% | cv output (1) |
| CV In (ZEBU) | 1 | 0.1% | CV In (1) |
| CV Out (ZEBU) | 1 | 0.2% | CV Out (1) |

### Audio modules
| Module | Blocks | DSP | Key blocks |
|---|---|---|---|
| VCA | 3–5 | 0.3% | audio in 1 (1), **level control** (3), audio out 1 (4) |
| Oscillator | 4 | 6.0% | frequency (1), audio out (4) |
| SV Filter | 4–6 | 1.0% | audio in (1), frequency (2), resonance (3), lowpass out (4) |
| Multi-Filter | 4–5 | 0.8% | audio in (1), frequency (3), q (4), audio out (5) |
| Delay Line | 3–4 | 2.0% | audio in (1), delay time (2), audio out (3) |
| Audio Balance | 4 or 7 | 0.8% | in1 (1), in2 (2), mix (3), out1 (4) · stereo: 7 blocks |
| Audio Mixer | 9–34 | 3–20% | varies by channel count |
| Audio Panner | 4–5 | 1.0% | in (1), pan (3), out1 (4), out2 (5) |
| Stereo Spread | 4–5 | 1.5% | audio in (1), delay time (2), out1 (3), out2 (4) |
| Pitch Shifter | 3 | 15.1% | audio in (1), pitch shift (2), audio out (3) |
| Looper | 8–9 | 0.3% | audio in (1), record (2), audio out (9) |
| Granular | 9–10 | 4–30% | audio in (1), grain size (3), audio out (9) |
| Noise | 1 | 0.4% | audio out (1) |

### Effects modules
| Module | Blocks | DSP | Notes |
|---|---|---|---|
| Tone Control | 9–10 | 2.2% | aud in L (1), low shelf (3), mid gain (4), mid freq (5), high shelf (8), out L (9) |
| Reverb Lite | 5–6 | 6–7% | input L (1), decay (3), mix (4), out L (5), out R* (6) |
| Plate Reverb | 8 | 16.7% | input L (1), input R (2), decay (3), mix (6), out L (7), out R (8) |
| Hall Reverb | 8 | 17.0% | same as Plate |
| Room Reverb | 8 | 17.0% | same as Plate |
| Reverb (Ghostverb) | 7–8 | 18–31% | audio in (1), decay (3), mix (6), out (7) |
| Delay w/Mod | 8–9 | 7–15% | in (1), delay time (3), feedback (4), mix (7), out (8) |
| Chorus | 7–8 | **6–10%** | in (1), control in (3), width (4), mix (6), out (7) |
| Flanger | 8–9 | 4.7–10% | in (1), control in (3), mix (7), out (8) |
| Phaser | 7–8 | 5–10% | in (1), control in (3), mix (6), out (7) |
| Tremolo | 5–6 | 1–2% | in (1), control in (3), depth (4), out (5) |
| Vibrato | 5–6 | 3.2–5% | in (1), control in (3), width (4), out (5) |
| Compressor | 4–9 | 2.4% | in (1), threshold (3), out (8) |
| Gate | 5–8 | 2.8% | in (1), threshold (3), out (7) |
| OD & Distortion | 4 | 14.2% | in (1), input gain (2), output gain (3), out (4) |
| Fuzz | 4 | 14.1% | in (1), input gain (2), output gain (3), out (4) |
| Cabinet Sim | 3–4 | 7.0% | in (1), out (3) |
| Ring Modulator | 4–5 | 3–7.6% | in (1), frequency (2), mix (4), out (5) |
| Diffuser | 6 | 1.7% | in (1), gain (2), size (3), out (6) |

### Analysis modules
| Module | Blocks | DSP | Notes |
|---|---|---|---|
| Pitch Detector | **2** | 2.3% | audio in (1), **pitch out only — NO gate** (2) |
| Env Follower | 2–4 | 2.5% | audio in (1), CV output (2) |
| Onset Detector | 2–3 | **12.3%** | expensive — use Env Follower + Comparator instead |

### Control modules
| Module | Blocks | DSP | Key blocks |
|---|---|---|---|
| Value | 2 | 0.15% | value/cv in (1), CV output (2) |
| ADSR | 6–10 | 0.07% | cv input (1), attack (4), decay (6), sustain (7), release (9), cv output (10) |
| Sample and Hold | 3 | 0.1% | CV input (1), trigger (2), CV output (3) |
| CV Mixer | 5–17 | 0.30% | cv in 1 (1), cv in 2 (2), atten 1 (3), atten 2 (4), cv output (5) |
| LFO | 4–5 | 0.3% | frequency (1), output (5) |
| Sequencer | 7–42 | 2.0% | steps, gate in, outputs |
| Comparator | 3 | 0.04% | CV positive (1), CV negative (2), CV output (3) |
| CV Rectify | 2 | 0.07% | CV input (1), CV output (2) |
| CV Invert | 2 | 0.02% | CV input (1), CV output (2) |
| CV Filter | 3–4 | 0.1% | CV input (1), time constant (2), CV output (3) |
| Slew Limiter | 3–4 | 0.2% | CV input (1), slew rate (2), CV output (3) |
| Quantizer | 2–4 | 1.0% | CV input (1), CV output (4) |
| Multiplier | 3–9 | 0.2% | CV input 1 (1), CV input 2 (2), CV output (3) |
| Clock Divider | 4–5 | 0.14% | input (1), CV output (5) |
| Random | 2 | 0.1% | trigger in* (1), CV output (2) |
| Trigger | 2 | 0.10% | CV input (1), CV output (2) |
| CV Flip Flop | 2 | 0.2% | CV input (1), CV output (2) |
| Steps | 3 | 0.7% | CV input (1), quant steps (2), CV output (3) |
| Tap to CV | 2–4 | 0.12% | tap input (1), output (4) |
| CV Delay | 3 | 1.5% | CV input (1), delay time (2), CV output (3) |

---

## Step 4 — Modules That Do NOT Exist (common AI errors)

| AI often generates | Correct ZOIA approach |
|---|---|
| "Resonator" module | Delay Line (3bl) + VCA feedback loop = comb filter |
| "CV Adder" module | CV Mixer (5bl) with both attenuators set to 1.0 |
| Pitch Detector gate output | Env Follower → Comparator generates gate (saves 9.76% vs Onset Detector) |
| VCA "gain_cv" block | VCA block 3 is **"level control"** |
| "Simple Reverb" | Official name is **"Reverb Lite"** |
| Chorus at 3% CPU | Chorus costs **6–10%** — remove if CPU-constrained |
| Filter LPF as standalone | Use **SV Filter** (lowpass output = block 4) or Multi-Filter |
| Audio Mixer as 2-block module | Audio Mixer minimum is 9 blocks for 2 stereo channels |

---

## Step 5 — CPU Budget Rules

**Target: ≤75% estimated. Design ceiling: 95%. CPU spikes during transients.**

### Key CPU facts
- Onset Detector (12.3%) → replace with Env Follower (2.5%) + Comparator (0.04%) = saves 9.76%
- Chorus (6–10%) → remove; use Audio Balance stereo (0.8%) + Haas delays for width
- Plate/Hall/Room Reverb (16.7–17%) → use Reverb Lite (6–7%) instead
- Granular (4–30%) → CPU highly variable; prototype and check ZOIA display
- ADSR costs only 0.07% — very cheap for what it does
- Value module costs 0.15% — use freely for parameter scaling
- Stompswitch costs 0.1% — negligible

### Build incrementally
Always add modules in logical groups and check ZOIA's on-screen CPU display
after each group. Stop adding if CPU exceeds 80% before the design is complete.

---

## Step 6 — Design Patterns

### Pre-FX dry split (always do this)
Split dry signal from Audio Input **before any processing** → Dry VCA.
This ensures bypass is click-free and dry always passes unaffected.

### Wet/dry mix bus (always do this)
```
Wet chain out → VCA [WET VCA] (level control ← WET VOL knob)
Dry signal   → VCA [DRY VCA] (level control ← DRY VOL knob)
Both VCAs    → Audio Balance (or Audio Mixer) → Audio Output
```
Never use reverb/delay internal mix for the dry signal.
Always route 100% wet into a send VCA.

### Value module fan-out pattern
When multiple modules need the same parameter at different ratios:
```
Knob [FEEDBACK] → Value [FEEDBACK]
  block 2 CV output → VCA V1 level control at 100% connection strength
  block 2 CV output → VCA V2 level control at  80% connection strength
  block 2 CV output → VCA V3 level control at  55% connection strength
```
One Value module provides proportional CV to multiple destinations via
connection strength — no additional modules required.

### Gate generation without Onset Detector
```
Audio Input → Env Follower [GATE DETECT]
  block 2 CV output → Comparator [GATE GEN] CV positive input (block 1)
Knob/Value [SENSITIVITY] → Comparator CV negative input (block 2) [threshold]
Comparator block 3 CV output → S&H trigger + ADSR cv input
```
Total cost: 2.54% vs Onset Detector 12.3%. Saves 9.76%.

### Comb filter resonator (replaces non-existent Resonator module)
```
Delay Line [V1]: audio in ← exciter signal
                 delay time ← pitch CV (scaled via connection strength)
                 audio out → VCA [V1 FEEDBACK] audio in 1
                 audio out → mix path
VCA [V1 FEEDBACK]: level control ← ADSR + FEEDBACK knob
                   audio out 1 → Delay Line audio in (feedback loop, ~75%)
```
FEEDBACK knob controls VCA level control = resonance sustain.
Higher feedback = longer decay. At ~95% may self-oscillate.

### Haas stereo width (CPU-efficient alternative to stereo resonators)
Two Delay Lines at 9ms (L) and 11ms (R), 0% feedback, panned hard L/R.
Costs ~4% total vs ~18% for two additional resonator voices.
R = L + 2ms to prevent symmetric comb filter cancellation.

### CV Mixer as CV summer (replaces non-existent CV Adder)
```
CV Mixer [PITCH OFFSET]:
  atten 1 = 1.0, atten 2 = 1.0
  cv in 1 ← Pitch Detector pitch out
  cv in 2 ← Knob [PITCH transpose]
  cv output → Sample and Hold
```

---

## Step 7 — Page Layout Rules

### Page order
1. **P1 — UI Controls** — all Value knobs + Stompswitches. Performers never leave this page.
2. **P2 — I/O + Mix Bus** — Audio Input, Audio Output, Wet/Dry VCAs, Audio Balance
3. **P3 — Analysis** — Pitch Detector, Env Follower, Comparator, S&H, ADSR, CV processing
4. **P4 — Core Processing** — main audio engine (resonators, delays, filters)
5. **P5 — Shaping + Space** — EQ, body, reverb

### Grid placement
- Modules span left-to-right following signal flow where possible
- Signal enters from left side of page, exits right
- Empty cells separate functional groups — leave gaps, not walls of modules
- Wider modules (Tone Control = 9 blocks) go on their own row
- ADSR (6 blocks) fits one row with 2 empty cells to spare

### Colour assignment
Match module colours to the 15-colour palette roles in Step 2.
Use the same colours consistently across HTML grids, Mermaid diagrams,
and any other documentation — single source of truth.

---

## Step 8 — HTML Documentation Standards

### Two variants required
**Inline** (`docs/inline/patch-explorer.html`):
- All CSS in `<style>` block in `<head>`
- Grid layouts as inline HTML (CSS Grid, not SVG)
- Zero external dependencies — works on `file://` protocol
- Open directly in any browser without a server

**Linked** (`docs/linked/` folder):
- `<link rel="stylesheet" href="assets/patch-explorer.css">`
- Grid layouts as inline HTML (same CSS Grid approach)
- Must be served (GitHub Pages, local server) — CSS won't load on `file://`
- Folder structure: `patch-explorer.html` + `assets/` must stay together

### CSS Grid page layouts (not SVGs)
Page grids are rendered as native CSS Grid HTML, not SVG files or img tags:
```html
<div class="zoia-grid">  <!-- display:grid; grid-template-columns: repeat(8,1fr); grid-template-rows: repeat(5,1fr) -->
  <div class="zg-mod zg-red" style="grid-column:1/span 3; grid-row:1/span 1;">
    <span class="zg-name">DELAY V1</span>
    <span class="zg-sub">FUNDAMENTAL</span>
    <span class="zg-badge">3</span>  <!-- official block count -->
  </div>
  <div class="zg-empty" style="grid-column:7; grid-row:1" aria-hidden="true"></div>
  ...
</div>
```
- `aspect-ratio: 8/5` maintains grid proportions at any width
- `max-height: 400px` prevents oversized grids
- Module colours use same CSS custom properties as module cards
- Block count badge on each module cell
- Empty cells fill unoccupied positions (aria-hidden)

### SVG files
SVG files in `docs/grid-layouts/` are kept as standalone exports
(for sharing, embedding in other tools, etc.) but are NOT used in the HTML.

### Accessibility requirements (WCAG AAA 7:1 on all text)
- All text must achieve ≥7:1 contrast ratio
- `--text-muted: #b4b4b4` (9.53:1 on `#0a0a0f`) replaces all `#666`/`#555`/`#444`
- Red module text: `--txt-red-name: #ffcccc` (13.78:1), `--txt-red-zoia: #ff8080` (8.07:1)
- Magenta module text: `--txt-mag-name: #ffccff` (14.0:1), `--txt-mag-zoia: #ff88ff` (9.32:1)
- Red nav active: `--txt-red-nav: #ff8080` (7.74:1 on `#111118`)
- Audio connections: ▶ symbol + sky colour
- CV connections: ⬦ symbol + yellow colour
- Never rely on colour alone — always pair with a shape symbol
- `role="img"` + `aria-label` on all grid containers
- `aria-label` on all interactive buttons and controls
- Skip link to main content
- Keyboard navigation on all tabs and preset cards

---

## Step 9 — GitHub CMS File Structure

```
patch-name/
├── README.md                       quick start · page summary · colour key
├── patch/
│   ├── module-index.csv            94 verified modules (Empress firmware 5)
│   ├── default-values.json         all parameter defaults, ranges, MIDI CCs
│   ├── connections.json            full From/To/Block/Strength connection list
│   └── sound-presets.json          named presets with all parameter values
├── docs/
│   ├── conversation-log.md         running record of all prompt/response exchanges
│   ├── flowchart.mmd               Mermaid signal flow diagram
│   ├── grid-layouts/               standalone SVG exports (not used in HTML)
│   │   ├── p1-ui.svg
│   │   ├── p2-io-mix.svg
│   │   └── ...
│   ├── inline/
│   │   └── patch-explorer.html     self-contained · inline CSS + inline grids
│   └── linked/
│       ├── patch-explorer.html     links to assets/
│       └── assets/
│           └── patch-explorer.css  shared stylesheet
├── prompts/
│   ├── patch-prompt.md             build instructions for this specific patch
│   ├── generic-zoia-prompt.md      reusable template for new patch requests
│   └── ai-conversation-skill.md   this file
└── .github/
    └── CODEOWNERS
```

---

## Step 10 — Conversation Log

Always maintain `docs/conversation-log.md`.
Each entry records: prompt summary, response summary, files changed, key decisions.

Add a new entry at the start of each session using this format:
```markdown
## Entry N
**Date:** [session date]
**Topic:** [one-line summary]

### Prompt summary
[what was asked]

### Response summary
[what was delivered]

### Files changed
[list]

### Key decisions
[design choices made and why]
```

---

## Step 11 — Common Mistakes to Avoid

| Mistake | Correct approach |
|---|---|
| Using "Resonator" module | Build from Delay Line + VCA feedback loop |
| Using "CV Adder" module | Use CV Mixer with attenuators set to 1.0 |
| Connecting Pitch Detector "gate_out" | Does not exist. Use Env Follower + Comparator. |
| Calling VCA block 3 "gain_cv" | Official name is "level control" |
| Using "Simple Reverb" | Official name is "Reverb Lite" |
| Chorus for static width at 3% CPU | Chorus costs 6–10%. Use Audio Balance + Haas delays. |
| Using Onset Detector for gate | 12.3% CPU. Use Env Follower + Comparator (2.54%). |
| Assuming 1 block per module | Each module has its own block count (see Step 3 table) |
| Designing at 90%+ CPU | Spike headroom required. Target ≤75%. |
| SVG files for HTML grid layouts | Use CSS Grid HTML — matches document font/colours exactly |
| max-width on grid SVG/img | Remove max-width or set to 100% — stale pixel values cause scaling |
| External CSS for local HTML use | Inline all CSS in `<style>` for `file://` compatibility |
| SVG without explicit width/height | Add `width="W" height="H"` attributes — viewBox alone fails in hidden parents |

---

## Step 12 — Output Checklist

Before delivering, verify all of the following:

**Architecture**
- [ ] All module names from official Empress Module Index only
- [ ] Every module's block count is correct (see Step 3 table)
- [ ] All pages fit within 40 blocks (8×5)
- [ ] Pre-FX dry split exists at Audio Input
- [ ] Wet/dry VCAs both present, feeding Audio Balance / Mixer
- [ ] Reverb/Delay is 100% wet (dry handled by Dry VCA path)
- [ ] Gate generation uses Env Follower + Comparator (not Onset Detector)
- [ ] CPU estimate ≤75% with at least 20% headroom
- [ ] Stomp switch alternatives documented for ZEBU

**Connections**
- [ ] Every connection has: From Page, From Module, From Block (official name),
  To Page, To Module, To Block (official name), Strength %
- [ ] Audio connections use official block names (e.g. "level control" not "gain_cv")

**HTML**
- [ ] Inline variant: all CSS in `<style>`, all grids as CSS Grid HTML
- [ ] Linked variant: CSS in external file, grids as CSS Grid HTML
- [ ] All CSS Grid page layouts use `aspect-ratio: 8/5` and `max-height`
- [ ] WCAG AAA 7:1 on all text — `--text-muted: #b4b4b4` used for secondary text
- [ ] Red and magenta module text uses lightened variants (not full-brightness)
- [ ] Audio uses ▶ symbol, CV uses ⬦ symbol
- [ ] All interactive elements have `aria-label`
- [ ] Skip link present

**Documentation**
- [ ] Default values for all knobs
- [ ] MIDI CC map complete
- [ ] Sound presets included
- [ ] Incremental build order with CPU checkpoints
- [ ] Conversation log updated
- [ ] GitHub file structure complete

---

*ZOIA/ZEBU AI Patch Designer Skill v2.0*
*Based on Sympathetic Strings Resonator v3 development — 8 sessions, 17+ files*
*Reference: Empress Effects ZOIA Module Index firmware 5 (official)*
