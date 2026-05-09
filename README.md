# QorWall Blocklists

**TonbilAi/QorWall Firewall** için kürasyon yapılmış DNS engelleme listeleri.

Türkiye'deki ev kullanıcısı için optimize edilmiş — popüler global servisler + Türkçe streaming/kumar siteleri dahil. Her kategori ayrı dosya, plain `domain_list` formatı, comment desteği.

## 📋 Listeler

| Kategori | Dosya | Açıklama | Tahmini Domain |
|----------|-------|----------|----------------|
| 🎬 **Streaming** | [`streaming.txt`](./streaming.txt) | YouTube, Netflix, Disney+, Amazon Prime, Apple TV+, HBO Max, Hulu, Twitch, Spotify, TikTok, BluTV, Exxen, Tabii, Vimeo, Dailymotion | ~150 |
| 💬 **Sosyal Medya** | [`social.txt`](./social.txt) | Facebook, Instagram, Twitter/X, Snapchat, LinkedIn, Reddit, Threads, Pinterest, Discord, Telegram (web) | ~80 |
| 🎮 **Oyun Siteleri** | [`games.txt`](./games.txt) | Steam, Epic, Roblox, Minecraft, Battle.net, Discord (oyun), online oyun siteleri | ~70 |
| 🚫 **Yetişkin İçerik** | [`adult.txt`](./adult.txt) | Pornografi siteleri (büyük popüler) | ~50 |
| 🎰 **Kumar** | [`gambling.txt`](./gambling.txt) | İddaa, casino, slot, poker (Türkçe + global) | ~120 |
| 📢 **Reklamlar** | [`ads.txt`](./ads.txt) | Reklam ağları, takip pikselleri | ~100 |
| 🛒 **Alışveriş** | [`shopping.txt`](./shopping.txt) | Trendyol, Hepsiburada, Amazon, AliExpress | ~30 |

## 🚀 QorWall'da Kullanım

### Yöntem 1: URL ile ekle (otomatik refresh)

QorWall webpanelden:
1. **İçerik Filtreleri** sayfası
2. İlgili kategori → **Düzenle**
3. **+ Yeni Liste Ekle**
4. URL: `https://raw.githubusercontent.com/TonbiLX/qorwall-blocklists/main/<kategori>.txt`
5. Format: **Domain List**, Update: **24 saat**
6. **Listeyi Ekle** → otomatik fetch + parse + kategoriye atama

### Raw URL'ler (kopyala-yapıştır)

```
# Streaming (YouTube, Netflix, Disney+, vb.)
https://raw.githubusercontent.com/TonbiLX/qorwall-blocklists/main/streaming.txt

# Sosyal Medya
https://raw.githubusercontent.com/TonbiLX/qorwall-blocklists/main/social.txt

# Oyun Siteleri
https://raw.githubusercontent.com/TonbiLX/qorwall-blocklists/main/games.txt

# Yetişkin İçerik
https://raw.githubusercontent.com/TonbiLX/qorwall-blocklists/main/adult.txt

# Kumar
https://raw.githubusercontent.com/TonbiLX/qorwall-blocklists/main/gambling.txt

# Reklamlar
https://raw.githubusercontent.com/TonbiLX/qorwall-blocklists/main/ads.txt

# Alışveriş
https://raw.githubusercontent.com/TonbiLX/qorwall-blocklists/main/shopping.txt
```

## 🤝 Katkıda Bulunma

Yeni domain ekleme veya yanlış pozitif düzeltmesi için PR açın. Liste formatı:

```
# Yorum satiri (# ile baslayan satirlar parser tarafindan atlanir)
example.com
www.example.com
cdn.example.com

# Bos satirlar da OK
```

**Format kuralları:**
- Her satırda 1 domain
- Comment: `#` ile başlar
- Boş satır: yorum gibi (atlanır)
- Wildcard YOK (subdomain'leri tek tek yaz)
- Hosts format değil — sadece domain (`0.0.0.0` prefix YOK)

## 📜 Lisans

[CC0 1.0 Universal](https://creativecommons.org/publicdomain/zero/1.0/) — kamu malı, serbest kullanım.

## 🔗 İlgili Projeler

- [QorWall Firewall](https://github.com/TonbiLX/TonbilAiFirewallv5) — Raspberry Pi tabanlı yapay zeka destekli router yönetim sistemi
- [BlocklistProject](https://blocklistproject.github.io/) — referans aldığım kategorize liste kaynağı
- [Hagezi DNS Blocklists](https://github.com/hagezi/dns-blocklists) — kapsamlı, tier-bazlı engelleme listesi
- [OISD](https://oisd.nl/) — düşük yanlış pozitif blocklist
