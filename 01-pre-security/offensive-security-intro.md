# Offensive Security Intro

**Platform:** TryHackMe
**Path:** Pre Security → Introduction to Cyber Security

## Nə etdim
- Saxta bank saytında (FakeBank) hesab nömrəmi tapdım.
- URL-ə əllə yol əlavə edərək gizli admin səhifəsini açdım.
- Admin panel vasitəsilə öz hesabıma pul köçürdüm.

## Nə öyrəndim
- Sayt admin səhifəsini gizlədib, amma ona parol qoymayıb. Ünvanı bilən hər kəs girə bilir.
- Bunun adı **Broken Access Control**-dur və web-də ən çox rast gəlinən zəifliklərdən biridir.
- Gizli səhifələri tapmaq üçün **directory brute-force** alətlərindən (məsələn `dirbuster`, `gobuster`) istifadə olunur.

## Blue Team baxışı
Log-larda bir IP-dən qısa vaxtda çoxlu **404** cavabı, sonra birdən **200** gəlməsi directory scan əlamətidir. Admin səhifələrinə gələn gözlənilməz sorğular alert yaratmalıdır.
