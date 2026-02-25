---
title: Not Alma Sistemi — Nasıl Kullanıyorum
description: Obsidian ile kişisel not alma sistemi — klasör yapısı, tag'ler ve iş akışı.
tags:
  - not-alma
  - obsidian
  - verimlilik
  - sistem
date: 2026-02-25
---

# Not Alma Sistemi 🗂

## Neden Obsidian?

Obsidian'ı tercih etmemin nedenleri:
1. **Yerel dosyalar** — notlar bilgisayarda, bulutta değil (Markdown)
2. **Bağlantılar** — notlar arası köprüler oluşturabiliyorum
3. **Graph view** — bilgi haritasını görsel görmek
4. **Esneklik** — her şeyi özelleştirebiliyorum
5. **Açık format** — ileride başka araçlara geçilebilir

---

## 📁 Klasör Yapım

```
📦 Vault
├── 💻 Yazılım/        → Teknik referanslar
│   ├── Git/
│   ├── Terminal/
│   ├── JavaScript/
│   └── Python/
├── ⚡ Verimlilik/     → Sistemler, alışkanlıklar
├── 🚀 Projeler/       → Aktif ve tamamlanmış projeler
├── 📅 Günlük/         → Düşünceler, yansımalar
│   └── 2026/
└── 📚 Kaynaklar/      → Kitaplar, kurslar, linkler
```

---

## 🔖 Tag Sistemi

Tag'leri 2 kategoride kullanıyorum:

### Durum Tag'leri
- `#taslak` — ham, işlenmemiş notlar
- `#aktif` — üzerinde çalışıyorum
- `#tamamlandi` — bitmiş
- `#arsiv` — eskimiş ama silinmesin

### Konu Tag'leri
- `#yazilim`, `#git`, `#javascript`
- `#verimlilik`, `#sistem`
- `#kitap`, `#kurs`

---

## ✍️ Not Alma Akışı

### Hızlı Yakalama (Capture)
Aklıma gelen her şeyi anında `Günlük/` altındaki günlük notuna atıyorum. Daha sonra işliyorum.

### İşleme (Process)
Haftada bir kez günlük notlarımı tarayıp:
- İlgili klasöre taşı
- Bağlantı ekle
- Tag'le

### İnceleme (Review)
Aylık olarak:
- Tamamlanmış projeleri arşivle
- Eski notları güncelle
- Grafiği incele

---

## 📝 Not Şablonları

### Proje Notu Şablonu
```markdown
---
title: [Proje Adı]
tags: [proje, aktif]
date: {{date}}
---

## Amaç
Projeyi neden yapıyorum?

## Hedefler
- [ ] Hedef 1
- [ ] Hedef 2

## Notlar
```

### Günlük Şablon
```markdown
---
date: {{date}}
tags: gunluk
---

## Bugün ne yaptım?

## Öğrendiklerim

## Yarına devirler
```

---

## 🔗 İlgili Notlar

- [[Verimlilik/zaman-yonetimi|Zaman Yönetimi]]
- [[Verimlilik/derin-odak|Derin Odak]]
