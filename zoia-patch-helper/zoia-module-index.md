# Empress ZOIA & ZOIA Euroburo (ZEBU) — Module Index
### as of v5.32

#### Notes
- All modules can be given a new name and colour in Module Options
- The ZOIA grid is 8 columns × 5 rows = 40 available blocks per page
- ZOIA has a maximum CPU usage of 100%
- `*` indicates optional block(s) for modules

## Categories and Modules
| [Interface](#interface-modules) | [Audio](#audio-modules) | [Control](#control-modules) | [Analysis](#analysis-modules) | [Effect](#effect-modules) | [Euroburo](#euroburo-modules) |
|-|-|-|-|-|-|
| [Audio Input](#audio-input) | [Oscillator](#oscillator) | [LFO](#lfo) | [Onset Detector](#onset-detector) | [Tone Control EQ](#tone-control-eq) | [CV In](#cv-in) |
| [Audio Output](#audio-output) | [VCA](#vca) | [Sequencer](#sequencer) | [Env Follower](#env-follower) | [Delay w Mod](#delay-w-mod) | [CV Out](#cv-out) |
| [MIDI Notes In](#midi-notes-in) | [SV Filter](#sv-filter) | [ADSR](#adsr) | [Pitch Detector](#pitch-detector) | [Ping Pong Delay](#ping-pong-delay) | |
| [MIDI Pitch Bend In](#midi-pitch-bend-in) | [Multi-Filter](#multi-filter) | [Sample and Hold](#sample-and-hold) | | [OD & Distortion](#od--distortion) | |
| [MIDI CC In](#midi-cc-in) | [Delay Line](#delay-line) | [CV Invert](#cv-invert) | | [Fuzz](#fuzz) | |
| [MIDI Pressure](#midi-pressure) | [Audio Panner](#audio-panner) | [CV Rectify](#cv-rectify) | | [Compressor](#compressor) | |
| [MIDI Clock In](#midi-clock-in) | [Pitch Shifter](#pitch-shifter) | [Value](#value) | | [Gate](#gate) | |
| [MIDI CC Out](#midi-cc-out) | [Audio Balance](#audio-balance) | [Trigger](#trigger) | | [Plate Reverb](#plate-reverb) | |
| [MIDI PC Out](#midi-pc-out) | [Audio Mixer](#audio-mixer) | [CV Flip Flop](#cv-flip-flop) | | [Hall Reverb](#hall-reverb) | |
| [MIDI Note Out](#midi-note-out) | [Inverter](#inverter) | [CV Delay](#cv-delay) | | [Room Reverb](#room-reverb) | |
| [MIDI Clock Out](#midi-clock-out) | [Audio In Switch](#audio-in-switch) | [CV Loop](#cv-loop) | | [Ghostverb](#ghostverb) | |
| [Stompswitch](#stompswitch) | [Audio Out Switch](#audio-out-switch) | [CV Filter](#cv-filter) | | [Reverb Lite](#reverb-lite) | |
| [Pixel](#pixel) | [All Pass Filter](#all-pass-filter) | [Slew Limiter](#slew-limiter) | | [Phaser](#phaser) | |
| [UI Button](#ui-button) | [Noise](#noise) | [Clock Divider](#clock-divider) | | [Chorus](#chorus) | |
| [Pushbutton](#pushbutton) | [Audio Multiply](#audio-multiply) | [Comparator](#comparator) | | [Vibrato](#vibrato) | |
| [Device Control](#device-control) | [Bit Crusher](#bit-crusher) | [In Switch](#in-switch) | | [Flanger](#flanger) | |
| [Keyboard](#keyboard) | [Aliaser](#aliaser) | [Out Switch](#out-switch) | | [Tremolo](#tremolo) | |
| [Cport Exp CV In](#cport-exp-cv-in) | [1 Buffer Delay](#1-buffer-delay) | [Quantizer](#quantizer) | | [Env Filter](#env-filter) | |
| [Cport CV Out](#cport-cv-out) | [Looper](#looper) | [Steps](#steps) | | [Ring Modulator](#ring-modulator) | |
| | [Granular](#granular) | [Multiplier](#multiplier) | | [Cabinet Sim](#cabinet-sim) | |
| | [Stereo Spread](#stereo-spread) | [Random](#random) | | [Univibe](#univibe) | |
| | [Bit Modulator](#bit-modulator) | [Rhythm](#rhythm) | | [Reverse Delay](#reverse-delay) | |
| | [Diffuser](#diffuser) | [Tap To CV](#tap-to-cv) | | | |
| | [Sampler](#sampler) | [CV Mixer](#cv-mixer) | | | |
| | | [Logic Gate](#logic-gate) | | | |

---

## Interface Modules

### Audio Input
Connect audio from the outside world into the grid. This could be a guitar, bass, synth module, computer audio, etc.

| | |
|-|-|
| Min blocks | 1 |
| Max blocks | 2 |
| Avg. CPU | 0.3% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `pedal input L` | no modifier | connects audio from left pedal input jack | outputs, audio effect inputs, envelope follower, pitch detector, VCAs, sidechain inputs |
| 2 | `pedal input R` | no modifier | connects audio from right pedal input jack | outputs, audio effect inputs, envelope follower, pitch detector, VCAs, sidechain inputs |

| Module options | Description | Settings |
|--|--|--|
| `channels` | select presence of left input, right input, or both | `L`, `R`, `L+R` |
| `input pad` | on the Euroburo, the input pad is set here | `0dB`, `-6dB`, `-12dB` |

back to [Categories & Modules](#categories-and-modules)

---

### Audio Output
Connect audio from your ZOIA into the outside world. Connect to your amplifier, a DI box, your audio interface, etc. An optional gain control lets you tweak the output level.

| | |
|-|-|
| Min blocks | 2 |
| Max blocks | 3 |
| Avg. CPU | 1.0% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `pedal output L` | no modifier | connects audio to left pedal output jack | inputs, audio effect outputs, VCAs, oscillators |
| 2 | `pedal output R` | no modifier | connects audio to right pedal output jack | inputs, audio effect outputs, VCAs, oscillators |
| 3 * | `gain` | output gain | selects output gain of pedal from +20dB to -100dB | LFOs, sequencers, MIDI inputs/outputs, CV inputs/outputs, ADSRs, VCAs, stomp switches/pushbuttons, expression pedal |

| Module options | Description | Settings |
|--|--|--|
| `gain control` | adds output gain control block | `on`, `off` |
| `channels` | select presence of left output, right output, or both | `L`, `R`, `L+R` |

back to [Categories & Modules](#categories-and-modules)

---

### MIDI Notes In
Connect your MIDI keyboard controller to the ZOIA. Connect the note out to an oscillator to have it play your note, and connect the gate out to an ADSR (connected to a VCA) for a natural envelope.

| | |
|-|-|
| Min blocks | 2 |
| Max blocks | 32 |
| Avg. CPU | 0.1% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `note out` | no modifier | detects played note as value from -1 to 1, where -1 is C-2, 0 is A0, and 1 is A10 | oscillators, MIDI inputs/outputs, CV inputs/outputs |
| 2 | `gate out` | no modifier | detects played note on/off status | LFOs, sequencers, MIDI inputs/outputs, CV inputs/outputs, ADSRs, VCAs |
| 3 * | `velocity out` | no modifier | detects velocity of played note | LFOs, sequencers, MIDI inputs/outputs, CV inputs/outputs, ADSRs, VCAs |
| 4 * | `trigger out` | no modifier | detects presence of played note as a single momentary pulse | LFOs, sequencers, MIDI inputs/outputs, CV inputs/outputs, ADSRs, VCAs |

| Module options | Description | Settings |
|--|--|--|
| `midi channel` | determines which MIDI channel the module will read from | `1`–`16` |
| `# of outputs` | adds additional note and gate out outputs, and velocity and trigger outputs if selected, for connecting simultaneously played midi notes. Select 1 note to build a monophonic synth, or add up to 8 notes per MIDI channel. | `1`–`8` |
| `priority` | toggles behaviour of simultaneously played MIDI notes, when number of played notes exceeds number of MIDI note outputs present | `newest`, `oldest`, `highest`, `lowest`, `round robin` |
| `greedy` | outputs are greedy for midi note inputs (all outputs will want to play) | `on`, `off` |
| `velocity output` | toggles presence of velocity out block | `on`, `off` |
| `trigger pulse` | toggles presence of trigger out block | `on`, `off` |
| `low note` | determines lowest played note to receive | MIDI note value |
| `high note` | determines highest played note to receive | MIDI note value |

back to [Categories & Modules](#categories-and-modules)

---

### MIDI Pitch Bend In 
Collects MIDI data from pitch bend wheel on keyboards, can be applied to oscillator frequency in parallel with MIDI note data, or used in other ways.

| | |
|-|-|
| Min blocks | 1 |
| Max blocks | 1 |
| Avg. CPU | 0.1% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `pitch bend` | no modifier | delivers incoming pitch bend data as a cv output that you can connect to other things | oscillators, audio effects parameters, LFOs, VCAs, output gain, sequencers |

| Module options | Description | Settings |
|--|--|--|
| `channel` | select MIDI channel to look for pitch bend signal on | `1`–`16` |

back to [Categories & Modules](#categories-and-modules)

---

### MIDI CC In
Connect encoder knobs and sliders on a MIDI interface. Take note of the outgoing CC number of each control and enter it into the controller option.

| | |
|-|-|
| Min blocks | 1 |
| Max blocks | 1 |
| Avg. CPU | 0.1% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `cc value` | no modifier | detects control change value from 0 - 127 | audio effects parameters, LFOs, VCAs, output gain |

| Module options | Description | Settings |
|--|--|--|
| `midi channel` | determines which MIDI channel the module will read from | `1`–`16` |
| `controller` | determines which controller # the module will read from | `0`–`127` |
| `output range` | determines range of CV output | `0 to 1`, `-1 to 1` |

back to [Categories & Modules](#categories-and-modules)

---

### MIDI Pressure
Many MIDI keyboards have an aftertouch feature that can be triggered by pressing down on a note after it's fully depressed. You can use aftertouch to trigger a little extra pizazz in your sound.

| | |
|-|-|
| Min blocks | 1 |
| Max blocks | 1 |
| Avg. CPU | 0.03% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `channel pressure` | no modifier | detects pressure of key after note is played. Pressure is additive when multiple keys have pressure applied | oscillators, audio effects parameters, LFOs, VCAs, output gain, sequencers |

| Module options | Description | Settings |
|--|--|--|
| `midi channel` | determines which MIDI channel the module will read from | `1`–`16` |

back to [Categories & Modules](#categories-and-modules)

---

### MIDI Clock In
Connect incoming MIDI clock to sync your patches to the outside world. Connects directly to ZOIA's MIDI input.

| | |
|-|-|
| Min blocks | 1 |
| Max blocks | 4 |
| Avg. CPU | 0.1% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `quarter out` | no modifier | outputs a square wave LFO whose period is the detected BPM | tap tempo inputs, sequencers, VCAs, ADSRs, oscillators, MIDI inputs/outputs, CV inputs/outputs |
| 2 * | `clock out` | no modifier | outputs a log sawtooth wave LFO whose period is the amount of time between clock signals | tap tempo inputs, sequencers, VCAs, ADSRs, oscillators, MIDI inputs/outputs, CV inputs/outputs |
| 3 * | `reset out` | no modifier | sends a pulse of cv when "song position ptr" message is detected with a value of 0 | cv switches, sequencers, VCAs, ADSRs, oscillators, MIDI inputs/outputs, CV inputs/outputs |
| 4 * | `running output` | no modifier | if incoming clock signal is detected, output will be 1. if not, output is 0. you can use this in conjunction with a cv switch to allow MIDI clock to override other tap sources, but only when detected. | cv switches, sequencers, VCAs, ADSRs, oscillators, MIDI inputs/outputs, CV inputs/outputs |

| Module options | Description | Settings |
|--|--|--|
| `clock out` | toggles the presence of clock out button | `on`, `off` |
| `reset out` | toggles the presence of reset out button | `on`, `off` |
| `run out` | toggles the presence of run out button | `on`, `off` |
| `beat modifier` | multiplies output at "quarter out" by selected value | `1`, `2`, `3`, `4`, `6`, `12`, `1/2`, `1/3`, `1/4`, `1/6`, `1/12` |

back to [Categories & Modules](#categories-and-modules)

---

### MIDI CC Out
Send Control Change messages to external MIDI enabled gear through ZOIA's MIDI outputs.

| | |
|-|-|
| Min blocks | 1 |
| Max blocks | 1 |
| Avg. CPU | 0.1% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `cc out` | cc out value | sends control change value from 0 - 127 | oscillator frequency, midi pressure |

| Module options | Description | Settings |
|--|--|--|
| `midi channel` | determines which MIDI channel the module will send to | `1`–`16` |
| `controller` | determines which controller # the module will send control change message to | `0`–`127` |

back to [Categories & Modules](#categories-and-modules)

---

### MIDI PC Out
Send Program Change messages to external MIDI enabled gear. Select the Program Change value and send a CV signal to trigger in to send message through ZOIA's MIDI outputs.

| | |
|-|-|
| Min blocks | 2 |
| Max blocks | 2 |
| Avg. CPU | 0.1% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `pc out` | pc out value | sends program change value from 0-127 | external MIDI devices |
| 2 | `trigger in` | minimum trigger state from 0-1 | triggers sending of program change message | footswitches/pushbuttons, MIDI inputs/outputs, CV inputs/outputs, expression pedal, LFOs, sequencers |

| Module options | Description | Settings |
|--|--|--|
| `midi channel` | determines which MIDI channel the module will send to | `1`–`16` |

back to [Categories & Modules](#categories-and-modules)

---

### MIDI Note Out
Send MIDI notes out to external MIDI enabled gear through ZOIA's MIDI outputs.

| | |
|-|-|
| Min blocks | 2 |
| Max blocks | 3 |
| Avg. CPU | 0.1% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `note in` | minimum note from 0-1 | sends played note value through selected MIDI channel | keyboard module, LFOs, MIDI inputs/outputs, CV inputs/outputs, expression pedal |
| 2 | `gate in` | minimum gate in 0-1 | sends played note on/off status through selected MIDI channel | keyboard module, LFOs, MIDI inputs/outputs, CV inputs/outputs, expression pedal |
| 3 * | `velocity out` | minimum note velocity out from 0-1 | sends played note velocity data through selected MIDI channel | LFOs, envelopes, expression pedals, footswitches, MIDI inputs |

| Module options | Description | Settings |
|--|--|--|
| `midi channel` | determines which MIDI channel the module will send to | `1`–`16` |
| `velocity output` | toggles the presence of a velocity data block for played note | `on`, `off` |

back to [Categories & Modules](#categories-and-modules)

---

### MIDI Clock Out
Generate MIDI clock to sync outside devices to your ZOIA. Clock sends directly to ZOIA's MIDI output.

| | |
|-|-|
| Min blocks | 1 |
| Max blocks | 5 |
| Avg. CPU | 0.3% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `cv/tap control` | cv: frequency of clock in Hz, s, or bpm. tap: none | determines frequency of MIDI clock either by adjusting knob, or connecting a tap, LFO, or other cv source | LFOs, sequencers, CV inputs/outputs, pushbuttons/stompswitches |
| 2 * | `sent` | cv | an upward change in cv sends "continue" message, a downward change in cv sends a "stop" message. MIDI clock continues to run. | LFOs, sequencers, CV inputs/outputs, pushbuttons/stompswitches |
| 3 * | `reset` | cv | an upward change in cv sends "stop", "song position prt 00 00", and "start" messages on 3 consecutive clock pulses. a downward change in cv arms this button for the next reset | LFOs, sequencers, CV inputs/outputs, pushbuttons/stompswitches |
| 4 * | `send position` | cv | an upward change in cv sends "stop" and "song position prt" messages on consecutive clock pulses. a downward change in cv arms this button for the next reset | LFOs, sequencers, CV inputs/outputs, pushbuttons/stompswitches |
| 5 * | `song position` | cv | displays desired song position to trigger as follows — measure : quarter note : sixteenth note | LFOs, sequencers, CV inputs/outputs, pushbuttons/stompswitches |

| Module options | Description | Settings |
|--|--|--|
| `input` | select if you'd like your MIDI clock rate determined by the knob/other cv source, or by an LFO or tap source | `cv`, `tap` |
| `run in` | toggles presence of "sent" control | `on`, `off` |
| `reset in` | toggles presence of "reset" control | `on`, `off` |
| `position` | toggles presence of send position and song position controls | `on`, `off` |

back to [Categories & Modules](#categories-and-modules)

---

### Stompswitch
Use this module to connect a stomp switch to other modules. This can be any of ZOIA's 3 stomp switches or an external one. If using an external, remember to set it up in the Config Menu. Once placed, the Scroll and Bypass stomp switches must be "switched to" by holding them both on together for 2 seconds, this will allow them to function in the modules instead of as ZOIA's main user interface. Hold again for 2 seconds to switch back.

| | |
|-|-|
| Min blocks | 1 |
| Max blocks | 1 |
| Avg. CPU | 0.1% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `cv output` | no modifier | toggles state of stompswitch as determined by edit options | tap tempos, MIDI inputs/outputs, oscillator frequency, audio effects, gain stages, sequencer |

| Module options | Description | Settings |
|--|--|--|
| `stompswitch` | select which footswitch to interface. Choose any of the 3 on the ZOIA or an external footswitch (be sure to enter in the Config Menu) | `left`, `middle`, `right`, `ext` |
| `action` | select the desired behaviour of the switch | `latching`, `momentary` |
| `normally` | select the desired default switch state | `zero`, `one` |

back to [Categories & Modules](#categories-and-modules)

---

### Pixel
Puts a coloured block on the grid. The brightness can be controlled by a cv signal or an audio signal. Pixel is a simple, elegant way to create a more visually interactive user interface for your patch.

| | |
|-|-|
| Min blocks | 1 |
| Max blocks | 1 |
| Avg. CPU | 0.01% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `cv in/audio in` | cv bias point | control the brightness of the led by sending either cv or audio in, depending on how it is configured in the Options menu | cv outputs, audio outputs |

| Module options | Description | Settings |
|--|--|--|
| `control` | select either cv or audio | `cv`, `audio` |

back to [Categories & Modules](#categories-and-modules)

---

### UI Button
UI Button can function in a couple different ways. It can show you a specific colour at a specific brightness based on the setting of or CV sent to the input. It can also act as a pushbutton with output enabled. To use as a visualizing pixel, connect CV and send the following values — EXTENDED RANGE: Red: 0–0.049, Orange: 0.05–0.099, Mango: 0.10–0.149, Yellow: 0.15–0.199, Lime: 0.20–0.249, Green: 0.25–0.299, Surf: 0.30–0.349, Aqua: 0.35–0.399, Sky: 0.40–0.449, Blue: 0.45–0.499, Purple: 0.50–0.549, Magenta: 0.55–0.599, Pink: 0.60–0.649, Peach: 0.65–0.699, White: 0.70–0.749. BASIC RANGE: Blue: 0–0.099, Green: 0.1–0.199, Red: 0.2–0.299, Yellow: 0.3–0.399, Cyan: 0.4–0.499, Magenta: 0.5–0.599, White: 0.6–0.699.

| | |
|-|-|
| Min blocks | 1 |
| Max blocks | 2 |
| Avg. CPU | 0.04% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `in` | CV input | displays colour/brightness selected by user or by CV input. use this button with optional CV output to send CV by pushing it. | your finger, LFOs, sequencers, CV inputs/outputs, envelopes, expression pedals, footswitches |
| 2 * | `CV output` | no modifier | outputs CV of 1 when in button is pushed | tap tempos, MIDI inputs/outputs, oscillator frequency, audio effects, gain stages, sequencers |

| Module options | Description | Settings |
|--|--|--|
| `colour range` | select between basic and extended colour mapping | `basic`, `extended` |

back to [Categories & Modules](#categories-and-modules)

---

### Pushbutton
Turns a grid button into a button you can push to send a CV signal. Tap in a tempo, open up a VCA, trigger a sequencer, or anything else. The grid is your oyster!

| | |
|-|-|
| Min blocks | 1 |
| Max blocks | 1 |
| Avg. CPU | 0.02% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `switch` | no modifier | push button to engage switch | your finger, tap tempos, MIDI inputs/outputs, oscillator frequency, audio effects, gain stages, sequencer |

| Module options | Description | Settings |
|--|--|--|
| `action` | select the desired behaviour of the switch | `latching`, `momentary` |
| `normally` | select the desired default switch state between zero and one. remember that your connection strength can help you achieve values in between. | `zero`, `one` |

back to [Categories & Modules](#categories-and-modules)

---

### Device Control
Control the bypass state, performance mode, or stomp aux mode using CV. A rising or falling CV value will toggle the selected control.

| | |
|-|-|
| Min blocks | 1 |
| Max blocks | 1 |
| Avg. CPU | 0.10% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `value` | CV slider from 0 to 1 | activates selected action when it sees a value of 1, deactivates action upon seeing a 0 | LFOs, footswitches/pushbuttons, MIDI inputs/outputs, CV inputs/outputs, other sequencers |

| Module options | Description | Settings |
|--|--|--|
| `control` | select between controlling the following actions | `audio bypass`, `performance mode`, `stomp aux` |

---

### Keyboard
Turns grid buttons into a keyboard you can connect to an oscillator and play. No external MIDI controller necessary! Tune each keyboard button using the knob to have it play your desired note.

| | |
|-|-|
| Min blocks | 4 |
| Max blocks | 26 |
| Avg. CPU | 0.1% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `note (#)` | selects desired note to play when button pushed. Click knob to toggle between frequency in Hz and music note | plays note when pushed, like a keyboard | your finger! |
| 2 | `note out` | no modifier | CV output of note or frequency played | oscillator frequency, MIDI note out, audio effects |
| 3 | `gate out` | no modifier | CV output of played note on/off status | ADSR, clock divider, MIDI note gate out, tap tempo inputs, audio effects |
| 4 | `trigger out` | no modifier | sends a single momentary pulse | LFOs, sequencers, MIDI inputs/outputs, CV inputs/outputs, ADSRs, VCAs |

| Module options | Description | Settings |
|--|--|--|
| `# of notes` | select how many notes you'd like your new keyboard to be. New buttons are added for each new note, all of which come out of the note out and gate out buttons. | `1`–`25` |

---

### Cport Exp CV In
Connect your expression pedal or a control voltage signal from an external source. Remember to set CPort to either exp or cv in the Config Menu.

| | |
|-|-|
| Min blocks | 1 |
| Max blocks | 1 |
| Avg. CPU | 0.1% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `cv output` | cv output | expresses value of either expression pedal or control voltage sensed by Control Port as a numerical value | audio effects, oscillator frequency, VCAs, LFOs, MIDI inputs/outputs, CV inputs/outputs |

| Module options | Description | Settings |
|--|--|--|
| `output range` | determines range of CV output | `0 to 1`, `-1 to 1` |

---

### Cport CV Out
This module interprets internal CV and sends it down the ring of a 1/4" TRS connector in the control port as a standard CV signal of 0-5 volts. Remember to set CPort to cv in the Config Menu.

| | |
|-|-|
| Min blocks | 1 |
| Max blocks | 1 |
| Avg. CPU | 0.1% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `cv input` | cv input | interprets value from a module and sends it out the Control Port on the ring of the connector as a control voltage signal from 0-5 volts | CV inputs/outputs, MIDI inputs/outputs, LFOs, sequencers, ADSRs |

| Module options | Description | Settings |
|--|--|--|
| `input range` | select if you'd like your input to be interpreted as a value from 0 to 1 or as a value from -1 to 1. This will then be sent as a control voltage from 0-5 volts | `0 to 1`, `-1 to 1` |

---

## Euroburo Modules

### CV In
Connect CV from the outside world to the grid. Euroburo only.

| | |
|-|-|
| Min blocks | 1 |
| Max blocks | 1 |
| Avg. CPU | 0.1% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `CV In` | connect to any module block that accepts control signals | connect external CV signals plugged into a CV IN jack on the euroburo to the control signal input block of modules on the grid | clocks, triggers, gates, VCAs, pitch, quantizers, ADSRs, sequencers, sample & hold, filter cutoff |

| Module options | Description | Settings |
|--|--|--|
| `out range` | sets what range of voltages you want to control other modules. 0-10V is typical for euro pitch control, 0-5V is very common for other CV. | `0-10V`, `0-5V`, `-5-5V` |
| `inpt range` | chooses if the range of what you're sending in goes from 0-1 or from -1 to 1 | `0 to 1`, `-1 to 1` |
| `clk filter` | acts as a schmitt trigger to output a clean clock signal from the cv input. The numbers represent the low and high threshold values. e.g. 2,8 would cause the module to output 0 when the input goes below 0.2 of the input voltage range, and output a high signal when the signal goes above 0.8 of the input voltage range. | various thresholds |
| `transpose 0V` | the euroburo maps 0V at its input to an A note by default. Other synths use C as 0V. Selecting the C option will transpose (add 0.25) to the output of this module so it maps to C on the euroburo oscillator. | `A`, `C` |

---

### CV Out
Connect CV from the grid to the outside world. Euroburo only.

| | |
|-|-|
| Min blocks | 1 |
| Max blocks | 1 |
| Avg. CPU | 0.2% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `CV Out` | connect to any module block that outputs control signals | connect control signal output block of modules on the grid to a CV OUT jack to be patched to external gear that uses CV | clocks, triggers, gates, VCAs, pitch, oscillators, ADSRs, sequencers, sample & hold, filter cutoff |

| Module options | Description | Settings |
|--|--|--|
| `out range` | sets what range of voltages you want to control other modules | `0-10V`, `0-5V`, `-5-5V` |
| `in range` | chooses if the range of what you're sending in goes from 0-1 or from -1 to 1 | `0 to 1`, `-1 to 1` |
| `transpose 0V` | the euroburo maps 0V to an A note by default. Some other synths/modules use C as 0V. Selecting the C option will transpose up three semitones (subtract 0.25V) from the output of this module so C in the euroburo plays a C on external synths. | `A`, `C` |

---

## Audio Modules

### Oscillator
Generates an audio signal in the waveform of your choice. Connect a MIDI device, keyboard module, sequencer, pitch detector, LFO, or any CV source to select the frequency or note the oscillator will play. You can modulate the frequency or pulse width with the optional parameters. Negative CV inputs (from -1 to 0) will generate sub-bass frequencies between 0.027Hz and 27.49Hz. Be careful!

| | |
|-|-|
| Min blocks | 2 |
| Max blocks | 4 |
| Avg. CPU | 6% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `frequency` | frequency in Hz | determines frequency of synthesized tone. The higher the frequency, the higher the note. Click the knob to toggle between frequency in Hz and music notes. Values -1 thru 0 represent sub-bass frequencies from 0.027 Hz to 27.49 Hz. Values from 0 thru 1 represent (mostly) audible frequencies from 27.5 Hz to 23999 Hz. | MIDI inputs, CV inputs, keyboard module output, pitch detector, stompswitches/push buttons, expression pedal |
| 2 * | `FM input` | no modifier | allows you to connect another oscillator or audio source to modulate the oscillator's frequency. | oscillator outputs, audio inputs |
| 3 * | `duty cycle` | value in % | adjusts the pulse width of the oscillator. | LFOs, CV inputs, MIDI inputs, expression pedal, ADSRs, envelope followers, pushbuttons/footswitches |
| 4 | `audio out` | no modifier | output of audio signal generated by oscillator. | audio inputs/outputs, VCAs, audio effects, FM inputs, analysis modules |

| Module options | Description | Settings |
|--|--|--|
| `waveform` | select pattern of generated waveform | `sine`, `square`, `triangle`, `sawtooth` |
| `fm in` | toggles presence of FM input parameter. this allows you to modulate an incoming audio signal against the oscillator, which acts as a carrier wave. | `on`, `off` |
| `duty cycle` | toggle presence of duty cycle parameter. this creates a distorted effect by varying the pulse width. | `on`, `off` |
| `upsampling` | allows waveform to be generated at 2X sampling rate for better quality (higher CPU). | `none`, `2X` |

back to [Categories & Modules](#categories-and-modules)

---

### VCA
The Voltage Controlled Amplifier module will interpret incoming CV at the level control and boost or cut the volume. Connect an ADSR to create a natural sounding envelope for an oscillator passing through. Connect an LFO to create a tremolo effect. Or connect an expression pedal module or MIDI input for an external volume control.

| | |
|-|-|
| Min blocks | 3 |
| Max blocks | 5 |
| Avg. CPU | 0.3% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `audio in 1` | no modifier | connects output of another audio source to gain stage | oscillators, audio inputs/outputs, audio effects |
| 2 * | `audio in 2` | no modifier | connects output of another audio source to gain stage (stereo) | oscillators, audio inputs/outputs, audio effects |
| 3 | `level control` | gain in dB | controls the gain of the output signal | ADSRs, envelope follower, LFOs, MIDI inputs, CV inputs, sequencers |
| 4 | `audio out 1` | no modifier | connects amplified signal from audio in 1 to an audio destination | audio inputs/outputs, VCAs, audio effects, FM inputs, analysis modules |
| 5 * | `audio out 2` | no modifier | connects amplified signal from audio in 2 to an audio destination | audio inputs/outputs, VCAs, audio effects, FM inputs, analysis modules |

| Module options | Description | Settings |
|--|--|--|
| `channels` | select if you'd like your voltage controlled amplifier to apply gain to 1 channel or 2 channels | `1`, `2` |

back to [Categories & Modules](#categories-and-modules)

---

### SV Filter
The State Variable Filter will resonate and cutoff around a set frequency.

| | |
|-|-|
| Min blocks | 4 |
| Max blocks | 6 |
| Avg. CPU | 1% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `audio in` | no modifier | connects audio source into state variable filter | audio inputs/outputs, VCAs, oscillators |
| 2 | `frequency` | frequency in Hz | determines cutoff frequency of filter. CV inputs from -1 to 0 cover the frequency range 0.03–27.5 Hz, CV inputs from 0 to 1 cover the frequency range 27.5–23999 Hz | LFOs, sequencer, CV outputs, MIDI outputs, gates/triggers, expression pedal, pushbutton/footswitch |
| 3 | `resonance` | resonance value | determines strength of resonant peak at cutoff frequency | LFOs, sequencer, CV outputs, MIDI outputs, gates/triggers, expression pedal, pushbutton/footswitch |
| 4 | `lowpass output` | no modifier | outputs audio filtered below cutoff frequency | audio inputs/outputs, VCAs, audio effects, FM inputs, analysis modules |
| 5 * | `hipass output` | no modifier | outputs audio filtered above cutoff frequency | audio inputs/outputs, VCAs, audio effects, FM inputs, analysis modules |
| 6 * | `bandpass output` | no modifier | outputs band of audio within upper and lower limits of frequency cutoff | audio inputs/outputs, VCAs, audio effects, FM inputs, analysis modules |

| Module options | Description | Settings |
|--|--|--|
| `low pass output` | toggles presence of low pass output. This is on by default | `on`, `off` |
| `hipass output` | toggles presence of hipass output | `on`, `off` |
| `bandpass output` | toggles presence of bandpass output | `on`, `off` |

back to [Categories & Modules](#categories-and-modules)

---

### Multi-Filter
A general purpose filter with gain, frequency, and Q controls. Configurable as a high pass, low pass, band pass, bell, hi shelf, or low shelf.

| | |
|-|-|
| Min blocks | 4 |
| Max blocks | 5 |
| Avg. CPU | 0.8% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `audio in` | no modifier | connects audio source into filter | audio inputs/outputs, VCAs, oscillators |
| 2 * | `gain` | gain in dB | determines gain of filter notch for hi shelf, low shelf, and bell filters | LFOs, sequencer, CV outputs, MIDI outputs, gates/triggers, expression pedal, pushbutton/footswitch |
| 3 | `frequency` | frequency in Hz | determines center frequency of filter notch | LFOs, sequencer, CV outputs, MIDI outputs, gates/triggers, expression pedal, pushbutton/footswitch |
| 4 | `q` | width from 1-100 | determines width of filter notch | LFOs, sequencer, CV outputs, MIDI outputs, gates/triggers, expression pedal, pushbutton/footswitch |
| 5 | `audio out` | no modifier | outputs filtered audio | audio inputs/outputs, VCAs, audio effects, FM inputs, analysis modules |

| Module options | Description | Settings |
|--|--|--|
| `filter shape` | select output characteristic of filter | `high pass`, `low pass`, `band pass`, `bell`, `hi shelf`, `low shelf` |

back to [Categories & Modules](#categories-and-modules)

---

### Delay Line
The Delay Line is a simple module that takes audio at the input and delays it by a set amount of time. There is no dry signal, there are no repeats. You can create repeats by connecting the output back to the input, using the connection strength to adjust number of repeats.

| | |
|-|-|
| Min blocks | 3 |
| Max blocks | 4 |
| Avg. CPU | 2% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `audio in` | no modifier | connects audio into delay line | audio inputs/outputs, VCAs, audio effects, oscillators |
| 2 | `delay time` | time in ms | delays audio playback by set time | expression pedals, CV outputs, MIDI outputs, LFOs, sequencers |
| 3 | `audio out` | no modifier | outputs delayed audio | audio inputs/outputs, VCAs, audio effects, FM inputs, analysis modules (connect back to delay line input at lower strength for natural repeats) |
| 1 | `audio in` | no modifier | connects audio into delay line (tap tempo mode) | audio inputs/outputs, VCAs, audio effects, oscillators |
| 2 | `modulation in` | time in ms | connect CV modifier to adjust delay time in real time, complete with pitch shifting | LFOs, sequencers, CV inputs, MIDI inputs, footswitches/pushbuttons, envelopes |
| 3 | `tap tempo in` | time in ms | connect CV for tap input. Try a clock divider connected to a stompswitch module to give your tapped tempo a ratio. | footswitch/pushbuttons, LFOs, sequencers, CV inputs, MIDI inputs |
| 4 | `audio out` | no modifier | outputs delayed audio (tap tempo mode) | audio inputs/outputs, VCAs, audio effects, FM inputs, analysis modules |

| Module options | Description | Settings |
|--|--|--|
| `max time` | select maximum delay time | `100ms`, `500ms`, `1s`, `2s`, `4s`, `8s`, `16s` |
| `tap tempo in` | enable tap tempo mode of delay line module | `on`, `off` |
| `interpolation` | when set to on, this emulates the blips and sweeps caused by playing back sampled audio at different rates when changing delay times | `on`, `off` |
| `CV Input` | when tap tempo in is set to "no", this sets the relationship of incoming CV to delay time | `exponential`, `linear` |

back to [Categories & Modules](#categories-and-modules)

---

### Audio Panner
Audio Panner takes either one or two input channels and pans them between two outputs. Connect an LFO for a stereo tremolo effect.

| | |
|-|-|
| Min blocks | 4 |
| Max blocks | 5 |
| Avg. CPU | 1% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `audio in 1` | no modifier | connects audio from source into panner | audio inputs/outputs, VCAs, audio effects, oscillators |
| 2 * | `audio in 2` | no modifier | connects audio from source into panner (stereo) | audio inputs/outputs, VCAs, audio effects, oscillators |
| 3 | `pan` | pan value from 0-100 | sends audio from one or two input tracks to output tracks depending on pan value. A value of 0 will pan hard to track 1 and a value of 100 will pan hard to track 2. A value of 50 is equal volume on both outputs | LFOs, sequencers, CV inputs, MIDI inputs, footswitches/pushbuttons, envelopes |
| 4 | `audio out 1` | no modifier | outputs audio panned from track 1 | audio inputs/outputs, VCAs, audio effects, FM inputs, analysis modules |
| 5 | `audio out 2` | no modifier | outputs audio panned from track 1 when 1 track mode selected, or audio panned from track 2 when stereo mode selected | audio inputs/outputs, VCAs, audio effects, FM inputs, analysis modules |

| Module options | Description | Settings |
|--|--|--|
| `channels` | select if you'd like to have one audio source panning between two outputs, or two audio sources panning between two outputs | `1 track`, `2 track` |
| `pan type` | select the behaviour of the pan type | `equal power`, `linear`, `-4.5dB` |

back to [Categories & Modules](#categories-and-modules)

---

### Pitch Shifter
Pitch Shifter transposes the pitch of incoming audio. Click the knob on the pitch shift parameter to cycle views of CV value, semitones, or cents. Connect an LFO to produce a vibrato effect, or connect whatever you'd like!

| | |
|-|-|
| Min blocks | 3 |
| Max blocks | 3 |
| Avg. CPU | 15.1% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `audio in` | no modifier | connects audio from source into pitch shifter | audio inputs/outputs, VCAs, audio effects, oscillators |
| 2 | `pitch shift` | pitch shift factor | shifts the pitch of the audio from input sources. Click the knob to toggle between CV factor, semitones, or notes | LFOs, sequencers, CV inputs, MIDI inputs, footswitches/pushbuttons, envelopes |
| 3 | `audio out` | no modifier | outputs pitch shifted audio | audio inputs/outputs, VCAs, audio effects, FM inputs, analysis modules |

back to [Categories & Modules](#categories-and-modules)

---

### Audio Balance
Audio Balance mixes an output from 2 inputs. You can run this module either mono or stereo.

| | |
|-|-|
| Min blocks | 4 |
| Max blocks | 7 |
| Avg. CPU | 0.8% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `audio in1` | no modifier | connect audio source to be balanced | audio inputs/outputs, VCAs, audio effects, oscillators |
| 2 | `audio in2` | no modifier | connect second audio source to be balanced | audio inputs/outputs, VCAs, audio effects, oscillators |
| 3 | `mix` | mix in CV | sets the mix. 0 is all audio in1, 50 is equal parts both inputs, 100 is all audio2 | LFOs, sequencers, CV inputs, MIDI inputs, footswitches/pushbuttons, envelopes |
| 4 | `audio out1` | no modifier | balanced audio output | audio inputs/outputs, VCAs, audio effects, FM inputs, analysis modules |
| 5 | `audio in1 L` | no modifier | connect audio source to be balanced — left (stereo mode) | audio inputs/outputs, VCAs, audio effects, oscillators |
| 6 | `audio in1 R` | no modifier | connect audio source to be balanced — right (stereo mode) | audio inputs/outputs, VCAs, audio effects, oscillators |
| 7 | `audio outR` | no modifier | balanced audio output right (stereo mode) | audio inputs/outputs, VCAs, audio effects, FM inputs, analysis modules |

| Module options | Description | Settings |
|--|--|--|
| `stereo` | select if you'd like mono or stereo channels. New inputs and outputs will be added for the left and right sides. | `mono`, `stereo` |

back to [Categories & Modules](#categories-and-modules)

---

### Audio Mixer
Audio Mixer functions like a stripped down mixing console, where gain is your channel fader and you can place an optional pan control. Mix up to 8 channels, in mono or stereo.

| | |
|-|-|
| Min blocks | 5 |
| Max blocks | 34 |
| Avg. CPU | 3%–20% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `inL 1` | no modifier | connect audio source to be mixed (left) | audio inputs/outputs, VCAs, audio effects, oscillators |
| 2 * | `inR 1` | no modifier | connect audio source to be mixed (right) | audio inputs/outputs, VCAs, audio effects, oscillators |
| 3 | `inL 2` | no modifier | connect second audio source to be mixed (left) | audio inputs/outputs, VCAs, audio effects, oscillators |
| 4 * | `inR 2` | no modifier | connect second audio source to be mixed (right) | audio inputs/outputs, VCAs, audio effects, oscillators |
| 5 | `gain 1` | gain in dB | adjust gain of input 1 | LFOs, sequencers, CV inputs, MIDI inputs, footswitches/pushbuttons, envelopes |
| 6 | `gain 2` | gain in dB | adjust gain of input 2 | LFOs, sequencers, CV inputs, MIDI inputs, footswitches/pushbuttons, envelopes |
| 7 * | `pan 1` | pan value L-R 0-100 | adjust pan of input 1 | LFOs, sequencers, CV inputs, MIDI inputs, footswitches/pushbuttons, envelopes |
| 8 * | `pan 2` | pan value L-R 0-100 | adjust pan of input 2 | LFOs, sequencers, CV inputs, MIDI inputs, footswitches/pushbuttons, envelopes |
| 9 | `out L` | no modifier | mixed audio output (left) | audio inputs/outputs, VCAs, audio effects, FM inputs, analysis modules |
| 10 * | `out R` | no modifier | mixed audio output (right) | audio inputs/outputs, VCAs, audio effects, FM inputs, analysis modules |

| Module options | Description | Settings |
|--|--|--|
| `num channels` | select how many channels you wish to mix. New inputs will be added for each channel | `2`–`8` |
| `stereo` | select if you'd like a mono or stereo mixer. New inputs and outputs will be added for the left and right sides. | `mono`, `stereo` |
| `panning` | toggles the presence of a pan control. Note that in mono mode, the pan control doesn't do anything | `on`, `off` |

back to [Categories & Modules](#categories-and-modules)

---

### Inverter
The Inverter module takes incoming audio signal and inverts the sound wave 180 degrees out of phase. This module is inaudible unless you have a phase related problem you are trying to solve, in which case it can be very audible. Be sure to put a 1 Buffer Delay module into your "dry" side to line up the Inverter in time for proper phase cancellation.

| | |
|-|-|
| Min blocks | 2 |
| Max blocks | 2 |
| Avg. CPU | 0.2% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `audio in` | no modifier | audio input to be inverted | audio inputs/outputs, VCAs, audio effects, oscillators |
| 2 | `audio out` | no modifier | inverted audio output | audio inputs/outputs, VCAs, audio effects, FM inputs, analysis modules |

back to [Categories & Modules](#categories-and-modules)

---

### Audio In Switch
Audio In Switch takes a selected quantity of audio inputs and allows you to switch between them to a single output. You can use this to select between instruments at your input jacks, use it in conjunction with the Audio Out Switch to select between effects chains, or use it anywhere you'd like to be able to select between incoming audio sources using CV.

| | |
|-|-|
| Min blocks | 4 |
| Max blocks | 18 |
| Avg. CPU | 0.8% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `audio in 1` | no modifier | connects audio to switch | audio inputs/outputs, VCAs, audio effects, oscillators |
| 2 * | `audio in 2` | no modifier | connects audio to switch | audio inputs/outputs, VCAs, audio effects, oscillators |
| 3 | `in select` | select value 0-1 | divides value from 0-1 between number of present switch inputs and selects audio source corresponding to value present | LFOs, sequencers, CV inputs, MIDI inputs, footswitches/pushbuttons, envelopes |
| 4 | `audio out` | no modifier | outputs selected audio source | audio inputs/outputs, VCAs, audio effects, FM inputs, analysis modules |

| Module options | Description | Settings |
|--|--|--|
| `# of inputs` | selects how many audio sources you'd like to switch between from 1-16. input jacks will be added for each source and the input select range from 0-1 will divide equally between them | `1`–`16` |

back to [Categories & Modules](#categories-and-modules)

---

### Audio Out Switch
Audio Out Switch takes an audio input and routes it between a set quantity of audio outputs. You can use it at your output jacks to select between amplifiers or mixer channels, use it in conjunction with the Audio In Switch to select between effects chains, or use it anywhere you'd like to be able to select an outgoing audio path using CV.

| | |
|-|-|
| Min blocks | 3 |
| Max blocks | 18 |
| Avg. CPU | 0.7% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `audio in` | no modifier | connects audio to switch | audio inputs/outputs, VCAs, audio effects, oscillators |
| 2 | `out select` | select value 0-1 | divides value from 0-1 between number of present switch outputs and sends input audio to corresponding switch output | LFOs, sequencers, CV inputs, MIDI inputs, footswitches/pushbuttons, envelopes |
| 3 | `audio out 1` | no modifier | sends audio from input source if chosen by switch parameter | audio inputs/outputs, VCAs, audio effects, FM inputs, analysis modules |
| 4 * | `audio out 2` | no modifier | sends audio from input source if chosen by switch parameter | audio inputs/outputs, VCAs, audio effects, FM inputs, analysis modules |

| Module options | Description | Settings |
|--|--|--|
| `# of outputs` | selects how many audio outputs you'd like to switch between from 1-16. output jacks will be added for each output and the select range from 0-1 will divide equally between them | `1`–`16` |

back to [Categories & Modules](#categories-and-modules)

---

### All Pass Filter
All Pass Filter passes through all frequencies at equal gain, but changes phase relationship between them.

| | |
|-|-|
| Min blocks | 3 |
| Max blocks | 3 |
| Avg. CPU | 3% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `audio in` | no modifier | connects audio from source into all pass filter | audio inputs/outputs, VCAs, audio effects, oscillators |
| 2 | `filter gain` | gain in dB | determines gain of phase shift | LFOs, sequencers, CV inputs, MIDI inputs, footswitches/pushbuttons, envelopes |
| 3 | `audio out` | no modifier | outputs filtered audio | audio inputs/outputs, VCAs, audio effects, FM inputs, analysis modules |

| Module options | Description | Settings |
|--|--|--|
| `# of poles` | selects quantity of poles phase shifting will augment | `1`–`8` |

back to [Categories & Modules](#categories-and-modules)

---

### Noise
Generates white noise from a single button. Use the strength of your connection as a level control. Helpful in connection with VCAs and ADSRs in creating drum sounds, etc.

| | |
|-|-|
| Min blocks | 1 |
| Max blocks | 1 |
| Avg. CPU | 0.4% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `audio out` | no modifier | outputs white noise generated by module | audio inputs/outputs, VCAs, audio effects, FM inputs, analysis modules |

back to [Categories & Modules](#categories-and-modules)

---

### Audio Multiply
Takes one audio input and mathematically multiplies it with the other. This produces a ring mod/vocoder-like effect, or can be used as an alternative to a pitch-shifter to produce analog-like octave fuzz sounds when used with a fuzz or distortion. This module likes hot signals so be sure to bump the connection strengths. Remember that silence at any one of the inputs will result in silence at the output!

| | |
|-|-|
| Min blocks | 3 |
| Max blocks | 3 |
| Avg. CPU | 0.2% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `audio in 1` | no modifier | connects audio in to multiplier | audio inputs/outputs, VCAs, audio effects, oscillators |
| 2 | `audio in 2` | no modifier | connects audio in to multiplier | audio inputs/outputs, VCAs, audio effects, oscillators |
| 3 | `audio out` | no modifier | multiplied audio output | audio inputs/outputs, VCAs, audio effects, FM inputs, analysis modules |

back to [Categories & Modules](#categories-and-modules)

---

### Bit Crusher
Bit Crusher produces distortion by reducing audio bandwidth by a set number of bits. Distortion becomes audible around 20 bits reduced. This effect can get noisy so try it with a gate.

| | |
|-|-|
| Min blocks | 3 |
| Max blocks | 3 |
| Avg. CPU | 0.3% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `audio in` | no modifier | connects audio in to bit crusher | audio inputs/outputs, VCAs, audio effects, oscillators |
| 2 | `crushed bits` | # bits crushed from 0-31 | determines number of bits to reduce sonic resolution by | LFOs, sequencers, CV inputs, MIDI inputs, footswitches/pushbuttons, envelopes |
| 3 | `audio out` | no modifier | outputs bit crushed audio | audio inputs/outputs, VCAs, audio effects, FM inputs, analysis modules |

| Module options | Description | Settings |
|--|--|--|
| `fractions` | allows you to adjust quantity of bits crushed by non-whole numbers | `on`, `off` |

back to [Categories & Modules](#categories-and-modules)

---

### Aliaser
Aliaser produces samples of incoming audio and compares them against each other to find imperfections. These imperfections become the outgoing audio. As sample count grows, so too does the thickness of the outgoing sound. This effect is a signal hog so be sure to boost your connection strengths incoming and outgoing. Try connecting a LFO or envelope follower to the alias amount.

| | |
|-|-|
| Min blocks | 3 |
| Max blocks | 3 |
| Avg. CPU | 0.6% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `audio in` | no modifier | connects audio in to aliaser | audio inputs/outputs, VCAs, audio effects, oscillators |
| 2 | `alias amount` | # of samples | depth of alias differential | LFOs, sequencers, CV inputs, MIDI inputs, footswitches/pushbuttons, envelopes |
| 3 | `audio out` | no modifier | outputs aliased audio | audio inputs/outputs, VCAs, audio effects, FM inputs, analysis modules |

back to [Categories & Modules](#categories-and-modules)

---

### 1 Buffer Delay
Delays internal audio signal by number of buffers set by buffers option. This module is inaudible, but useful anywhere you need to line up internal parallel audio connections precisely.

| | |
|-|-|
| Min blocks | 2 |
| Max blocks | 2 |
| Avg. CPU | 0.2% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `audio in` | no modifier | connects audio to be delayed | audio inputs/outputs, VCAs, audio effects, oscillators |
| 2 | `audio out` | no modifier | outputs delayed audio | audio inputs/outputs, VCAs, audio effects, FM inputs, analysis modules |

| Module options | Description | Settings |
|--|--|--|
| `buffers` | select how many buffers to delay by | `1`–`16` |

back to [Categories & Modules](#categories-and-modules)

---

### Looper
The Looper module allows you to record, overdub, and play back incoming audio, forwards or backwards, at the speed of your choice (pitch shifted). Get loopy!

| | |
|-|-|
| Min blocks | 4 |
| Max blocks | 9 |
| Avg. CPU | 0.3% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `audio in` | no modifier | connects audio to be recorded by sampler | audio inputs/outputs, VCAs, audio effects, oscillators |
| 2 | `record` | rec/stop or rec/overdub/play states | in "playback: once" mode, this button triggers the beginning and the end of recording a loop. in "playback: loop" mode, this button cycles between recording start/overdub/play similar to a conventional looper pedal. try with both latching and momentary footswitch modules, or press with your finger | LFOs, sequencers, CV inputs, MIDI inputs, footswitches/pushbuttons, envelopes |
| 3 | `restart playback` | no modifier | triggers loop to play back from the beginning. use this to replay a recorded loop again and again in "playback: once" mode. | LFOs, sequencers, CV inputs, MIDI inputs, footswitches/pushbuttons, envelopes |
| 4 * | `stop/play` | stop/play state | triggers a pause in the playback of a loop. send another trigger or press again to unpause at same location in the loop. | LFOs, sequencers, CV inputs, MIDI inputs, footswitches/pushbuttons, envelopes |
| 5 | `speed/pitch` | click knob to cycle views of speed in %, pitch in semitones, or pitch in cents | determines speed and pitch profile of recording and loop playback, similar to recording to tape. the first loop is recorded at 100% by default. | LFOs, sequencers, CV inputs, MIDI inputs, footswitches/pushbuttons, envelopes |
| 6 * | `start position` | time in s | determines point in loop to start playback, when playback restarts. the value presents itself as a value from 0s to the maximum length of time contained in that loop. | LFOs, sequencers, CV inputs, MIDI inputs, footswitches/pushbuttons, envelopes |
| 7 * | `loop length` | time in s | determines duration of loop to playback. the value is represented as total loop duration minus the time chosen in the start position parameter, so duration of loop playback can never be longer than the originally recorded loop. | LFOs, sequencers, CV inputs, MIDI inputs, footswitches/pushbuttons, envelopes |
| 8 * | `reverse playback` | forward or reverse state | determines if looper is recording, overdubbing, or playing back in a forward or reverse trajectory. press button to toggle state or control with latching or momentary footswitch | LFOs, sequencers, CV inputs, MIDI inputs, footswitches/pushbuttons, envelopes |
| 9 | `audio out` | no modifier | outputs audio playback | audio inputs/outputs, VCAs, audio effects, FM inputs, analysis modules |

| Module options | Description | Settings |
|--|--|--|
| `max rec time` | choose how much audio you'd like to be able to sample | `1s`–`32s` |
| `length edit` | toggles presence of start position and loop length parameters | `on`, `off` |
| `playback` | select if your loop will playback continuously or just once when triggered | `loop`, `once` |
| `length` | Fixed plays back your loop for its original duration, regardless of playback speed. Pre-speed plays back your loop for its full duration, regardless if you've sped it up or slowed it down. | `fixed`, `pre-speed` |
| `hear while rec` | "on" will allow original audio to pass through the looper as you're recording it | `on`, `off` |
| `play reverse` | toggles presence of reverse playback parameter | `on`, `off` |
| `overdub` | "yes" will add a loop reset trigger, and allow the looper to overdub additional layers of audio over the original loop | `yes`, `no` |
| `stop/play but` | toggles the presence of a loop playback stop and start trigger input | `on`, `off` |

back to [Categories & Modules](#categories-and-modules)

---

### Granular
Granular breaks up incoming audio into tiny little grains and spits them back out in the quantity and shape of your choosing. Go from modest textures to completely unrecognizable oscillations. Granular can also be used as a granular delay by creating a feedback path from the output back to the input.

| | |
|-|-|
| Min blocks | 8 |
| Max blocks | 10 |
| Avg. CPU | 4%–30% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `audio in` | no modifier | connects audio to be granulated | audio inputs/outputs, VCAs, audio effects, oscillators |
| 2 * | `audio inR` | no modifier | connects audio to be granulated (right channel) | audio inputs/outputs, VCAs, audio effects, oscillators |
| 3 | `grain size` | sample length in ms | determines length of time to sample to create individual grains | LFOs, sequencers, CV inputs, MIDI inputs, footswitches/pushbuttons, envelopes |
| 4 | `grain position` | time elapsed in ms | determines amount of time to elapse before playing back a sampled grain. when using granular as a delay, this parameter is your delay time. | LFOs, sequencers, CV inputs, MIDI inputs, footswitches/pushbuttons, envelopes |
| 5 | `density` | grain saturation in CV | works in conjunction with grain size to determine how many grains get created and played back | LFOs, sequencers, CV inputs, MIDI inputs, footswitches/pushbuttons, envelopes |
| 6 | `texture` | grain shape in CV | shapes the fade in and fade out of each grain | LFOs, sequencers, CV inputs, MIDI inputs, footswitches/pushbuttons, envelopes |
| 7 | `speed/pitch` | time factor in % | warps the playback speed and pitch of the grains | LFOs, sequencers, CV inputs, MIDI inputs, footswitches/pushbuttons, envelopes |
| 8 | `freeze` | running or frozen state | toggle between continuously running grains or freeze a continuous playback of a certain grain | your finger, LFOs, sequencers, CV inputs, MIDI inputs, footswitches/pushbuttons |
| 9 | `audio out` | no modifier | outputs granulated audio | audio inputs/outputs, VCAs, audio effects, FM inputs, analysis modules |
| 10 * | `audio outR` | no modifier | outputs granulated audio (right channel) | audio inputs/outputs, VCAs, audio effects, FM inputs, analysis modules |

| Module options | Description | Settings |
|--|--|--|
| `num grains` | determine how many of the same grain to string together | `1`–`8` |
| `channels` | toggles between mono or stereo operation | `mono`, `stereo` |
| `pos control` | toggles behaviour of grain position parameter between CV control and tap tempo | `cv`, `tap` |
| `size control` | toggles behaviour of grain size parameter between CV control and tap tempo | `cv`, `tap` |

back to [Categories & Modules](#categories-and-modules)

---

### Stereo Spread
Stereo Spread will take one or two channels and enhance their stereo field. This is generally used right before an audio output module but, as always, feel free to experiment! Available in two modes: Haas (mono in, stereo out) or Mid-Side (2 in, 2 out).

| | |
|-|-|
| Min blocks | 4 |
| Max blocks | 5 |
| Avg. CPU | 1.5% |

**Haas mode:**

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `audio in` | no modifier | connects audio source to be enhanced | audio inputs/outputs, VCAs, audio effects, oscillators |
| 2 | `delay time` | time in ms | amount of delay applied to audio out 2 | LFOs, sequencers, CV inputs, MIDI inputs, footswitches/pushbuttons, envelopes |
| 3 | `audio out 1` | no modifier | outputs a clean copy of the audio input | audio inputs/outputs, VCAs, audio effects, FM inputs, analysis modules |
| 4 | `audio out 2` | no modifier | outputs a delayed copy of the audio input as determined by delay time | audio inputs/outputs, VCAs, audio effects, FM inputs, analysis modules |

**Mid-Side mode:**

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `audio in 1` | no modifier | connects audio source to be enhanced | audio inputs/outputs, VCAs, audio effects, oscillators |
| 2 | `audio in 2` | no modifier | connects audio source to be enhanced | audio inputs/outputs, VCAs, audio effects, oscillators |
| 3 | `side gain` | gain in dB | adds or subtracts gain from phase inverted audio 1 | LFOs, sequencers, CV inputs, MIDI inputs, footswitches/pushbuttons, envelopes |
| 4 | `audio out 1` | no modifier | outputs stereo enhanced audio "mid" | audio inputs/outputs, VCAs, audio effects, FM inputs, analysis modules |
| 5 | `audio out 2` | no modifier | outputs stereo enhanced audio "side" | audio inputs/outputs, VCAs, audio effects, FM inputs, analysis modules |

| Module options | Description | Settings |
|--|--|--|
| `method` | select stereo spread technique | `haas`, `mid-side` |

back to [Categories & Modules](#categories-and-modules)

---

### Bit Modulator
Bit Modulator takes one audio input and compares it against the other, creating an unholy glitchy combination of both sounds at the output. Choose between 3 different logic flavours with the "type" option. When taking audio from an external source, it's recommended to put a gate before the input.

| | |
|-|-|
| Min blocks | 3 |
| Max blocks | 3 |
| Avg. CPU | 0.8% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `audio in 1` | no modifier | connect an audio source | audio inputs/outputs, VCAs, audio effects, oscillators |
| 2 | `audio in 2` | no modifier | connect another audio source | audio inputs/outputs, VCAs, audio effects, oscillators |
| 3 | `audio out` | no modifier | outputs bit modulated combination of both inputs | audio inputs/outputs, VCAs, audio effects, FM inputs, analysis modules |

| Module options | Description | Settings |
|--|--|--|
| `type` | select the flavour of your bit modulation | `and`, `or`, `xor` |

back to [Categories & Modules](#categories-and-modules)

---

### Diffuser
Diffuser spreads your signal across the galaxy like so many shimmering little stars. On its own it sounds like a modulated slapback delay with no dry signal, but it can be used to construct many a tonal/atonal masterpiece.

| | |
|-|-|
| Min blocks | 6 |
| Max blocks | 6 |
| Avg. CPU | 1.7% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `audio in` | no modifier | connect an audio source | audio inputs/outputs, VCAs, audio effects, oscillators |
| 2 | `gain` | gain in dB | sets gain of delayed audio sent back to input as a feedback loop | LFOs, sequencers, CV inputs, MIDI inputs, footswitches/pushbuttons, envelopes |
| 3 | `size` | delay size from 80-4999 | size of delay gap in samples | LFOs, sequencers, CV inputs, MIDI inputs, footswitches/pushbuttons, envelopes |
| 4 | `mod width` | width size from 3-499 samples | modulation width in samples | LFOs, sequencers, CV inputs, MIDI inputs, footswitches/pushbuttons, envelopes |
| 5 | `mod rate` | rate from 0-5.90 seconds | modulation rate in seconds | LFOs, sequencers, CV inputs, MIDI inputs, footswitches/pushbuttons, envelopes |
| 6 | `audio out` | no modifier | outputs modulated audio | audio inputs/outputs, VCAs, audio effects, FM inputs, analysis modules |

back to [Categories & Modules](#categories-and-modules)

---

### Sampler
Load or record your favorite sample, chop it up, then play it back at any speed/pitch your heart desires. All samples must be mono or stereo PCM WAV files that are 10 minutes or less in length.

| | |
|-|-|
| Min blocks | 3 |
| Max blocks | 12 |
| Avg. CPU | 10%–20% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 * | `audio inL` | no modifier | the left audio input | audio inputs/outputs, VCAs, audio effects, oscillators |
| 2 * | `audio inR` | no modifier | the right audio input | audio inputs/outputs, VCAs, audio effects, oscillators |
| 3 * | `record` | no modifier | triggers recording of the sample. Recording begins on a positive CV change, and stops on a negative CV change. | footswitches/pushbuttons, LFOs, sequencers, CV inputs |
| 4 | `sample playback` | no modifier | triggers playback of the sample. The sample begins playing on a positive CV change, and stops depending on what the playback option is set to. | LFOs, sequencers, CV inputs, MIDI inputs, footswitches/pushbuttons, envelopes |
| 5 | `speed/pitch` | press the knob to change value to %, semitones, or cents | changes the speed and pitch of the sample | LFOs, sequencers, CV inputs, MIDI inputs, footswitches/pushbuttons, envelopes |
| 6 * | `direction` | no modifier | sets the direction of sample playback. A CV value above 0.5 will play it in reverse, and below this plays it forward | footswitches/pushbuttons, LFOs, sequencers, CV inputs |
| 7 | `start` | no modifier | set where you want the sample to start (or end if going in reverse). Holding shift will zoom in to a 250ms window for fine tuning | LFOs, sequencers, CV inputs, expression pedal |
| 8 | `length` | no modifier | set where you want the sample to end (or start if going in reverse). Holding shift will zoom in to a 250ms window for fine tuning | LFOs, sequencers, CV inputs, expression pedal |
| 9 * | `position cv out` | no modifier | outputs a cv value representing the current playback position within the sample | CV inputs, sequencers, LFOs |
| 10 * | `loop end cv out` | no modifier | outputs a quick CV pulse every time the end of the sample is reached | sequencers, ADSRs, triggers |
| 11 | `audio outL` | no modifier | the left audio output | audio inputs/outputs, VCAs, audio effects, FM inputs, analysis modules |
| 12 | `audio outR` | no modifier | the right audio output | audio inputs/outputs, VCAs, audio effects, FM inputs, analysis modules |

back to [Categories & Modules](#categories-and-modules)

---

## Control Modules

### LFO
The Low Frequency Oscillator is one of the workhorse modules of the ZOIA. This will generate CV in the waveform and range of your choosing. Connect it to a sequencer to cycle through steps, to an audio effect to swing its parameters around, or to any outboard piece of gear through a MIDI or CV interface module. The connection strength you enter at the output will determine the maximum sweep of the LFO.

| | |
|-|-|
| Min blocks | 2 |
| Max blocks | 5 |
| Avg. CPU | 0.3% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `frequency/trigger in` | frequency in Hz (trigger in: no modifier) | sets the frequency at which the LFO oscillates (trigger in: calculates rate of LFO via incoming CV input) | other LFOs, sequencers, CV inputs, MIDI inputs, footswitches/pushbuttons, envelopes |
| 2 * | `swing amount` | swing factor from -100 to 100 | determines asymmetry of waveform. Apply negative CV for swing factors under 0 | LFOs, sequencers, CV inputs, MIDI inputs, footswitches/pushbuttons, envelopes |
| 3 * | `phase input` | wave phase in degrees | determines the phase of the generated LFO waveform relative to its native starting point. Use in conjunction with phase reset to sync multiple LFOs with various phase relationships. | LFOs, sequencers, CV inputs/outputs, MIDI outputs, audio effects, frequency inputs, pushbuttons/stompswitches |
| 4 * | `phase reset` | send CV signal to restart LFO generation | resets LFO back to its native starting point. Enable this parameter in multiple LFOs and connect a stomp, pushbutton, or other CV source to force them to sync up. | LFOs, sequencers, CV inputs/outputs, MIDI outputs, audio effects, frequency inputs, pushbuttons/stompswitches |
| 5 | `output` | no modifier | CV output of LFO | other LFOs, sequencers, CV inputs/outputs, MIDI outputs, audio effects, frequency inputs, tap tempos, VCAs, samplers, oscillators |

| Module options | Description | Settings |
|--|--|--|
| `waveform` | select waveform of oscillator | `square`, `sine`, `triangle`, `sawtooth`, `ramp`, `random` |
| `swing control` | toggles presence of swing amount parameter | `on`, `off` |
| `output` | determines range of CV output | `0 to 1`, `-1 to 1` |
| `input` | select oscillator frequency source. CV input allows you to dial it in with the knob or control with another source, linear cv is similar but with a different input relationship, and trigger will interpret changes in CV as a tap tempo | `cv`, `linear cv`, `trigger` |
| `phase input` | toggles presence of phase input parameter | `on`, `off` |
| `phase reset` | toggles presence of phase reset parameter | `on`, `off` |

back to [Categories & Modules](#categories-and-modules)

---

### Sequencer
The sequencer allows you to create a number of "steps" (1-32) that can be cycled through, and each step can be used to send a CV value out of that track's output. The sequencer can have up to 8 tracks, each with their own unique output so it's possible to create complex melodies or rhythmic patterns. Try connecting an LFO to the sequencer's gate input to start the sequencer cycle. Then connect the sequencer output to an oscillator, a cv track to the oscillator's frequency input, and set each step to a different note. Now your ZOIA is playing itself! Note: the first track on the sequencer can have each step controlled directly by other CV sources as well.

| | |
|-|-|
| Min blocks | 5 |
| Max blocks | 42 |
| Avg. CPU | 2% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `step 1` | note in CV (click knob to show note), CV value of gate, or # of divisions of ratchet on selected track | step will affect the value that's being sent out the output | — |
| 2 * | `step 2` | note in CV, CV value of gate, or # of ratchet divisions | step will affect the value that's being sent out the output | — |
| 3 * | `step 3` | note in CV, CV value of gate, or # of ratchet divisions | step will affect the value that's being sent out the output | — |
| 4 * | `step 4` | note in CV, CV value of gate, or # of ratchet divisions | step will affect the value that's being sent out the output | — |
| 5 | `gate in` | CV value | minimum CV input that triggers the sequencer to engage steps. apply CV over minimum to engage next step | LFOs, footswitches/pushbuttons, MIDI inputs/outputs, CV inputs/outputs, other sequencers |
| 6 * | `queue start` | CV value | minimum CV input that triggers the sequencer to start its loop over. bring CV above queue start threshold during a step to start the sequencer back at step 1 | LFOs, footswitches/pushbuttons, MIDI inputs/outputs, CV inputs/outputs, other sequencers |
| 7 | `CV out` | colour of track | CV type output will display steps as played notes or CV values. Click knob to change track type. Rotate knob to change track colour. | oscillators, VCAs, audio effect parameters, LFOs, MIDI inputs/outputs, CV inputs/outputs, other sequencers |
| 8 * | `gate out` | colour of track | gate type output will output an on/off status of the associated step. While output selected, steps can be assigned on/off status simply by pushing them. | VCAs, ADSRs, audio effect parameters, LFOs, MIDI inputs/outputs, CV inputs/outputs, other sequencers, tap tempo inputs |
| 9 * | `ratchet out` | colour of track | ratchet type output will divide the step's duration into a set number of divisions. | VCAs, gain stages, audio effect parameters, LFOs, MIDI inputs/outputs, CV inputs/outputs, tap tempo inputs |

| Module options | Description | Settings |
|--|--|--|
| `number of steps` | select number of steps from 1-32. sequencer will consume a button for each step so make sure you have room | `1`–`32` |
| `num of tracks` | select number of tracks from 1-8. sequencer will add a button for each track output | `1`–`8` |
| `restart jack` | toggles presence of queue start module | `on`, `off` |
| `behaviour` | select if you'd like your sequencer to play continuously or only when it's triggered to do so | `loop`, `one-shot`, `cv step` |

back to [Categories & Modules](#categories-and-modules)

---

### ADSR
The Attack Decay Sustain Release module is what gives a note generated from an oscillator a natural sounding envelope when played from a keyboard. Connect your oscillator or other audio source to the input of a VCA, and connect the CV output of the ADSR to the CV input on the VCA. Connect the keyboard or MIDI note gate out to the CV input of the ADSR and you've got yourself a simple synthesizer! Tweak the values to taste, or connect them to other CV inputs for experimentation. Use the optional retrigger input to restart the envelope around a note that is played before the ADSR is released.

| | |
|-|-|
| Min blocks | 4 |
| Max blocks | 10 |
| Avg. CPU | 0.07% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `cv input` | CV value | an increase in CV value will trigger the ADSR envelope. A plateau of CV at the input will hold the CV output at the set sustain level | MIDI notes in (gate in), keyboard (gate out), pushbuttons/footswitches, sequencers, LFOs, MIDI inputs/outputs, CV inputs/outputs |
| 2 * | `retrigger` | CV value | a detected increase in CV value will retrigger the attack/decay of the envelope during a sustained note/CV input | MIDI notes in (trigger out), sequencers, LFOs, MIDI inputs/outputs, CV inputs/outputs |
| 3 * | `delay` | time in ms | time between CV detection at the input and beginning of attack. Useful in adding blooming textures when using multiple voices/effects | nothing, LFOs, sequencers, MIDI inputs/outputs, CV inputs/outputs |
| 4 | `attack` | time in ms | attack time of envelope. Go from short crisp starts to long slow fade-ins | nothing, LFOs, sequencers, MIDI inputs/outputs, CV inputs/outputs |
| 5 * | `hold attack decay` | time in ms | time between peak of attack and start of decay during sustained note/CV input. Will hold the envelope at its peak for set duration | nothing, LFOs, sequencers, MIDI inputs/outputs, CV inputs/outputs |
| 6 | `decay` | time in ms | decay time from peak of attack into sustain section. Go from abruptly stopped notes to gentle fades to the sustain level | nothing, LFOs, sequencers, MIDI inputs/outputs, CV inputs/outputs |
| 7 | `sustain` | CV value | selects CV output level during sustained note/CV input. This can be thought of as the "volume" of your sustained notes | nothing, LFOs, sequencers, MIDI inputs/outputs, CV inputs/outputs |
| 8 * | `hold sustain release` | time in ms | this variable will tack on additional time between sustain and release once the CV input stops receiving input. This can be useful in lining up fade outs when using multiple voices/effects | nothing, LFOs, sequencers, MIDI inputs/outputs, CV inputs/outputs |
| 9 | `release` | time in ms | "fade out" time of envelope once sustain has been lifted. End notes abruptly or gently | nothing, LFOs, sequencers, MIDI inputs/outputs, CV inputs/outputs |
| 10 | `cv output` | no modifier | CV output of envelope | VCAs, audio effects, MIDI inputs/outputs, CV inputs/outputs, LFOs, sequencers, oscillators |

| Module options | Description | Settings |
|--|--|--|
| `retrigger input` | toggles presence of retrigger parameter | `on`, `off` |
| `initial delay` | toggles presence of delay parameter | `on`, `off` |
| `hold attack/decay` | toggles presence of hold attack decay parameter | `on`, `off` |
| `str` | toggles presence of parameters associated with sustain section. When off, notes and CV inputs will not sustain but rise and fall back down to 0 | `on`, `off` |
| `hold sustain/release` | toggles presence of hold sustain release parameter | `on`, `off` |
| `immediate release` | ON: if note/CV input is not held until attack reaches its peak, immediate release will skip sustain section and release immediately. OFF: envelope will travel to the top of the attack and carry the CV output through the envelope as set up by the user | `on`, `off` |
| `time scale` | select between linear and exponential time scales at input | `linear`, `exponential` |

back to [Categories & Modules](#categories-and-modules)

---

### Sample and Hold
Sample and Hold will take the CV value at the input and hold it in place at the output until triggered to look again at the input and update the output. Connect a LFO to the trigger to convert smooth changes in CV into stepped changes in CV. The speed of the LFO will determine the perceived resolution of the CV output.

| | |
|-|-|
| Min blocks | 3 |
| Max blocks | 3 |
| Avg. CPU | 0.1% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `CV input` | CV value | CV input to get sampled/held | LFOs, sequencers, MIDI inputs/outputs, CV inputs/outputs |
| 2 | `trigger` | CV value | if track & hold is off: a rise in CV at trigger will cause value at input to be held at output, a decline in CV arms next trigger. if track & hold is on: a rise in CV will cause value at input to be held at output, a decline in CV causes output to follow input. | LFOs, sequencers, MIDI inputs/outputs, CV inputs/outputs |
| 3 | `CV output` | no modifier | CV output will hold CV value at input when CV applied to trigger input | VCAs, audio effects, LFOs, sequencers, MIDI inputs/outputs, CV inputs/outputs, oscillators |

| Module options | Description | Settings |
|--|--|--|
| `track and hold` | when enabled, output follows input while trigger is low and holds the value when trigger is high | `on`, `off` |

back to [Categories & Modules](#categories-and-modules)

---

### CV Invert
Inverts the incoming CV. For example, a CV input of 1 will output as -1. An input of 0.2 will output as -0.2.

| | |
|-|-|
| Min blocks | 2 |
| Max blocks | 2 |
| Avg. CPU | 0.02% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `CV input` | minimum CV value | CV input to get inverted | LFOs, sequencers, MIDI inputs/outputs, CV inputs/outputs |
| 2 | `CV output` | no modifier | inverted CV output | VCAs, audio effects, LFOs, sequencers, MIDI inputs/outputs, CV inputs/outputs, oscillators |

back to [Categories & Modules](#categories-and-modules)

---

### CV Rectify
CV Rectify will interpret incoming CV from -1 to 1 and "flip" the negative values into positive values equidistant from 0.

| | |
|-|-|
| Min blocks | 2 |
| Max blocks | 2 |
| Avg. CPU | 0.07% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `CV input` | CV bias | CV input to get rectified | nothing, LFOs, sequencers, MIDI inputs/outputs, CV inputs/outputs |
| 2 | `CV output` | no modifier | rectified CV output (all negative values flipped to positive) | VCAs, audio effects, LFOs, sequencers, MIDI inputs/outputs, CV inputs/outputs, oscillators |

back to [Categories & Modules](#categories-and-modules)

---

### Value
Value allows you to connect to multiple modules and adjust their parameters simultaneously from one CV adjustment at the input.

| | |
|-|-|
| Min blocks | 2 |
| Max blocks | 2 |
| Avg. CPU | 0.15% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `value` | CV input | input a CV value to be shared. click knob to toggle between CV value and music note | LFOs, sequencers, MIDI inputs/outputs, CV inputs/outputs |
| 2 | `CV output` | no modifier | CV output | tap tempo inputs, sequencers, VCAs, ADSRs, audio effects, MIDI inputs/outputs, CV inputs/outputs, LFOs, oscillators |

| Module options | Description | Settings |
|--|--|--|
| `output` | determines range of CV output | `0 to 1`, `-1 to 1` |

back to [Categories & Modules](#categories-and-modules)

---

### Trigger
Creates a very short CV pulse (value of 1) on detection of upward CV input. This is useful in creating tap tempos from regular or irregular CV waveforms, triggering sequencers or ADSRs at specific times, etc.

| | |
|-|-|
| Min blocks | 2 |
| Max blocks | 2 |
| Avg. CPU | 0.10% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `CV input` | CV input | connect CV to be triggered from | LFOs, sequencers, MIDI inputs/outputs, CV inputs/outputs |
| 2 | `CV output` | no modifier | outgoing CV trigger | tap tempo inputs, sequencers, VCAs, ADSRs, audio effects, MIDI inputs/outputs, CV inputs/outputs, LFOs, oscillators |

back to [Categories & Modules](#categories-and-modules)

---

### CV Flip Flop
This is essentially a latching CV switch with an output of 0 or 1. When the input sees an upward CV change, the flip flop is triggered to change its output state from 0 to 1 at the next upward change in CV, which must occur after a downward change in CV. So, the flip flop changes from 0 to 1 at every other upward change in CV.

| | |
|-|-|
| Min blocks | 2 |
| Max blocks | 2 |
| Avg. CPU | 0.2% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `CV input` | CV input | connect CV to be analysed | LFOs, sequencers, MIDI inputs/outputs, CV inputs/outputs |
| 2 | `CV output` | no modifier | outputs either 0 or 1 CV, as determined by the flip flop | VCAs, ADSRs, audio effects, MIDI inputs/outputs, CV inputs/outputs, LFOs, oscillators |

back to [Categories & Modules](#categories-and-modules)

---

### CV Delay
CV Delay will take incoming CV and delay it in time by a set amount.

| | |
|-|-|
| Min blocks | 3 |
| Max blocks | 3 |
| Avg. CPU | 1.5% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `CV input` | CV input | connect CV to delay. An increase in threshold here will add adjustment to outgoing CV | LFOs, sequencers, MIDI inputs/outputs, CV inputs/outputs |
| 2 | `delay time` | time in ms | determines how long to delay CV for before sending to output | LFOs, sequencers, MIDI inputs/outputs, CV inputs/outputs |
| 3 | `CV output` | no modifier | outputs delayed CV | VCAs, audio effects, MIDI inputs/outputs, CV inputs/outputs, LFOs, sequencers, oscillators |

back to [Categories & Modules](#categories-and-modules)

---

### CV Loop
CV Loop functions similar to an audio looper except records patterns of CV signal instead of audio. You can record and play back snippets of LFOs, sequences, changes in CV or MIDI control etc.

| | |
|-|-|
| Min blocks | 5 |
| Max blocks | 8 |
| Avg. CPU | 0.1% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `CV input` | CV input | connect CV in to get looped | LFOs, sequencers, MIDI inputs/outputs, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 2 | `record` | press button, and/or CV up to record, CV down to play back | toggles between playback and record states. Push button to toggle between recording and playing loop. Alternatively, a rise in CV will trigger record, and a decrease will trigger playback | LFOs, sequencers, MIDI inputs/outputs, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 3 | `play` | press button, and/or CV up to play back, CV down to stop | toggles between playback and stopped states. Push button to toggle between playing loop and stopping. Alternatively, a rise in CV will trigger playback, and a decrease will trigger stop | LFOs, sequencers, MIDI inputs/outputs, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 4 | `playback speed` | playback speed in % | adjusts speed of CV Loop playback | LFOs, sequencers, MIDI inputs/outputs, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 5 * | `start position` | position from start of loop in seconds | determines starting point of playback of recorded CV signal. By changing this you can have your loop shortened by chopping off the beginning. | LFOs, sequencers, MIDI inputs/outputs, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 6 * | `stop position` | position from end of loop in seconds | determines maximum length of recorded CV signal played back. By changing this you can shorten the loop by chopping off the end. | LFOs, sequencers, MIDI inputs/outputs, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 7 | `restart loop` | push button | push button or send a CV increase to restart loop playback from the beginning of recorded loop | LFOs, sequencers, MIDI inputs/outputs, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 8 | `cv output` | no modifier | outputs CV playback | VCAs, audio effects, MIDI inputs/outputs, CV inputs/outputs, LFOs, sequencers, oscillators |

| Module options | Description | Settings |
|--|--|--|
| `max rec time` | select maximum amount of time you'd like to be able to loop | `1s`–`4s` |
| `length edit` | toggles presence of start position and stop position parameters | `on`, `off` |

back to [Categories & Modules](#categories-and-modules)

---

### CV Filter
CV Filter dictates the length of time a CV output will take to respond to a change in CV input, determined by the time constant. The CV change occurs logarithmically for a nice smooth transition. Use this module in series with a MIDI/keyboard note to add portamento to your synth voice. You can also use this module to vary the shape of an LFO waveform or connect to a stomp switch to produce a long slow change in an audio effect.

| | |
|-|-|
| Min blocks | 3 |
| Max blocks | 4 |
| Avg. CPU | 0.1% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `CV input` | CV to be filtered | connect CV to be filtered | LFOs, sequencers, MIDI inputs/outputs, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 2 | `time constant` | time in ms | determines the time it takes the CV output to reach 63%, or decay to 37%, of the input (linked mode) | LFOs, sequencers, MIDI inputs/outputs, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 3 | `CV output` | no modifier | filtered CV output | VCAs, LFOs, audio effects, MIDI inputs/outputs, CV inputs/outputs, sequencers, oscillators |
| 2 | `rise constant` | time in ms | determines the time it takes the CV output to reach 63% of the input (separated mode) | LFOs, sequencers, MIDI inputs/outputs, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 3 | `fall constant` | time in ms | determines the time it takes the CV output to decay to 37% of the input (separated mode) | LFOs, sequencers, MIDI inputs/outputs, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 4 | `CV output` | no modifier | filtered CV output (separated mode) | VCAs, LFOs, audio effects, MIDI inputs/outputs, CV inputs/outputs, sequencers, oscillators |

| Module options | Description | Settings |
|--|--|--|
| `control` | allows for combined or separate control of upward and downward CV changes | `linked`, `separate` |

back to [Categories & Modules](#categories-and-modules)

---

### Slew Limiter
Slew Limiter is similar in behaviour to CV Filter except that the rate of change in changes of CV happen linearly instead of logarithmically. This is the classic portamento, and can be used anywhere CV changes occur to give them a different feel. Try using an unlinked Slew Limiter with a stomp switch module to give more expression pedal-like behaviour to your stomp switch.

| | |
|-|-|
| Min blocks | 3 |
| Max blocks | 4 |
| Avg. CPU | 0.2% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `CV input` | CV input | connect CV source | LFOs, sequencers, MIDI inputs/outputs, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 2 | `slew rate` | time in seconds | determines slew rate. This time value changes the speed at which the CV source responds to changes from its current value. | LFOs, sequencers, MIDI inputs/outputs, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 3 | `CV output` | no modifier | outputs slew limited CV | VCAs, LFOs, audio effects, MIDI inputs/outputs, CV inputs/outputs, sequencers, oscillators |
| 2 | `rising lag` | time in seconds | determines time change factor of upward changes in CV (separated mode) | LFOs, sequencers, MIDI inputs/outputs, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 3 | `falling lag` | time in seconds | determines time change factor of downward changes in CV (separated mode) | LFOs, sequencers, MIDI inputs/outputs, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 4 | `CV output` | CV output | outputs slew limited CV (separated mode) | VCAs, LFOs, audio effects, MIDI inputs/outputs, CV inputs/outputs, sequencers, oscillators |

| Module options | Description | Settings |
|--|--|--|
| `control` | allows for combined or separate control of upward and downward slew limited CV changes | `linked`, `separate` |

back to [Categories & Modules](#categories-and-modules)

---

### Clock Divider
Clock Divider module will detect tempo of incoming CV upward changes, divide it by a user determined ratio, and output CV triggers at the resulting tempo. This can be a handy way of getting a tap tempo from a slightly irregular waveform.

| | |
|-|-|
| Min blocks | 4 |
| Max blocks | 5 |
| Avg. CPU | 0.14% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `input` | frequency in Hz, ms, or bpm (tap: no modifier) | sets the frequency at which the LFO oscillates (tap in: calculates rate of LFO via incoming CV input) | LFOs, sequencers, MIDI inputs/outputs, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 2 | `reset switch` | toggles between "waiting" and "armed" | an increase in CV will cease output, a new tap tempo at the input will continue on until reset switch is triggered again | footswitches/pushbuttons, LFOs, sequencers, MIDI inputs/outputs, CV inputs/outputs, expression pedals |
| 3 | `dividend` | select the numerator of your tap fraction from 1-32 | create your custom clock division fraction! if this number is higher than the one after it, your clock will be faster than your tap source. | LFOs, sequencers, MIDI inputs/outputs, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 4 | `divisor` | select the denominator of your tap fraction from 1-32 | create your custom clock division fraction! if this number is higher than the one before it, your clock will be slower than your tap source. | LFOs, sequencers, MIDI inputs/outputs, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 5 | `CV output` | no modifier | tap tempo CV output | tap tempo inputs, VCAs, audio effects, MIDI inputs/outputs, CV inputs/outputs, LFOs, sequencers, oscillators |

| Module options | Description | Settings |
|--|--|--|
| `input` | select clock frequency source. CV input allows you to dial it in with the knob or control with another source, tap will interpret changes in CV as a tap tempo | `cv`, `tap` |

back to [Categories & Modules](#categories-and-modules)

---

### Comparator
Comparator is a logic module that will switch CV on if positive input is equal to or greater than negative input, and off if positive input is less than negative input. Off can be defined as 0 or -1 by the output range. This can be useful if you'd like to have something happen, but only above a certain threshold.

| | |
|-|-|
| Min blocks | 3 |
| Max blocks | 3 |
| Avg. CPU | 0.04% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `CV positive input` | CV input positive threshold | sets incoming CV positive threshold | LFOs, sequencers, MIDI inputs/outputs, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 2 | `CV negative input` | CV input negative threshold | sets incoming CV negative threshold | LFOs, sequencers, MIDI inputs/outputs, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 3 | `CV output` | no modifier | CV output. If CV at positive side is greater than CV at negative side, CV output will be 1. If CV at positive side is lower than CV at negative side, CV output will be 0 or -1, depending on output range | VCAs, LFOs, audio effects, MIDI inputs/outputs, CV inputs/outputs, sequencers, oscillators, ADSRs |

| Module options | Description | Settings |
|--|--|--|
| `output` | determines range of CV output | `0 to 1`, `-1 to 1` |

back to [Categories & Modules](#categories-and-modules)

---

### In Switch
In Switch takes a selected quantity of CV inputs and allows you to switch between them to a single CV output. You can use this to select between LFOs to a CV source, external CV modules, or use in conjunction with the CV out switch to choose between ADSRs or other CV module chains.

| | |
|-|-|
| Min blocks | 4 |
| Max blocks | 18 |
| Avg. CPU | 0.2% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `CV input 1` | CV input | set or connect CV source | LFOs, sequencers, MIDI inputs/outputs, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 2 * | `CV input 2` | CV input | set or connect CV source | LFOs, sequencers, MIDI inputs/outputs, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 3 | `in select` | select value 0-1 | divides value from 0-1 between number of present switch inputs and selects CV source corresponding to value present | LFOs, sequencers, MIDI inputs/outputs, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 4 | `CV output` | no modifier | outputs selected CV source | VCAs, LFOs, audio effects, MIDI inputs/outputs, CV inputs/outputs, sequencers, oscillators, ADSRs |

| Module options | Description | Settings |
|--|--|--|
| `num inputs` | selects how many CV sources you'd like to switch between. Input parameters will be added for each source and the input select range from 0-1 will divide equally between them | `2`–`16` |

back to [Categories & Modules](#categories-and-modules)

---

### Out Switch
Out Switch takes a CV input and routes it between a set quantity of CV outputs. You can use it to select which sequencers, ADSRs, or tap tempos to send triggers to, etc.

| | |
|-|-|
| Min blocks | 4 |
| Max blocks | 18 |
| Avg. CPU | 0.2% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `CV input` | CV input | set or connect CV source | LFOs, sequencers, MIDI inputs/outputs, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 2 | `out select` | select value 0-1 | divides value from 0-1 between number of present switch outputs and selects CV output corresponding to value present. If only one output is present, a select value of 0 will turn switch off, a select value above 0 will turn switch on. | LFOs, sequencers, MIDI inputs/outputs, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 3 | `CV output 1` | no modifier | if selected, outputs CV input | VCAs, LFOs, audio effects, MIDI inputs/outputs, CV inputs/outputs, sequencers, oscillators, ADSRs |
| 4 * | `CV output 2` | no modifier | if selected, outputs CV input | VCAs, LFOs, audio effects, MIDI inputs/outputs, CV inputs/outputs, sequencers, oscillators, ADSRs |

| Module options | Description | Settings |
|--|--|--|
| `# of outputs` | selects how many CV outputs you'd like to switch between. Output parameters will be added for each source and the output select range from 0-1 will divide equally between them | `2`–`16` |

back to [Categories & Modules](#categories-and-modules)

---

### Quantizer
Quantizer will interpret incoming CV and send its nearest equivalent note as a CV output.

| | |
|-|-|
| Min blocks | 2 |
| Max blocks | 4 |
| Avg. CPU | 1% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `CV input` | CV input | set or connect CV source | LFOs, sequencers, MIDI inputs/outputs, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 2 * | `key` | key of output | choose a key between A and G#. connect CV to control remotely | LFOs, sequencers, MIDI inputs/outputs, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 3 * | `scale` | scale type | choose between chromatic, major, minor natural, minor harmonic, or minor melodic. connect CV to control remotely | LFOs, sequencers, MIDI inputs/outputs, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 4 | `CV output` | no modifier | outputs CV corrected to match closest note | oscillators, VCAs, LFOs, audio effects, MIDI inputs/outputs, CV inputs/outputs, sequencers |

| Module options | Description | Settings |
|--|--|--|
| `key/scale jacks` | toggles presence of key and scale jacks | `on`, `off` |
| `scale` | select the scale for quantization | `chromatic`, `major`, `minor natural`, `minor harmonic`, `minor melodic`, `+ extended scales` |
| `mode` | select basic or extended scale library | `basic`, `extended` |

back to [Categories & Modules](#categories-and-modules)

---

### Steps
Steps will interpret incoming changes in upward CV as a tempo, split the wave cycle into a set number of steps, and then send the CV present at the input during each step to the output. You can use this to convert a nice smooth LFO and reduce its resolution into steps.

| | |
|-|-|
| Min blocks | 3 |
| Max blocks | 3 |
| Avg. CPU | 0.7% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `CV input` | CV input | connect CV source | LFOs, sequencers, MIDI inputs/outputs, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 2 | `quant steps` | number of steps to split wave cycle into | select number of steps from 2 to 63. A higher quantity of steps results in a smoother output wave. | LFOs, sequencers, MIDI inputs/outputs, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 3 | `CV output` | no modifier | outputs quantized CV | oscillators, VCAs, ADSRs, LFOs, audio effects, MIDI inputs/outputs, CV inputs/outputs, sequencers |

back to [Categories & Modules](#categories-and-modules)

---

### Multiplier
Multiply will take the CV signal present at each input and multiply them together at the output. In this way you can use one CV source to amplify, tame, or modulate another. Remember that a value of 0 at any input will result in 0 at the output. It's math!

| | |
|-|-|
| Min blocks | 3 |
| Max blocks | 9 |
| Avg. CPU | 0.2% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `CV input 1` | CV input | set or connect CV source | LFOs, sequencers, MIDI inputs/outputs, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 2 | `CV input 2` | CV input | set or connect CV source | LFOs, sequencers, MIDI inputs/outputs, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 3 | `CV output` | no modifier | outputs multiplied CV | oscillators, VCAs, LFOs, audio effects, MIDI inputs/outputs, CV inputs/outputs, sequencers |

| Module options | Description | Settings |
|--|--|--|
| `num inputs` | select how many sources you'd like to multiply together. Each value above 2 will add a corresponding input jack. | `2`–`8` |

back to [Categories & Modules](#categories-and-modules)

---

### Random
Random will generate numbers continuously or when triggered with the option trigger in. Connect an LFO to the trigger in to get regularly updated random numbers. Try it with a CV in switch to toggle some randomness into your life.

| | |
|-|-|
| Min blocks | 1 |
| Max blocks | 2 |
| Avg. CPU | 0.1% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 * | `trigger in` | CV input | a change in CV here will generate a new random number and hold it at the output | LFOs, sequencers, MIDI inputs/outputs, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 2 | `CV output` | no modifier | generates constantly refreshing random numbers until stopped by optional trigger | oscillators, VCAs, LFOs, audio effects, MIDI inputs/outputs, CV inputs/outputs, sequencers |

| Module options | Description | Settings |
|--|--|--|
| `output` | determines range of CV output | `0 to 1`, `-1 to 1` |
| `new val on trig` | toggles presence of trigger in parameter | `on`, `off` |

back to [Categories & Modules](#categories-and-modules)

---

### Rhythm
Rhythm will take an incoming CV signal, interpret it as a series of triggers, record those triggers and play them back at the output.

| | |
|-|-|
| Min blocks | 4 |
| Max blocks | 5 |
| Avg. CPU | 0.5% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `rec start-stop` | CV input | triggers starting and stopping of recording | footswitches/pushbuttons, LFOs, sequencers, MIDI inputs/outputs, CV inputs/outputs, expression pedals |
| 2 | `rhythm in` | CV input | connect CV to be recorded | LFOs, sequencers, MIDI inputs/outputs, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 3 | `play` | CV input | triggers playback of rhythm | footswitches/pushbuttons, LFOs, sequencers, MIDI inputs/outputs, CV inputs/outputs, expression pedals |
| 4 * | `play done` | no modifier | goes high when playback is done | sequencers, ADSRs, other triggers |
| 5 | `rhythm out` | no modifier | CV rhythm output — interprets recorded loop as series of rhythmic pulses | tap tempo inputs, ADSRs, oscillators, VCAs, LFOs, audio effects, MIDI inputs/outputs, CV inputs/outputs, sequencers |

| Module options | Description | Settings |
|--|--|--|
| `done ctl` | toggles presence of play done parameter | `on`, `off` |

back to [Categories & Modules](#categories-and-modules)

---

### Tap To CV
Outputs a CV value proportional to the tap tempo input.

| | |
|-|-|
| Min blocks | 2 |
| Max blocks | 4 |
| Avg. CPU | 0.12% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `tap input` | no modifier | connect tap source, MIDI clock, or LFO | footswitches/pushbuttons, LFOs, sequencers, MIDI inputs/outputs, CV inputs/outputs |
| 2 * | `min time` | time in s | set the tap tempo minimum time | LFOs, sequencers, MIDI inputs/outputs, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 3 * | `max time` | time in s | set the tap tempo maximum time | LFOs, sequencers, MIDI inputs/outputs, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 4 | `output` | no modifier | outputs CV as a value proportional to the detected frequency of incoming taps | oscillators, VCAs, LFOs, audio effects, MIDI inputs/outputs, CV inputs/outputs, sequencers |

| Module options | Description | Settings |
|--|--|--|
| `range control` | toggles presence of min time and max time buttons | `on`, `off` |
| `time scale` | determines how module interprets cv output from tap source | `linear`, `exponential` |

back to [Categories & Modules](#categories-and-modules)

---

### CV Mixer
An 8 channel CV Mixer and Attenuverter. The atten parameter for each channel controls amount and polarity: a CV value of 1.0 passes the full signal, 0.5 fully attenuates it, and 0.0 fully inverts it.

| | |
|-|-|
| Min blocks | 3 |
| Max blocks | 17 |
| Avg. CPU | 0.30% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `cv in 1` | CV input | connect input CV for mixer/attenuverter channel 1 | LFOs, sequencers, MIDI inputs/outputs, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 2 * | `cv in 2` | CV input | connect input CV for mixer/attenuverter channel 2 | LFOs, sequencers, MIDI inputs/outputs, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 3 | `atten 1` | CV input slider | set mix/atten level for channel 1: a CV value of 1.0 passes the full signal, 0.5 fully attenuates it, and 0.0 fully inverts it. | LFOs, sequencers, MIDI inputs/outputs, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 4 * | `atten 2` | CV input slider | set mix/atten level for channel 2: a CV value of 1.0 passes the full signal, 0.5 fully attenuates it, and 0.0 fully inverts it. | LFOs, sequencers, MIDI inputs/outputs, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 5 | `cv output` | no modifier | outputs mixed/attenuated CV | oscillators, VCAs, LFOs, audio effects, MIDI inputs/outputs, CV inputs/outputs, sequencers |

| Module options | Description | Settings |
|--|--|--|
| `num channels` | select number of channels from 1 to 8. each additional channel adds both a CV input block and a mix/atten slider | `1`–`8` |
| `mode` | select output calculation type. "summing" will add all outputs together, clipping anything outside the +1/-1 CV range, while "average" will output the mean of the outputs, ensuring that the output doesn't get clipped | `summing`, `average` |

back to [Categories & Modules](#categories-and-modules)

---

### Logic Gate
Perform logical operations with CV inputs.

| | |
|-|-|
| Min blocks | 3 |
| Max blocks | 10 |
| Avg. CPU | 0.1% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `CV input 1` | CV input | first CV input for logic operation | LFOs, sequencers, MIDI inputs/outputs, CV inputs/outputs, comparators, flip flops |
| 2 | `CV input 2` | CV input | second CV input for logic operation | LFOs, sequencers, MIDI inputs/outputs, CV inputs/outputs, comparators, flip flops |
| 3 | `CV output` | no modifier | outputs result of selected logic operation | VCAs, ADSRs, sequencers, oscillators, MIDI inputs/outputs, CV inputs/outputs |

| Module options | Description | Settings |
|--|--|--|
| `operation` | select the logic operation to perform | `AND`, `OR`, `NOT`, `NOR`, `NAND`, `XOR`, `XNOR` |
| `num inputs` | select number of inputs | `2`–`8` |

back to [Categories & Modules](#categories-and-modules)

---

## Analysis Modules

### Onset Detector
Onset Detector looks for incoming audio signal and generates a CV trigger at the peaks. Use a regular audio source to advance a sequencer, tap a tempo, etc.

| | |
|-|-|
| Min blocks | 2 |
| Max blocks | 3 |
| Avg. CPU | 12.3% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `audio in` | no modifier | connect audio input | inputs, audio effect outputs, VCAs |
| 2 * | `sensitivity` | value in CV | determines signal strength at which incoming audio triggers outgoing CV | MIDI inputs/outputs, LFOs, sequencers, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 3 | `CV output` | no modifier | sends CV trigger when incoming audio surpasses threshold | tap tempo inputs, ADSRs, oscillators, VCAs, LFOs, audio effects, MIDI inputs/outputs, CV inputs/outputs, sequencers |

| Module options | Description | Settings |
|--|--|--|
| `sensitivity` | toggles presence of sensitivity jack | `on`, `off` |

back to [Categories & Modules](#categories-and-modules)

---

### Env Follower
Envelope Follower will interpret an incoming audio signal as a CV signal based on its signal strength. Use this to trigger filter sweeps, audio effects parameters, LFO rates, etc. The connection strength can act as a sensitivity control.

| | |
|-|-|
| Min blocks | 2 |
| Max blocks | 4 |
| Avg. CPU | 2.5% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `audio in` | no modifier | connect audio input | inputs, audio effect outputs, VCAs |
| 2 * | `rise time` | time in seconds | determines time taken for CV to reach peak once audio is detected at input | MIDI inputs/outputs, LFOs, sequencers, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 3 * | `fall time` | time in seconds | determines time taken for CV to reach zero once audio is no longer detected at input | MIDI inputs/outputs, LFOs, sequencers, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 4 | `CV output` | no modifier | sends incoming audio level as CV output | ADSRs, oscillators, VCAs, LFOs, audio effects, MIDI inputs/outputs, CV inputs/outputs, sequencers |

| Module options | Description | Settings |
|--|--|--|
| `rise/fall time` | toggles presence of rise and fall time parameters | `on`, `off` |
| `output scale` | determines curve of dB to CV interpretation. log is recommended for use with outside audio source, log or linear both work well with internally generated audio | `log`, `linear` |

back to [Categories & Modules](#categories-and-modules)

---

### Pitch Detector
Pitch Detector interprets the pitch of a connected audio signal as a CV note output, which can be sent to an oscillator or quantizer. You can affect the tracking by changing the connection strength between the audio source and the audio input, and transpose which note the oscillator will generate using the connection strength to the oscillator. Click knob to toggle display between frequency in Hz and note.

| | |
|-|-|
| Min blocks | 2 |
| Max blocks | 2 |
| Avg. CPU | 2.3% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `audio in` | no modifier | connect audio input | inputs, audio effect outputs, VCAs, oscillators |
| 2 | `pitch out` | no modifier | interprets pitch of incoming audio into a music note | oscillators, VCAs, LFOs, audio effects, MIDI inputs/outputs, CV inputs/outputs, sequencers |

back to [Categories & Modules](#categories-and-modules)

---

## Effect Modules

### Tone Control EQ
Tone Control is a 3 or 4 band tone control. Use this in conjunction with Distortion, Delay w/Mod, Reverb, or even a clean sound to fundamentally change its character.

| | |
|-|-|
| Min blocks | 6 |
| Max blocks | 10 |
| Avg. CPU | 2.2% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `aud in L` | no modifier | connect audio input | inputs, audio effect outputs, VCAs, oscillators |
| 2 * | `aud in R` | no modifier | connect second audio input | inputs, audio effect outputs, VCAs, oscillators |
| 3 | `low shelf` | level in dB | adjust gain of all frequencies below X Hz | MIDI inputs/outputs, LFOs, sequencers, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 4 | `mid gain 1` | level in dB | adjust gain of mid frequency 1 | MIDI inputs/outputs, LFOs, sequencers, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 5 | `mid frequency 1` | frequency in Hz | adjust frequency of mid frequency 1 | MIDI inputs/outputs, LFOs, sequencers, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 6 * | `mid gain 2` | level in dB | adjust gain of mid frequency 2 | MIDI inputs/outputs, LFOs, sequencers, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 7 * | `mid frequency 2` | frequency in Hz | adjust frequency of mid frequency 2 | MIDI inputs/outputs, LFOs, sequencers, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 8 | `high shelf` | level in dB | adjust gain of all frequencies above X Hz | MIDI inputs/outputs, LFOs, sequencers, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 9 | `output L` | no modifier | connect audio output | audio inputs/outputs, VCAs, audio effects, FM inputs, analysis modules |
| 10 * | `output R` | no modifier | connect second audio output | audio inputs/outputs, VCAs, audio effects, FM inputs, analysis modules |

| Module options | Description | Settings |
|--|--|--|
| `channels` | select if you'd like to EQ one or two channels | `1`, `2` |
| `num mid bands` | toggles presence of mid frequency band 2 | `1`, `2` |

back to [Categories & Modules](#categories-and-modules)

---

### Delay w Mod
Delay is one of the classic delay effects. Delay w/Mod differs from the Delay Line module in that it runs a dry signal alongside the wet, has a feedback section, and a modulation section. Set the delay time either by tap or rotary/CV input. Optional stereo outputs round out the list of features. You can change the character of the delay effect with the "type" option, and/or by setting your mix to wet only, adding tone control and other effects to the output, and connecting your audio source directly to your output (bypassing the delay module) to act as the dry signal.

| | |
|-|-|
| Min blocks | 7 |
| Max blocks | 9 |
| Avg. CPU | 7%–15% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `audio in1` | no modifier | connect audio input | inputs, audio effect outputs, VCAs, oscillators |
| 2 * | `audio in2` | no modifier | connect audio input (stereo) | inputs, audio effect outputs, VCAs, oscillators |
| 3 | `delay time` | time in seconds, bpm, or Hz | click knob to cycle views of delay time. this jack acts as the tap tempo in when selected in control. connect stomp switch, pushbutton, LFO etc | MIDI inputs/outputs, LFOs, sequencers, CV inputs/outputs, expression pedals, stompswitches/pushbuttons |
| 4 | `feedback` | level in dB | sets feedback in dB. Achieve self oscillation by going fully clockwise to 0dB | MIDI inputs/outputs, LFOs, sequencers, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 5 | `mod rate` | rate in Hz | modulation rate in Hz | MIDI inputs/outputs, LFOs, sequencers, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 6 | `mod depth` | level in CV | modulation depth as CV value | MIDI inputs/outputs, LFOs, sequencers, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 7 | `mix` | level in dB | wet to dry signal level. go from no audible delay at -inf dB to no audible dry signal at -0.00dB | MIDI inputs/outputs, LFOs, sequencers, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 8 | `audio out1` | no modifier | connect audio output | audio inputs/outputs, VCAs, audio effects, FM inputs, analysis modules |
| 9 * | `audio out2` | no modifier | connect secondary audio output if present | audio inputs/outputs, VCAs, audio effects, FM inputs, analysis modules |

| Module options | Description | Settings |
|--|--|--|
| `channels` | select if you'd like mono, mono to stereo, or stereo channels | `mono`, `mono to stereo`, `stereo` |
| `control` | toggles behaviour of tempo input between tap and cv | `tap`, `cv` |
| `type` | select character of delay line | `clean`, `tape`, `old tape`, `bbd` |
| `tap ratio` | when using tap tempo control mode, this option determines the ratio of repeats per tap cycle | `1:1`, `2:3`, `1:2`, `1:3`, `3:8`, `1:4`, `3:16`, `1:8`, `1:16`, `1:32` |

back to [Categories & Modules](#categories-and-modules)

---

### Ping Pong Delay
Ping Pong Delay is almost identical to the Delay w/Mod except for one key aspect: the delay repeats ping pong from left to right across stereo outputs. When stereo inputs are selected, one input will ping while the other pongs, followed by a pong while the other pings into the opposite and then correct outputs.

| | |
|-|-|
| Min blocks | 8 |
| Max blocks | 9 |
| Avg. CPU | 10.4%–16.4% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `audio in1` | no modifier | connect audio input | inputs, audio effect outputs, VCAs, oscillators |
| 2 * | `audio in2` | no modifier | connect audio input (stereo) | inputs, audio effect outputs, VCAs, oscillators |
| 3 | `delay time` | time in seconds, bpm, or Hz | click knob to cycle views of delay time. this jack acts as the tap tempo in when selected in control. connect stomp switch, pushbutton, LFO etc | MIDI inputs/outputs, LFOs, sequencers, CV inputs/outputs, expression pedals, stompswitches/pushbuttons |
| 4 | `feedback` | level in dB | sets feedback in dB. Achieve self oscillation by going fully clockwise to 0dB | MIDI inputs/outputs, LFOs, sequencers, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 5 | `mod rate` | rate in Hz | modulation rate in Hz | MIDI inputs/outputs, LFOs, sequencers, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 6 | `mod depth` | level in CV | modulation depth as CV value | MIDI inputs/outputs, LFOs, sequencers, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 7 | `mix` | level in dB | wet to dry signal level. go from no audible delay at -inf dB to no audible dry signal at -0.00dB | MIDI inputs/outputs, LFOs, sequencers, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 8 | `audio out1` | no modifier | connect audio output | audio inputs/outputs, VCAs, audio effects, FM inputs, analysis modules |
| 9 | `audio out2` | no modifier | connect secondary audio output | audio inputs/outputs, VCAs, audio effects, FM inputs, analysis modules |

| Module options | Description | Settings |
|--|--|--|
| `channels` | select if you'd like mono to stereo or stereo channels | `mono to stereo`, `stereo` |
| `control` | toggles behaviour of tempo input between tap and cv | `tap`, `cv` |
| `type` | select character of delay line | `clean`, `tape`, `old tape`, `bbd` |
| `tap ratio` | when using tap tempo control mode, this option determines the ratio of repeats per tap cycle | `1:1`, `2:3`, `1:2`, `1:3`, `3:8`, `1:4`, `3:16`, `1:8`, `1:16`, `1:32` |

back to [Categories & Modules](#categories-and-modules)

---

### OD & Distortion
The OD & Distortion module provides classic overdrive and distortion tones.

| | |
|-|-|
| Min blocks | 4 |
| Max blocks | 4 |
| Avg. CPU | 14.2% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `audio in` | no modifier | connect audio input | inputs, audio effect outputs, VCAs, oscillators |
| 2 | `input gain` | gain in dB | sets input gain of distortion. the louder the input gain, the higher the distortion factor | MIDI inputs/outputs, LFOs, sequencers, CV inputs/outputs, expression pedals, stompswitches/pushbuttons |
| 3 | `output gain` | gain in dB | sets master volume of module. as input gain rises, volume increases just like a typical distortion pedal. use output gain to compensate for this | MIDI inputs/outputs, LFOs, sequencers, CV inputs/outputs, expression pedals, stompswitches/pushbuttons |
| 4 | `audio out` | no modifier | connect audio output | audio inputs/outputs, VCAs, audio effects, FM inputs, analysis modules |

| Module options | Description | Settings |
|--|--|--|
| `model` | choose between several flavours of distortion | `plexi`, `germ`, `classic`, `pushed` |

back to [Categories & Modules](#categories-and-modules)

---

### Fuzz
The Fuzz module provides gnarly fuzz tones for your sonic enjoyment.

| | |
|-|-|
| Min blocks | 4 |
| Max blocks | 4 |
| Avg. CPU | 14.1% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `audio in` | no modifier | connect audio input | inputs, audio effect outputs, VCAs, oscillators |
| 2 | `input gain` | gain in dB | sets input gain of distortion. the louder the input gain, the higher the distortion factor | MIDI inputs/outputs, LFOs, sequencers, CV inputs/outputs, expression pedals, stompswitches/pushbuttons |
| 3 | `output gain` | gain in dB | sets master volume of module. as input gain rises, volume increases just like a typical distortion pedal. use output gain to compensate for this | MIDI inputs/outputs, LFOs, sequencers, CV inputs/outputs, expression pedals, stompswitches/pushbuttons |
| 4 | `audio out` | no modifier | connect audio output | audio inputs/outputs, VCAs, audio effects, FM inputs, analysis modules |

| Module options | Description | Settings |
|--|--|--|
| `model` | choose between several flavours of fuzz | `efuzzy`, `burly`, `scoopy`, `ugly` |

back to [Categories & Modules](#categories-and-modules)

---

### Compressor
Compression is a vastly useful audio tool that controls your signal level according to changes in input level. You can create natural reductions in gain to help things mix better, help tame or enhance transients in synth or instrument signals, etc. The optional stereo side will trigger the module's functions in unison on both channels, creating true stereo compression.

| | |
|-|-|
| Min blocks | 3 |
| Max blocks | 9 |
| Avg. CPU | 2.4% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `audio in` | no modifier | connect audio input | inputs, audio effect outputs, VCAs, oscillators |
| 2 * | `audio inR` | no modifier | connect second channel of audio input | MIDI inputs/outputs, LFOs, sequencers, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 3 | `threshold` | level in dB | input level at which compressor engages | MIDI inputs/outputs, LFOs, sequencers, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 4 * | `attack` | time in ms | time in which compressor reacts to incoming signal | MIDI inputs/outputs, LFOs, sequencers, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 5 * | `release` | time in s | time in which compressor returns to its initial level once signal falls below threshold | MIDI inputs/outputs, LFOs, sequencers, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 6 * | `ratio` | ratio in X:1 | determines how aggressive the gain reduction is | MIDI inputs/outputs, LFOs, sequencers, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 7 * | `sidechain in` | no modifier | connect an audio input from which to receive dynamic information | inputs, audio effect outputs, VCAs, oscillators |
| 8 | `audio out` | no modifier | connects audio compressed from input | audio inputs/outputs, VCAs, audio effects, FM inputs, analysis modules |
| 9 * | `audio outR` | no modifier | connects audio compressed from input R | audio inputs/outputs, VCAs, audio effects, FM inputs, analysis modules |

| Module options | Description | Settings |
|--|--|--|
| `attack ctrl` | toggles presence of attack control. if not selected, attack is 5.0 ms | `on`, `off` |
| `release ctrl` | toggles presence of release control. if not selected, release is 1.05 s | `on`, `off` |
| `ratio ctrl` | toggles presence of ratio control. if not selected, ratio is 10.5:1 | `on`, `off` |
| `channels` | select if you'd like 1 channel of compression or 2. in 2 channel mode, both channels trigger the attack and release in parallel | `1`, `2` |
| `sidechain` | select if you'd like the compressor to engage based on the signal dynamic at its input or from another audio signal | `input`, `sidechain` |

back to [Categories & Modules](#categories-and-modules)

---

### Gate
A standard in studio audio tools, gate can also be used as the key ingredient in gated fuzz tones. Use it to filter out noise from an audio source, or to cut the end off of a reverb's decay, thus creating the classic gated reverb sound. Make sure to experiment with the sidechain input!

| | |
|-|-|
| Min blocks | 4 |
| Max blocks | 8 |
| Avg. CPU | 2.8% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `audio inL` | no modifier | connect audio input | inputs, audio effect outputs, VCAs, oscillators |
| 2 * | `audio inR` | no modifier | connect audio input (stereo) | inputs, audio effect outputs, VCAs, oscillators |
| 3 | `threshold` | level in dB | sets the level at which the audio gate will open and close | MIDI inputs/outputs, LFOs, sequencers, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 4 * | `attack` | time in seconds | once threshold is reached, sets the time it takes for audio gate to fully open. go from sharp and snappy to long and gentle | MIDI inputs/outputs, LFOs, sequencers, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 5 * | `release` | time in seconds | once gate is fully open, sets time the time to close the gate once audio falls back below threshold | MIDI inputs/outputs, LFOs, sequencers, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 6 * | `sidechain in` | no modifier | connect audio input from which gate receives its dynamic information | inputs, audio effect outputs, VCAs, oscillators |
| 7 | `audio outL` | no modifier | connect audio output | audio inputs/outputs, VCAs, audio effects, FM inputs, analysis modules |
| 8 * | `audio outR` | no modifier | connect audio output (stereo) | audio inputs/outputs, VCAs, audio effects, FM inputs, analysis modules |

| Module options | Description | Settings |
|--|--|--|
| `attack ctrl` | toggles presence of attack control. if not selected, attack is 50.5 ms | `on`, `off` |
| `release ctrl` | toggles presence of release control. if not selected, release is 1.03 s | `on`, `off` |
| `channels` | select if you'd like mono, mono to stereo, or stereo channels | `mono`, `mono to stereo`, `stereo` |
| `sidechain` | select if you'd like the gate to open based on the signal dynamic at its input or from another audio signal | `input`, `sidechain` |

back to [Categories & Modules](#categories-and-modules)

---

### Plate Reverb
Bask in the ebb and flow of steel molecules as they vibrate with the warm vintage vibe of so many classic recordings.

| | |
|-|-|
| Min blocks | 7 |
| Max blocks | 8 |
| Avg. CPU | 16.7% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `input L` | no modifier | connect audio input | inputs, audio effect outputs, VCAs, oscillators |
| 2 | `input R` | no modifier | connect second audio input | inputs, audio effect outputs, VCAs, oscillators |
| 3 | `decay time` | time in s | length of time for reverberations to trail off | MIDI inputs/outputs, LFOs, sequencers, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 4 | `low eq` | level in dB | cuts or boosts low frequencies from wet signal | MIDI inputs/outputs, LFOs, sequencers, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 5 | `high eq` | level in dB | cuts or boosts high frequencies from wet signal | MIDI inputs/outputs, LFOs, sequencers, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 6 | `mix` | value from 0-100 | sets mix level from 0 (fully dry) to 100 (fully wet) | MIDI inputs/outputs, LFOs, sequencers, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 7 | `output L` | no modifier | connect audio output | audio inputs/outputs, VCAs, audio effects, FM inputs, analysis modules |
| 8 | `output R` | no modifier | connect second audio output | audio inputs/outputs, VCAs, audio effects, FM inputs, analysis modules |

back to [Categories & Modules](#categories-and-modules)

---

### Hall Reverb
It's like you're there, looking up at the pulpit, with the warm sun casting in beams of coloured light from the stained glass windows. You're in reverb heaven, now.

| | |
|-|-|
| Min blocks | 7 |
| Max blocks | 8 |
| Avg. CPU | 17% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `input L` | no modifier | connect audio input | inputs, audio effect outputs, VCAs, oscillators |
| 2 | `input R` | no modifier | connect second audio input | inputs, audio effect outputs, VCAs, oscillators |
| 3 | `decay time` | time in s | length of time for reverberations to trail off | MIDI inputs/outputs, LFOs, sequencers, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 4 | `low eq` | level in dB | cuts or boosts low frequencies from wet signal | MIDI inputs/outputs, LFOs, sequencers, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 5 | `high eq (lpf freq)` | frequency in Hz | select cutoff point of high frequencies from wet signal | MIDI inputs/outputs, LFOs, sequencers, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 6 | `mix` | value from 0-100 | sets mix level from 0 (fully dry) to 100 (fully wet) | MIDI inputs/outputs, LFOs, sequencers, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 7 | `output L` | no modifier | connect audio output | audio inputs/outputs, VCAs, audio effects, FM inputs, analysis modules |
| 8 | `output R` | no modifier | connect second audio output | audio inputs/outputs, VCAs, audio effects, FM inputs, analysis modules |

back to [Categories & Modules](#categories-and-modules)

---

### Room Reverb
Well, you're cooped up in your little room. But that's okay, because you've got some tasty room reverb to swim around in. Don't worry, somebody will come get you out someday.

| | |
|-|-|
| Min blocks | 7 |
| Max blocks | 8 |
| Avg. CPU | 17% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `input L` | no modifier | connect audio input | inputs, audio effect outputs, VCAs, oscillators |
| 2 | `input R` | no modifier | connect second audio input | inputs, audio effect outputs, VCAs, oscillators |
| 3 | `decay time` | time in s | length of time for reverberations to trail off | MIDI inputs/outputs, LFOs, sequencers, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 4 | `low eq` | level in dB | cuts or boosts low frequencies from wet signal | MIDI inputs/outputs, LFOs, sequencers, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 5 | `high eq (lpf freq)` | frequency in Hz | select cutoff point of high frequencies from wet signal | MIDI inputs/outputs, LFOs, sequencers, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 6 | `mix` | value from 0-100 | sets mix level from 0 (fully dry) to 100 (fully wet) | MIDI inputs/outputs, LFOs, sequencers, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 7 | `output L` | no modifier | connect audio output | audio inputs/outputs, VCAs, audio effects, FM inputs, analysis modules |
| 8 | `output R` | no modifier | connect second audio output | audio inputs/outputs, VCAs, audio effects, FM inputs, analysis modules |

back to [Categories & Modules](#categories-and-modules)

---

### Ghostverb
A spooky, ghostly reverb sound akin to the Ghost mode found in the Empress Reverb. Scare the crap out of all your friends!

| | |
|-|-|
| Min blocks | 6 |
| Max blocks | 8 |
| Avg. CPU | 18%–31% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `audio in1` | no modifier | connect audio input | inputs, audio effect outputs, VCAs, oscillators |
| 2 * | `audio in2` | no modifier | connect second audio input | inputs, audio effect outputs, VCAs, oscillators |
| 3 | `decay/feedback` | value in CV | sets overall length of reverb tails | MIDI inputs/outputs, LFOs, sequencers, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 4 | `rate` | rate in Hz | sets rate of ghostly modulation | MIDI inputs/outputs, LFOs, sequencers, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 5 | `resonance` | value in CV | sets the resonance of ghostly modulation | MIDI inputs/outputs, LFOs, sequencers, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 6 | `mix` | value in CV | sets mix level from 0 (fully dry) to 100 (fully wet) | MIDI inputs/outputs, LFOs, sequencers, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 7 | `audio out1` | no modifier | connect audio output | audio inputs/outputs, VCAs, audio effects, FM inputs, analysis modules |
| 8 * | `audio out2` | no modifier | connect second audio output | audio inputs/outputs, VCAs, audio effects, FM inputs, analysis modules |

| Module options | Description | Settings |
|--|--|--|
| `channels` | select if you'd like mono, mono to stereo, or stereo channels | `mono`, `mono to stereo`, `stereo` |

back to [Categories & Modules](#categories-and-modules)

---

### Reverb Lite
A straightforward CPU friendly reverb sound to add some smoosh to heavier workload patches.

| | |
|-|-|
| Min blocks | 4 |
| Max blocks | 6 |
| Avg. CPU | 6%–7% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `input L` | no modifier | connect audio input | inputs, audio effect outputs, VCAs, oscillators |
| 2 * | `input R` | no modifier | connect second audio input | inputs, audio effect outputs, VCAs, oscillators |
| 3 | `decay time` | time in s | sets overall length of reverb tails | MIDI inputs/outputs, LFOs, sequencers, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 4 | `mix` | value in CV | sets mix level from 0 (fully dry) to 100 (fully wet) | MIDI inputs/outputs, LFOs, sequencers, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 5 | `output L` | no modifier | connect audio output | audio inputs/outputs, VCAs, audio effects, FM inputs, analysis modules |
| 6 * | `output R` | no modifier | connect second audio output | audio inputs/outputs, VCAs, audio effects, FM inputs, analysis modules |

| Module options | Description | Settings |
|--|--|--|
| `channels` | select if you'd like mono, mono to stereo, or stereo channels | `mono`, `mono to stereo`, `stereo` |

back to [Categories & Modules](#categories-and-modules)

---

### Phaser
Set to stun, Phaser shifts the phase over a set quantity of stages and sweeps the frequency of these poles at a set rate. An optional stereo channel rounds out the list of features.

| | |
|-|-|
| Min blocks | 6 |
| Max blocks | 8 |
| Avg. CPU | 5%–10% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `input left` | no modifier | connect audio input | inputs, audio effect outputs, VCAs, oscillators |
| 2 * | `input right` | no modifier | connect second audio input | inputs, audio effect outputs, VCAs, oscillators |
| 3 | `control in` | rate in Hz, bpm, or ms (click knob to cycle views) | depending on how you set the control mode: dial in a rate, tap in a tempo, or connect a CV source | MIDI inputs/outputs, LFOs, sequencers, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 4 | `resonance` | level in dB | phased signal can be fed back into input for resonance. dial this in from none all the way to self oscillation | MIDI inputs/outputs, LFOs, sequencers, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 5 | `width` | level in CV | determines the width of the phased effect | MIDI inputs/outputs, LFOs, sequencers, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 6 | `mix` | percentage in CV | mix controls the level of uneffected signal to phased signal. go from fully dry to fully wet | MIDI inputs/outputs, LFOs, sequencers, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 7 | `output left` | no modifier | connect audio output | audio inputs/outputs, VCAs, audio effects, FM inputs, analysis modules |
| 8 * | `output right` | no modifier | connect second audio output | audio inputs/outputs, VCAs, audio effects, FM inputs, analysis modules |

| Module options | Description | Settings |
|--|--|--|
| `channels` | select phaser audio path | `mono`, `mono to stereo`, `stereo` |
| `control` | select control method over phaser. rate is the typical phaser pedal behaviour with an internal LFO, tap tempo allows you to connect a CV input to tap a tempo into the internal LFO, and CV direct will allow you to connect an external CV source to augment the phase directly. | `rate`, `tap tempo`, `cv direct` |
| `number of stages` | select number of phasing stages. the fewer the stages, the more subtle and classic the phasing. more stages will result in a lusher effect | `2`, `4`, `6`, `8`, `10`, `12` |

back to [Categories & Modules](#categories-and-modules)

---

### Chorus
The classic chorus effect. A nice sounding, fairly standard chorus. Get wackier sounds from it by using CV direct, or build your own from LFOs and delay lines!

| | |
|-|-|
| Min blocks | 6 |
| Max blocks | 8 |
| Avg. CPU | 6%–10% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `input left` | no modifier | connect audio input | inputs, audio effect outputs, VCAs, oscillators |
| 2 * | `input right` | no modifier | connect second audio input | inputs, audio effect outputs, VCAs, oscillators |
| 3 | `control in` | rate in Hz, bpm, or ms (click knob to cycle views) | depending on how you set the control mode: dial in a rate, tap in a tempo, or connect a CV source | MIDI inputs/outputs, LFOs, sequencers, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 4 | `width` | level in CV | sets width of modulation | MIDI inputs/outputs, LFOs, sequencers, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 5 | `tone tilt eq` | eq tilt in dB | a subtle tone control on the wet signal. from flat, negative values dial out high end and add warmth, while positive values cut bass and add highs | MIDI inputs/outputs, LFOs, sequencers, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 6 | `mix` | percentage in CV | mix controls the level of uneffected signal to modulated signal. go from fully dry to fully wet | MIDI inputs/outputs, LFOs, sequencers, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 7 | `output left` | no modifier | connect audio output | audio inputs/outputs, VCAs, audio effects, FM inputs, analysis modules |
| 8 * | `output right` | no modifier | connect second audio output | audio inputs/outputs, VCAs, audio effects, FM inputs, analysis modules |

| Module options | Description | Settings |
|--|--|--|
| `channels` | select chorus audio path | `mono`, `mono to stereo`, `stereo` |
| `control` | select control method over chorus | `rate`, `tap tempo`, `cv direct` |
| `type` | select chorus type | work in progress |

back to [Categories & Modules](#categories-and-modules)

---

### Vibrato
Vibrato is your typical pitch bending, wet only sound you'd find on such classic units as the Empress Nebulus, just to name one. Get bendy!

| | |
|-|-|
| Min blocks | 4 |
| Max blocks | 6 |
| Avg. CPU | 3.2%–5% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `input left` | no modifier | connect audio input | inputs, audio effect outputs, VCAs, oscillators |
| 2 * | `input right` | no modifier | connect second audio input | inputs, audio effect outputs, VCAs, oscillators |
| 3 | `control in` | rate in Hz, bpm, or ms (click knob to cycle views) | depending on how you set the control mode: dial in a rate, tap in a tempo, or connect a CV source | MIDI inputs/outputs, LFOs, sequencers, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 4 | `width` | level in CV | sets width of vibrato effect | MIDI inputs/outputs, LFOs, sequencers, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 5 | `output left` | no modifier | connect audio output | audio inputs/outputs, VCAs, audio effects, FM inputs, analysis modules |
| 6 * | `output right` | no modifier | connect second audio output | audio inputs/outputs, VCAs, audio effects, FM inputs, analysis modules |

| Module options | Description | Settings |
|--|--|--|
| `channels` | select vibrato audio path | `mono`, `mono to stereo`, `stereo` |
| `control` | select control method over vibrato | `rate`, `tap tempo`, `cv direct` |
| `waveform` | select waveform of vibrato pitch | `sine`, `triangle`, `swung sine`, `swung` |

back to [Categories & Modules](#categories-and-modules)

---

### Flanger
ZOIA's Flanger module is borrowed right from the Empress Nebulus. This quite versatile flanger encompasses lots of comb filtering territory, but don't hesitate to build flange tones yourself using LFOs and delay lines!

| | |
|-|-|
| Min blocks | 7 |
| Max blocks | 9 |
| Avg. CPU | 4.7%–10% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `input left` | no modifier | connect audio input | inputs, audio effect outputs, VCAs, oscillators |
| 2 * | `input right` | no modifier | connect second audio input (optional) | inputs, audio effect outputs, VCAs, oscillators |
| 3 | `control in` | rate in Hz, bpm, or ms (click knob to cycle views) | depending on how you set the control mode: dial in a rate, tap in a tempo, or connect a CV source | MIDI inputs/outputs, LFOs, sequencers, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 4 | `regeneration` | level in dB | sends some modulated effect back to the beginning of the flanger for added mojo. dial in a subtle shimmer all the way up to some mega self oscillating weirdness | MIDI inputs/outputs, LFOs, sequencers, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 5 | `width` | level in CV | sets width of flanger effect | MIDI inputs/outputs, LFOs, sequencers, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 6 | `tone tilt eq` | level in dB | a subtle tone control on the wet signal. from flat, negative values dial out high end and add warmth, while positive values cut bass and add highs | MIDI inputs/outputs, LFOs, sequencers, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 7 | `mix` | percentage in CV | mix controls the level of uneffected signal to modulated signal. go from fully dry to fully wet | MIDI inputs/outputs, LFOs, sequencers, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 8 | `output left` | no modifier | connect audio output | audio inputs/outputs, VCAs, audio effects, FM inputs, analysis modules |
| 9 * | `output right` | no modifier | connect second audio output | audio inputs/outputs, VCAs, audio effects, FM inputs, analysis modules |

| Module options | Description | Settings |
|--|--|--|
| `channels` | select flanger audio path | `mono`, `mono to stereo`, `stereo` |
| `control` | select control method over flanger | `rate`, `tap tempo`, `cv direct` |
| `type` | select between three different flavours of flanger | `1960s`, `1970s`, `thru-0` |

back to [Categories & Modules](#categories-and-modules)

---

### Tremolo
Up and down, side to side. Tremolo helps your smile get wide. Set speed and depth and tap in a tempo if you like. If you'd like a tremolo effect with more control, try creating one using the VCA or Audio Panner along with LFOs and various other CV tools to get radical!

| | |
|-|-|
| Min blocks | 4 |
| Max blocks | 6 |
| Avg. CPU | 1%–2% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `audio inL` | no modifier | connect audio input | inputs, audio effect outputs, VCAs, oscillators |
| 2 * | `audio inR` | no modifier | connect second audio input | inputs, audio effect outputs, VCAs, oscillators |
| 3 | `control in` | rate in Hz, bpm, or ms (click knob to cycle views) | depending on how you set the control mode: dial in a rate, tap in a tempo, or connect a CV source | MIDI inputs/outputs, LFOs, sequencers, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 4 | `depth` | level in CV | depth of tremolo effect. go from subtle dips to complete silence during dips | MIDI inputs/outputs, LFOs, sequencers, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 5 | `audio outL` | no modifier | connect audio output | audio inputs/outputs, VCAs, audio effects, FM inputs, analysis modules |
| 6 * | `audio outR` | no modifier | connect second audio output | audio inputs/outputs, VCAs, audio effects, FM inputs, analysis modules |

| Module options | Description | Settings |
|--|--|--|
| `channels` | select tremolo audio path | `mono`, `mono to stereo`, `stereo` |
| `control` | select control method over tremolo | `rate`, `tap tempo`, `cv direct` |
| `waveform` | select flavour of tremolo effect | `fender'ish`, `vox'ish`, `triangle`, `sine`, `square` |

back to [Categories & Modules](#categories-and-modules)

---

### Env Filter
Get your quack on! This fully featured envelope filter has everything you need to tune in that perfect envelope filter and get funky. Great on guitar, bass, or anything else!

| | |
|-|-|
| Min blocks | 6 |
| Max blocks | 8 |
| Avg. CPU | 2.7%–4% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `audio in1` | no modifier | connect audio input | inputs, audio effect outputs, VCAs, oscillators |
| 2 * | `audio in2` | no modifier | connect second audio input | inputs, audio effect outputs, VCAs, oscillators |
| 3 | `sensitivity` | level in CV | determines the sensitivity of the envelope to incoming audio levels | MIDI inputs/outputs, LFOs, sequencers, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 4 | `min freq` | frequency in Hz | determines the downward cutoff frequency of the envelope filter | MIDI inputs/outputs, LFOs, sequencers, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 5 | `max freq` | frequency in Hz | determines the upward cutoff frequency of the filter | MIDI inputs/outputs, LFOs, sequencers, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 6 | `filter Q` | level in CV | determines the width of the filter notch | MIDI inputs/outputs, LFOs, sequencers, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 7 | `audio out1` | no modifier | connect audio output | audio inputs/outputs, VCAs, audio effects, FM inputs, analysis modules |
| 8 * | `audio out2` | no modifier | connect second audio output | audio inputs/outputs, VCAs, audio effects, FM inputs, analysis modules |

| Module options | Description | Settings |
|--|--|--|
| `channels` | select filter audio path | `mono`, `mono to stereo`, `stereo` |
| `filter type` | select filter type | `high pass`, `low pass`, `band pass` |
| `direction` | select direction of filter sweep | `up`, `down` |

back to [Categories & Modules](#categories-and-modules)

---

### Ring Modulator
A gnarly ring modulation effect. A robot's nightmare, a tweaker's delight!

| | |
|-|-|
| Min blocks | 4 |
| Max blocks | 5 |
| Avg. CPU | 3%–7.6% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `audio in` | no modifier | connect audio input | inputs, audio effect outputs, VCAs, oscillators |
| 2 | `frequency or ext in` | frequency in Hz, or no modifier | this jack will either generate a carrier frequency to modulate the input signal against, or bring in a second audio source to act as the carrier wave. when "ext audio in" is off, CV inputs from -1 to 0 cover the frequency range 0.03–27.5 Hz, CV inputs from 0 to 1 cover the frequency range 27.5–23999 Hz | MIDI inputs/outputs, LFOs, sequencers, CV inputs/outputs, expression pedals, footswitches/pushbuttons OR inputs, audio effect outputs, VCAs, oscillators |
| 3 * | `duty cycle` | value in % | adjusts the pulse width of the ring modulation | MIDI inputs/outputs, LFOs, sequencers, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 4 | `mix` | percentage in CV | mix controls the level of uneffected signal to modulated signal. go from fully dry to fully wet | MIDI inputs/outputs, LFOs, sequencers, CV inputs/outputs, expression pedals, footswitches/pushbuttons |
| 5 | `audio out` | no modifier | connect audio output | audio inputs/outputs, VCAs, audio effects, FM inputs, analysis modules |

| Module options | Description | Settings |
|--|--|--|
| `waveform` | select waveform of generated carrier wave | `sine`, `square`, `triangle`, `sawtooth` |
| `ext audio in` | toggles parameter #2 to act as a tone generator or as a sidechain input | `on`, `off` |
| `duty cycle` | toggles presence of duty cycle parameter | `on`, `off` |
| `upsampling` | allows waveform to be generated at 2X sampling rate for better quality (higher CPU) | `none`, `2X` |

back to [Categories & Modules](#categories-and-modules)

---

### Cabinet Sim
A versatile guitar cabinet simulator.

| | |
|-|-|
| Min blocks | 3 |
| Max blocks | 4 |
| Avg. CPU | 7% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `audio in1` | no modifier | connect audio input | inputs, audio effect outputs, VCAs, oscillators |
| 2 * | `audio in2` | no modifier | connect second audio input | inputs, audio effect outputs, VCAs, oscillators |
| 3 | `audio out1` | no modifier | connect audio output | audio inputs/outputs, VCAs, audio effects, FM inputs, audio in CV out modules |
| 4 * | `audio out2` | no modifier | connect second audio output | audio inputs/outputs, VCAs, audio effects, FM inputs, analysis modules |

| Module options | Description | Settings |
|--|--|--|
| `channels` | select audio path between mono, mono into stereo, or stereo | `mono`, `mono to stereo`, `stereo` |
| `type` | select cabinet type | `4x12 full`, `2x12 dark`, `2x12 modern`, `1x12`, `1x8 lofi`, `1x12 vintage`, `4x12 hifi` |

back to [Categories & Modules](#categories-and-modules)

---

### Univibe
A multi-dimensional effect that combines vibrato and phase shifting to create lush, swooshing sounds.

| | |
|-|-|
| Min blocks | 6 |
| Max blocks | 8 |
| Avg. CPU | 14%–16% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `audio inL` | no modifier | the left audio input | audio inputs/outputs, VCAs, audio effects, oscillators |
| 2 | `audio inR` | no modifier | the right audio input | audio inputs/outputs, VCAs, audio effects, oscillators |
| 3 | `rate / tap tempo / CV control` | rate / direct control | depending on how you set the control mode: dial in a rate, tap in a tempo, or connect a CV source | oscillators, tap tempo in, MIDI inputs/outputs, CV inputs/outputs |
| 4 | `depth` | depth | depth of the vibrato effect | oscillators, MIDI inputs/outputs, CV inputs/outputs |
| 5 | `resonance` | resonance | controls the amount of resonance intensity | oscillators, MIDI inputs/outputs, CV inputs/outputs |
| 6 | `mix` | mix | sets the mix level from 0 (fully dry) to 100 (fully wet) | oscillators, MIDI inputs/outputs, CV inputs/outputs |
| 7 | `audio outL` | no modifier | the left audio output | audio inputs/outputs |
| 8 | `audio outR` | no modifier | the right audio output | audio inputs/outputs |

| Module options | Description | Settings |
|--|--|--|
| `control` | select control method | `rate`, `tap tempo`, `cv direct` |

back to [Categories & Modules](#categories-and-modules)

---

### Reverse Delay
This delay effect lets you twist time with reversed, pitch shifted repeats.

| | |
|-|-|
| Min blocks | 6 |
| Max blocks | 9 |
| Avg. CPU | 7%–9% |

| Block # | Title | Value modified by knob | Description | Might typically connect to |
|--|--|--|--|--|
| 1 | `audio in` | no modifier | the left audio input | audio inputs/outputs, VCAs, audio effects, oscillators |
| 2 | `audio inR` | no modifier | the right audio input | audio inputs/outputs, VCAs, audio effects, oscillators |
| 3 | `delay time` | delay time | set delay time (press knob to toggle between seconds, BPM, and Hz) | oscillators, MIDI inputs/outputs, CV inputs/outputs |
| 4 | `tap tempo in` | no modifier | tap in the delay time, combined with the tap ratio this sets the actual delay time | tap tempo inputs |
| 5 | `tap ratio` | tap ratio | sets the ratio of repeats per tap cycle. Adjusting this alongside tap tempo sets the actual delay time | — |
| 6 | `feedback` | feedback | set feedback amount in dB. Set to 0dB for self-oscillation. | oscillators, MIDI inputs/outputs, CV inputs/outputs |
| 7 | `pitch` | pitch | adjusts the pitch of the delay repeats | oscillators, MIDI inputs/outputs, CV inputs/outputs |
| 8 | `mix` | mix | sets the mix level from 0 (fully dry) to 100 (fully wet) | oscillators, MIDI inputs/outputs, CV inputs/outputs |
| 9 | `audio outL` | no modifier | the left audio output | audio inputs/outputs |
| 10 | `audio outR` | no modifier | the right audio output | audio inputs/outputs |

| Module options | Description | Settings |
|--|--|--|
| `control` | select tap tempo or rate control | `tap tempo`, `rate` |

back to [Categories & Modules](#categories-and-modules)

---

*Last updated: June 2026. Based on firmware v5.32. Source data: Empress Effects official module index CSV and accompanying documentation.*

---
---

# Appendix

## Colors

| Color     | Hexcode   |
|-----------|-----------|
| `red`     | #FF0000 |
| `orange`  | #FFA500 |
| `mango`   | #FFB000 |
| `yellow`  | #FFFF00 | 
| `lime`    | #AFFF00 | 
| `green`   | #00FF00 | 
| `surf`    | #00FF99 | 
| `aqua`    | #00FFFF | 
| `sky`     | #00BFFF | 
| `blue`    | #0000FF |
| `purple`  | #7F00FF |
| `magenta` | #FF00FF |
| `pink`    | #FF69B4 |
| `peach`   | #FFDAB9 |
| `white`   | #FFFFFF |

---

## Template 

```
### {module-name}
{description}

| | |
|-|-|
| Min blocks | {min-blocks} |
| Max blocks | {max-blocks} |
| Avg. CPU | {CPU}% |

| Block # | Title | Description | Value modified by knob | Might typically connect to |
|--|--|--|--|--|
| {#} | `{title}` | {block-description} | {value-modified} | {connections} |

| Module options | Description | Settings |
|--|--|--|
| `{option title}` | {description} | `{settings}` |

back to [Categories & Modules](#categories-and-modules)
```
---
