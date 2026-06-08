# Generic ZOIA / ZEBU Patch Creation Prompt Template

Use this document when asking an AI to design a new ZOIA or ZEBU patch.
Fill in every section marked `[FILL IN]` before submitting.
The more detail you provide, the better and faster the result.

---

This form will help give guidance and help building ZOIA patches with the help with AI tools. 

The following files are used to help in the patch design:
- `zoia-module-index.json` (human readable version: [ZOIA Module Index](/zoia-module-index.md)
- `zoia-rules.json` (human readable version: [ZOIA Rules](/zoia-rules.md)

## 1. Patch Goal

**What should this patch do?**
[FILL IN — e.g. "A harmonic tremolo that splits signal into two bands and tremoloes them out of phase"]

**Sound reference** (hardware, plugin, album track, or YouTube link):
[FILL IN — e.g. "Mutable Instruments Rings polyphonic mode" or "Rhodes electric piano body resonance"]

**What should NOT be in the sound?**
[FILL IN — e.g. "No pitch modulation, no obvious chorus wobble, no distortion"]

**What input does it take?**
- [ ] Guitar
- [ ] Bass
- [ ] Synth / keyboard
- [ ] Drum machine
- [ ] Samples
- [ ] Microphone
- [ ] MIDI only (no audio input)
- [ ] No input — self-generating
- [ ] Other: [FILL IN]

**What audio inputs are needed?**
- [ ] Mono in
- [ ] Mono in & mono fx return
- [ ] Stereo in
- [ ] Parallel mono
- [ ] No audio input required
- [ ] Other: [FILL IN]

**What outputs are needed?**
- [ ] Mono out
- [ ] Mono fx send & mono out
- [ ] Stereo out *(most common for effects)*
- [ ] Dry/Wet split (e.g. dry to amp, wet to PA)
- [ ] Parallel mono
- [ ] No audio output required
- [ ] Other: [FILL IN]

---

## 2. Hardware Target

- [ ] ZOIA (3 stomp switches · 1 control port)
- [ ] ZEBU / Euroburo (no stomps · 2 aux buttons · 4 CV in · 4 CV out)
- [ ] Both (design to work on either)

---

## 3. CPU Budget

**Target maximum CPU:** [e.g. 75%, 80%, 85%]

CPU fluctuates when signal passes through ZOIA. Design conservatively:
- Aim for ~75% at most to leave room for CPU spikes during loud playing
- If unsure, say 85% and the AI will work within that

---

## 4. Controls
For both ZOIA & ZEBU

### 4.1. What value controls would you like to have?

List controls you would like to have available
- [ ] [FILL IN] List controls
- [ ] AI can help decide

**ZOIA limits:** max 9 knobs + 3 stomps per page (each knob = a 2-block Value module).
Controls that overflow one page go on additional pages.

### For ZOIA
### 4.2.1 What would you like the stompswitches to control? (if required)

List controls you would like stompswitches to control.

- [ ] Left footswitch: [FILL IN]
- [ ] Center footswitch: [FILL IN]
- [ ] Right footswitch: [FILL IN]

### 4.2.2. Expression pedal?**
- [ ] Yes — maps to: [FILL IN e.g. filter cutoff / reverb depth]
- [ ] Maybe - give me an option for it
- [ ] No

### For ZEBU

### 4.3.1. ZEBU CV mapping** (if applicable):
Which parameters should the 4 CV inputs control?
[FILL IN or leave blank — AI will suggest]

Which parameters should the 4 CV outputs send?
[FILL IN or leave blank — AI will suggest]

### 4.3.2 What would you like Auxiliary buttons to control?
- [ ] I don't need to use them
- [ ] [FILL IN] List controls
- [ ] AI can help decide

List all real-time-adjustable parameters. Add rows as needed.

| Control name | Type | What it does | Default | MIDI CC? |
|---|---|---|---|---|
| [FILL IN] | knob / stomp / CV | | | |

---

## 5. Page Structure

- [ ] Let AI decide
- [ ] My preference: [FILL IN — e.g. "P0 UI, P1 I/O, P2 effects"]

** Example structure (AI default):**
- P0 — UI controls (all knobs + stomps)
- P1 — I/O + Mix bus
- P2 — Analysis / pitch tracking (if needed)
- P3 — Core audio processing
- P4 — Shaping / EQ / body
- P5+ — Reverb / time-based effects

Keep P0 as the UI page, and P1 as the I/O (& Mix bus if required) so performers never need to navigate during a set.

---

## 6. MIDI Requirements

- [ ] No MIDI
- [ ] MIDI CC control of parameters listed in section 4
- [ ] MIDI note input (for synth voice / pitch-triggered effects)
- [ ] MIDI clock sync
- [ ] MIDI program change (to recall presets)

---

## 7. SD Card / Samples

- [ ] Not needed
- [ ] Need sample playback from SD card

**If SD card is used — ZOIA requirements:**
- Format: **FAT32 only** (not exFAT, not APFS — reformat on Windows or use SD Formatter)
- Sample folder: `/samples/` in the root of the card
- File format: WAV, 48kHz, 16-bit or 24-bit, mono or stereo
- Filename: simple alphanumeric only, no spaces, max 8 characters recommended
- Loading: via the **Sampler** module — specify filename in module options
- Max file size: 10 minutes or less per file

```
SD_CARD_ROOT/
├── patches/
│   └── my-patch.bin
└── samples/
    ├── piano_c3.wav
    └── strings.wav
```

---

## 8. Additional Context

**Modules to avoid:**
[FILL IN — e.g. "No granular (CPU)" or "No pitch shifter (latency)"]

**Modules to include:**
[FILL IN — e.g. "Must use a phaser" or "Want a looper"]

**Existing patch to extend:**
[FILL IN or N/A]

**Other notes:**
[FILL IN]

---

## 9. Output Format Requested

- [ ] Interactive HTML patch explorer — tabbed, with CSS Grid page layouts, module cards, connections, MIDI map, presets
  - [ ] Inline variant (single `.html` file, works on `file://` locally)
  - [ ] Linked variant (`.html` + `assets/` folder, for GitHub Pages / web server)
- [ ] Mermaid flowchart (paste into mermaid.live or Obsidian)
- [ ] Full connections list — From/To Page/Module/Block/Strength in JSON and markdown
- [ ] JSON data files — default values, connections, sound presets
- [ ] Patch build prompt (this format — instructions for rebuilding the patch)
- [ ] GitHub CMS folder structure
- [ ] MIDI CC map
- [ ] Sound presets (named variations with all parameter values)
- [ ] Patch description (for patchstorage.com or sharing)
- [ ] Conversation log (running record of all prompt/response exchanges)

---

## What Helps AI Get It Right the First Time

**Definitely provide:**
- A sound reference (hardware, plugin, or a track) — more useful than technical specs
- The CPU ceiling (section 3)
- Which hardware you own — ZOIA and ZEBU have meaningfully different capabilities
- Whether you want separate Wet/Dry controls (common oversight if not specified)

**Don't worry about providing:**
- Which ZOIA modules to use — AI handles that
- V/Oct, CV routing, or signal flow — describe the sound, not the wiring
- Page layout — AI will fit everything in the 8×5 grid

**Things that improve results most:**
- "It should sound like [X]" beats "use a resonator at 440Hz"
- Specifying expression pedal use unlocks a useful performance dimension
- "I want ZEBU CV patch points for the filter and reverb" gives a specific ZEBU mapping target
- Listing what you *don't* want (wobble, noise, obvious chorus) shapes the design significantly

---

## Module Verification Note

Always verify module names and block counts against the official Empress Module
Index before building. Key facts that catch AI errors:

- **No "Resonator" module exists** — build from Delay Line + VCA feedback
- **No "CV Adder" module exists** — use CV Mixer (attenuators set to 1.0)
- **Pitch Detector has 2 blocks only** — audio in + pitch out. No gate output.
- **VCA block 3 is "level control"** not "gain_cv"
- **Chorus CPU is 6–10%** not 3% — expensive for static width use
- **Onset Detector is 12.3% CPU** — use Env Follower + Comparator (2.54%) for gate detection
- **Reverb Lite is "Reverb Lite"** — not "Simple Reverb"

---
