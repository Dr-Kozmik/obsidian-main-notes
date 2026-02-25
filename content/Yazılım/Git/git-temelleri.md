---
title: Git Temelleri
description: Günlük git kullanımı için temel komutlar ve açıklamaları.
tags:
  - git
  - yazilim
  - referans
date: 2026-02-25
---

# Git Temelleri 🔀

Günlük geliştirme sürecinde en sık kullandığım Git komutları.

## Temel Kavramlar

| Kavram | Açıklama |
|---|---|
| **Repository (Repo)** | Projenin tüm dosya geçmişini tutan yer |
| **Commit** | Dosya değişikliklerinin anlık görüntüsü |
| **Branch** | Bağımsız geliştirme hattı |
| **Merge** | İki branch'i birleştirme |
| **Remote** | Uzak sunucudaki repo (GitHub, GitLab vs.) |
| **Working Directory** | Aktif çalışma alanı |
| **Staging Area** | Commit'e hazır değişikliklerin beklediği alan |

---

## 🚀 Kurulum & Yapılandırma

```bash
# İlk kurulum — kim olduğunu tanıt
git config --global user.name "Koray Çalap"
git config --global user.email "koray@koraycalap.com"

# Varsayılan editörü ayarla
git config --global core.editor "code --wait"

# Renklendirme aç
git config --global color.ui auto

# Tüm ayarları listele
git config --list
```

---

## 📁 Repo Oluşturma

```bash
# Yeni bir repo başlat
git init

# Mevcut repo'yu klonla
git clone https://github.com/kullanici/proje.git

# Belirli bir branch ile klonla
git clone -b develop https://github.com/kullanici/proje.git
```

---

## 📸 Değişiklikleri Kaydetme

```bash
# Durumu gör — neyin staged, neyin unstaged olduğunu gösterir
git status

# Belirli dosyayı stage'e ekle
git add dosya.txt

# Tüm değişiklikleri stage'e ekle
git add .

# Belirli bir klasörü stage'e ekle
git add src/

# Stage'e eklemeyi geri al (dosyayı silmez)
git restore --staged dosya.txt

# Commit yap
git commit -m "feat: login sayfası eklendi"

# Stage + commit birlikte (sadece tracked dosyalar için)
git commit -am "fix: hata düzeltildi"

# Son commit'i düzenle (henüz push'lamadıysan)
git commit --amend -m "Yeni mesaj"
```

### 📝 Commit Mesajı Formatı (Conventional Commits)

```
<type>: <açıklama>

[opsiyonel gövde]
[opsiyonel footer]
```

| Type | Ne Zaman |
|---|---|
| `feat` | Yeni özellik |
| `fix` | Hata düzeltme |
| `docs` | Sadece dokümantasyon |
| `style` | Kod formatı (mantık değişmez) |
| `refactor` | Ne yeni özellik ne bug fix |
| `test` | Test ekleme/düzenleme |
| `chore` | Build, bağımlılık güncelleme |

---

## 🔍 Geçmişe Bakma

```bash
# Commit geçmişini gör
git log

# Tek satır özet formatı
git log --oneline

# Grafik görünümü
git log --oneline --graph --all

# Belirli bir dosyanın geçmişi
git log --follow dosya.txt

# Belirli bir commit'in detayları
git show abc1234

# Son n commit
git log -n 5
```

---

## 🌿 Branch İşlemleri

```bash
# Branch listesi (local)
git branch

# Tüm branch'ler (remote dahil)
git branch -a

# Yeni branch oluştur
git branch feature/yeni-ozellik

# Branch'e geç
git checkout feature/yeni-ozellik

# Oluştur + geç (kısa yol)
git checkout -b feature/yeni-ozellik

# Modern syntax
git switch -c feature/yeni-ozellik

# Branch sil (merge edilmişse)
git branch -d feature/eski

# Branch zorla sil
git branch -D feature/eski
```

---

## 🔗 Remote İşlemleri

```bash
# Remote listesi
git remote -v

# Remote ekle
git remote add origin https://github.com/kullanici/proje.git

# Push — local'i remote'a gönder
git push origin main

# İlk push (upstream ayarla)
git push -u origin main

# Pull — remote'u local'e çek
git pull origin main

# Fetch — indirectly güncelle (merge etmez)
git fetch origin
```

---

## ↩️ Geri Alma İşlemleri

```bash
# Staged değişikliği unstage et
git restore --staged dosya.txt

# Dosyadaki değişiklikleri at (son commit'e dön)
git restore dosya.txt

# Son commit'i geri al, değişiklikleri koru (staged)
git reset --soft HEAD~1

# Son commit'i geri al, değişiklikleri unstage et
git reset HEAD~1

# Son commit'i tamamen sil (DİKKAT!)
git reset --hard HEAD~1

# Commit'i geri al ama geçmişe dokunma (güvenli)
git revert abc1234
```

> [!CAUTION]
> `--hard` reset, kayıt altına alınmamış değişiklikleri **kalıcı olarak siler**. Dikkatli kullan!

---

## 🔀 Merge & Rebase

```bash
# Branch'i mevcut branch'e merge et
git merge feature/yeni-ozellik

# Fast-forward olmadan merge (commit oluşturur)
git merge --no-ff feature/yeni-ozellik

# Rebase (geçmişi temizlemek için)
git rebase main

# İnteraktif rebase — son 3 commit'i düzenle
git rebase -i HEAD~3
```

---

## 🏷 Stash — Geçici Saklama

```bash
# Değişiklikleri geçici sakla
git stash

# Açıklama ile stash
git stash push -m "Login formu yarım kaldı"

# Stash listesi
git stash list

# Son stash'i geri yükle
git stash pop

# Belirli stash'i geri yükle
git stash apply stash@{2}

# Stash sil
git stash drop stash@{0}
```

---

## 🔗 İlgili Notlar

- [[Yazılım/Git/git-workflow|Git Workflow & Branching Stratejisi]]
- [[Yazılım/Git/git-ipuclari|Git İpuçları & Püf Noktaları]]
- [[Yazılım/Git/git-aliases|Git Alias Kurulumu]]
