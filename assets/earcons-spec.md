# Earcons Specification
Audio assets for the voice-first banking interface

This document lists all production earcons, their intended use, technical parameters and export guidance.

---

## Naming convention
All files: `{id}_v{version}.{ext}`  
Examples: `ear_listen_v1.wav`, `ear_success_v1.wav`, `sonic_logo_v1.wav`

Export formats:
- Primary: WAV, 48 kHz, 24-bit
- Lightweight: OGG Vorbis 48 kHz, VBR (for mobile preview)
- Loops must be exported as seamless WAV clips.

Loudness target: −16 ± 2 LUFS (adjust per platform).

---

## Earcon list

### 1) `ear_listen_v1` — Listening / Inhale
- Purpose: indicates system ready to listen
- Duration: 200–240 ms
- Notes: rising two-note gesture (G3 → C4)
- Frequency focus: 600–1200 Hz
- ADSR: A 2 ms / D 100 ms / S 0.2 / R 120 ms
- FX: short reverb tail (50–100 ms), subtle HP filter sweep
- Export: single shot, centered

### 2) `ear_processing_loop_v1` — Processing Pulse
- Purpose: fills pauses during processing (loopable)
- Loop length: 500 ms (seamless)
- Layers: low thump (C2) + high tick (C5)
- Volume: −18 dB relative to voice
- Frequency: 60–240 Hz (body) + 2–4 kHz ticks
- Export: 500 ms seamless WAV, name indicates BPM/loop length

### 3) `ear_success_v1` — Success Quint (brand chord)
- Purpose: confirmed successful operation
- Duration: 250–350 ms (plus tail)
- Notes: major fifth (C4 + G4) with metallic bell partials
- ADSR: A 2 ms / D 200 ms / S 0.7 / R 300 ms
- FX: reverb 220–300 ms; slight delay on tail
- Export: single shot, consider stereo width on tail for richness

### 4) `ear_error_v1` — Error / Reject
- Purpose: non-blocking error feedback
- Duration: 200–320 ms
- Notes: short damped dissonance (minor second)
- ADSR: short attack, fast decay
- FX: minimal reverb (dry), avoid high frequencies that startle
- Export: single shot, lower loudness than success

### 5) `ear_tx_small_v1` — Outgoing Transfer Whoosh
- Purpose: represent money leaving account
- Duration: 120–180 ms
- Design: noise sweep + tonal accent, pan slightly right
- FX: HP sweep 200→6k Hz, short reverb tail
- Export: single shot, stereo with right bias

### 6) `ear_privacy_low_v1` / `ear_privacy_mid_v1` / `ear_privacy_high_v1` — Balance textures
- Purpose: convey relative balance without numbers
- Duration: ~400–600 ms
- Low: thin sine + small bell partials (low density)
- Mid: two folded layers (pad + harmonic)
- High: dense harmonic cluster with gentle low end
- Use: public / privacy mode responses for balance queries
- Export: single shots, consistent loudness, lowpass to avoid harshness

---

## UX notes for designers & devs
- Keep earcon durations < 600 ms to preserve perceived speed.
- Maintain tonal unity: use same base key (C major) across melodic earcons.
- Use subtle stereo panning for directionality (left=incoming, right=outgoing).
- Always accompany critical earcons with haptics on the phone (if available).
- Test across headphone types (in-ear, on-ear, ANC) and normalize accordingly.

---
