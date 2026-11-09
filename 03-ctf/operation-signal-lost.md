# Operation: Signal Lost (Beginner CTF)

**Platform:** TryHackMe
**Növ:** Beginner CTF (3 challenge)

İlk CTF-im. Bir rabitə stansiyasının yayımı dayandırılıb. Tapşırıq: açıq qalmış səhifəni tapmaq, hücumçunu izləmək və stansiyanı qorumaq.

## Task 1: Find the exposed page (hücumçu rolu)
1. `dirbuster -u http://signal.thm -w common.txt` ilə directory scan etdim.
2. Tapılan yollar: `/`, `/assets/`, `/diagnostics/`, `/backup/`, `/admin/` (403).
3. `/diagnostics/` səhifəsində diaqnostikaları bir-bir işlətdim.
4. **System information** diaqnostikası `--debug` rejimində texnik konsolunun istifadəçi adını və parolunu açıq göstərdi.
5. Default parolla konsola daxil oldum.

**Bir-birinə bağlanan 3 zəiflik:**
1. Daxili səhifə **internetə açıq** qalıb
2. **Debug rejimi** həssas məlumatları ekrana çıxarır
3. **Default parol** dəyişdirilməyib

## Task 2: Trace the hack (SOC rolu)
Access log-ları analiz etdim:

| Vaxt | Mənbə | Hadisə | Qiymətləndirmə |
|---|---|---|---|
| 08:12–08:30 | 198.51.100.x | `GET /`, `app.css` | normal ziyarətçi |
| 08:41 | 192.0.2.10 | diagnostics (signal), console login | E. Hart (engineer log ilə uyğun) |
| 09:02 | 192.0.2.11 | diagnostics (uplink) | R. Okafor (engineer log ilə uyğun) |
| 09:14:02–05 | 203.0.113.47 | 3 saniyədə 10 qovluq sınanıb (403/404) | **avtomatik directory scan** |
| 09:14:03 | 203.0.113.47 | `/backup/` → 200 | həssas qovluq tapılıb |
| 09:15:03 | 203.0.113.47 | `/diagnostics/?check=system` | parolların göründüyü diaqnostika |
| 09:16 | unknown | `restart-signal issued` | **yayım söndürülüb** |

**Nəticə:** Hücumçu Task 1-də etdiyim addımların eynisini edib: scan → diagnostics → system → default parol → konsol.

**Öyrəndiyim:** log analizində tək sətrə yox, **nümunəyə** (eyni saniyədə çoxlu sorğu) və **korrelyasiyaya** (access log + engineer log vaxtları) baxılır. Bunu **timeline qurmaq** adlandırırlar.

## Task 3: Secure the relay (Incident Response)
Firewall-a `Deny 203.0.113.47` qaydası əlavə etdim.

- Firewall qaydaları adətən yuxarıdan aşağı oxunur və ilk uyğun gələn tətbiq olunur. Deny qaydası `allow any`-dən **yuxarıda** olmalıdır.
- IP bloklamaq yalnız **containment**-dir. Hücumçu başqa IP-yə keçə bilər.

**Əsl həll (eradication):**
- default parolu dəyişmək
- debug rejimini söndürmək
- diagnostics-i yalnız daxili şəbəkəyə açmaq

## Incident Response ardıcıllığı
**Detection → Containment → Eradication → Recovery**

## OT/ICS əlaqəsi
Engineer log-dakı `unknown restart-signal issued` sətri sənaye mühitində **"naməlum şəxs PLC-ni STOP rejiminə keçirdi"** ola bilərdi. Fərq odur ki, OT-da nəticə fiziki prosesdir: nasos, turbin, istehsal xətti.
Default parollar OT/IoT cihazlarında hələ də çox yayılıb (Mirai botneti milyonlarla cihazı bu yolla ələ keçirmişdi).
