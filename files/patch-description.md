# Sympathetic String Resonator

**For:** ZOIA / ZEBU (Empress Effects)  
**Firmware:** 5.0+  
**CPU:** ~46%  
**Version:** 1.0

---

## Description

Adds the organic resonance of a grand piano's sympathetic strings to your guitar, bass, or synth.

When a concert piano stands in the room while you play, its un-damped strings vibrate sympathetically with every note in the air. This patch recreates that acoustic phenomenon entirely inside ZOIA. Four delay-line resonators track your pitch in real time and vibrate at the fundamental, octave above, perfect fifth, and octave below — the same intervals that piano strings respond to. A Haas stereo spread creates natural stereo width with zero modulation artifact. Plate reverb adds the acoustic body of the instrument and the room.

The result is entirely clean and organic: no chorus, no distortion, no vibrato. Just the sensation of a piano resonating alongside you.

---

## Controls

| Knob | Function |
|---|---|
| **Detune** | Spreads Voice 1 and Voice 3 in opposite directions for string thickness |
| **Feedback** | Resonator loop sustain (0 = short stab · 0.95 = near-infinite) |
| **Reverb** | Plate reverb level and decay length together |
| **Piano Tone** | SV Filter cutoff (0 = dark upright · 1 = bright harpsichord) |
| **Resonance** | SV Filter Q — ringing, singing string quality |
| **Dry/Wet** | Guitar-to-resonance blend. Expression pedal compatible. |
| **Sensitivity** | How loud you need to play to excite the resonators |

| Footswitch | Function |
|---|---|
| **Left (latching)** | Infinite Sustain — gates off input, maximises feedback |
| **Center (momentary)** | Resonance Kill — instantly silences all voices |
| **Right (latching)** | Audio Bypass |

---

## Presets

- **Grand Hall** — Full concert grand, long reverb
- **Chamber Piano** — Intimate, close-miked
- **Upright Piano** — Dark, short decay
- **String Halo** — Very subtle atmospheric shimmer
- **Infinite Shimmer** — Pad building via sustain footswitch

---

## Technical Notes

- Built from 4× Delay Line resonators + feedback VCAs — no Pitch Shifter used (lower latency, ¼ the CPU)
- Pitch Detector → CV Filter → CV Invert → all delay time inputs (exponential CV mode)
- Haas spread: stereo width without chorus modulation artefacts
- K_REVERB controls Plate Reverb mix and decay time simultaneously
- All 10 parameters are MIDI CC-automatable (see MIDI tab in patch explorer)

---

*patchstorage.com · tags: resonator, piano, sympathetic, pitch-tracking, ambient, clean*
