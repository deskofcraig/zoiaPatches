# ZOIA Patch Documentation Framework

A reusable system for documenting Empress ZOIA and ZEBU patches — built from the *Sympathetic Strings Resonator* as the reference patch.

---

## What's in here

```
zoia-doc-framework/
  SKILL.md                              ← AI skill: use this when prompting Claude
  FRAMEWORK-README.md                   ← this file

  design-system/
    zoia-design-system.css              ← standalone CSS for any patch explorer

  templates/
    patch-data.schema.json              ← JSON schema all patch data files must conform to
    patch-readme.template.md            ← README template (fill in the {{PLACEHOLDERS}})
    patch-explorer-template.html        ← self-contained HTML interactive doc template
    flowchart.template.mmd              ← Mermaid signal flow template
    sound-presets.template.json         ← 6-preset JSON template
```

---

## How to use with Claude (AI workflow)

### Documenting an existing patch

Paste this into Claude with your patch files attached:

```
Use the ZOIA Patch Documentation Skill (SKILL.md).

I have an existing patch: [describe it briefly].

Attached files:
- default-values.json (or describe the patch parameters)
- connections list (or describe the signal flow)

Please generate the full documentation set:
1. default-values.json (validate against the schema)
2. flowchart.mmd
3. README.md
4. patch-explorer.html
5. sound-presets.json
```

### Designing a new patch

```
Use the ZOIA Patch Documentation Skill (SKILL.md).

I want to design a new ZOIA patch: [describe the effect].

Musical intent: [what it does to the signal]
Hardware: ZOIA / ZEBU / both
CPU budget: ~[n]% (leave headroom for live use)
Stereo output: yes/no
MIDI control: yes/no

Please design the patch and generate all documentation files.
```

---

## Per-patch folder structure

When you create a new patch, use this layout:

```
patches/
  my-patch-name/
    patch/
      default-values.json     ← all parameters (conform to schema)
      connections.json        ← full from/to/type/strength list
      sound-presets.json      ← 4–6 named presets
      midi-map.json           ← MIDI CC assignments

    docs/
      README.md               ← human-readable overview
      patch-explorer.html     ← interactive browser documentation
      flowchart.mmd           ← Mermaid signal flow diagram
      connections-list.md     ← human-readable connections reference
```

---

## Design system quick reference

### Module colour groups

| Class | LED colour | Use for |
|---|---|---|
| `m-io` / `zg-io` | Sky `#00BFFF` | Audio In, Audio Out |
| `m-pitch` / `zg-pitch` | Green `#00FF00` | Pitch Detector, Env Follower, S&H, ADSR |
| `m-res` / `zg-res` | Red `#FF0000` | Delay Lines, filters in resonator role |
| `m-body` / `zg-body` | Aqua `#00FFFF` | Tone Control, EQ, body shaping |
| `m-rev` / `zg-rev` | Magenta `#FF00FF` | Reverb chain |
| `m-mix` / `zg-mix` | Orange `#FFA500` | VCAs, Mixers, wet/dry bus |
| `m-ctrl` / `zg-ctrl` | White `#FFFFFF` | Knobs, Stomps |
| `m-val` / `zg-val` | Yellow `#FFFF00` (dashed) | Value scaling modules |

### Mermaid classDefs (copy into every flowchart)

```
classDef io      fill:#001b23,stroke:#00BFFF,color:#d4e4ff
classDef pitch   fill:#002300,stroke:#00FF00,color:#b8f5cb
classDef res     fill:#230000,stroke:#FF0000,color:#ffd4d4
classDef body    fill:#003a3a,stroke:#00cccc,color:#b0f0f0
classDef rev     fill:#3a003a,stroke:#dd44dd,color:#f5b8f5
classDef mix     fill:#170b00,stroke:#FFA500,color:#d4d4ff
classDef ctrl    fill:#1c1c1c,stroke:#FFFFFF,color:#f0f0f0
classDef val     fill:#232300,stroke:#FFFF00,color:#fff0a0
```

---

## Key ZOIA module facts (most common gotchas)

- **No Resonator module** → use Delay Line + VCA feedback (comb filter)
- **No CV Adder** → use CV Mixer with attenuators set to 1.0
- **Pitch Detector has NO gate output** → add Env Follower + Comparator for gate
- **Chorus is 6–10% CPU** → use Audio Balance for stereo width instead
- **Onset Detector is 12.3% CPU** → prefer Env Follower (2.5%) + Comparator (0.04%)
- **CPU ceiling is 95%** — design for ≤80% for live stability

---

## Reference patch

The *Sympathetic Strings Resonator v3* (in `patches/sympathetic-strings/`) is the reference implementation showing every framework convention in use.
