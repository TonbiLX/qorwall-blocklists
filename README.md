<div align="center">

# 🛡️ QorWall Blocklists

**Kategori-bazlı, kürasyonlu DNS engelleme listeleri**

*Türkiye'deki ev kullanıcısı için optimize, popüler global servisler + Türkçe streaming/kumar siteleri dahil*

[![License: CC0-1.0](https://img.shields.io/badge/License-CC0%201.0-lightgrey.svg?style=for-the-badge)](https://creativecommons.org/publicdomain/zero/1.0/)
[![Domains](https://img.shields.io/badge/Domains-668-00d4ff?style=for-the-badge&logo=shield&logoColor=white)](#-listeler)
[![Categories](https://img.shields.io/badge/Categories-7-39ff14?style=for-the-badge)](#-listeler)
[![Auto Update](https://img.shields.io/badge/Auto--Refresh-24h-ff6b35?style=for-the-badge)](#-otomatik-güncelleme)

[**📋 Listeler**](#-listeler) • [**🚀 Kullanım**](#-kullanım) • [**🌐 Web Sayfası**](https://tonbilx.github.io/qorwall-blocklists/) • [**🤝 Katkıda Bulun**](#-katkıda-bulunma)

</div>

---

## 🎯 Niçin?

Mevcut DNS blocklist'leri (StevenBlack, Hagezi, OISD) **global** odaklı — milyonlarca domain ama Türkçe streaming, yerel bahis siteleri ve TR e-ticaret eksik. **QorWall Blocklists** bu boşluğu doldurur:

- ✅ **TR + Global birleşik** — BluTV, Exxen, Tabii, iddaa, mobilbahis ile beraber YouTube, Netflix, Bet365
- ✅ **Kategori-bazlı** — her kategori ayrı dosya, sadece istediğini ekle
- ✅ **Az false-positive** — sadece bilinen, doğrulanmış domain'ler
- ✅ **CDN'ler dahil** — `googlevideo.com`, `nflxvideo.net`, `bamgrid.com` gibi gerçek block için kritik domain'ler
- ✅ **Otomatik refresh** — 24 saat
- ✅ **Açık kaynak (CC0)** — kamu malı, serbestçe kullan

---

## 📋 Listeler

| | Kategori | Dosya | Domain | Açıklama |
|:-:|---|---|:-:|---|
| 🎬 | **Streaming** | [`streaming.txt`](./streaming.txt) | **132** | YouTube, Netflix, Disney+, Prime Video, Apple TV+, HBO Max, Hulu, Twitch, Spotify, TikTok, BluTV, Exxen, Tabii, Vimeo |
| 💬 | **Sosyal Medya** | [`social.txt`](./social.txt) | **107** | Facebook, Instagram, X (Twitter), Snapchat, LinkedIn, Reddit, Threads, Pinterest, Discord, Telegram, Bluesky |
| 🎮 | **Oyun Siteleri** | [`games.txt`](./games.txt) | **83** | Steam, Epic Games, Roblox, Minecraft, Battle.net, EA, Riot, online oyun siteleri, cloud gaming |
| 🚫 | **Yetişkin İçerik** | [`adult.txt`](./adult.txt) | **72** | Pornografi siteleri ana domainleri (CDN dahil) |
| 🎰 | **Kumar** | [`gambling.txt`](./gambling.txt) | **123** | İddaa/casino/slot/poker — TR yasaklı bahis siteleri (mobilbahis, betpas, restbet vb.) + global devler (Bet365, 1xbet) |
| 📢 | **Reklamlar** | [`ads.txt`](./ads.txt) | **84** | Google Ads, Meta Ads, Adobe, Yahoo, takip pikselleri |
| 🛒 | **Alışveriş** | [`shopping.txt`](./shopping.txt) | **67** | Trendyol, Hepsiburada, Amazon, AliExpress, Shein, Temu, Getir, Yemeksepeti |

> **Toplam:** 668 domain · 7 kategori · CC0 lisans

---

## 🚀 Kullanım

### A) QorWall ile (önerilen — otomatik refresh)

QorWall webpanel → **İçerik Filtreleri** → ilgili kategori → **Düzenle** → **+ Yeni Liste Ekle**:

```
URL    : https://raw.githubusercontent.com/TonbiLX/qorwall-blocklists/main/<kategori>.txt
Format : Domain List
Refresh: 24 saat
```

QorWall otomatik fetch + parse + bu kategoriye atama yapar. Liste güncellendiğinde 24 saat içinde Pi otomatik yenilemeyi alır.

### B) Pi-hole / AdGuard Home

Adlists / DNS Blocklists kısmına URL ekle, format **Domain** veya **Auto-detect** seç.

### C) Curl + custom script

```bash
curl -fsS https://raw.githubusercontent.com/TonbiLX/qorwall-blocklists/main/streaming.txt
```

---

## 🔗 Hızlı Erişim — Raw URL'ler

```
# Streaming (YouTube/Netflix/Disney+/Prime/Twitch/Spotify/BluTV/Exxen)
https://raw.githubusercontent.com/TonbiLX/qorwall-blocklists/main/streaming.txt

# Sosyal Medya (Facebook/Instagram/X/TikTok/Reddit/LinkedIn)
https://raw.githubusercontent.com/TonbiLX/qorwall-blocklists/main/social.txt

# Oyun Siteleri (Steam/Epic/Roblox/Minecraft/Riot)
https://raw.githubusercontent.com/TonbiLX/qorwall-blocklists/main/games.txt

# Yetişkin İçerik (18+)
https://raw.githubusercontent.com/TonbiLX/qorwall-blocklists/main/adult.txt

# Kumar (TR + Global)
https://raw.githubusercontent.com/TonbiLX/qorwall-blocklists/main/gambling.txt

# Reklamlar
https://raw.githubusercontent.com/TonbiLX/qorwall-blocklists/main/ads.txt

# Alışveriş (TR + Global)
https://raw.githubusercontent.com/TonbiLX/qorwall-blocklists/main/shopping.txt
```

---

## 🔄 Otomatik Güncelleme

| Konu | Detay |
|---|---|
| Liste güncelleme sıklığı | Tipik haftalık, gerektiğinde anlık |
| QorWall fetch sıklığı | 24 saat (varsayılan, ayarlanabilir) |
| Format | `domain_list` (her satırda 1 domain, `#` yorum) |
| Encoding | UTF-8 |
| SHA256 cache | QorWall değişmemiş içeriği tekrar parse etmez |

---

## 📐 Format Spesifikasyonu

```
# Yorum satiri (# ile baslar — atlanir)
example.com
www.example.com
cdn.example.com

# Bos satirlar OK (atlanir)
```

**Kurallar:**
- Her satırda 1 domain
- Comment: `#` ile başlar
- Boş satır: yorum gibi (atlanır)
- Wildcard YOK (subdomain'leri tek tek yaz: `www.example.com`, `m.example.com`)
- Hosts format değil — sadece domain (`0.0.0.0` prefix YOK)
- IPv4/IPv6 adres YOK (sadece domain)
- Lowercase tercih edilir (parser case-insensitive)

---

## 🤝 Katkıda Bulunma

Yeni domain ekleme veya yanlış pozitif düzeltmesi için:

### Issue açma
[New issue](https://github.com/TonbiLX/qorwall-blocklists/issues/new) → kategori + domain + sebep

### Pull Request
1. Repo'yu fork et
2. İlgili `.txt` dosyasını düzenle
3. Domain'i ilgili gruba ekle (yorumla işaretle)
4. PR aç — tek satır mesaj yeter

### Ne **eklemeyin**?
- ❌ Genel global blocklist'lerde olan jenerik reklam/tracking domain'leri (StevenBlack/Hagezi var zaten)
- ❌ Tek seferlik domain'ler (kısa ömürlü, yarın değişecek)
- ❌ IP adresleri (sadece domain)
- ❌ Wildcard (`*.example.com`) — subdomain'leri tek tek yaz

### Ne **ekleyin**?
- ✅ Türkiye-spesifik servisler (TR streaming, e-ticaret, bahis)
- ✅ Yaygın CDN'ler (`googlevideo.com`, `nflxvideo.net`)
- ✅ Subdomain'ler (`m.example.com`, `api.example.com`, `www.example.com`)
- ✅ Mobile uygulama API endpoint'leri (`api.tiktok.com` vb.)

---

## 🛡️ Lisans

[**CC0 1.0 Universal**](https://creativecommons.org/publicdomain/zero/1.0/) — kamu malı, hiçbir hak iddiası yok. Serbestçe kopyala, değiştir, dağıt, kullan. Atıf zorunlu değil ama hoş.

---

## 🔗 İlgili Projeler

| Proje | Açıklama |
|---|---|
| [**QorWall Firewall**](https://github.com/TonbiLX/TonbilAiFirewallv5) | Bu repo'nun ana projesi — Raspberry Pi tabanlı yapay zeka destekli router yönetim sistemi |
| [Hagezi DNS Blocklists](https://github.com/hagezi/dns-blocklists) | Tier-bazlı kapsamlı engelleme listesi (Light → Ultimate) |
| [StevenBlack/hosts](https://github.com/StevenBlack/hosts) | Birleştirilmiş hosts dosyası (klasik) |
| [BlocklistProject](https://github.com/blocklistproject/Lists) | Kategori-bazlı modern liste seti |
| [OISD](https://oisd.nl/) | Düşük yanlış-pozitif blocklist |
| [USOM](https://www.usom.gov.tr/) | Türkiye Ulusal Siber Olaylara Müdahale Merkezi resmi liste |

---

<div align="center">

**Made with 🛡️ by [TonbiLX](https://github.com/TonbiLX)** · part of [QorWall Firewall](https://github.com/TonbiLX/TonbilAiFirewallv5)

[⬆ Back to top](#%EF%B8%8F-qorwall-blocklists)

</div>
