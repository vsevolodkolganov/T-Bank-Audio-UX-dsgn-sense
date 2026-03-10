Happy path (quiet)

Input: full phrase -> confirm -> success.

Expect: full voice confirmation, success earcon, receipt pushed.

Public path (metro)

Input: full phrase in noisy environment

Expect: no digits spoken, ear_privacy_mid_v1 used, success earcon only, haptic feedback.

ASR fallback

Input: mumble -> low ASR confidence

Expect: ear_error_v1 + request to repeat or tactile confirm.

VoiceID reject

Input: confirmed phrase but voice mismatch

Expect: require tactile long-press; no transfer without it.

No network

Input make transfer offline

Expect: queue offline + voice: «Связь потеряна» + ear_error_v1.
