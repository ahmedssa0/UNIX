# 🖥️ YMU446 UNIX PROGRAMLAMA – Sınav Özeti ve Soru-Cevap

## 📁 1. Dosya ve Dizin İşlemleri

```bash
ls           # Dosya ve klasörleri listeler
ls -l        # Uzun listeleme
ls -a        # Gizli dosyaları da göster

cd dosyalar  # Dizinler arasında geçiş
cd ..        # Bir üst dizine geçiş

mkdir yeni_klasor     # Yeni dizin oluşturma
rmdir resimler        # Boş dizini silme
rm dosya.txt          # Dosya silme
cp dosya1 klasor/     # Dosya kopyalama
mv dosya1 dosya2      # Dosya taşıma/yeniden adlandırma

pwd                   # Çalışılan dizini gösterir
cat dosya.txt         # Dosya içeriğini gösterir
wc dosya.txt          # Satır, kelime, karakter sayar


# 2. Metin Görüntüleme ve Dosya Oluşturma

```bash
echo "Merhaba"        # Ekrana yazı yazar
pico isimler.txt      # Dosya oluştur ve düzenle (nano da olabilir)
vi dosya.txt          # Gelişmiş metin editörü


# 🔐 3. Dosya Erişim Hakları

## rwx: read, write, execute
## Örnek: -rwxr-xr--

```bash
chmod 755 dosya.txt   # Kullanıcı: rwx, Grup: r-x, Diğer: r-x
chmod +x dosya.sh     # Çalıştırma yetkisi ekler
chmod 444 dosya.txt   # Sadece okuma izni verir




❓ Bir klasörün ismini nasıl değiştirirsin?
➡️ mv dosyalar arsiv

❓ pico ile yeni bir dosya oluştur ve içinde isimler yaz.
➡️ pico isimler.txt  # CTRL+O, ENTER, CTRL+X

❓ Bir dosyanın karakter, kelime, satır sayılarını nasıl görürüz?
➡️ wc metin.txt

❓ rwxr-xr-- ne anlama gelir?
➡️ Kullanıcı: rwx | Grup: r-x | Diğer: r--

❓ Bir dosyaya çalıştırma yetkisi nasıl eklenir?
➡️ chmod +x run.sh

❓ echo çıktısını bir dosyaya yazdırmak
➡️ echo "Merhaba" > selam.txt

❓ Sadece dosyaları sayan bir komut yaz.
➡️ ls -l | grep "^-" | wc -l

❓ *, ?, [a-z] gibi wildcard'lar ne işe yarar?
➡️ *.txt = .txt uzantılılar, ?.sh = 2 harfli .sh, [a-c]* = a/b/c ile başlayanlar

❓ Yeni bir klasör oluştur, içine dosya kopyala
➡️ mkdir yedek
➡️ cp veri.txt yedek/

❓ Shell’de bir döngü yaz
➡️ for i in *.txt; do
➡️   cat "$i"
➡️ done

❓ whoami ve pwd komutları ne işe yarar?
➡️ whoami: kullanıcı adı | pwd: dizin yolu

❓ Bir dosyanın içeriğini silmeden adını değiştir.
➡️ mv eski.txt yeni.txt

❓ Bir klasörü ve içeriğini sil
➡️ rm -r gecici

❓ grep ile bir satırı bul
➡️ grep "HATA" log.txt

❓ Sistemdeki aktif kullanıcı sayısını bul
➡️ who | wc -l

❓ Dosyaları büyüklüğüne göre sırala
➡️ ls -lhS

❓ En çok RAM kullanan 5 işlem nedir?
➡️ ps aux --sort=-%mem | head -5

❓ Bir dosyanın izinlerini sadece okumaya düşür
➡️ chmod 444 dosya.txt

❓ Sadece .sh uzantılı dosyaları bul
➡️ find . -name "*.sh"

❓ Aynı içeriğe sahip iki dosya arasında farkı göster
➡️ diff dosya1.txt dosya2.txt
