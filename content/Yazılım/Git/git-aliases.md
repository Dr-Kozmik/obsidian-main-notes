---
title: Git Alias Kurulumu
description: Sık kullanılan Git komutları için kısa yollar - zaman kazandıran alias'lar.
tags:
  - git
  - yazilim
  - uretkenlik
date: 2026-02-25
---

# Git Alias Kurulumu ⚡

Uzun komutları kısa kısayollarla çağırarak çok zaman kazanabilirsin.

## Kurulum

```bash
# .gitconfig'e alias ekle
git config --global alias.st status
git config --global alias.co checkout
git config --global alias.br branch
git config --global alias.ci commit
```

Veya `~/.gitconfig` dosyasını doğrudan düzenle:

```ini
[alias]
  # Temel kısayollar
  st = status
  co = checkout
  br = branch
  ci = commit
  
  # Tek satır log (güzel görünümlü)
  lg = log --oneline --graph --all --decorate
  
  # Kısa durumu göster
  s = status -s
  
  # Son commit'i göster
  last = log -1 HEAD
  
  # Staged ve unstaged farklar
  df = diff
  dfs = diff --staged
  
  # Yeni branch oluştur ve geç
  new = checkout -b
  
  # Push kısayolu (upstream set ile)
  psh = push -u origin HEAD
  
  # Pull + rebase
  up = pull --rebase
  
  # Merge edilmiş branch'leri sil
  cleanup = "!git branch --merged | grep -v main | xargs git branch -d"
  
  # Bu hafta ne yaptım?
  week = log --author='Koray' --since='1 week ago' --oneline
  
  # Commit sayısı
  count = rev-list --count HEAD
```

## Kullanım Örnekleri

```bash
# Artık bunları kullanabilirsin:
git st         # git status
git co main    # git checkout main
git lg         # güzel grafik log
git new feat/xyz  # git checkout -b feat/xyz
git psh        # git push -u origin HEAD
git cleanup    # merge edilmiş branch'leri temizle
```

---

## 🔗 İlgili Notlar

- [[Yazılım/Git/git-temelleri|Git Temelleri]]
- [[Yazılım/Git/git-ipuclari|Git İpuçları]]
