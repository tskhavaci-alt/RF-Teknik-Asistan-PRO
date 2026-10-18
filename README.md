# Kart Arıza PRO V3 — Mobil Elektronik ve RF Arıza Rehberi

**Türkçe, telefona uyumlu, internetsiz açılabilen arıza tespit yardımcısı.**

Bu proje tamamen genel elektronik ve RF arıza arama yöntemlerini öğretir. Herhangi bir işverene, kuruma, özel devre kartına, kurum içi prosedüre veya özel test frekansına ait bilgi içermez.

## Uygulamayı aç

- Tek dosyalık web sürümü: [index.html](index.html)
- Android WebView HTML: [app/src/main/assets/index.html](app/src/main/assets/index.html)
- Her iki HTML aynı içerikle güncellenir; tarayıcıdan veya APK içinden çevrimdışı açılabilir.
- Derlenmiş, yeni APK bu depoya kod eklemekten farklıdır; GitHub Actions sonucunu kontrol edin.

## Mobil alt menü

1. **Ana Sayfa:** hızlı teşhis kısayolları, konu ve kayıt sayacı.
2. **Arıza Bul:** 8 belirti akışı, ölçümle değişen öneri, kısa devrede seri/paralel ve kaynak/yük ayrımı.
3. **Kütüphane:** 18 pasif/aktif elektronik bileşen, 8 ölçüm cihazı, arıza yöntemleri ve yabancı teknik kaynakların özgün Türkçe özetleri.
4. **Araçlar:** dBm↔mW, RF kazanç, dalga boyu, Ohm Kanunu, RC kesim, LC rezonans, S11→VSWR.
5. **Kayıtlar:** ölçüm değerleri, sağlam kartla kıyas, yerel arşiv, JSON yedek indirme ve mevcut yedeği geri yükleme.

## Arıza izleme prensibi

Örnek: Bir parçayı sökünce CC kayboldu, yenisini takınca CC geri geldi.

Parçanın seri/paralel konumunu ve kısa görülen tarafı belirt. Yazılım bir sonraki kontrolü önerir. Bu, **otomatik arızalı eleman tespiti değildir**. Kart şeması ve ölçüm sonuçları kullanıcı tarafından doğrulanmalıdır.

## Genel güvenlik ve gizlilik

- Direnç ve diyot ölçümü öncesinde enerjiyi kesin, depolanan yükü güvenli boşaltın.
- Rastgele voltaj veya yüksek akım enjekte etmeyin.
- RF, osiloskop ve güç kaynağı giriş/sınırlarını aşmayın.
- Kayıtlar yerel depolamada tutulur; otomatik olarak başka yere gönderilmez.
- Uygulama verileri temizlenirse, yedek alınmayan kayıtlar kaybolabilir.
- Gerçek karta ait gizli şema, belge, marka dışı dahili kod veya ticari bilgileri açık GitHub deposuna yüklemeyin.

## Araştırma kaynakları

Uygulama içinde bağlantıları ile listelenen kaynaklar:

- iFixit: adım adım onarım arayüzü yaklaşımı.
- Electrodoc: elektronik referans ve hesaplayıcı deneyimi.
- Analog Devices: PLL lock detect, ADC referans ve güç koruma uygulama notları.
- Tektronix: osiloskop prob topraklaması.
- Keysight: S-parametre kalibrasyonu.
- Rohde & Schwarz: spektrum analizöründe RBW ve spur ölçümü.

Bu dış kaynakların teknik içerikleri **özetlenip yeniden yazılmıştır**; kaynak kodu, uygulama ekranı veya telifli kılavuzlar kopyalanmamıştır.

## Geliştirme yol haritası

**V3 — tamamlandı:** Mobil ana ekran, alt menü, ölçüm kaydı, karar ağaçları, malzeme/cihaz kütüphanesi, hesaplayıcılar, JSON aktarım.

**Gelecek sürümler için taslak:** Şema/topolojiye özel işaretli hat haritası; kullanıcı fotoğrafı üzerinde test noktası; ölçümle olasılıkların daraltılması; rapor PDF çıktısı; güvenli paylaşım ve kayıt etiketleri. Bunlar henüz V3'ün özellikleri değildir.

## Test

Başlıca tarayıcı testleri: menü dolaşımı, CC karar ağacı, seri/paralel + kaynak/yük seçimi, ölçüm kaydı, arşiv, kütüphane araması, kaynaklar ve hesaplayıcılar.

Program bir teknik yardımcıdır; kesin teşhis, elektriksel güvenlik sertifikası veya otomatik devre analizi sunmaz.
