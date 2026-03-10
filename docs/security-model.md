# Security Model — Voice Payments

This document describes the security model for voice-activated transactions.

Goals:
- prevent unauthorized transfers
- maintain privacy in public spaces
- provide usable fallback for real-world scenarios

---

## Threats considered
- replay attacks (recorded voice)
- synthetic voice (deepfakes)
- social engineering while the user is distracted
- device theft / physical access

---

## Layers of security

1. **Device binding & enrollment**
   - User enrolls device(s) during onboarding.
   - Device public key is registered; transactions require device signature for high-risk ops.
   - Pairing limits the set of devices allowed to authorize transactions.

2. **Voice Biometrics (VoiceID)**
   - Model outputs confidence score [0..1].
   - Continuous enrollment improves model robustness.
   - Thresholds:
     - Normal ops: accept if score ≥ 0.85
     - Sensitive ops (above limit): require additional confirmation if score in [0.6..0.85]
     - Reject if score < 0.6

3. **Anti-Spoofing & Liveness**
   - Anti-spoof detectors (spectral, phase, and anti-artifact nets) run before voiceID.
   - Liveness checks: challenge-response (e.g., ask to say a random word or whisper code) if environment suspicious.

4. **Whisper Code**
   - For high-value transfers, the user can confirm by whispering a pre-shared short code ("шёпот-код").
   - Whisper detection uses energy and frequency domain checks to ensure low amplitude signal.

5. **Tactile & Device-confirm fallback**
   - When voice confidence is low or privacy concerns arise, require tactile input:
     - long-press on earbud (1.5 s) OR
     - unlock phone with biometrics and confirm in app

6. **Policy Engine**
   - Enforces per-user limits and risk rules (time-of-day, new payee, unusual amount).
   - For flagged transactions, require multi-factor (voice + tactile + device biometrics).

7. **Network & Transport**
   - All audio samples and verification data encrypted in transit (TLS 1.3).
   - Minimal required data sent to server: hashed voice embeddings (not raw audio, except for anti-spoofing when allowed).
   - Local on-device models preferred for initial voice matching (on-device privacy).

8. **Audit & Non-Repudiation**
   - All voice-confirmed transactions logged with: timestamp, device ID, voice model fingerprint (hash), ASR transcript, policy decisions.
   - Logs stored in immutable ledger within bank backend.

---

## UX security guidelines

- Never read full account numbers aloud in public mode.
- For public confirmations, replace numbers with audio-avatars or privacy textures.
- Provide clear fallback flows: tactile confirm or app confirmation link.
- Ensure false reject cases are recoverable quickly (graceful retry).

---

## Risk thresholds (example)
- Low risk: transfers < 3,000 RUB — voiceID accepted (score ≥ 0.8)
- Medium risk: transfers 3k–50k RUB — voiceID + tactile OR whisper code when score ∈ [0.6..0.85]
- High risk: >50k RUB — voiceID + device biometric + app confirmation

---

## Incident response
- On suspected fraud: block outgoing voice transactions, send push / SMS to owner, require web login to enable voice payments again.
- Allow user to revoke a device from account and reset voice profile.

---

## Privacy & Data Retention
- Raw audio retention minimized: keep raw audio only when needed for anti-spoofing analysis; otherwise store voice embeddings and hashes.
- Retention policy: raw audio max 30 days (unless user consents), embeddings/audit logs retained per bank policy/regulation.
- Users can request deletion/anonymization of voice data subject to regulatory rules.

---
