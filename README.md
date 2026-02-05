# Autistic Synth Machine (ASM)

![ASM Screenshot](https://raw.githubusercontent.com/DigiMancer3D/ASM/refs/heads/main/Screenshot_20260205_003114.png) 

## Overview

The Autistic Synth Machine (ASM) is a web-based audio synthesizer designed to generate and manipulate vowel-like sounds, hums, and groans that mimic non-verbal vocalizations often associated with autistic communication. Built using HTML, CSS, and JavaScript with the Web Audio API, it allows users to create customizable synthetic sounds, apply effects, loop them, and sequence multiple sounds into patterns. This tool aims to facilitate exploration and replication of "autistic vowel language", sequences of sounds and gaps, that could potentially aid in understanding or communicating with non-verbal autistic individuals.

### Does It Meet the Original Goal?
The original goal was to create a synthesizer capable of generating vowel-like audio forms, building sequences of sounds and gaps to form an "autistic vowel language," mimicking heard non-verbal vocalized noises for communication purposes. It should also support generating, sequencing, storing, and listening to these sounds.

- **Strengths and Alignment**: ASM excels in sound generation and sequencing. It produces realistic vowel approximations (e.g., /ɑ/, /i:/) with fine-tuned parameters for pitch, formants, breathiness, and more. The sequencer allows building patterns with gaps and loops, enabling the creation of rhythmic "language-like" sequences. This directly supports mimicking and experimenting with non-verbal sounds.
  
- **Gaps and Shortcomings**: While generation and sequencing are robust, **storage** is absent. Users cannot save/load presets, sequences, or recordings. Listening is real-time only, with no export options (e.g., WAV/MP3). The interface is functional but could be more accessible (e.g., for users with sensory sensitivities; i.e., have dark/light/medium themes and have a simple or advanced User Interface [dials for simple, sliders for advanced]). Overall, it partially meets the goal but requires enhancements for full storage and playback capabilities.

## Features

- **Sound Generation**: Create vowel-like sounds using presets (e.g., "Ah", "Ee", "Hum", "Groan") with adjustable parameters for pitch, volume, ADSR envelope (Attack, Decay, Sustain, Release), formant frequencies/gains, and effects like vibrato, reverb, breathiness, humming, jaw jitter, pitch jitter, and amplitude shimmer.
- **Multiple Sounds**: Start with Sound A; add more (B, C, etc.) dynamically.
- **Looping**: Enable looping for individual sounds with customizable gaps (0-3 seconds) to simulate repetitive vocalizations.
- **Transitions**: Smooth morphing between start, mid, and end vowel presets over a transition time (0-5 seconds).
- **Sequencer**: An 8-step sequencer to trigger sounds in patterns, with global loop and gap controls. Supports polyphony (multiple sounds per step).
- **Live Adjustments**: Real-time parameter tweaks while sounds play.
- **Reset Options**: Per-parameter reset or full sound reset to defaults.
- **Tooltips**: Hover over sliders for value display.
- **Responsive Design**: Adapts to different screen sizes for mobile/desktop use.
- **Effects**: Reverb, detune, and various modulations for naturalistic variations.

## Installation and Setup

ASM is a single-file HTML application – no installation required!

1. **Download**: Clone this repository or download `ASM.1.7.html`.
2. **Run**: Open the file in a modern web browser (e.g., Chrome, Firefox). Ensure your browser supports the Web Audio API (most do).
3. **Permissions**: The first click may prompt for audio access; allow it to enable sound.
4. **Dependencies**: None, everything is self-contained.

**Note**: For best performance, use headphones or speakers. If audio doesn't play, check browser audio settings or try resuming the AudioContext via a click.

## Usage

### Basic Sound Creation
1. **Select a Preset**: Use the "Start Preset," "Mid Preset," or "End Preset" dropdowns to choose vowel types (e.g., "Ah" for open vowel sounds).
2. **Adjust Parameters**:
   - **Pitch (1-650 Hz)**: Base frequency; lower for deeper groans, higher for squeals.
   - **Volume (0-1)**: Overall loudness.
   - **ADSR Envelope**:
     - Attack (0-2s): Time to reach full volume.
     - Decay (0-2s): Time to drop to sustain level.
     - Sustain (0-1): Hold level after decay.
     - Release (0-2s): Fade-out time after hold.
   - **Hold Duration (0.1-10s)**: How long the sound sustains.
   - **Formants (F1-F6 Freq/Gain)**: Shape the vowel timbre (e.g., F1 low for dark sounds).
   - **Effects**:
     - Humming/Breathiness/Jaw Jitter: Add nasal, airy, or wobbly qualities.
     - Vibrato/Pitch Jitter/Amplitude Shimmer: For natural fluctuations.
     - Reverb (0-1): Add echo for spatial feel.
     - Detune (-1200-1200 cents): Slight pitch offset for chorusing.
   - **Loop**: Check to repeat; set "Loop Gap" for pauses between loops.
   - **Transition (0-5s)**: Time to morph from start to mid to end presets.
3. **Play/Stop**: Click "Play" to start (toggles to "Pause"); "Stop" for immediate halt.
4. **Reset**: Click "Reset" for the sound or per-slider via label click (shows Reset/Cancel).

### Adding More Sounds
- Click "Add Sound" to create Sound B, C, etc. Each has independent controls.

### Using the Sequencer
1. **Enable Steps**: In the Sequencer section, check boxes for each sound (rows) and step (columns 1-8).
2. **Play Sequence**: Click "Play Sequence" to trigger checked sounds step-by-step.
3. **Controls**:
   - **Sequence Loop Gap (0-3s)**: Pause between full sequence loops.
   - **Loop Sequence**: Check to repeat indefinitely.
4. **Stop Sequence**: Halts playback and stops all sounds.
5. **Behavior**: Each step plays triggered sounds fully (including their hold/release), then advances based on the longest sound duration + gap. Looping sounds continue across steps.

### Tips
- **Mimicking Autistic Vocalizations**: Start with low pitch (e.g., 47 Hz), add breathiness/humming for realism, and use the sequencer for patterned "phrases" with gaps.
- **Experimentation**: Tweak formants for unique timbres; use jitter/shimmer for variability.
- **Performance**: On slower devices, limit active sounds to avoid lag.
- **Accessibility**: The interface is text-based; consider screen readers for labels.

## Parameter Reference Table

| Category | Parameter | Range | Default | Description |
|----------|-----------|-------|---------|-------------|
| **Presets** | Start/Mid/End Preset | Options: Ah, Ee, I, U, O, Y, Hum, Groan | Ah | Vowel starting/middle/ending shape. |
| **Core** | Pitch | 1-650 Hz | 47 | Base frequency. |
| **Core** | Volume | 0-1 | 0.33 | Loudness. |
| **Envelope** | Attack | 0-2s | 0.3 | Ramp-up time. |
| **Envelope** | Decay | 0-2s | 0.4 | Drop to sustain. |
| **Envelope** | Sustain | 0-1 | 0.7 | Hold level. |
| **Envelope** | Release | 0-2s | 0.3 | Fade-out time. |
| **Envelope** | Hold Duration | 0.1-10s | 3 | Sustain length. |
| **Looping** | Loop | Checkbox | False | Repeat sound. |
| **Looping** | Loop Gap | 0-3s | 0 | Pause between loops. |
| **Transition** | Transition Time | 0-5s | 0 | Morph duration between presets. |
| **Formants** | F1-F6 Freq | Varies (e.g., 200-1000 Hz for F1) | Preset-dependent | Frequency peaks for vowel timbre. |
| **Formants** | F1-F6 Gain | -40-40 dB | 20 | Boost/cut for each formant. |
| **Effects** | Humming Strength/Depth/Amount | 0-30 dB / 100-500 Hz / 1-20 | 0 / 175 / 10 | Nasal hum addition. |
| **Effects** | Breathiness Strength/Depth/Amount | 0-0.2 / 500-2000 Hz / 0.1-2 | 0 / 1795 / 1.2 | Airy breath noise. |
| **Effects** | Jaw Jitter Strength/Depth/Amount | 0-20 cents / 0-50 Hz / 0-1 Hz | 0 / 41 / 0.77 | Formant wobble. |
| **Effects** | Detune | -1200-1200 cents | 0 | Pitch offset for second oscillator. |
| **Effects** | Vibrato Rate/Depth | 0-10 Hz / 0-200 cents | 0 / 0 | Pitch modulation. |
| **Effects** | Reverb Wet | 0-1 | 0 | Reverb mix. |
| **Effects** | Pitch Jitter Rate/Depth | 0-2 Hz / 0-20 cents | 0 / 0 | Random pitch variation. |
| **Effects** | Amplitude Shimmer Rate/Depth | 0-2 Hz / 0-0.2 | 0 / 0 | Volume fluctuation. |
| **Fades** | Fade-In/Fade-Out Time | 0-2s | 0.1 | Global fade (not fully implemented in code; uses envelope). |

## Action Plan for Improvements
To fully align with the original goal (especially storage and listening), here's a prioritized roadmap:

1. **Short-Term (Next Version - ASM 1.7)**:
   - Add save/load for individual sound presets (JSON via localStorage or file export).
   - Implement sequence saving/loading.
   - Add audio export (e.g., record and download as WAV using MediaRecorder API).

2. **Medium-Term**:
   - Add recording/playback of generated sequences for "listening" archives.
   - Improve accessibility: Color contrasts, keyboard navigation, ARIA labels.
   - Expand sequencer: Variable steps (e.g., expandable steps being added), tempo control.

3. **Long-Term**:
   - Machine learning integration: Analyze uploaded audio to auto-generate mimicking presets.
   - Community features: Share presets/sequences via hashings with a simple backend.
   - Testing with autistic users for feedback on sound realism, usability, and how autistics respond to the sounds this synth generates.


## License
MIT License – Free to use, modify, and distribute. See [LICENSE](LICENSE) for details.

## Credits
- Built with Web Audio API.
- Inspired by watching autistic individuals seemingly communicate publicly in this vowel-like manner.
- Original code by [3Douglas "3D"](https://x.com/Z0M8I3D).
- Code assisted by [GROK 4](https://grok.com).
