# Windows Basics

**Platform:** TryHackMe
**Path:** Pre Security

## Nə etdim
- Quraşdırıcı (installer) ilə proqram qurdum.
- **Settings → Time & Language** bölməsində region parametrlərinə baxdım.
- **Task Manager → Users** tabında daxil olan istifadəçini yoxladım.
- **Windows Security**-də **Custom scan** ilə müəyyən qovluğu skan etdim və EICAR test faylını tapdım.

## Nə öyrəndim
- **Quick scan** hər yeri yoxlamır. Müəyyən qovluğu yoxlamaq üçün **Custom scan** lazımdır.
- **EICAR** zərərsiz test faylıdır. Antivirusun işlədiyini yoxlamaq üçün istifadə olunur.
- Təhlükənin **See details** bölməsində **Affected items** göstərilir: təkcə fayl yox, onunla bağlı hər şey.

## Blue Team baxışı: persistence
Affected items-də fayldan əlavə bunlar da var idi:
- `C:\Windows\System32\Tasks\...` → **Scheduled Task**
- `HKLM\...\Schedule\TaskCache\...` → həmin tapşırığın **Registry** qeydləri

Zərərli proqram kompüter yenidən başlayanda da işləsin deyə özünü Scheduled Task kimi qeyd edir. Bunun adı **persistence**-dir.
Yalnız faylı silmək kifayət deyil. Onunla bağlı tapşırıqları və registry açarlarını da tapıb təmizləmək lazımdır.
