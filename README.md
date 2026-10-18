# Kart Arıza PRO V4.3 — Açıklamalı Mobil Elektronik ve RF Asistanı

Türkçe, tek HTML dosyasında çevrimdışı çalışabilen, telefona uygun **genel elektronik ve RF kart arıza arama yardımcı uygulaması**. Şirket, özel kart, işveren, kurum içi test değeri ya da gizli bilgi içermez.

## Açma
- [index.html](index.html) dosyasını telefona indirip tarayıcıda aç.
- Android WebView uygulamasının kullandığı [app/src/main/assets/index.html](app/src/main/assets/index.html) aynı HTML içeriğini taşır.
- HTML güncellemesi **otomatik olarak APK'nın hazır olduğu anlamına gelmez**. Derleme [GitHub Actions](../../actions) üzerinden ayrıca kontrol edilmeli.

## Ana menü
**Ana Sayfa · Arıza Bul · Kütüphane · Araçlar · Kayıtlar** — alttaki beş sabit menü. Sağ alttaki **+ Hızlı işlem** menüsünden arıza türlerine, hat haritasına, **Vaka Dosyası**na ve diğer araçlara geçilir.

## V4.3 yenilikleri: 🗂️ Çoklu Hat Vaka Dosyası
- Aynı incelemede **birden fazla besleme hattı** kaydet.
- Her hat için beklenen/ölçülen gerilim (V), enerjisiz GND direnci (Ω), sağlam kart karşılaştırması, EN ve PG durumu, kontrol sırası, manuel normal/şüpheli işareti ve ölçüm notu ekle.
- Girilen sayılardan **gerilim farkını yüzde olarak görüntüle**; bu tek başına arıza kararı değildir.
- Şüpheli işaretlediğin hatlar ve kontrol eksikleri için **sonraki kontrolleri öner**.
- Hat ekleme/düzenleme/silme, vaka oluşturma/silme ve temsili üç hatlı örnek vaka.
- Seçili vakanın adını ve şüpheli/ilk hattın adını önceki **Görsel Hat Haritası**na aktar. Mevcut ölçüm noktaları otomatik silinmez.
- Eski JSON yedeklerine uyumluluk; yeni JSON yedeklerine **railCases** alanıyla vaka/hat kayıtları dahil edilir.

## Önceki sürümlerden kalanlar
- Sekiz arıza akışı: kısa devre/CC, besleme, RF sinyal, aralıklı arıza, PLL/LO, S11/S21, ADC/AGC, spur/gürültü.
- Seri/paralel malzeme ayrımı ve kaynak/yük tarafı kontrolü.
- Fotoğraflı görsel hat haritası, renkli manuel test noktaları.
- 18 elektronik malzeme ve 8 ölçüm cihazı açıklaması.
- 27 terimlik sözlük ve 4 adımlık ilk kullanım rehberi.
- İşaretlenebilir kontrol adımları, RF/elektronik hesaplayıcılar ve eski ölçüm kayıtları.

## Teknik ilkeler
- **EN/Enable:** Regülatörün çalışmasını denetleyen giriş; aktif seviyesi bileşen türüne bağlıdır.
- **PG/Power Good:** Çıkış geriliminin uygun koşullarda olup olmadığını gösteren işaret. PG pull-up, koruma ve EN durumu değerlendirilmelidir.
- **Açılış sırası:** Çok beslemeli cihazlarda sıra önemli olabilir; her karta aynı sıra uygulanamaz.
- **CC/CV:** Laboratuvar kaynağının akım/gerilim sınırlama kipleridir. CC görmek tek başına kısa devre kanıtı değildir.

Genel araştırma kaynakları:
- [Analog Devices — Power Supply Sequencing (AN-1311)](https://www.analog.com/en/resources/app-notes/an-1311.html)
- [Texas Instruments — Power Good ve Enable](https://www.ti.com/document-viewer/lit/html/SSZTB93)
- [Keysight — The Power Handbook](https://www.keysight.com/us/en/assets/3121-1101/application-notes/The-Power-Handbook.pdf)

Bu kaynaklara dayalı metinler özgün Türkçe açıklamalardır; dış uygulama kodu/kılavuz metni kopyalanmamıştır.

## Güvenlik ve gizlilik
- Enerji varken direnç ve süreklilik ölçme; kondansatörlerin depoladığı yükü güvenle boşalt.
- Şemasını ve sınırlarını bilmediğin hatta rastgele gerilim veya akım enjekte etme.
- GND direncinin düşük olması tek başına kesin kısa devre demek değildir; şema ve sağlam kartla karşılaştır.
- Gerilim farkı, EN/PG ve açılış sırası değerlerini **üretici toleransları ve gerçek şemayla doğrula**.
- Kayıtlar ve isteğe bağlı görseller yalnızca tarayıcı/uygulama yerel depolamasında tutulur. JSON dosyalarını paylaşırken gizlilik kontrolü yap; tarayıcı verileri temizlenirse yedeksiz kayıtlar kaybolabilir.

## Test kapsamı
320/360/390/430 px Chromium emülasyonunda Vaka Dosyası örneği, yeni hat ekleme, düzenleme, vaka saklama, hat haritasına geçiş, JSON dışa aktarımı ve sayfa hataları kontrol edildi. Gerçek Android APK kurulum testi veya fiziksel PCB ile otomatik teşhis yapılmadı.
