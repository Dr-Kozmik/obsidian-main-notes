---
title: Modern JavaScript (ES6+)
description: ES6 ve sonrasında gelen modern JavaScript özellikleri ve pratik kullanımları.
tags:
  - javascript
  - es6
  - yazilim
date: 2026-02-25
---

# Modern JavaScript (ES6+) 🟨

## 🔄 Destructuring

```javascript
// Array destructuring
const [ilk, ikinci, ...geri_kalanlar] = [1, 2, 3, 4, 5];
// ilk = 1, ikinci = 2, geri_kalanlar = [3, 4, 5]

// Object destructuring
const { ad, yas, sehir = "İstanbul" } = kullanici;

// Farklı isimle destructuring
const { ad: kullaniciAdi } = kullanici;

// Nested destructuring
const { adres: { sokak, ilce } } = kullanici;
```

---

## 📦 Spread & Rest

```javascript
// Spread — array/object yayma
const yeni = [...eskiArray, yeniEleman];
const merged = { ...obj1, ...obj2 };

// Rest — kalan şeyleri topla
function topla(...sayilar) {
  return sayilar.reduce((a, b) => a + b, 0);
}
```

---

## ⚡ Arrow Functions

```javascript
// Klasik
function topla(a, b) { return a + b; }

// Arrow
const topla = (a, b) => a + b;

// Çok satırlı
const isle = (x) => {
  const sonuc = x * 2;
  return sonuc + 1;
};
```

> [!NOTE]
> Arrow function'lar kendi `this` bağlamına sahip değildir — bu bazen istenen, bazen istenmeyen bir davranıştır.

---

## 🤝 Promise & Async/Await

```javascript
// Promise zinciri
fetch('/api/kullanici')
  .then(res => res.json())
  .then(data => console.log(data))
  .catch(err => console.error(err));

// Async/Await (önerilen)
async function kullaniciyiGetir(id) {
  try {
    const res = await fetch(`/api/kullanici/${id}`);
    const data = await res.json();
    return data;
  } catch (hata) {
    console.error('Hata:', hata);
    throw hata;
  }
}

// Paralel istekler
const [kullanici, siparisler] = await Promise.all([
  fetch('/api/kullanici').then(r => r.json()),
  fetch('/api/siparisler').then(r => r.json()),
]);
```

---

## 🗺 Array Metodları

```javascript
const sayilar = [1, 2, 3, 4, 5];

// map — dönüştür
const kareleri = sayilar.map(x => x ** 2);
// [1, 4, 9, 16, 25]

// filter — filtrele
const ciftler = sayilar.filter(x => x % 2 === 0);
// [2, 4]

// reduce — tek değere indir
const toplam = sayilar.reduce((acc, x) => acc + x, 0);
// 15

// find — ilk eşleşeni bul
const ilkBuyuk = sayilar.find(x => x > 3);
// 4

// every / some
sayilar.every(x => x > 0)  // true — hepsi sağlıyor
sayilar.some(x => x > 4)   // true — en az biri sağlıyor

// flat — iç içe açma
[[1, 2], [3, 4]].flat()    // [1, 2, 3, 4]

// flatMap — map + flat
["hello world"].flatMap(s => s.split(" "))  // ["hello", "world"]
```

---

## 🔑 Optional Chaining & Nullish Coalescing

```javascript
// Optional chaining (?.)
const sehir = kullanici?.adres?.sehir;
// kullanici veya adres null/undefined ise undefined döner, hata vermez

// Nullish coalescing (??)
const ad = kullanici.ad ?? "Anonim";
// sadece null/undefined ise varsayılanı kullanır (0 veya "" geçerlidir)

// Birlikte kullanım
const yas = kullanici?.profil?.yas ?? 18;
```

---

## 📚 Template Literals

```javascript
const ad = "Koray";
const mesaj = `Merhaba, ${ad}! Bugün ${new Date().toLocaleDateString("tr-TR")}.`;

// Multiline
const html = `
  <div class="kart">
    <h2>${baslik}</h2>
    <p>${aciklama}</p>
  </div>
`;

// Tagged template
const sorgu = sql`SELECT * FROM kullanicilar WHERE id = ${userId}`;
```

---

## 🔗 İlgili Notlar

- [[Yazılım/JavaScript/js-temelleri|JavaScript Temelleri]]
- [[Yazılım/Python/index|Python Notları]]
