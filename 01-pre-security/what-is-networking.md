# What is Networking

**Platform:** TryHackMe
**Path:** Pre Security

## IP ünvanı
- **IP** = Internet Protocol.
- IPv4 ünvanı 4 hissədən ibarətdir, hər hissə **octet** adlanır (8 bit, 0–255).
- Məsələn `192.168.1.10` → 4 octet × 8 bit = 32 bit.

## MAC ünvanı
- **MAC** = Media Access Control.
- Şəbəkə kartının zavodda verilmiş fiziki ünvanıdır, məsələn `00:12:32:2F:33:39`.
- IP şəbəkədən asılı olaraq dəyişir. MAC isə kartla gəlir, **amma proqramla saxtalaşdırıla bilər**.

## MAC spoofing (labda etdim)
Otel Wi-Fi-ı yalnız pul ödəyənlərin MAC ünvanlarını buraxırdı.
Bob-un MAC ünvanını Alice-in ünvanı ilə əvəz etdim. Router Bob-u Alice zənn edib paketlərini internetə buraxdı.

**Nəticə:** MAC ünvanı etibarlı identifikasiya üsulu deyil.

Labda öyrəndiyim praktik məqam: düyməni dəfələrlə basanda köhnə paketlər növbədə qalır. Bir dəfə bas və gözlə.

## Ping (ICMP)
- `ping` **ICMP** protokolundan istifadə edir.
- `ping 10.10.10.10`: hədəfə paket göndərib cavab gözləyir.
- `ping -c 4 10.10.10.10`: yalnız 4 paket göndərir (Linux-da `-c` olmasa, Ctrl + C ilə dayandırılır).

Nəticəni oxumaq:
- `time=9.47 ms`: gedib-gəlmə vaxtı
- `ttl=56`: paketin keçə biləcəyi router sayı
- `0% packet loss`: heç bir paket itməyib

`8.8.8.8` Google-un DNS serveridir. İnternetin işlədiyini yoxlamaq üçün ən çox istifadə olunan ünvandır.

## Blue Team baxışı
- Şəbəkədə **eyni MAC ünvanlı iki cihazın** eyni vaxtda görünməsi MAC spoofing əlamətidir.
- Hücumçular canlı cihazları tapmaq üçün **ping sweep** edirlər. Ona görə bəzi firewall-lar ICMP-ni bloklayır.
- Ping vaxtının və packet loss-un birdən artması şəbəkə problemi və ya **DDoS** əlaməti ola bilər.
- **OT-da:** köhnə sənaye sistemləri cihazları yalnız MAC/IP ilə tanıyır. Hücumçu özünü PLC və ya HMI kimi təqdim edə bilər.
