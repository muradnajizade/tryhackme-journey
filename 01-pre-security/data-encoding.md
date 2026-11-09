# Data Encoding

**Platform:** TryHackMe
**Path:** Pre Security

## Nə öyrəndim
- **ASCII:** ingilis hərfləri və əsas simvollar üçün köhnə standart (7 bit).
- **Unicode:** dünyadakı bütün simvollara (emoji, yapon hərfləri, şahmat fiqurları) nömrə verir. Yazılışı: `U+XXXX`.
- **UTF-8 / UTF-16 / UTF-32:** eyni Unicode nömrəsini baytlarla saxlamağın fərqli üsulları.
  - UTF-8: 1–4 bayt (internetdə ən çox istifadə olunan)
  - UTF-16: 2 və ya 4 bayt
  - UTF-32: həmişə 4 bayt

## Səhvlərimdən öyrəndiklərim
- Sual simvolun **adını** yox, **simvolun özünü** istəyəndə ad yazmaq səhvdir.
- Klaviaturada olmayan simvolları yazmaq üçün: kopyala-yapışdır və ya **Win + .** (emoji paneli).
- Bir-birinə çox oxşayan simvollar fərqli ola bilər, məsələn yapon `ツ` (tsu) və `シ` (shi).

## Blue Team baxışı
Hücumçular oxşar görünən Unicode simvollarından saxta domenlər yaratmaq üçün istifadə edirlər (**homoglyph / IDN phishing**). Məsələn latın `a` əvəzinə kiril `а`. Gözlə fərq görünmür, amma kodları fərqlidir.
