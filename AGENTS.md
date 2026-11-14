# Project & Agent Instructions

## Toolchain & Verification
- **Project Type & Stack:** Single-file HTML/CSS/JavaScript web application (Web Audio API synth engine, no build step)
- **Build & Test Command:** `open index.html` in any browser — no compilation needed. Verify audio plays and export produces valid MIDI/WAV/AIFF.
- **Origin:** Ported from [ldrolez/free-midi-chords](https://github.com/ldrolez/free-midi-chords) Python (chords2midi + Mingus) to a standalone browser app.
- **Target Use:** Retro game music generation (C64 SID, Amiga MOD, NES, SNES, Genesis FM, Atari VCS sound engines).

## Architecture Overview
- **Single file:** `index.html` contains all HTML, CSS, and JS (~46KB)
- **Music theory engine:** Roman numeral resolver, 176 chord progressions from the original MIDI chord pack, scale/chord interval tables
- **Pattern libraries:** Bass (14), Chords (14), Melody (11), Rhythm (10) — each is an 8-step array
- **Synth engine:** Web Audio API oscillators with ADSR, lowpass filter, detuning, feedback-delay reverb
- **12 sound engines:** NES, C64 SID, Amiga MOD, SNES, Genesis FM, Arcade, Atari VCS, Pop, EDM, Industrial, Ambient, Anime
- **Export:** MIDI (pure JS writer, Format 1, 4 tracks), WAV (PCM), AIFF

## Standing Rules
- **No Build Tools:** This is a zero-dependency single HTML file. Do not add npm, webpack, or any build step.
- **Mobile First:** All UI must work on 375px viewport. Test touch interactions.
- **Retro Focus:** Prioritize retro game sound engines (chiptune square/triangle/saw) over modern production sounds.
- **Context Hygiene:** Keep edits focused strictly on the assigned task. Do not refactor unrelated functions.
- **Pattern Libraries:** When adding new patterns, follow the existing 8-step array format with values 0-4.

## Mandatory Session Handoff Rule
- Before ending your session, you MUST overwrite `HANDOFF.md` (strictly under 35 lines) with:
  1. Current branch/commit status and what builds cleanly
  2. Immediate next backlog task (reference GitHub Issue number)
  3. Dead ends / failed approaches tried in this session
- Always include the updated `HANDOFF.md` in your commit/PR.
