# ZOIA Sympathetic Strings Resonator v2

Piano string sympathiser with real-time pitch tracking. Adds the resonant character of a grand piano's undamped strings to your guitar signal.

**CPU: ~68% estimated · Firmware 5+ · ZOIA and ZEBU compatible**

## Quick start

1. Guitar mono in → Left jack
2. Stereo out → Left + Right jacks  
3. Dry Vol: 85%, Wet Vol: 45%, Dampening: 3.5kHz, Decay: 2.8s
4. Play a note. Raise Wet Vol slowly until you hear the effect.

## Files

```
patch/
  default-values.json   — all parameter defaults and ranges
  connections.json      — full connection list (From/To/Block/Strength)
  sound-presets.json    — 6 named presets
  midi-map.json         — MIDI CC assignments

docs/
  patch-explorer.html   — interactive patch documentation (open in browser)
  flowchart.mmd         — Mermaid signal flow diagram
  grid-layouts/         — SVG grid layouts for all 6 pages
  connections-list.md   — human-readable connections reference

prompts/
  patch-prompt.md       — complete build instructions for this patch
  generic-zoia-prompt.md — reusable template for new ZOIA patches
  ai-conversation-skill.md — AI skill for generating ZOIA patches
```

## Page structure

| Page | Name | Key modules |
|---|---|---|
| P1 | UI Controls | 9 knobs, 3 stomps, Value modules |
| P2 | I/O + Mix Bus | Audio In/Out, Wet/Dry VCAs, Mixer |
| P3 | Pitch Tracking | Pitch Detector, Soft Limiter, CV Adder, S&H, ADSR |
| P4 | Resonator Bank | V1–V4, Delay L/R, Dampening LPF, Value×3 |
| P5 | Piano Body | Tone Control, Chorus, Value BODY SCALE |
| P6 | Reverb | VCA Send, Simple Reverb, VCA Return |

## Colour coding

All documentation uses ZOIA's official 7 LED colours:

- 🔵 Sky `#00BFFF` — I/O (Audio In, Audio Out)
- 🟢 Green `#00FF00` — Pitch tracking modules
- 🔴 Red `#FF0000` — Resonators, Delay Lines, Dampening LPF
- 🟡 Yellow `#FFFF00` (dashed border) — Value / scaling modules
- 🩵 Aqua `#00FFFF` — Piano Body (Tone Control, Chorus)
- 🟣 Magenta `#FF00FF` — Reverb chain
- 🟠 Orange `#FFA500` — Mix Bus (VCAs, Mixer)
- ⬜ White `#FFFFFF` — UI controls (Knobs, Stomps)
- 🟡 Mango `#FFB000` — Warnings
- 💚 Surf `#00FF99` — MIDI tags

## Hardware configuration

**ZOIA:** 3 stomp switches (Bypass / Pitch Hold / Decay Kill), MIDI via 3.5mm  
**ZEBU:** Map Bypass → CV In 1, Pitch Hold → CV In 2, Decay Kill → CV In 3  
**Input:** Mono (left jack). Right input unused.  
**Output:** Stereo (left TS + right TRS)

## CPU safety

Estimated ~68%, ceiling 95%. Build incrementally — check ZOIA CPU display:
1. Audio I/O → Pitch + Soft Limiter
2. Add V1 + Delays + Dampening LPF
3. Add V2, V3, V4 individually
4. Add Body EQ + Reverb + Mix
5. Add knob CV routing last (nearly free)

If CPU > 85%: remove V3 first (saves ~9%). Then V4 (saves another ~9%).
