---
title: Terminal Komutları Referans
description: Bash ve Windows terminali için günlük kullanım komutları.
tags:
  - terminal
  - bash
  - yazilim
  - referans
date: 2026-02-25
---

# Terminal Komutları Referans ⌨️

## 📁 Dosya & Klasör İşlemleri

```bash
# Neredesin?
pwd

# Klasör listesi
ls
ls -la    # gizli dosyalar dahil, detaylı
ls -lh    # dosya boyutları okunabilir formatta

# Klasöre git
cd klasor-adi
cd ..           # bir üste çık
cd ~            # home dizinine git
cd -            # önceki dizine dön

# Klasör oluştur
mkdir yeni-klasor
mkdir -p a/b/c  # iç içe klasörler

# Dosya oluştur
touch dosya.txt

# Dosya kopyala
cp kaynak.txt hedef.txt
cp -r kaynak/ hedef/  # klasör kopyala

# Dosya taşı / yeniden adlandır
mv eski.txt yeni.txt
mv dosya.txt /hedef/klasor/

# Dosya sil
rm dosya.txt
rm -rf klasor/  # klasörü zorla sil (DİKKAT!)

# Boş klasör sil
rmdir klasor
```

---

## 📖 Dosya İçeriği

```bash
# Dosyayı göster
cat dosya.txt

# Sayfalı görüntüle
less dosya.txt    # q ile çık

# İlk 10 satır
head dosya.txt
head -n 20 dosya.txt

# Son 10 satır
tail dosya.txt
tail -n 20 dosya.txt

# Canlı takip (log dosyaları için süper)
tail -f log.txt
```

---

## 🔍 Arama

```bash
# Dosya adı ile ara
find . -name "*.txt"
find . -name "dosya*" -type f
find . -mtime -7  # son 7 günde değişenler

# İçerik ile ara (grep)
grep "aranan" dosya.txt
grep -r "aranan" ./klasor/   # özyinelemeli
grep -i "aranan" dosya.txt   # büyük/küçük harf duyarsız
grep -n "aranan" dosya.txt   # satır numaraları ile

# Modern grep (ripgrep)
rg "aranan"
rg "aranan" --type js
```

---

## ⚙️ İşlem Yönetimi

```bash
# Çalışan işlemler
ps aux
ps aux | grep node

# İşlem sonlandır
kill 1234          # PID ile
kill -9 1234       # zorla sonlandır
pkill node         # isim ile

# Arka plana gönder
komut &

# Arka plan işlemleri listesi
jobs

# Ön plana getir
fg %1
```

---

## 🌐 Ağ Komutları

```bash
# IP adresi
ip addr
ifconfig  # eski sistemlerde

# Bağlantı testi
ping google.com
ping -c 4 google.com  # 4 paket

# Port dinliyor mu?
netstat -tulpn
ss -tulpn  # modern alternatif

# Dosya indir
curl -O https://example.com/dosya.zip
wget https://example.com/dosya.zip

# API test
curl -X GET https://api.example.com/data
curl -X POST -H "Content-Type: application/json" \
  -d '{"key":"value"}' https://api.example.com/data
```

---

## 📦 Paket Yönetimi

```bash
# npm (Node.js)
npm install paket-adi
npm install -D paket-adi  # devDependency
npm install -g paket-adi  # global
npm update
npm run build

# pip (Python)
pip install paket-adi
pip install -r requirements.txt
pip freeze > requirements.txt
```

---

## 🧰 Kullanışlı Komutlar

```bash
# Komut geçmişi
history
history | grep git

# Çıktıyı dosyaya yaz
komut > output.txt      # üzerine yaz
komut >> output.txt     # ekle

# İki komutu birleştir (ikincisi sadece birinci başarılıysa çalışır)
komut1 && komut2

# Her durumda ikincisi çalışır
komut1 || komut2

# Boru (pipe) — birinin çıktısını diğerine ver
ps aux | grep node
ls -la | sort -k5 -n

# Ortam değişkeni
echo $HOME
echo $PATH
export MY_VAR="deger"

# Komutu nerede?
which node
which python3

# Dosya boyutu
du -sh klasor/
df -h  # disk kullanımı
```

---

## 💡 Kısayollar

| Kısayol | Ne Yapar |
|---|---|
| `Ctrl+C` | Komutu iptal et |
| `Ctrl+Z` | Komutu arka plana al |
| `Ctrl+L` | Ekranı temizle (`clear`) |
| `Ctrl+A` | Satır başına git |
| `Ctrl+E` | Satır sonuna git |
| `Ctrl+R` | Geçmişte ara |
| `Tab` | Otomatik tamamla |
| `!!` | Son komutu tekrar çalıştır |
| `!git` | Son `git` komutunu tekrar çalıştır |

---

## 🔗 İlgili Notlar

- [[Yazılım/Git/git-temelleri|Git Komutları]]
- [[Yazılım/Araçlar/vscode-kisayollari|VS Code Kısayolları]]
