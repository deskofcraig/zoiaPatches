Now I have everything I need. Let me work out the full V4 spec from the patch's own internal logic.Here is the complete specification for **V4 SEVENTH**, derived precisely from the patch's existing voice ratios and scaling patterns.

---

## The Tuning Logic — derived from your existing voices

The patch encodes pitch as delay time. The pattern is:

| Voice | Interval | Ratio | Base delay time | CV Rectify strength |
|---|---|---|---|---|
| V1 | Fundamental | 1:1 | **2.3 ms** | **6%** |
| V2 | Octave | 2:1 | 1.1 ms | 3% (= 6% × ½) |
| V3 | Fifth | 3:2 | 1.5 ms | 4% (= 6% × ⅔) |
| **V4** | **Minor 7th** | **16:9** | **1.3 ms** | **3.5%** (= 6% × 9/16) |

The minor 7th (16:9) is the best choice here — it's the natural piano harmonic 7th and will resonate cleanly rather than beating. The delay time is the fundamental divided by the ratio: `2.3ms × (9/16) = 1.294ms`, round to **1.3 ms**.

---

## DELAY LINE [V4 SEVENTH] — Module Settings

| Block | Parameter | Value |
|---|---|---|
| Option | Max time | **100 ms** (same as all other voices) |
| Block 1 | audio in | ← P3 SV Filter [SOFT LIMITER] lowpass output (block 4) |
| Block 1 | audio in | ← P4 VCA [V4 FEEDBACK] audio out 1 (block 4) — feedback loop |
| Block 2 | delay time | base **1.3 ms** |
| Block 3 | audio out | → P4 VCA [V4 FEEDBACK] audio in 1 (block 1) |
| Block 3 | audio out | → P4 SV Filter [DAMPENING] audio in (block 1) |

---

## VCA [V4 FEEDBACK] — Module Settings

| Block | Parameter | Value / Source |
|---|---|---|
| Block 1 | audio in 1 | ← Delay Line [V4] audio out (block 3) |
| Block 3 | level control | ← P3 ADSR [GATE ENVELOPE] cv output (block 10) |
| Block 3 | level control | ← P1 Value [FEEDBACK] CV output (block 2) |
| Block 3 | level control | ← P1 Stompswitch [DECAY KILL] cv output — overrides to 0 |
| Block 4 | audio out 1 | → Delay Line [V4] audio in (block 1) — feedback loop |

---

## Connection Strengths

These follow the descending harmonic series pattern of the patch (V1=100%, V2=80%, V3=55%):

| Connection | Strength |
|---|---|
| SV Filter [SOFT LIMITER] → Delay [V4] audio in (exciter) | **40%** |
| Delay [V4] audio out → VCA [V4] audio in | **100%** |
| VCA [V4] audio out → Delay [V4] audio in (feedback loop) | **75%** |
| Delay [V4] audio out → SV Filter [DAMPENING] audio in | **100%** |
| ADSR → VCA [V4] level control | **40%** |
| Value [FEEDBACK] → VCA [V4] level control | **40%** |
| Stompswitch [DECAY KILL] → VCA [V4] level control | **0%** (kill) |
| CV Rectify [PITCH POS] → Delay [V4] delay time | **3.5%** |

---

## New Connections Summary (CX table additions)

| ID | Type | From | To | Strength |
|---|---|---|---|---|
| A30 | AUDIO | SV Filter [SOFT LIMITER] bl4 | Delay [V4 SEVENTH] bl1 | **40%** |
| A31 | AUDIO | Delay [V4 SEVENTH] bl3 | VCA [V4 FEEDBACK] bl1 | 100% |
| A32 | AUDIO | VCA [V4 FEEDBACK] bl4 | Delay [V4 SEVENTH] bl1 | **75%** |
| A33 | AUDIO | Delay [V4 SEVENTH] bl3 | SV Filter [DAMPENING] bl1 | 100% |
| C33 | CV | CV Rectify [PITCH POS] bl2 | Delay [V4 SEVENTH] bl2 | **3.5%** |
| C34 | CV | ADSR [GATE ENVELOPE] bl10 | VCA [V4 FEEDBACK] bl3 | **40%** |
| C35 | CV | Value [FEEDBACK] bl2 | VCA [V4 FEEDBACK] bl3 | **40%** |
| C36 | CV | Stompswitch [DECAY KILL] bl1 | VCA [V4 FEEDBACK] bl3 | **0%** |

---

## Block & CPU Impact

P4 currently uses **28/40 blocks**. V4 adds 6 blocks (Delay Line = 3, VCA = 3), bringing P4 to **34/40 blocks** — still 6 slots free. CPU goes from ~32% to ~**34.3%**, with ~61% headroom remaining.

---

## A Note on Tuning Feel

Start with the 40% exciter/envelope strengths above, then dial to taste. The 7th is a slightly dissonant interval that adds shimmer and tension — lower it toward 30% for a subtle "shimmer" effect that sits behind the octave and fifth, or push it up toward 50% for a more pronounced jazz-piano character. If you want a major 7th instead (brighter, more leading-tone tension), change the base delay to **1.2 ms** and the CV Rectify strength to **3%** (ratio 15:8).
