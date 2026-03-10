# Voice Interaction Prototype
T-Bank Audio Interface

This document demonstrates how a user interacts with the banking system without using a screen.

The interface relies on three elements:

- voice commands
- earcons (functional sounds)
- short system responses

---

# Interaction Principles

1. The system responds within 150–300 ms.
2. Every step is confirmed by sound.
3. Critical actions require confirmation.

---

# Scenario 1: Money Transfer

Context: user walking outside, phone in pocket.

User:
"Переведи 350 рублей Маше"

System flow:

1. Listening signal  
🎧 rising tone

2. Intent recognized

Voice response:
"350 рублей Маше. Подтвердить?"

3. Voice biometric check

4. Transaction processing  
🎧 low pulse

5. Success signal  
🎧 major chord

Voice response:
"Готово."

Total interaction time:  
≈ 2 seconds

---

# Scenario 2: Balance Request

User:
"Какой у меня баланс?"

System determines privacy context.

If user is in a quiet environment:

Voice response:
"Ваш баланс 42 300 рублей."

Success tone plays.

---

# Scenario 3: Balance in Public

If environment is noisy or public.

System switches to **privacy audio mode**.

Instead of speaking the number, the system plays a **balance texture**.

Example:

Low balance → thin tone  
Medium balance → harmonic pad  
High balance → rich layered sound

User understands financial state without hearing numbers.

---

# Scenario 4: Quick Payment

User in store queue.

User:
"Оплати 240 рублей"

System:

🎧 listening tone

Voice:
"240 рублей. Подтвердить?"

User:
"Да"

Processing pulse → success chord

Voice:
"Оплачено."

---

# Scenario 5: Suspicious Command

If system detects voice mismatch.

User:
"Переведи 10 тысяч"

System:

🎧 error tone

Voice response:
"Нужна дополнительная проверка."

User must confirm using voice + phone unlock.

---

# Voice Command Structure

Commands follow simple patterns:

"Переведи [сумма] [контакт]"

"Какой баланс"

"Оплати [сумма]"

"Покажи последние операции"

---

# Interaction States

IDLE  
LISTENING  
PROCESSING  
CONFIRMATION  
AUTHENTICATION  
TRANSACTION  
RESULT

Transitions are illustrated in the system state diagram.

---

# UX Goal

The user should feel that the system is:

fast  
safe  
predictable  
almost invisible
