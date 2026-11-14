# ChordForge 🎵

A browser-based song generator for retro game music. Pick a sound engine, set a mood, hit Generate — get a playable multi-track song instantly. Export to MIDI, WAV, or AIFF for use in your games, DAW, or chiptune projects.

**No install. No dependencies. One HTML file.**

🎮 [**Try it live →**](https://carloscamacho.github.io/ChordForge/)

## What It Does

ChordForge generates short songs from 176 chord progressions using pattern-based composition across 4 independent tracks. Each track has its own rhythm pattern, note selection logic, and synthesizer voice — so you hear actual arrangements, not just chords repeating.

**Tracks:**
- **Chords** — Full chord voicings with 14 rhythm patterns (sustained pad, offbeat stab, arpeggio up/down, broken triad, driving 8ths, etc.)
- **Bass** — Root-note patterns with 14 groove templates (octave drive, walking, syncopated, stomp, funk, gallop, etc.)
- **Melody** — Motif-based phrases with 11 templates (lyrical, heroic, melancholy, energetic, bounce, call & response, etc.)
- **Rhythm** — Percussive hits with 10 drum patterns (basic 4/4, rock, techno, chiptune, march, swing, etc.)

## Sound Engines

12 built-in synthesizer presets, each with distinct waveforms, envelopes, detuning, and filter settings:

| Engine | Character | Waveforms |
|--------|-----------|-----------|
| 🎮 **NES** | 2A03 chiptune | Pure square waves, zero detune, instant attack |
| 💾 **C64 SID** | Commodore 64 | Sawtooth + triangle, SID-style filtering |
| 📀 **Amiga MOD** | Tracker music | Detuned sawtooth, softer envelopes |
| 🕹️ **SNES** | 16-bit console | Warm triangle, gentle filtering |
| 🎹 **Genesis FM** | Sega Mega Drive | Bright sawtooth, FM-like character |
| 🕹️ **Arcade** | Coin-op cabinet | Ultra-fast square, minimal sustain |
| 👾 **Atari VCS** | TIA chip | Pure square, very short envelopes |
| 🎤 **Pop** | Modern pop | Triangle chords, sine bass |
| 🎧 **EDM** | Electronic dance | 5-osc supersaw, deep sub |
| 🔩 **Industrial** | Harsh/dark | Heavy detuned saw, square bass |
| 🌿 **Ambient** | New age/chill | Sine pads, long attack/release |
| ⭐ **Anime** | J-pop/J-rock | Bright triangle/saw, heroic motifs |

## How to Use

1. **Pick a sound engine** — tap one of the 12 genre buttons
2. **Set mood and length** — Happy/Sad/Epic/Dark/Chill + Short/Medium/Full Song
3. **Hit "Generate & Play"** — song auto-plays immediately
4. **Tweak per track** — change patterns, mute, lock, or regenerate individual tracks
5. **Export** — download as MIDI (for your DAW), WAV (for your game), or AIFF

### Mood Changes the Music

Mood doesn't just filter progressions — it changes how the song is built:

- **Sad** → BPM drops 20, sustained pad chords, pedal bass, melancholy melody, sparse rhythm
- **Epic** → BPM up 10, driving chords, octave-drive bass, heroic melody, rock drums
- **Dark** → Short stab chords, stomp bass, industrial melody, techno rhythm
- **Chill** → BPM down 15, arpeggio chords, sparse bass, ambient melody, no drums

### Track Controls

Each of the 4 tracks has:
- **Pattern dropdown** — select a different musical pattern (changes notes and rhythm, not just sound)
- **M** (Mute) — silence that track
- **🔒** (Lock) — keep this track when regenerating the rest
- **↻** (Regenerate) — re-roll just this one track

## Export Formats

| Format | Use Case |
|--------|----------|
| **MIDI** | Import into any DAW (Format 1, 4 tracks, tempo-encoded) |
| **WAV** | Direct use in games, video, or further editing |
| **AIFF** | Apple/Logic Pro workflows |

## Music Theory

ChordForge includes the complete progression database from the [SHLD Free MIDI Chord Pack](https://github.com/ldrolez/free-midi-chords):

- **49 major** progressions (I-IV-V-IV, I-V-vi-IV, ii-V-I, etc.)
- **54 minor** progressions (i-VI-III-VII, i-iv-v, i-VII-VI-III, etc.)
- **73 modal** progressions (I-bVIIM-IV-V, im-bIIIM-bVIIM-IV, etc.)

Each tagged with moods: Joyful, Hopeful, Romantic, Nostalgic, Triumphant, Mysterious, Dark, Sad, Rebellious, Peaceful, Playful, Relaxed, Spiritual, Tender.

Progressions are browsable and sortable (A→Z, by mood, by length) and can be loaded directly.

## Architecture

Single-file `index.html` (~46KB) containing:

- **Music theory engine** — Roman numeral resolver, scale/chord interval tables, key transposition
- **Pattern libraries** — 49 total patterns across 4 track types (8-step arrays at 8th note resolution)
- **Synth engine** — Web Audio API with multi-oscillator stacking, ADSR envelopes, lowpass filters, feedback-delay reverb
- **MIDI writer** — Pure JavaScript, no libraries, Format 1 with 4 tracks
- **WAV/AIFF encoders** — Direct PCM encoding from offline-rendered AudioBuffer

Zero dependencies. No npm. No build step. Works offline.

## For Game Developers

ChordForge was built for making music for retro games. The retro engines (NES, C64, Amiga, SNES, Genesis, Arcade, Atari VCS) use authentic waveforms and envelopes that match the character of those platforms. Export to MIDI and import into your tracker or DAW, or export to WAV and drop directly into your game assets.

## Origin

Ported from [ldrolez/free-midi-chords](https://github.com/ldrolez/free-midi-chords) — a Python project (chords2midi + Mingus) that generates 12,000+ MIDI chord files. ChordForge takes the same 176 progressions and music theory but runs entirely in the browser with real-time synthesis and playback.

## License

MIT — use the generated music freely in any project.
