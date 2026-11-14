# Changelog

## v9 — November 2026 (Current Release)

### Sound Engines (12 total)
- **NES** — Pure square wave synthesis, zero detune, instant attack (authentic 2A03 character)
- **C64 SID** — Sawtooth + triangle oscillators with SID-style filtering
- **Amiga MOD** — Slightly detuned sawtooth with softer envelopes, tracker feel
- **SNES** — Warm triangle waves with gentle filtering
- **Genesis FM** — Bright sawtooth with FM-like detuning and character
- **Arcade** — Ultra-fast square waves, minimal sustain
- **Atari VCS** — Pure square waves, very short envelopes, TIA-inspired
- **Pop** — Triangle chords, sine bass, square lead
- **EDM** — 5-oscillator supersaw, deep sub bass, saw lead
- **Industrial** — Heavy detuned sawtooth, square bass, harsh lead
- **Ambient** — Sine pads with long attack/release, sparse rhythm
- **Anime** — Bright triangle/sawtooth with fast envelopes, heroic motifs

### Composition Engine
- **176 chord progressions** from the original SHLD Free MIDI Chord Pack (49 major, 54 minor, 73 modal)
- **Pattern-based generation** — each chord defines a bar of 8 steps (8th note resolution)
- **4 independent tracks:** Chords (14 patterns), Bass (14 patterns), Melody (11 motifs), Rhythm (10 patterns)
- **Section-aware arrangement** — Full Song generates: intro → verse → chorus → verse → chorus → bridge → chorus → outro
- **Section density profiles** — intro is sparse, chorus is full, outro fades
- **Mood modifiers** — Sad slows BPM and forces sustained pads; Epic drives BPM up with heroic motifs; Dark uses stab chords and stomp bass

### Track Controls
- Per-track **pattern selector** dropdown (changes musical behavior, not just timbre)
- Per-track **Mute** button
- Per-track **Lock** button (preserves track when regenerating)
- Per-track **Regenerate** button (re-rolls just that track)
- Step-level visualization showing note names (K/S/H for rhythm)

### Audio Engine
- Multi-oscillator stacking (1-5 oscillators per note depending on detune setting)
- Per-voice lowpass filter with genre-specific cutoff frequencies
- ADSR envelope per voice (attack, sustain, release all genre-configured)
- Feedback-delay reverb with random routing for spatial depth
- **Seamless loop** — next iteration scheduled 20ms before end, no audible gap

### Export
- **MIDI** — Format 1, 4 tracks (Chords ch0, Bass ch1, Melody ch2, Rhythm ch10), tempo-accurate
- **WAV** — 16-bit 44100Hz PCM, offline-rendered
- **AIFF** — Apple-compatible lossless audio

### UI/UX
- Single-mode interface (Simple/Advanced split removed — was confusing)
- Mobile-first responsive design (works at 375px)
- Press Start 2P pixel font for retro aesthetic
- Progression browser with 3-way sort (A→Z, By Mood, By Length) and type/mood filters
- Auto-play on generate — hit the button, hear the result immediately
- Chord flow display with real-time playback highlighting
- Section map showing intro/verse/chorus/bridge/outro with playhead

### Bug Fixes (from v1–v8)
- Fixed mobile scrolling (`overflow-x:hidden` removed from body)
- Fixed Safari canvas crash (`roundRect()` → `fillRect()`)
- Fixed silent songs when roman numeral resolver returned empty arrays
- Fixed loop gap (was +50ms timeout causing audible pause)
- Fixed audio node cleanup between pattern plays
- Fixed MIDI delta timing for first notes

---

## v1–v8 — Development History

### v1 — Initial Port
- Ported Python chords2midi theory engine to JavaScript
- Basic chord palette, timeline builder, piano roll visualization
- MIDI/WAV/AIFF/OGG export

### v2 — Step Sequencer
- Added 8-slot pattern system (A–H) with step sequencer grid
- Loop playback, song chain builder
- Drag-and-drop chord reordering

### v3 — Simple/Advanced Mode
- Added Simple mode (one-click generate) and Advanced mode (grid editor)
- Fixed mobile scrolling bug, Safari roundRect crash

### v4 — Genre Sound Design
- 10 genre presets with distinct synthesis per genre
- Multi-oscillator stacking with detuning
- Genre-specific waveforms, envelopes, and filter settings

### v5 — DAW-like Rows
- Restructured to 3 instrument rows (Chords, Bass, Melody)
- Each row plays different musical content (not same chord repeated)
- Mute buttons per row

### v6 — Simplified UX
- Removed grid complexity for Simple mode
- Big genre icons, one-tap create
- Chord card display with playback highlighting

### v7 — Pattern Libraries
- Added bass pattern library (10), chord pattern library (10), melody motif library (8)
- Section-aware arrangement with density profiles
- Lock/regenerate per track
- Musician advisor feedback integrated

### v8 — All 176 Progressions
- Embedded complete progression database from original Python source
- Added progression sort (alphabetical, by mood, by length)
- Added mood filter for progressions

### v9 — Retro Game Focus
- Replaced Rock/Classical with Atari VCS and kept Industrial
- Added NES, C64 SID, Amiga MOD, SNES, Genesis FM, Arcade engines
- Rhythm/percussion track (4th track)
- Mood modifiers change patterns and BPM, not just progression selection
- Seamless loop fix
- Single-mode UI (removed Simple/Advanced split)
