# YMU446 UNIX PROGRAMLAMA – Sınav Özeti ve Soru-Cevap

## 1. Dosya ve Dizin İşlemleri

| Komut | Açıklama | Örnek |
|-------|----------|-------|
| `ls` | Dosya ve klasörleri listeler | `ls -l`, `ls -a` |
| `cd` | Dizinler arasında geçiş | `cd dosyalar`, `cd ..` |
| `mkdir` | Yeni dizin oluşturur | `mkdir yeni_klasor` |
| `rmdir` | Boş dizini siler | `rmdir resimler` |
| `rm` | Dosya siler | `rm dosya.txt` |
| `cp` | Dosya kopyalar | `cp dosya1 klasor/` |
| `mv` | Dosya taşır veya adını değiştirir | `mv dosya1 dosya2` |
| `pwd` | Çalışılan dizini gösterir | `pwd` |
| `cat` | Dosya içeriğini gösterir | `cat dosya.txt` |
| `wc` | Satır, kelime, karakter sayar | `wc dosya.txt`, `wc -l`, `wc -w`, `wc -c` |

## 2. Metin Görüntüleme ve Dosya Oluşturma

| Komut | Açıklama | Örnek |
|-------|----------|-------|
| `echo` | Ekrana yazı yazar | `echo Merhaba` |
| `pico` | Metin editörü | `pico dosya.txt` |
| `nano` | Metin editörü | `nano dosya.txt` |
| `vi` | Gelişmiş metin editörü | `vi dosya.txt` |

## 3. Dosya Erişim Hakları (Permissions)

- `r` - okuma (read)
- `w` - yazma (write)
- `x` - çalıştırma (execute)

**Biçim:** `-rwxr-xr--`

**chmod ile değiştirme:**
```bash
chmod 755 dosya.txt  # Sayısal değerle
chmod +x dosya.txt   # Sembolik değerle
```

## 4. Dosya Adı Filtreleme ve Karakter Eşleşme

| Wildcard | Açıklama | Örnek |
|----------|----------|-------|
| `*` | Her şeyle eşleşir | `ls *txt` |
| `?` | Tek karakter eşleşmesi | `ls ?.txt` |
| `[a-z]` | Belirli aralıkla eşleşme | `ls [a-c]*` |
| `[!a-z]` | Dışlama | `ls [!a-z]*` |

## 5. Çıktı Yönlendirme

| Operatör | Açıklama | Örnek |
|----------|----------|-------|
| `>` | Çıktıyı dosyaya yazar | `echo "ali" > users.txt` |
| `>>` | Çıktıyı dosyaya ekler | `echo "mehmet" >> users.txt` |
| `<` | Dosyadan okuma yönlendirmesi | `wc -l < dosya.txt` |
| `\|` | Pipe: İki komutu birbirine bağlar | `who \| wc -l` |

## 6. Sık Kullanılan Komutlar

| Komut | Açıklama |
|-------|----------|
| `who` | Giriş yapan kullanıcıları gösterir |
| `whoami` | Aktif kullanıcı adını gösterir |
| `ps aux` | Çalışan tüm işlemleri listeler |
| `grep` | Belirli kalıba uyan satırları filtreler |
| `head` | İlk N satırı gösterir |
| `sort` | Sıralama yapar (`-k`, `-r`, `%mem` gibi) |

## 7. Diğer Faydalı Komutlar

| Komut | Açıklama | Örnek |
|-------|----------|-------|
| `touch` | Boş dosya oluşturma | `touch yeni.txt` |
| `find` | Dosya arama | `find . -name "*.txt"` |
| `diff` | İki dosya farkını gösterme | `diff dosya1 dosya2` |
| `man` | Yardım kılavuzu | `man ls` |
| `chown` | Dosya sahipliğini değiştirme | `chown kullanici:grup dosya` |
| `umask` | Varsayılan izin değeri | `umask 022` |

---

# 📝 Soru-Cevap Tekrar Kartları

### ❓ 1. Bir klasörün ismini nasıl değiştirirsin?
➡️ `mv dosyalar arsiv`

### ❓ 2. pico ile yeni bir dosya oluştur ve içinde isimler yaz.
➡️ `pico isimler.txt` # Sonra CTRL+O, CTRL+X

### ❓ 3. Bir dosyanın karakter, kelime, satır sayılarını nasıl görürüz?
➡️ `wc metin.txt`

### ❓ 4. rwxr-xr-- ne anlama gelir?
➡️ Kullanıcı: rwx | Grup: r-x | Diğer: r--

### ❓ 5. Bir dosyaya çalıştırma yetkisi nasıl eklenir?
➡️ `chmod +x run.sh`

### ❓ 6. echo çıktısını bir dosyaya yazdırmak
➡️ `echo "Merhaba" > selam.txt`

### ❓ 7. Sadece dosyaları sayan bir komut yaz.
➡️ `ls -l | grep "^-" | wc -l`

### ❓ 8. *, ?, [a-z] gibi wildcard'lar ne işe yarar?
➡️ `*.txt` = .txt uzantılılar, `?.sh` = 2 harfli .sh, `[a-c]*` = a/b/c ile başlayanlar

### ❓ 9. Yeni bir klasör oluştur, içine dosya kopyala
➡️ `mkdir yedek`
➡️ `cp veri.txt yedek/`

### ❓ 10. Shell'de bir döngü yaz
```bash
for i in *.txt; do
    cat "$i"
done
```

### ❓ 11. whoami ve pwd komutları ne işe yarar?
➡️ `whoami`: kullanıcı adı | `pwd`: dizin yolu

### ❓ 12. Bir dosyanın içeriğini silmeden adını değiştir.
➡️ `mv eski.txt yeni.txt`

### ❓ 13. Bir klasörü ve içeriğini sil
➡️ `rm -r gecici`

### ❓ 14. grep ile bir satırı bul
➡️ `grep "HATA" log.txt`

### ❓ 15. Sistemdeki aktif kullanıcı sayısını bul
➡️ `who | wc -l`

### ❓ 16. Dosyaları büyüklüğüne göre sırala
➡️ `ls -lhS`

### ❓ 17. En çok RAM kullanan 5 işlem nedir?
➡️ `ps aux --sort=-%mem | head -5`

### ❓ 18. Bir dosyanın izinlerini sadece okumaya düşür
➡️ `chmod 444 dosya.txt`

### ❓ 19. Sadece .sh uzantılı dosyaları bul
➡️ `find . -name "*.sh"`

### ❓ 20. Aynı içeriğe sahip iki dosya arasında farkı göster
➡️ `diff dosya1.txt dosya2.txt`


# UNIX Komutları ve Örnekler

## Temel Sistem Komutları

### Tarih ve Kullanıcı Bilgileri

```bash
$ date
Sali mar 2025-03-04

$ who
# Sistemde oturum açmış kullanıcıları listeler

$ whoami
# Mevcut kullanıcı adını gösterir
```

## Metin ve Dosya İşlemleri

### Ekrana Yazı Yazdırma

```bash
$ echo merhaba yazilim
merhaba yazilim

$ echo merhaba yazilim      yazilim
merhaba yazilim  yazilim

$ echo "merhaba yazilim"
merhaba yazilim
```

### Dosya Oluşturma

```bash
$ pico
# Dosya açılır (içine isimler yazılabilir: ahmet, ayse vb.)

$ pico isimler
# "isimler" adında dosya oluşturur veya düzenler
```

### Dosya Listeleme

```bash
$ ls
# Mevcut dizindeki dosyaları listeler
isimler....

$ ls -l
# Dosyaları ayrıntılı olarak listeler (izinler, boyut, tarih vb.)
```

### Dosya İçeriğini Görüntüleme

```bash
$ cat isimler
ahmet
mehmet
ayse
```

### Dosya İstatistikleri

```bash
$ wc isimler
3        3        18
# satır    kelime    karakter sayısı

# Seçenekler:
# -l: satır sayısı
# -w: kelime sayısı
# -c: karakter sayısı
```

## Dizin İşlemleri

### Dizin Oluşturma

```bash
$ mkdir dosyalar
$ ls -l
# Çıktı:
# ----- isimler
# ----- dosyalar
```

### Dosya Kopyalama

```bash
$ cp isimler dosyalar
$ ls dosyalar
isimler
```

### Dosya İsim Değiştirme

```bash
$ mv isimler isimler2
```

### Dosya Silme

```bash
$ rm dosya-isim
```

### Çalışılan Dizini Öğrenme

```bash
$ pwd
/home/suman
```

### Dizin Değiştirme

```bash
# cd komutu:
# cd ..: bulunulan dizinden çıkış
# cd isim: isim adındaki dizine giriş
# cd: ev dizinine dönüş

$ cd dosyalar
$ ls
isimler

$ cd ..
$ ls
isimler
dosyalar

$ cd dosyalar
$ mkdir resimler
$ cd resimler
$ pwd
/home/suman/dosyalar/resimler

$ cd
$ pwd
/home/suman

$ cp isimler2 dosyalar/resimler
$ ls dosyalar/resimler
isimler2
```

### Klasör/Dizin Silme

```bash
$ cd dosyalar
$ rmdir resimler  # Boş klasör için
$ rm -r resimler  # İçi dolu klasör için
```

## Dosya ve Dizin Erişim Hakları

```bash
$ ls -l
-rw-r--r-- 1 suman odd--- isimler
drwxr-x--- 2 suman odd--- dosyalar
```

### Erişim Hakları Açıklaması

```
d rwx rwx rwx
  |   |   |
  |   |   +-- Diğerlerin yetkileri (others)
  |   +------ Grubun yetkileri (group)
  +---------- Kullanıcının yetkileri (user/owner)

d: dizin
-: dosya

r: read (okuma)
w: write (yazma)
x: execution (çalıştırma)

Örnek: -rw-r--r--
Örnek: drwxr-x---
Örnek: -rwx--x--x
```

### Erişim Haklarının Değiştirilmesi

```bash
# İzinlerin sayısal değerleri:
# r = 4
# w = 2
# x = 1

$ chmod 644 isimler
$ ls -l
-rw-r--r-- isimler

$ chmod 754 isimler
$ ls -l
-rwxr-xr-- isimler

$ chmod 777 isimler
$ ls -l
-rwxrwxrwx isimler

$ chmod +x isimler  # Tüm kullanıcılara çalıştırma hakkı ekler

$ chmod 755 isimler
$ ls -l isimler
-rwxr-xr-x isimler
```

## Dosya Adı Filtreleme

```bash
$ ls
a b c aa bb cc chapt1 chapt2
```

### Joker Karakterler (Wildcards)

```bash
# *: tüm karakterler veya null
# ?: tek karakter

$ ls *t*
chapt1 chapt2

$ ls *a*
a aa chapt1 chapt2

$ ls *a
a aa

$ ls ?
a b c

$ ls ??
aa bb cc

$ ls ??*
aa bb cc chapt1 chapt2

$ ls ?n*
chapt1 chapt2

$ ls *a*a*
aa

$ ls *?t?
chapt1 chapt2

$ ls c*?
cc chapt1 chapt2
```

### Karakter Sınıfları

```bash
# [-]: eşleştirmek için kullanılır
# [0-9]: rakamlar
# [a-z]: küçük harfler
# [A-Z]: büyük harfler
# [!0-9]: rakam olmayan
# [!a-z]: küçük harf olmayan
# [!A-Z]: büyük harf olmayan
# [a-zA-Z]: küçük harf veya büyük harf
# [0-9a-z]: rakam veya küçük harf

$ ls *[0-9]  # Rakam ile biten isimler
chapt1 chapt2

$ ls *[!0-9]  # Rakam ile bitmeyen isimler
a b c aa bb cc

$ ls *[a-zA-Z]  # Harfle biten isimler
a b c aa bb cc

$ ls [b-c][b-c]  # b veya c ile başlayan ve b veya c ile devam eden
bb cc

$ ls [c-d]*[0-9]  # c veya d ile başlayan ve rakamla biten
chapt1 chapt2
```

## Çıktı Yönlendirme

```bash
# komut > yönlendirilen_dosya: Dosyaya yazar (üzerine yazar)
# komut >> yönlendirilen_dosya: Dosyaya ekler

$ who > users
$ cat users
# kullanıcı listesi görüntülenir

$ > dosya3
# İçi boş dosya oluşturur

$ echo mehmet
mehmet

$ echo mehmet > users
$ cat users
mehmet

$ who > users
$ echo mehmet >> users
$ cat users
ali
suman
ozcan
mehmet
```

## Pipeline İşlemleri (|)

```bash
# |: Bir komutun çıktısını başka bir komuta aktarır

# Sistemdeki kullanıcı sayısı
$ who | wc -l
43

$ who > users
$ wc -l < users
# Kullanıcı sayısını gösterir

# Dosyaların sayısını verir
$ ls -l | grep "^-" | wc -l

# Dizinlerin sayısını verir
$ ls -l | grep "^d" | wc -l

# 'suman' kullanıcısının çalıştırdığı işlem sayısı
$ ps aux | grep suman | wc -l

# En çok bellek kullanan 6 işlemi listeler
$ ps aux --sort=-%mem | head -6
```
