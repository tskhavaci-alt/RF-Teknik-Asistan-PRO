# Kart Arıza Rehberi — Elektronik ve RF

Bu proje, **genel elektronik/RF kartlarda arıza arama** için hazırlanmış sade, Türkçe ve telefona uyumlu bir yardımcıdır. Herhangi bir şirkete, özel karta, kurum içi test prosedürüne veya gerçek ürüne ait gizli bilgi içermez.

## Özellikler

- Kısa devre / CC, besleme yok, RF sinyal yok, aralıklı arıza
- Ölçüm sonucuna göre bir sonraki kontrol adımı
- “Parçayı sökünce kısa kayboldu, yenisini takınca geri geldi” özel senaryosu
- Genel devre elemanı ve RF kontrol yöntemleri
- Ölçüm notlarını cihazda saklama, JSON yedeği alma
- İnternetsiz çalışma; haricî servis, hesap, veri aktarımı veya reklam kütüphanesi yok

## Açma

- **Tarayıcı:** Kök dizindeki [index.html](index.html) dosyasını indirip aç.
- **Android proje:** Aynı sürüm [app/src/main/assets/index.html](app/src/main/assets/index.html) içinde bulunur. APK derlemesi Android GitHub Actions iş akışından yapılır.
- **Dosya eşitliği:** Kök HTML ve Android assets HTML aynı tutulur.

## Dikkat

Bu yazılım otomatik devre analizi, şema okuma veya kesin arıza tespiti yapmaz. Ölçüm tavsiyelerini kartın şemasına, teknik sınırlara ve güvenli çalışma prosedürüne göre doğrula. Özel/gizli teknik bilgi kaydetme.

Kayıtlar yalnızca tarayıcı/uygulama yerel depolamasındadır. Uygulama verisi silinirse kayıtlar kaybolabilir.