# Linux Fundamentals Part 1

**Platform:** TryHackMe
**Path:** Pre Security

## Əsas əmrlər

| Əmr | Nə edir |
|---|---|
| `ls` | olduğun qovluğun içini göstərir |
| `ls folder1` | qovluğa girmədən içini göstərir |
| `cd folder1` | qovluğa daxil olur |
| `cd ..` | bir qovluq geri qayıdır |
| `cat fayl.txt` | faylın məzmununu ekrana çıxarır |
| `cat folder1/fayl.txt` | başqa qovluqdakı faylı oxuyur |
| `pwd` | hazırda harada olduğunu göstərir |

## Səhvlərimdən öyrəndiklərim
- `cat`-i **fayl adı olmadan** yazanda o, klaviaturadan giriş gözləyir və yazdığım hər şeyi təkrarlayır. Çıxmaq üçün: **Ctrl + C** (və ya **Ctrl + D**).
- `cat` **qovluqları** oxumur, yalnız faylları. Qovluğun içinə baxmaq üçün `ls`.
- **Tab** düyməsi fayl və qovluq adlarını avtomatik tamamlayır.
- Linux-da qovluqlar adətən **mavi** rənglə göstərilir.

## Blue Team baxışı
Serverlərin çoxu Linux-dur. Log faylları (`/var/log/`) adətən `cat`, `less`, `grep` ilə oxunur. Bir qovluqda `access.log` və `passwords.txt` kimi faylların yanaşı durması özü bir təhlükəsizlik problemidir.
