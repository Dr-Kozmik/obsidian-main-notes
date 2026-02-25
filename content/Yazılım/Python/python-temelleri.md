---
title: Python Temelleri & Hızlı Referans
description: Python'un temel yapıları, sık kullanılan kütüphaneler ve pratik snippets.
tags:
  - python
  - yazilim
  - referans
date: 2026-02-25
---

# Python Temelleri & Hızlı Referans 🐍

## Veri Tipleri

```python
# String
ad = "Koray"
mesaj = f"Merhaba, {ad}!"   # f-string (önerilen)

# Liste
sayilar = [1, 2, 3, 4, 5]
sayilar.append(6)
sayilar[0]    # 1 (baştan)
sayilar[-1]   # 6 (sondan)

# Tuple (değişmez)
koordinat = (41.0, 29.0)

# Dictionary
kullanici = {
    "ad": "Koray",
    "yas": 25,
    "aktif": True
}
kullanici["ad"]          # "Koray"
kullanici.get("email", "yok")  # KeyError vermez

# Set (benzersiz)
renkler = {"kırmızı", "mavi", "yeşil"}
```

---

## Koşul ve Döngüler

```python
# if/elif/else
if yas >= 18:
    print("Yetişkin")
elif yas >= 13:
    print("Genç")
else:
    print("Çocuk")

# Ternary
durum = "yetişkin" if yas >= 18 else "çocuk"

# for döngüsü
for i in range(10):
    print(i)

for eleman in liste:
    print(eleman)

# enumerate — index ile birlikte
for i, eleman in enumerate(liste):
    print(f"{i}: {eleman}")

# Comprehension
kareler = [x**2 for x in range(10)]
ciftler = [x for x in range(20) if x % 2 == 0]
sozluk = {k: v for k, v in items.items() if v > 0}
```

---

## Fonksiyonlar

```python
# Temel
def selamla(ad, selamlama="Merhaba"):
    return f"{selamlama}, {ad}!"

# *args ve **kwargs
def topla(*sayilar):
    return sum(sayilar)

def bilgi(**kwargs):
    for k, v in kwargs.items():
        print(f"{k}: {v}")

# Type hints (önerilen)
def yas_hesapla(dogum_yili: int) -> int:
    return 2026 - dogum_yili

# Lambda
kare = lambda x: x ** 2
```

---

## Hata Yönetimi

```python
try:
    sonuc = 10 / sayi
except ZeroDivisionError:
    print("Sıfıra bölünemez!")
except ValueError as e:
    print(f"Değer hatası: {e}")
except Exception as e:
    print(f"Beklenmedik hata: {e}")
    raise  # hatayı yeniden fırlat
else:
    print("Hata yok, devam et")
finally:
    print("Her zaman çalışır")
```

---

## Sık Kullanılan Modüller

```python
import os
import sys
import json
from datetime import datetime, timedelta
from pathlib import Path

# OS işlemleri
os.getcwd()             # şu anki klasör
os.listdir()            # klasör içeriği
os.path.exists("dosya") # dosya var mı?

# Path (modern yol)
p = Path("klasor/dosya.txt")
p.read_text()
p.write_text("içerik")
p.mkdir(parents=True, exist_ok=True)

# JSON
veri = json.loads('{"ad": "Koray"}')
metin = json.dumps(veri, ensure_ascii=False, indent=2)

# Tarih
simdi = datetime.now()
simdi.strftime("%d.%m.%Y")
bir_hafta_sonra = simdi + timedelta(days=7)

# HTTP isteği (requests)
import requests
r = requests.get("https://api.example.com/data")
r.json()
```

---

## Virtual Environment

```bash
# Oluştur
python -m venv venv

# Aktifleştir
source venv/bin/activate    # Linux/Mac
venv\Scripts\activate       # Windows

# Devre dışı bırak
deactivate

# Bağımlılıkları kaydet
pip freeze > requirements.txt

# Bağımlılıkları yükle
pip install -r requirements.txt
```

---

## 🔗 İlgili Notlar

- [[Yazılım/JavaScript/modern-js|Modern JavaScript]]
- [[Yazılım/Terminal/terminal-komutlari|Terminal Komutları]]
