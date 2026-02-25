---
title: Git Workflow & Branching
description: Profesyonel projelerde kullanılan Git branching stratejileri ve iş akışları.
tags:
  - git
  - yazilim
  - workflow
date: 2026-02-25
---

# Git Workflow & Branching 🌿

## Neden Branch Stratejisi?

Tek kişilik projelerde bile bir branch stratejisi izlemek:
- Kararlı bir `main` branch'i korur
- Değişiklikleri izole eder, test etmeyi kolaylaştırır
- Hataları geri almayı basitleştirir

---

## 🏆 Feature Branch Workflow (Önerilen)

Benim kullandığım temel yaklaşım. Her yeni özellik veya fix kendi branch'inde gelişir.

```
main ──────────────────────────────────► (production)
       \                        /
        feature/login ─────────
```

### Adımlar

```bash
# 1. main'den güncel halini çek
git checkout main
git pull origin main

# 2. Yeni branch aç
git checkout -b feature/kullanici-profili

# 3. Geliştir, commit'le
git add .
git commit -m "feat: profil sayfası oluşturuldu"

# 4. main'i rebase et (temiz geçmiş için)
git rebase main

# 5. Push et
git push origin feature/kullanici-profili

# 6. Pull Request / Merge Request aç → review → merge

# 7. Branch'i temizle
git branch -d feature/kullanici-profili
```

---

## 🌊 Gitflow

Daha büyük projelerde kullanılan, sürüm bazlı strateji.

```
main        ──────────────────────────────────►
            ↑           ↑              ↑
release/1.0 ─────────── ──────────────
            ↑
develop     ──────────────────────────────────►
            ↑           ↑
feature/A ──────────────
                        ↑
feature/B               ──────────────
```

### Branch Yapısı

| Branch | Amaç |
|---|---|
| `main` | Production — her zaman yayında |
| `develop` | Sonraki release için entegrasyon |
| `feature/*` | Yeni özellikler |
| `release/*` | Sürüm hazırlığı |
| `hotfix/*` | Production'a acil fix |

---

## 🚀 Trunk-Based Development

Modern CI/CD yaklaşımı — herkes `main`'e küçük, sık commit'ler atar.

```bash
# Feature flag ile küçük değişiklikler
git checkout main
git pull
# ... küçük değişiklik yap
git commit -m "feat: yeni buton eklendi (flag arkasında)"
git push
```

**Ne zaman tercih edilir?**
- CI/CD pipeline'ı varsa
- Ekip küçükse ve deployment sıksa
- Feature flag mekanizması kullanılıyorsa

---

## 📋 Pull Request Checklist

PR açmadan önce:

- [ ] Kod çalışıyor mu?
- [ ] Test yazıldı mı?
- [ ] Commit mesajları anlamlı mı?
- [ ] `main`'den rebase yapıldı mı?
- [ ] Gereksiz dosya (console.log, debug kodu) kaldırıldı mı?
- [ ] Açıklama/README güncellendi mi?

---

## 🔗 İlgili Notlar

- [[Yazılım/Git/git-temelleri|Git Temelleri — Komutlar]]
- [[Yazılım/Git/git-ipuclari|Git İpuçları & Püf Noktaları]]
