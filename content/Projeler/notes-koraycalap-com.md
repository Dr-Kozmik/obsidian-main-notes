---
title: notes.koraycalap.com — Dijital Bahçe
description: Kişisel dijital bahçe projesi — Obsidian + Quartz ile oluşturulan not sitesi.
tags:
  - projeler
  - aktif
  - web
date: 2026-02-25
---

# notes.koraycalap.com 🌱

Kişisel dijital bahçem — öğrendiklerimi ve düşüncelerimi organize etmek için kurduğum platform.

## Teknik Stack

| Bileşen | Teknoloji |
|---|---|
| İçerik | Obsidian Markdown |
| Site Üretici | [Quartz 4](https://quartz.jzhao.xyz) |
| Hosting | GitHub Pages / Coolify |
| Domain | notes.koraycalap.com |
| Repo | [GitHub](https://github.com/Dr-Kozmik/obsidian-main-notes) |

## Hedefler

- [x] Temel Quartz kurulumu
- [x] Domain bağlantısı
- [x] İlk not yapısı oluştur
- [ ] Özel tema/renk düzenlemesi
- [ ] Analytics entegrasyonu
- [ ] Düzenli not ekleme alışkanlığı

## Nasıl Çalışır?

```
Obsidian (yerel düzenleme)
    ↓ git push
GitHub Repo
    ↓ Coolify/GitHub Actions
notes.koraycalap.com
```

## Klasör Yapısı

```
content/
├── index.md          ← Ana sayfa
├── Yazılım/          ← Teknik notlar
├── Verimlilik/       ← Sistem & alışkanlıklar
├── Projeler/         ← Bu not dahil
├── Günlük/           ← Günlük düşünceler
└── Kaynaklar/        ← Kitaplar, linkler
```

## Notlar & Kararlar

- **Dil:** Türkçe/İngilizce karma — teknik terimler İngilizce kalacak
- **Yayınlama:** Her commit otomatik deploy
- **Gizlilik:** `private/` klasörüne konan notlar yayınlanmaz

## 🔗 İlgili

- [[index|Ana Sayfa]]
- [[Verimlilik/not-alma-sistemi|Not Alma Sistemi]]
