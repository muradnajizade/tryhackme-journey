# TryHackMe Journey

Mexatronika tələbəsi → **OT/ICS Security (Blue Team)**

Bu repo TryHackMe-də keçdiyim otaqlar üzrə qeydlərimdir. Hər qeyddə nə öyrəndiyimi və bunun **Blue Team / SOC** baxışından nə üçün vacib olduğunu yazıram.

> Qeydlərdə flag və hazır cavablar yoxdur, yalnız anlayışlar və metodlar var.

## Otaqlar

| # | Otaq | Path | Mövzu |
|---|---|---|---|
| 1 | [Offensive Security Intro](01-pre-security/offensive-security-intro.md) | Pre Security | Gizli səhifələr, Broken Access Control |
| 2 | [Inside a Computer System](01-pre-security/inside-a-computer-system.md) | Pre Security | Kompüter hissələri |
| 3 | [Linux Fundamentals Part 1](01-pre-security/linux-fundamentals-part1.md) | Pre Security | `ls`, `cd`, `cat`, `pwd` |
| 4 | [Windows Basics](01-pre-security/windows-basics.md) | Pre Security | Windows Security, EICAR, persistence |
| 5 | [Data Representation](01-pre-security/data-representation.md) | Pre Security | Binary, hex, decimal |
| 6 | [Data Encoding](01-pre-security/data-encoding.md) | Pre Security | ASCII, Unicode, UTF-8/16/32 |
| 7 | [What is Networking](01-pre-security/what-is-networking.md) | Pre Security | IP, MAC, MAC spoofing, ping |
| 8 | [SOC Fundamentals](02-soc-level-1/soc-fundamentals.md) | SOC Level 1 | SOC rolları, 5W, SIEM alert |
| 9 | [Operation: Signal Lost](03-ctf/operation-signal-lost.md) | Beginner CTF | Tam incident timeline |

## Ən vacib dərslər

- Səhifəni **gizlətmək** onu **qorumaq** demək deyil.
- **Default parollar** (`admin:admin`) real hücumların ən çox istifadə olunan giriş yoludur, xüsusilə OT/IoT cihazlarında.
- Log analizində tək sətrə yox, **nümunəyə** və **zaman əlaqəsinə** baxılır.
- IP bloklamaq yalnız ilk addımdır (**containment**). Kök səbəb aradan qaldırılmalıdır.
