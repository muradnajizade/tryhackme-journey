# Data Representation

**Platform:** TryHackMe
**Path:** Pre Security

## Say sistemləri

| Sistem | Əsas | Rəqəmlər | Nümunə |
|---|---|---|---|
| Binary | 2 | 0–1 | `1111 1111` |
| Octal | 8 | 0–7 | `377` |
| Decimal | 10 | 0–9 | `255` |
| Hexadecimal | 16 | 0–9, A–F | `FF` |

## Nə öyrəndim
- 1 hex rəqəmi = 4 bit, 2 hex rəqəmi = 1 bayt (8 bit).
- `FF` = `1111 1111` = 255 (bir baytın ala biləcəyi ən böyük dəyər).
- `FFFFFF` bir ədəd kimi = 16,777,215 ≈ 17 milyon.
- Bu, **24-bit rəng** sayıdır: Qırmızı, Yaşıl, Mavi üçün hər biri 1 bayt. Ona görə CSS-də `#FFFFFF` ağdır.

## Blue Team baxışı
Hex-i oxumaq hər gün lazımdır: log-larda, şəbəkə paketlərində (Wireshark), MAC ünvanlarında və malware analizində.
