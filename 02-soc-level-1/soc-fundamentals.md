# SOC Fundamentals

**Platform:** TryHackMe
**Path:** SOC Level 1

## SOC-un iki əsas qabiliyyəti
- **Detection:** təhlükəni aşkarlamaq (nəyinsə baş verdiyini görmək)
- **Response:** təhlükəyə cavab vermək (bloklamaq, təcrid etmək)

## SOC-un üç sütunu
**People, Process, Technology.** Peşəkar insanlar, düzgün proseslər və müasir alətlər birlikdə yetkin SOC yaradır.

## SOC rolları
| Rol | Məsuliyyəti |
|---|---|
| SOC Analyst L1 | Alert triage, ilk araşdırma, hesabat |
| SOC Analyst L2 | Dərin araşdırma, mənbələri əlaqələndirmə |
| SOC Analyst L3 | Təhdid ovu (threat hunting), incident response |
| Security Engineer | Təhlükəsizlik alətlərini qurmaq və konfiqurasiya etmək |
| Detection Engineer | Alert yaradan qaydaları yazmaq |
| SOC Manager | Prosesləri idarə etmək, CISO-ya hesabat |

## Praktik tapşırıq: port scan alerti
SIEM-də port scan alertini **5W** ilə araşdırdım:
- **What:** port scan
- **When:** alertin vaxtı
- **Where:** hədəf (destination) host
- **Who:** mənbə (source) IP
- **Why:** Vulnerability assessment komandası planlı scan edirdi → **Intended**

Alerti **Acknowledge** edib öz üzərimə götürdüm, araşdırdım və planlı fəaliyyət olduğu üçün **False Positive** kimi bağladım.

## Öyrəndiklərim
- **Source IP** (hücumun gəldiyi yer) ilə **Destination IP** (hədəf) fərqlidir.
- Real SIEM-lər (Splunk, Microsoft Sentinel, Elastic, QRadar, Wazuh) eyni məntiqlə işləyir, amma log sayı milyonlarla olur və axtarış sorğu dili ilə edilir.
- L1 analitikin əsas işi səs-küydən (false positive) əsl təhlükəni ayırmaqdır.

## OT/ICS əlaqəsi
**Detection Engineer** rolu OT üçün çox uyğundur: PLC/SCADA trafikində (Modbus, S7, DNP3) anomaliyaları tutan qaydalar yazmaq.
Nozomi, Claroty, Dragos kimi OT monitorinq alətləri alertlərini məhz belə SIEM-lərə göndərir.
