# {{PATCH_NAME}}

{{ONE_SENTENCE_DESCRIPTION}}

**CPU: ~{{CPU_ESTIMATE}}% estimated · Firmware {{FIRMWARE_MIN}}+ · {{COMPATIBLE_UNITS}} compatible**

## Quick start

1. {{INPUT_ROUTING}} — e.g. "Guitar mono in → Left jack"
2. {{OUTPUT_ROUTING}} — e.g. "Stereo out → Left + Right jacks"
3. {{KEY_DEFAULTS}} — e.g. "Dry Vol: 85%, Wet Vol: 45%, Dampening: 3.5kHz"
4. {{FIRST_THING_TO_TRY}} — e.g. "Play a note. Raise Wet Vol slowly until you hear the effect."

## Files

```
patch/
  default-values.json   — all parameter defaults and ranges
  connections.json      — full connection list (From/To/Type/Strength)
  sound-presets.json    — {{PRESET_COUNT}} named presets
  midi-map.json         — MIDI CC assignments

docs/
  patch-explorer.html   — interactive patch documentation (open in browser)
  flowchart.mmd         — Mermaid signal flow diagram
  connections-list.md   — human-readable connections reference
```

## Page structure

| Page | Name | Key modules |
|---|---|---|
| P1 | UI Controls | {{P1_MODULES}} |
| P2 | I/O + Mix Bus | {{P2_MODULES}} |
{{ADDITIONAL_PAGES}}

## Parameters

| Parameter | Default | Range | MIDI CC | Description |
|---|---|---|---|---|
{{PARAMETERS_TABLE}}

## Stomps

| Stomp | Mode | MIDI CC | Description |
|---|---|---|---|
{{STOMPS_TABLE}}

## Presets

| Name | Description | Key settings |
|---|---|---|
{{PRESETS_TABLE}}

## Colour coding

All documentation uses ZOIA's official LED colours:

- 🔵 Sky `#00BFFF` — I/O (Audio In, Audio Out)
- 🟢 Green `#00FF00` — Pitch tracking modules
- 🔴 Red `#FF0000` — {{RED_USE}}
- 🟡 Yellow `#FFFF00` (dashed border) — Value / scaling modules
- 🩵 Aqua `#00FFFF` — {{AQUA_USE}}
- 🟣 Magenta `#FF00FF` — {{MAGENTA_USE}}
- 🟠 Orange `#FFA500` — Mix Bus (VCAs, Mixer)
- ⬜ White `#FFFFFF` — UI controls (Knobs, Stomps)

## Hardware configuration

**ZOIA:** {{ZOIA_STOMP_ASSIGNMENTS}} · MIDI via 3.5mm
**ZEBU:** {{ZEBU_CV_MAPPINGS}}
**Input:** {{INPUT_DESCRIPTION}}
**Output:** {{OUTPUT_DESCRIPTION}}

## CPU safety

Estimated ~{{CPU_ESTIMATE}}%, ceiling 95%. Build incrementally — check ZOIA CPU display:

1. {{BUILD_STEP_1}}
2. {{BUILD_STEP_2}}
3. {{BUILD_STEP_3}}
4. {{BUILD_STEP_4}}

If CPU > 85%: {{CPU_REDUCTION_ADVICE}}
