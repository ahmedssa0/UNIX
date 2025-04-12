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
