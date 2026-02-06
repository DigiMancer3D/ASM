# Autistic Synth Machine (ASM)


## Why
##### With the right tools where we all can recreate the same experiement can we then discover what we previously didn't understand or know.

&nbsp;&nbsp;&nbsp;Since autistic parents and guardians began gathering to swap help and gain a socially active community around people caring for autistic indivduals has also created a social system with autistic indivduals and this is when the vowel-like autsitic emotinal language was really begining to be seen. Nowadays, many peoples have seen or heard these sounds unaware they could be potential communications from non-verbal or non-speaking individuals. Some people within and around the autistic communities have determined and prooven that the mimicking seen amoungst autistic indiviuals when around other autisitc individuals is potentially a form of interaction by autistic individuals. Now, anyone can test this theroy. Now, anyone can share their loved one's sounds in-hopes to find out what they mean for them. Hopefully one day in our future, caregivers, parents, family and friends of non-verbal autistic indivuals may be able to know what they are saying and for some may be able to communicate back with them.

---

###### screenshot of main program view
![ASM Screenshot](https://raw.githubusercontent.com/DigiMancer3D/ASM/refs/heads/main/Screenshot_20260206_092655.png) 

---

## Overview

&nbsp;&nbsp;&nbsp;The Autistic Synth Machine (ASM) version 2.2 is a web-based audio synthesizer designed to generate and manipulate vowel-like sounds, hums, groans, and imported audio that mimic non-verbal vocalizations often associated with autistic communication. Built using HTML, CSS, and JavaScript with the Web Audio API, it allows users to create customizable synthetic sounds, apply a wide range of effects, loop them, sequence multiple sounds into patterns, import external audio files, and even record from a microphone. This tool aims to facilitate exploration and replication of "autistic vowel language", sequences of sounds and gaps to express emotion, that could potentially aid in understanding or communicating with non-verbal autistic individuals.

&nbsp;&nbsp;&nbsp;Key enhancements in version 2.2 include support for importing WAV/audio files as "media" sounds with dedicated controls (e.g., playback speed, pitch shift, reverse, trimming, EQ), microphone recording for capturing real vocalizations, global master effects like compressor and delay, BPM synchronization, dynamic sequencer step adjustments, preset/sequence saving/loading/export/import, audio export for individual sounds or full sequences, and improved UI with fine-tune buttons and value displays.

## Features

- **Master Controls**: Global compressor (threshold, ratio, makeup gain), delay (time, feedback), BPM setting (30-300) for timing synchronization, and BPM Sync toggle for aligning loops to beats.
- **Sound Generation (Vowels)**: Create vowel-like sounds using extensive presets (e.g., "Ah", "Ee", "Hum", "Groan", diphthongs like "Ai", nasals, elongated sounds) with adjustable parameters for pitch, ADSR envelope (Attack, Decay, Sustain, Release), hold duration, formant frequencies/gains (F1-F6), and effects like humming, breathiness, jaw jitter, detune, vibrato, reverb, pitch jitter, amplitude shimmer, distortion, chorus, LFO assignment, noise gate, and waveform selection (glottal, sine, sawtooth, square).
- **Media Import**: Load external WAV or audio files as sounds, with controls for playback speed (0.5-2x), pitch shift (-1200 to 1200 cents), reverse playback, trim start/end, 3-band EQ (freq/gain for low/mid/high), alongside shared features like volume, pan, reverb, fades, and looping.
- **Multiple Sounds**: Start with Sound A; dynamically add more (B, C, etc.) via "Add Sound" button. Mix vowels and imported media.
- **Looping**: Enable per-sound looping with customizable gaps (0-3s); supports BPM-sync for rhythmic alignment.
- **Transitions and Fades**: Smooth morphing between start/mid/end presets over transition time (0-5s); bell-curve fade-in/out (0-2s) for natural starts/ends.
- **Sequencer**: Dynamic 8+ step sequencer (increase/decrease steps) to trigger sounds in patterns. Supports polyphony, global loop with gap (0-3s), and saving/loading/export/import of sequences including sound presets.
- **Live Adjustments**: Real-time tweaks to most parameters while playing; fine-tune sliders with +/- buttons.
- **Presets and Sequences**: Save/load/export/import individual sound presets or full sequences (including all sound settings and step triggers) as JSON files.
- **Audio Export**: Export individual sounds or full sequences as WAV files.
- **Mic Recording**: Record audio from microphone, play back, and export as WAV.
- **Reset Options**: Per-parameter reset (via label click) or full sound reset; global resets to defaults.
- **Responsive Design**: Adapts slider layout for different screen sizes (mobile to desktop).
- **Performance**: Uses Web Audio API for efficient synthesis; handles multiple simultaneous sounds.

---

## Installation and Setup

ASM is a single-file HTML application. No installation or server required!

1. **Download**: Clone this repository or download `ASM.2.2.html`.
2. **Run**: Open the file in a modern web browser (e.g., Chrome, Firefox, Edge). Ensure the browser supports the Web Audio API (most current versions do).
3. **Permissions**: On first interaction, the browser may prompt for audio/microphone access; allow it to enable sound playback and recording.
4. **Dependencies**: None, everything is self-contained in the HTML file.
5. **Browser Notes**: For optimal performance, use headphones or external speakers. If audio doesn't play, check browser settings (e.g., autoplay policies) or resume the AudioContext via a click. Microphone recording requires HTTPS or localhost in some browsers.

**Note**: Test in incognito mode if extensions interfere. The app works offline after inital loading.

## Usage

### Master Controls
- **Compressor**: Toggle on/off; adjust threshold (-60-0 dB, default -24), ratio (1-20, default 12), makeup gain (0-24 dB, default 0) for dynamic range control.
- **Delay**: Toggle on/off; set time (0-2s, default 0.3) and feedback (0-1, default 0.5) for echo effects.
- **BPM**: Set tempo (30-300, default 120) for synchronization.
- **BPM Sync**: Toggle to align loop gaps to beat timing.

Changes apply globally and update in real-time.

--

### Sound Creation (Default Type)
1. **Select Presets**: Choose from "Start Preset," "Mid Preset," or "End Preset" dropdowns (e.g., "Ah (/ɑ/)", "Hum", "Spanish A", diphthongs like "Ai", nasals like "A nasal"). Presets auto-set formants; changing start updates mid/end if transition is 0.
2. **Adjust Parameters**:
   - **Pitch (1-650 Hz, default 47)**: Base frequency; low for groans, high for squeals.
   - **Volume (0-1, default 0.33)**: Loudness.
   - **Pan (-1-1, default 0)**: Stereo position.
   - **ADSR Envelope**: Attack (0-2s, default 0.3), Decay (0-2s, default 0.4), Sustain (0-1, default 0.7), Release (0-2s, default 0.3).
   - **Hold Duration (0.1-10s, default 3)**: Sustain length.
   - **Formants (F1-F6)**: Freq (varies, e.g., F1 200-1000 Hz) and Gain (-40-40 dB, default 20); shape timbre.
   - **Humming**: Strength (0-30 dB, default 0), Depth (100-500 Hz, default 175), Amount (1-20, default 10); nasal quality.
   - **Breathiness**: Strength (0-0.2, default 0), Depth (500-2000 Hz, default 1795), Amount (0.1-2, default 1.2); airy noise.
   - **Jaw Jitter**: Strength (0-20 cents, default 0), Depth (0-50 Hz, default 41), Amount (0-1 Hz, default 0.77); formant wobble.
   - **Detune (-1200-1200 cents, default 0)**: Second oscillator offset.
   - **Vibrato**: Rate (0-10 Hz, default 0), Depth (0-200 cents, default 0); pitch modulation.
   - **Reverb Wet (0-1, default 0)**: Echo mix.
   - **Pitch Jitter**: Rate (0-2 Hz, default 0), Depth (0-20 cents, default 0); random pitch variation.
   - **Amplitude Shimmer**: Rate (0-2 Hz, default 0), Depth (0-0.2, default 0); volume fluctuation.
   - **Waveform**: Glottal (default), Sine, Sawtooth, Square.
   - **Distortion**: Toggle; Intensity (0-1, default 0), Threshold (0-1, default 0.5).
   - **Chorus**: Toggle; Rate (0-10 Hz, default 0), Depth (0-50%, default 0).
   - **LFO Assign**: None (default) or to F1-F6 Freq/Gain; Rate (0-10 Hz, default 0), Depth (0-100%, default 0).
   - **Noise Gate**: Toggle; Threshold (-60-0 dB, default -30).
   - **Fade-In/Out (0-2s, default 0.1)**: Bell-curve fades.
   - **Loop**: Toggle; Gap (0-3s, default 0).
   - **Transition (0-5s, default 0)**: Morph time between presets.
3. **Play/Pause/Stop**: "Play" starts/toggles pause; "Stop" halts immediately.
4. **Fine-Tune**: Use +/- buttons on sliders for step adjustments.
5. **Reset**: Label click shows Reset/Cancel per param; "Reset" button for full sound.
6. **Presets**: Save/Load/Export/Import sound settings as JSON.

--

### Media Sound Creation (Via Import)
1. **Import Audio**: Click "Import Audio" in Sequencer; select WAV/audio file, creates a new "Media X" section.
2. **Adjust Parameters** (Shared + Media-Specific):
   - Shared: Volume, Pan, Reverb, Fade-In/Out, Loop/Gap.
   - **Playback Speed (0.5-2, default 1)**: Slow down/speed up.
   - **Pitch Shift (-1200-1200 cents, default 0)**: Tune up/down.
   - **Reverse**: Toggle to play backward.
   - **Trim Start/End (0-max duration, default 0/full)**: Crop audio.
   - **EQ1-3**: Freq (20-20000 Hz, defaults 250/1000/5000), Gain (-40-40 dB, default 0); low/mid/high bands.
3. **Play/Pause/Stop/Reset**: Same as vowels; reset restores defaults.

--

### Sequencer
1. **Add Steps**: Use "Increase/Decrease Sequence" to adjust columns (min 2).
2. **Trigger Sounds**: Check boxes per sound (rows) and step.
3. **Play Sequence**: Triggers checked sounds per step, advancing after longest duration.
4. **Controls**: "Stop Sequence" halts; "Loop Sequence" repeats; "Sequence Loop Gap" (0-3s) pauses between cycles.
5. **Save/Load/Export/Import**: Full sequences (steps + all sound presets) as JSON.
6. **Export Sequence Audio**: Renders full sequence as WAV (non-looping for export).

--

### Microphone Recording
1. **Start Record**: Begins mic input; shows timer.
2. **Stop Record**: Ends recording.
3. **Play Record**: Plays back.
4. **Export Record**: Downloads as WAV.

---

### Tips
- **Autistic Vocal Mimicry**: Use low pitches, breathiness/humming for realism; sequencer for "conversations" with gaps.
- **Mixing**: Combine vowels/media; use pan for stereo separation.
- **Sync**: Enable BPM Sync for rhythmic loops.
- **Export**: Great for sharing sounds/sequences.
- **Performance**: Limit sounds/steps on mobile; close tabs if lag.
- **Customization**: Import real vocal samples, tweak EQ for matching.
- **Accessibility**: Labels for screen readers; keyboard-navigable sliders.

---

## Parameter Reference Table

| Category       | Parameter              | Range/Default          | Description |
|----------------|------------------------|------------------------|-------------|
| **Master**     | Compressor Toggle      | On/Off (Off)           | Global dynamic compression. |
| **Master**     | Comp Threshold         | -60-0 dB (-24)         | Level to start compressing. |
| **Master**     | Comp Ratio             | 1-20 (12)              | Compression amount. |
| **Master**     | Comp Makeup            | 0-24 dB (0)            | Post-compression gain. |
| **Master**     | Delay Toggle           | On/Off (Off)           | Global echo. |
| **Master**     | Delay Time             | 0-2s (0.3)             | Echo delay. |
| **Master**     | Delay Feedback         | 0-1 (0.5)              | Echo repeats. |
| **Master**     | BPM                    | 30-300 (120)           | Tempo for sync. |
| **Master**     | BPM Sync               | On/Off (Off)           | Align gaps to beats. |
| **Core**       | Pitch                  | 1-650 Hz (47)          | Base frequency. |
| **Core**       | Volume                 | 0-1 (0.33)             | Loudness. |
| **Core**       | Pan                    | -1-1 (0)               | Stereo position. |
| **Envelope**   | Attack                 | 0-2s (0.3)             | Ramp-up. |
| **Envelope**   | Decay                  | 0-2s (0.4)             | Drop to sustain. |
| **Envelope**   | Sustain                | 0-1 (0.7)              | Hold level. |
| **Envelope**   | Release                | 0-2s (0.3)             | Fade-out. |
| **Envelope**   | Hold Duration          | 0.1-10s (3)            | Sustain length. |
| **Fades**      | Fade-In Time           | 0-2s (0.1)             | Bell-curve start fade. |
| **Fades**      | Fade-Out Time          | 0-2s (0.1)             | Bell-curve end fade. |
| **Looping**    | Loop                   | On/Off (Off)           | Repeat sound. |
| **Looping**    | Loop Gap               | 0-3s (0)               | Pause between loops. |
| **Transition** | Transition Time        | 0-5s (0)               | Morph presets. |
| **Formants**   | F1 Freq/Gain           | 200-1000 Hz / -40-40 dB (500/20) | Vowel shaping. |
| **Formants**   | F2 Freq/Gain           | 500-3000 Hz / -40-40 dB (750/20) | (Similar for F3-F6 with varying ranges/defaults). |
| **Humming**    | Strength/Depth/Amount  | 0-30 dB (0) / 100-500 Hz (175) / 1-20 (10) | Nasal hum. |
| **Breathiness**| Strength/Depth/Amount  | 0-0.2 (0) / 500-2000 Hz (1795) / 0.1-2 (1.2) | Airy noise. |
| **Jaw Jitter** | Strength/Depth/Amount  | 0-20 cents (0) / 0-50 Hz (41) / 0-1 Hz (0.77) | Formant variation. |
| **Detune**     | Detune Cents           | -1200-1200 (0)         | Oscillator offset. |
| **Vibrato**    | Rate/Depth             | 0-10 Hz (0) / 0-200 cents (0) | Pitch modulation. |
| **Reverb**     | Wet                    | 0-1 (0)                | Echo mix. |
| **Jitter**     | Pitch Rate/Depth       | 0-2 Hz (0) / 0-20 cents (0) | Random pitch. |
| **Shimmer**    | Amplitude Rate/Depth   | 0-2 Hz (0) / 0-0.2 (0) | Volume fluctuation. |
| **Waveform**   | Waveform               | Glottal/Sine/Sawtooth/Square (Glottal) | Oscillator type. |
| **Distortion** | Toggle/Intensity/Threshold | On/Off (Off) / 0-1 (0) / 0-1 (0.5) | Clipping effect. |
| **Chorus**     | Toggle/Rate/Depth      | On/Off (Off) / 0-10 Hz (0) / 0-50% (0) | Modulation effect. |
| **LFO**        | Assign/Rate/Depth      | None or F/G1-6 (None) / 0-10 Hz (0) / 0-100% (0) | Low-frequency oscillation. |
| **Noise Gate** | Toggle/Threshold       | On/Off (Off) / -60-0 dB (-30) | Cut low-level noise. |
| **Media-Specific** | Playback Speed     | 0.5-2 (1)              | Speed adjustment. |
| **Media-Specific** | Pitch Shift        | -1200-1200 (0)         | Tune shift. |
| **Media-Specific** | Reverse            | On/Off (Off)           | Backward play. |
| **Media-Specific** | Trim Start/End     | 0-duration (0/full)    | Crop audio. |
| **Media-Specific** | EQ1 Freq/Gain      | 20-20000 Hz (250) / -40-40 (0) | Low band. |
| **Media-Specific** | EQ2 Freq/Gain      | 20-20000 Hz (1000) / -40-40 (0) | Mid band. |
| **Media-Specific** | EQ3 Freq/Gain      | 20-20000 Hz (5000) / -40-40 (0) | High band. |
| **Sequencer**  | Steps                  | 2+ (8)                 | Dynamic columns. |
| **Sequencer**  | Sequence Gap           | 0-3s (0)               | Loop pause. |
| **Sequencer**  | Loop Sequence          | On/Off (Off)           | Repeat sequence. |

---

###### screenshot of main sound section
![ASM Screenshot](https://raw.githubusercontent.com/DigiMancer3D/ASM/refs/heads/main/Screenshot_20260206_092707.png) 

###### screenshot of main program bottom
![ASM Screenshot](https://raw.githubusercontent.com/DigiMancer3D/ASM/refs/heads/main/Screenshot_20260206_092724.png) 

---

## License

MIT License: Free to use, modify, and distribute. See [LICENSE](LICENSE) for details.

---

## Credits

- Built with Web Audio API.
- Inspired by watching autistic individuals seemingly communicate publicly in this vowel-like manner.
- Original code by [3Douglas "3D"](https://x.com/Z0M8I3D).
- Code assisted by [GROK 4](https://grok.com).
  
---

