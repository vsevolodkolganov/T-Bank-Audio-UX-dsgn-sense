# No Screen Flow
T-Bank Audio UX

## Scenario
Money transfer while walking without touching the phone.

User context:
- hands occupied
- headphones connected
- voice interaction only

Goal:
Transfer money using only **voice + earcons + haptics**.

---

# Interaction Flow

## 1 — Wake

Trigger options:

- voice: "Т-Бот"
- double tap on earbud

System response:

earcon: ear_listen_v1

Meaning:
System is ready to listen.

---

## 2 — Command

User says:

"Переведи 350 рублей Маше"

System actions:

1. Voice Activity Detection
2. Speech recognition
3. Intent parsing

Detected slots:

recipient = Маша  
amount = 350 ₽

---

## 3 — Confirmation

Private environment:

Voice response:
"Перевести 350 рублей Маше?"

Public environment:

earcon: ear_privacy_mid_v1

Voice:
"Подтвердите перевод"

---

## 4 — Authentication

Security layer:

Voice biometric check.

If confidence > threshold:

transaction continues

If confidence < threshold:

system asks for:

- whisper confirmation
or
- tactile confirmation

---

## 5 — Transaction

Earcon:

ear_tx_small_v1

Meaning:
Money is moving.

Stereo behavior:
Sound pans slightly to the **right ear**.

---

## 6 — Result

Success:

ear_success_v1  
haptic_short

Optional voice:
"Готово"

Failure:

ear_error_v1  
haptic_long

Voice:
"Не получилось. Повторить?"

---

# Latency Targets

| Stage | Target |
|------|------|
Wake → Listen | <200 ms |
Speech recognition | <150 ms |
Transaction feedback | <300 ms |

---

# State Machine

States:

IDLE  
LISTENING  
PROCESSING  
CONFIRMING  
AUTHENTICATING  
TRANSACTION  
SUCCESS / ERROR

Transitions triggered by:

- voice input
- earbud tap
- timeout
- biometric result

---

# UX Principle

The user must **always feel feedback**.

Dead silence is never allowed.

Even during processing, the system uses the **Processing Pulse** earcon.
