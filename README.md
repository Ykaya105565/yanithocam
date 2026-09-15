# FORGE

Antrenman, beslenme ve toparlanma takibi. Tek HTML dosyası — build yok, npm yok, sunucu yok. Veriler telefonun tarayıcısında kalır.

**Canlı:** https://ykaya105565.github.io/yanithocam/

## Ne yapar

- **Antrenman** — egzersiz bazlı set/tekrar/ağırlık kaydı, önceki antrenmanla karşılaştırma, hacim takibi
- **Beslenme** — günlük protein / karbonhidrat / yağ / kalori ve hedefe göre değerlendirme
- **Uyku & toparlanma** — süre, kalite, enerji, stres ve takviye kaydı
- **Takvim & analiz** — haftalık/aylık görünüm, gelişim grafikleri (Recharts)
- **Egzersiz veritabanı** — kas grubu (göğüs, bacak, biceps, hamstring, core…) ve ekipmana (barbell, dumbbell, kablo, band, askı) göre filtreleme, seviye kademeleri
- **AI Koç** — kendi Anthropic API anahtarınla antrenman ve beslenme yorumu

## Programlar

Uygulamada 6 hazır program şablonu var (**Antrenman → Hazır Program Yükle**). Bunlardan biri iş yerinde öğle arasında uygulanmak üzere ayrıca tasarlandı:

- **[Öğle Arası 3 Gün — Salı / Çarşamba / Cuma](program/ogle-arasi-3-gun.md)** — 1 saatlik pencerede ~50 dk, antagonist süpersetlerle, her kas 2x/hafta. Gerekçeleri ve kaynakları dokümanda.

## Telefona kurma

Telefonda **Chrome** ile [uygulamayı](https://ykaya105565.github.io/yanithocam/) aç → sağ üst (⋮) → **"Ana ekrana ekle"**.

iPhone'da **Safari** ile aç → paylaş ikonu → **"Ana Ekrana Ekle"**.

Artık ana ekrandaki ikondan tam ekran açılır ve **internet olmadan da çalışır** — service worker uygulamayı ve kütüphaneleri önbelleğe alır.

## AI Koç kurulumu

Ayarlar → API anahtarı alanına [console.anthropic.com](https://console.anthropic.com/settings/keys)'tan aldığın anahtarı yapıştır → Kaydet.

Anahtar yalnızca senin tarayıcında (`localStorage`) saklanır, hiçbir yere gönderilmez. İstekler doğrudan tarayıcıdan `api.anthropic.com`'a gider.

## Güncelleme

`index.html` dosyasını GitHub'da düzenle (kalem ikonu) → commit. 1-2 dakikada canlıya geçer. Telefondaki uygulama bir sonraki açılışta yeni sürümü çeker.

## Veri

Tüm kayıtlar tarayıcının `localStorage`'ında tutulur — cihazdan çıkmaz, sunucuya gitmez. Tarayıcı verisini silmek kayıtları da siler, o yüzden Ayarlar'dan düzenli yedek almak iyi olur.

## Dosyalar

| Dosya | Ne |
|---|---|
| `index.html` | Uygulamanın tamamı (React, tek dosya) |
| `manifest.json`, `sw.js` | PWA — ana ekrana kurulum ve çevrimdışı çalışma |
| `icon.svg`, `icon-*.png` | Uygulama ikonu |
| `react*.js`, `prop-types.min.js`, `Recharts.js` | Kütüphaneler repoda gömülü; önce yerelden yüklenir, olmazsa CDN'e düşer |

Eski sürüm (`index2.html`) `b810a22` commit'inin içinde duruyor.
