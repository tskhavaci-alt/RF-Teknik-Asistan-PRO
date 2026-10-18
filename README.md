# Kart Arıza PRO V4 — Elektronik ve RF Kart Arıza Asistanı

Türkçe, telefon odaklı ve **tek HTML dosyasında çevrimdışı çalışan** elektronik/RF arıza arama uygulaması. Tamamen genel yöntemleri içerir; herhangi bir kuruma veya özel kart tasarımına ait gerçek veriler bulunmaz.

## Uygulamayı aç

- **HTML:** [index.html](index.html) dosyasını telefona indirip tarayıcıda aç.
- **Android kaynağı:** [app/src/main/assets/index.html](app/src/main/assets/index.html) aynı içeriği taşır.
- **APK:** Kodların güncellenmesi ile APK derlemesi ayrı işlemlerdir. Güncel APK'nın başarıyla oluşturulup oluşturulmadığı GitHub Actions üzerinden kontrol edilmelidir.

## Telefon menüsü

- **Ana Sayfa** — hızlı arıza girişleri.
- **Arıza Bul** — 8 arıza başlığında ölçüm sonucuna göre değişen adımlar.
- **Hat Haritası (V4, Ana Sayfa veya Arıza Bul içinden)** — kullanıcı tanımlı kaynak / seri ayırma / yük noktaları, ölçülen ve beklenen değerler, manuel şüpheli/normal işaretleri ve kontrol önerileri.
- **Kütüphane** — 18 elektronik bileşen, 8 ölçüm cihazı, 10'dan fazla yöntem, yabancı kaynakların özgün Türkçe özetleri.
- **Araçlar** — dBm/mW, kazanç, dalga boyu, Ohm, RC/LC, S11→VSWR hesapları.
- **Kayıtlar** — ölçüm incelemeleri ve JSON yedek alma / geri yükleme.

## V4 — görsel hat haritası

1. **Kaynak → Seri ayırma → Yük** temsili görünümündeki bölümünü seç.
2. Ölçüm noktasını, ölçülen değeri, referans değerini ve **manuel** yorumunu kaydet.
3. Şemadan doğrulanmış seri ayırmanın gerçekten açılıp iki tarafın enerjisiz ölçüldüğünü yalnızca doğruysa işaretle.
4. Program, girilen değerlendirmelere göre sonraki **kontrol bölgesini** önerir; otomatik arızalı parça teşhisi yapmaz.
5. İstersen genel kart fotoğrafını seç; fotoğrafı telefonda küçültür ve görsel üzerine etiketli test noktaları işaretleyebilirsin.
6. Tüm haritayı (görsel dâhil) **JSON yedeğine** ekleyebilir, yine uygulamadan geri yükleyebilirsin.

**Örnek yükle:** V4 Hat Haritası ekranındaki **Örnek hat yükle** düğmesi üç noktalı temsili bir arıza gösterir. Örnek direnç değerleri gerçek bir karttan alınmamıştır.

## Veri ve güvenlik

- İnternet bağlantısı şart değildir; fotoğraflar ve ölçümler kendi cihazında tutulur, bir sunucuya otomatik gönderilmez.
- Bu HTML gizli veri saklamak için onaylanmış kurumsal bir araç değildir. **Özel kart fotoğrafı, şirket şeması, gizli ölçüm veya kurum içi teknik bilgiler eklemeyin**, özellikle JSON yedeklerini paylaşmayın.
- Yerel tarayıcı / uygulama verisi silinirse yedeklenmeyen kayıtlar kaybolabilir.
- Direnç / süreklilik ölçmeden önce enerji kesilmeli, kondansatörler güvenli boşaltılmalıdır.
- Düşük direnç her zaman kısa devre değildir; kart topolojisi, ölçüm sınırları ve sağlam karşılaştırma gerekir.
- Bilinmeyen hatta rastgele akım/voltaj enjekte etmeyin. Osiloskop toprak bağlantısını şebekeye göre tehlikeli noktalara bağlamayın.

## Araştırma temeli

- [Analog Devices — Locating Shorts on Power Planes of Multi-Layer PCBs](https://www.analog.com/en/resources/technical-articles/locating-shorts-on-power-planes-of-multi-layer-pcbs.html): çok katmanlı kartlarda hat/kısa arama güçlüğü.
- [Tektronix — Probing Techniques for Accurate Voltage Measurements](https://www.tek.com/en/documents/application-note/probing-techniques-accurate-voltage-measurements-power-converters-oscillos): prob-toprak bağlantısı, indüktans ve yalancı dalga şekli.
- [Analog Devices — How to Protect Your Power System Designs Against Faults](https://www.analog.com/en/resources/analog-dialogue/raqs/raq-issue-216.html): aşırı akım, gerilim ve ısıl koruma.
- Önceki PLL, VNA, ADC, RF referansları uygulama içindeki kaynaklar bölümündedir.

## Test kapsamı

Chromium mobil emülasyonunda 320/360/390 piksel genişlik, gezinme, üçlü hat haritası, ayrım doğrulaması, manuel ölçüm ekleme, fotoğraf işaretleme, JSON dışa/geri alma, eski arıza akışı ve hesaplayıcılar kontrol edildi. Gerçek Android APK kurulum testi ve fiziksel kart üzerinde otomatik teşhis **yapılmadı**.

## Sürüm yolu

V3 ana fonksiyonlar korunarak V4 eklenmiştir. Sonraki adaylar: vakaya özel birden fazla hat, kayıtları karşılaştırmalı gösterme ve dışa aktarılabilir teknik rapor. Bunlar henüz mevcut değildir.
