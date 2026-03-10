<?xml version="1.0" encoding="UTF-8"?>
<svg width="1200" height="360" viewBox="0 0 1200 360" xmlns="http://www.w3.org/2000/svg" font-family="Inter, Arial, sans-serif">
  <style>
    .bg { fill:#0b0b0b }
    .title { fill:#fff; font-size:28px; font-weight:700 }
    .subtitle { fill:#ddd; font-size:14px }
    .pill { fill:#ffdd2d; stroke:none; rx:18 }
    .panel { fill:#ffffff10; stroke:#ffffff22; stroke-width:0.5; rx:10 }
    .small { fill:#eee; font-size:12px }
  </style>

  <rect class="bg" x="0" y="0" width="1200" height="360"/>
  <text class="title" x="60" y="64">T-Bot — T-Bank Audio UX</text>
  <text class="subtitle" x="60" y="94">Zero-UI banking: voice + sound + privacy (fast micro-transactions in your ears)</text>

  <!-- left hero -->
  <g transform="translate(60,120)">
    <rect x="0" y="0" width="320" height="200" class="panel"/>
    <text class="small" x="20" y="28">User context</text>
    <text class="small" x="20" y="56">Hands occupied • On the move • Privacy concerns</text>

    <rect x="18" y="80" width="120" height="36" fill="#222" rx="8"/>
    <text class="small" x="78" y="104" text-anchor="middle">Voice • Commands</text>

    <rect x="160" y="80" width="120" height="36" fill="#222" rx="8"/>
    <text class="small" x="220" y="104" text-anchor="middle">Earcons • Feedback</text>

    <rect x="18" y="128" width="262" height="36" fill="#222" rx="8"/>
    <text class="small" x="149" y="152" text-anchor="middle">Privacy modes • VoiceID • Haptics</text>
  </g>

  <!-- right hero -->
  <g transform="translate(420,120)">
    <rect x="0" y="0" width="720" height="200" class="panel"/>
    <text class="small" x="20" y="28">Design goals</text>
    <text class="small" x="20" y="56">Speed • Safety • Emotional branding • Accessibility</text>

    <g transform="translate(20,82)">
      <rect x="0" y="0" width="200" height="36" fill="#ffdd2d" rx="8"/>
      <text x="100" y="24" text-anchor="middle" font-weight="700">Fast</text>

      <rect x="220" y="0" width="200" height="36" fill="#9be4ff" rx="8"/>
      <text x="320" y="24" text-anchor="middle" font-weight="700">Private</text>

      <rect x="440" y="0" width="200" height="36" fill="#c2ffd6" rx="8"/>
      <text x="540" y="24" text-anchor="middle" font-weight="700">Trusted</text>
    </g>

    <text class="small" x="20" y="142">Core assets</text>
    <text class="small" x="20" y="164">Sonic logo • Earcon library • Security model • UX flows</text>
  </g>
</svg>

# T-Bank Audio UX
### Zero-UI Banking Interface

Control your finances without looking at the screen.

T-Bot is an experimental **voice-first banking interface** designed for situations where screens are inconvenient or unsafe.

Walking with groceries.  
Driving in traffic.  
Running through the city.

Your phone stays in your pocket.  
Your finances stay in your ears.

---

# The Problem

Modern banking apps depend entirely on visual interfaces.

But in many real situations:

- hands are occupied
- eyes are focused elsewhere
- unlocking and navigating an app becomes slow and unsafe

Financial interaction becomes **friction**.

---

# The Shift: Zero-UI

By 2026, interfaces increasingly move beyond screens.

Voice, sound and context-aware systems allow interaction without visual attention.

This project explores a **Zero-UI banking paradigm**.

---

# The Solution: T-Bot

T-Bot is an invisible financial assistant that lives in your headphones.

It combines:

- voice interaction
- sonic feedback
- contextual privacy
- biometric security

All financial actions can be performed using **voice + sound + haptics**.

---

# Core Idea

Sound replaces the screen.

Instead of icons and buttons, the interface uses a **language of earcons** — functional sound signals.

Examples:

| Action | Sound |
|------|------|
Listening | rising tone |
Processing | low pulse |
Success | major chord |
Error | descending tone |

These sounds form an **auditory interface vocabulary**.

---

# Smart Silence

Traditional voice assistants often feel noisy.

T-Bot uses **Smart Silence Protocol**.

The system dynamically adapts between four modes:

| Mode | Context |
|-----|------|
Silent | meetings / do-not-disturb |
Micro | public environments |
Conversational | quiet spaces |
Ambient | long operations |

The goal is simple:

The interface should always feel **alive but unobtrusive**.

---

# Security

Removing the screen requires stronger security.

T-Bot uses:

- Voice biometric identification
- Anti-spoofing protection
- Whisper confirmation for critical actions

Large transfers require additional confirmation signals.

---

# Example Scenario

User walking with grocery bags.

Command:

"Переведи 350 рублей Маше"

System flow:

1. Listening tone
2. Intent recognition
3. Confirmation
4. Voice biometric check
5. Transaction
6. Success chord

Total interaction time:

≈ 2 seconds.
# Demo Interaction

User: "Переведи 500 Маше"

T-Bot:
🎧 listening tone  
🎧 processing pulse  
🎧 success chord

Transaction completed in 2 seconds.
---

# Sound as Data

Financial information can also be represented as sound.

Example:

Balance query in privacy mode.

Instead of speaking numbers, the system uses **sound density**.

Low balance → light texture  
Medium balance → fuller sound  
High balance → rich harmonic layer

This allows private feedback even in crowded environments.

---

# System Architecture

![State Machine](diagram/state-machine.svg)

Interaction states:

IDLE → LISTENING → PROCESSING → CONFIRMATION → AUTH → TRANSACTION → RESULT

---

# Why This Matters

Audio UX opens new opportunities for financial interaction.

Benefits:

- safer interactions while moving
- accessibility for visually impaired users
- faster micro-transactions
- deeper emotional connection with the brand

---

# Project Structure
