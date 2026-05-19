# 🏛️ livehistory.app — İstanbul, 1550

> **Yapay zekâ destekli yaşayan tarih simülasyonu**
> *AI-powered living history simulation set in 16th-century Ottoman Istanbul*

🌐 **Canlı / Live demo:** [hasanhgunes-hue.github.io/livehistory-app](https://hasanhgunes-hue.github.io/livehistory-app/)

---

## 🇹🇷 Türkçe

### Proje Hakkında

`livehistory-app`, Kanuni Sultan Süleyman dönemi İstanbul'unu (1550) yapay zekâ ile etkileşimli olarak deneyimlemeye olanak veren bir **dijital tarih simülasyonudur**. Kullanıcı; Padişah'tan Mimar Sinan'a, Hürrem Sultan'dan Venedik Balyosu'na kadar **sekiz tarihî karakterle** birinci ağızdan Türkçe sohbet edebilir.

Proje, **dijital beşeri bilimler** ve **deneyimsel tarih pedagojisi** alanlarına bir katkı olarak tasarlanmıştır. Aşağıdaki sorular etrafında geliştirilmektedir:

- Üretici yapay zekâ, tarihî kaynak okuma ile karakter simülasyonu arasındaki sınırı nasıl yeniden tanımlar?
- Çoklu karakter modelleri, **olay-haberdarlık** ve **bilgi asimetrisi** üzerinden yaşayan bir şehir yanılsaması yaratabilir mi?
- Yapay zekâ destekli ortamlar, tarih eğitiminde **kaynaklı düşünme**yi geliştirir mi, yoksa onun yerine geçer mi?

### Yöntemsel Yaklaşım

Karakterler statik metin havuzundan **değil**, her etkileşimde Claude (Anthropic) modeline dinamik olarak gönderilen **bağlamsal sistem promptları** üzerinden cevap verir. Sistem her çağrıda şu bağlamı enjekte eder:

- Karakterin tarihî kimliği, üslubu, görüş ufku
- Şu anki **dünya saati** (Gün X · Vakit Y)
- O karakterin **haberdar olduğu** son olaylar (Vekâyiname)
- Kullanıcının diğer karakterlerle yaptığı konuşmaların **dedikodu çıktısı**

Bu sayede karakterler, statik bir chatbot olmaktan çıkıp **yaşayan bir tarih dünyasının paydaşları** olarak konuşur. Padişah Mimar Sinan'ın inşaattaki güncel sorunundan haberdardır; Hürrem Sultan ise sizin Padişah ile az önce ne konuştuğunuzu kulağına çalmış olabilir.

### Karakterler ve Mekânlar

**Mekânlar:** Topkapı Sarayı · Süleymaniye · Kapalıçarşı · Galata İskelesi · Yeniçeri Kışlası · Mevlevî Tekkesi

**Karakterler:**

| Karakter | Mevki | Mekân |
|----------|------|-------|
| Kanuni Sultan Süleyman | Padişah, Halife, Kanuni | Topkapı Sarayı |
| Hürrem Sultan | Haseki Sultan | Topkapı Sarayı |
| Rüstem Paşa | Sadrazam | Divan-ı Hümayun |
| Mimar Sinan | Hassa Mimarbaşı | Süleymaniye inşaatı |
| Yusuf el-Halebî | Tüccar | Kapalıçarşı |
| Marco Grimani | Venedik Balyosu | Galata |
| Mehmed Ağa | Yeniçeri Bölük Komutanı | Kışla |
| Şeyh İbrahim Efendi | Mevlevî Şeyhi | Tekke |

### Kullanım

Site, kullanıcının kendi **Anthropic API anahtarı** ile çalışır. Anahtar yalnızca tarayıcı belleğinde tutulur; **hiçbir sunucuya gönderilmez**.

1. [console.anthropic.com](https://console.anthropic.com/settings/keys) üzerinden ücretsiz hesap açın ve bir API anahtarı oluşturun (`sk-ant-...`)
2. Hesabınıza küçük bir kredi yükleyin (~5 USD, yüzlerce sohbete yeter)
3. Siteyi açın, anahtarı yapıştırın, **Şehre Gir** deyin

### Mimari

- **Tek dosyalı uygulama** — React + Babel-standalone (build aşaması yok)
- **Doğrudan tarayıcı → Anthropic API** çağrısı
- **Vekâyiname motoru** — gün/vakit ilerlemesi, olay zinciri, karakter haberdarlık matrisi
- **Konuşma kayıt motoru** — dedikodu bağlamı için karakter-arası log

### Yol Haritası

- [ ] Çoklu dil (EN, AR, FR)
- [ ] Konuşma paylaşımı (görsel kart çıktısı)
- [ ] Başka şehirler: Bağdat 803, Floransa 1500, Edo 1640, Kudüs 1550
- [ ] Sınıf/eğitmen modu
- [ ] Akademik citation modülü

### Atıf

```
Güneş, H. H. (2026). livehistory.app — İstanbul 1550:
Yapay Zekâ Destekli Yaşayan Tarih Simülasyonu.
https://hasanhgunes-hue.github.io/livehistory-app/
```

### Geliştirici

**Prof. Dr. Hasan Hüseyin Güneş**, Bartın Üniversitesi Tarih Bölümü öğretim üyesidir. Doktorasını 2014'te Afyon Kocatepe Üniversitesi'nde "16. Asırda Kudüs Meğâribe Mahallesi ve Cemâati" başlıklı teziyle tamamlamıştır. 2023-2024 yılları arasında, Prof. Dr. Cemal Kafadar'ın daveti üzerine TÜBİTAK bursuyla Harvard Üniversitesi Ortadoğu Araştırmaları Enstitüsü'nde "Osmanlı Râfızî Reddiyeleri: Türsel Uyumsuzlukta Müşterek Bir Söylem İnşası" başlıklı projesi üzerinde çalışmıştır.

Çalışma alanları: Osmanlı vakıf müessesi, Osmanlı Kudüs'ü, Filistin, Şiilik. Arapça, Farsça ve İngilizce bilmektedir.

**Yayımlanmış kitapları:**
- *Kudüs'ü Yeniden Düşünmek* (Önsöz Yayınları)
- *Kudüs Meğâribe Mahallesi* (Vakıflar Genel Müdürlüğü Yayınları)
- *Bir Taşra Şehrinden İnsan Manzaraları: Osmanlı Kudüsü'nde Vakıflar ve İnsanlar* (Ketebe Yayınları)

### Lisans

Bu proje **Creative Commons Atıf-GayriTicari-AynıLisanslaPaylaş 4.0 Uluslararası Lisansı (CC BY-NC-SA 4.0)** altında lisanslanmıştır.

✅ **Serbest kullanım:** Akademik araştırma, eğitim, kişisel kullanım, derslerde gösterim, atıfla paylaşım.

❌ **Yasak kullanım:** Ticari kullanım (satış, reklam yoluyla gelir, ücretli platformlara entegrasyon).

📧 **Ticari lisanslama** için yazarla iletişime geçiniz.

[Lisansın tam metni](https://creativecommons.org/licenses/by-nc-sa/4.0/deed.tr)

© 2026 Prof. Dr. Hasan Hüseyin Güneş. Tüm hakları saklıdır.

---

## 🇬🇧 English

### About

`livehistory-app` is an **AI-powered interactive history simulation** set in Istanbul during the reign of Sultan Süleyman the Magnificent (1550). Users converse in Turkish (with English support planned) with **eight historical figures** — from the Sultan and Architect Sinan to Hürrem Sultan and the Venetian *Bailo* — each rendered as a contextually aware AI agent.

Built as a contribution to **digital humanities** and **experiential historical pedagogy**, the project explores:

- How does generative AI redefine the boundary between historical source-reading and character simulation?
- Can multi-agent models create a "living city" illusion through **event-awareness** and **information asymmetry**?
- Do AI-mediated environments enhance or substitute source-based historical thinking in education?

### Methodology

Characters do **not** respond from a static pool of texts. Each interaction sends a **dynamically composed system prompt** to Anthropic's Claude model, injecting:

- The character's historical identity, voice, and epistemic horizon
- The current **world time** (Day X, time of day Y)
- Recent events **the character is aware of** (the *Vekâyiname* — Chronicle)
- A **gossip stream** of the user's conversations with other characters

This turns each character from a static chatbot into a **stakeholder in a living historical world**. The Sultan knows of Sinan's construction issues; Hürrem may have heard what you just discussed with the Sultan.

### Architecture

- Single-file React app (Babel-standalone, no build step)
- Direct browser-to-Anthropic API calls
- Chronicle engine: time/event progression
- Cross-character awareness log for emergent gossip

### Usage

The site runs entirely in the user's browser with their own **Anthropic API key**. The key is held only in browser memory and is **never sent to any server**.

1. Get a free API key at [console.anthropic.com](https://console.anthropic.com/settings/keys)
2. Top up a small credit (~5 USD, enough for hundreds of conversations)
3. Open the site, paste your key, and enter the city

### Citation

```
Güneş, H. H. (2026). livehistory.app — Istanbul 1550:
An AI-Powered Living History Simulation.
https://hasanhgunes-hue.github.io/livehistory-app/
```

### Author

**Prof. Dr. Hasan Hüseyin Güneş** is a faculty member at the Department of History, Bartın University, Türkiye. He received his PhD in 2014 from Afyon Kocatepe University with a dissertation on "The Maghreb Quarter and Community of 16th-Century Jerusalem." Between 2023 and 2024, he was a Visiting Scholar at Harvard University's Center for Middle Eastern Studies, hosted by Prof. Cemal Kafadar, under a TÜBİTAK fellowship for his project *Ottoman Refutations of the Rāfiḍī: Constructing a Shared Discourse of Genre Incompatibility*.

His research focuses on Ottoman *waqf* institutions, Ottoman Jerusalem, Palestine, and Shi'a–Sunni intellectual history. He works in Arabic, Persian, and English.

**Selected books:**
- *Rethinking Jerusalem* (Önsöz Publications)
- *The Maghreb Quarter of Jerusalem* (General Directorate of Foundations)
- *Human Landscapes from a Provincial City: Waqfs and People in Ottoman Jerusalem* (Ketebe Publications)

### License

This work is licensed under the **Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License (CC BY-NC-SA 4.0)**.

✅ **Permitted:** Academic research, education, personal use, classroom demonstration, sharing with attribution.

❌ **Prohibited:** Commercial use (sale, ad-monetization, integration into paid platforms).

📧 **For commercial licensing**, please contact the author.

[Full license text](https://creativecommons.org/licenses/by-nc-sa/4.0/)

© 2026 Prof. Dr. Hasan Hüseyin Güneş. All rights reserved.
