# T-Bank Audio UX — Без-экранный путь: перевод на ходу + «Умная тишина»

**Автор**: Колганов Всеволод Р.  
**Проект**: T-Bank Audio UX (dsgn sense)
  
## Цель
Обеспечить возможность безопасного и быстрого управления финансами без использования экрана: голос, звуки и тактильная обратная связь.

## Перевод на ходу — flow (кратко)
1. Триггер: double-tap на наушнике *или* «Т-Бот, плати 350 Маше».  
2. `ear_listen_v1` (вход). ASR слушает.  
3. Если полный запрос: подтверждение. Если публично — замена цифр на `ear_privacy_mid_v1`.  
4. Подтвердил — VoiceID → execute → `ear_tx_small_v1` → на success: `ear_success_v1`.  
5. Error → `ear_error_v1` + предложение альтернативы.

## Правила «Умной тишины»
- Режимы: Silent / Micro / Conversational / Ambient.  
- Решение режима: VAD + SNR + голосовой детектор + proximity + user prefs.  
- Пороги SNR: Quiet ≥ 20 dB, Mixed 8–20 dB, Noisy < 8 dB.  
- В публичных условиях — не озвучивать цифры, использовать earcons + audio-avatars.

## Earcon mapping (реализация)
- wake → `ear_listen_v1`  
- processing → `ear_processing_loop_v1` (loopable)  
- privacy confirmation → `ear_privacy_mid_v1`  
- tx out → `ear_tx_small_v1` (pan right)  
- success → `ear_success_v1`  
- error → `ear_error_v1`

## Security
- VoiceID + anti-spoofing mandatory.  
- Для крупных переводов: whisper code + tactile confirm.

## Тесты (MVP)
- Лаб: 20 участников (тишина / парк / метро) — метрики CR, TtC, ASR errors.  
- Бета: 200 пользователей (2 недели) — сравнение verbose vs micro.


