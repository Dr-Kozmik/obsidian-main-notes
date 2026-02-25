---
title: Git İpuçları & Püf Noktaları
description: Zaman kazandıran Git ipuçları, pratik tricks ve az bilinen komutlar.
tags:
  - git
  - yazilim
  - ipuclari
date: 2026-02-25
---

# Git İpuçları & Püf Noktaları 💡

## 🔍 Arama & Filtreleme

```bash
# Commit mesajlarında ara
git log --grep="login"

# Belirli bir kodu kimin yazdığını bul
git log -S "functionName" --source --all

# Satır bazlı değişiklik geçmişi
git blame dosya.txt

# İki commit arasındaki fark
git diff abc1234 def5678

# Staged değişikliklerin farkı
git diff --staged
```

---

## ✨ Temiz Çalışma

```bash
# Takip edilmeyen dosyaları göster
git clean -n

# Takip edilmeyen dosyaları sil
git clean -f

# .gitignore'da olmayanları sil (DİKKAT)
git clean -fd

# Tüm değişiklikleri at, son commit'e dön
git checkout -- .
```

---

## 🏷 Etiketleme (Tags)

```bash
# Tag listesi
git tag

# Lightweight tag
git tag v1.0.0

# Annotated tag (önerilen)
git tag -a v1.0.0 -m "İlk kararlı sürüm"

# Tag'i push et
git push origin v1.0.0

# Tüm tag'leri push et
git push origin --tags

# Tag sil (local)
git tag -d v1.0.0

# Tag sil (remote)
git push origin --delete v1.0.0
```

---

## 🔧 Cherry-pick

Başka bir branch'teki belirli bir commit'i al:

```bash
# Tek commit al
git cherry-pick abc1234

# Birden fazla commit al
git cherry-pick abc1234 def5678

# Commit yapmadan al (değişiklikler staged olur)
git cherry-pick -n abc1234
```

---

## 📊 İstatistikler

```bash
# Katkıda bulunanlar listesi
git shortlog -sn

# Dosya başına değişiklik sayısı
git log --name-only --pretty=format: | sort | uniq -c | sort -rn | head

# Repository boyutu
git count-objects -vH
```

---

## 🔁 Tehlikeli Ama Bazen Lazım

```bash
# Remote branch'i tamamen sil
git push origin --delete branch-adi

# Force push (dikkatli!)
git push --force-with-lease

# Tüm remote branch'leri güncelle
git remote prune origin

# Merge edilmiş branch'leri temizle
git branch --merged | grep -v main | xargs git branch -d
```

> [!WARNING]
> `--force` push, başkalarının üzerinde çalıştığı geçmişi bozabilir. Her zaman `--force-with-lease` kullan.

---

## 💾 .gitignore Şablonları

Yaygın .gitignore girişleri:

```gitignore
# Node.js
node_modules/
npm-debug.log
.env
.env.local

# Python
__pycache__/
*.py[cod]
*.egg-info/
.venv/
venv/

# OS dosyaları
.DS_Store
Thumbs.db
desktop.ini

# Editor
.vscode/
.idea/
*.swp

# Build
dist/
build/
*.log
```

---

## 🔗 İlgili Notlar

- [[Yazılım/Git/git-temelleri|Git Temelleri]]
- [[Yazılım/Git/git-aliases|Git Alias Kurulumu]]
