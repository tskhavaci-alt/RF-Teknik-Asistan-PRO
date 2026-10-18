# Kart Arıza PRO V4.4 — 5 V Kısa Devre / Entegre Pin Rehberi

**Mobil uyumlu, çevrimdışı çalışabilen, tamamen genel elektronik ve RF kart arıza arama uygulaması.** Şirket, gerçek kart tasarımı, kurum içi test değerleri ve gizli içerik bulunmaz.

## Dosyalar

- [index.html](index.html) — tek dosyalık mobil web arayüzü
- [app/src/main/assets/index.html](app/src/main/assets/index.html) — Android WebView'in kullandığı aynı HTML
- [GitHub Actions](../../actions) — Android APK derleme işlemleri; HTML yüklenmesi yeni APK'nın oluştuğunu doğrulamaz.

## V4.4: 5 V Kısa Devre Yol Gösterici

Ana Sayfa veya **+ Hızlı İşlem → 5 V kısa / Entegre pini** üzerinden erişilir.

1. Hattı yaz: 5 V varsayılandır, farklı beslemeler de incelenebilir.
2. Sorunu seç: düşük GND direnci, CC, gerilim çökmesi veya belirsiz.
3. Kaynak mı yük mü şüpheli, seri ayırma gerçekten şemadan doğrulanıp açıldı mı seç.
4. Gerçek ölçüm ve sağlam kart referansını ekle.
5. Varsa **entegre kodunu** yaz ve şüpheli pini seç: **VIN, VOUT, VCC/VDD, GND, EN, PG, FB, SW, BST, RESET, CLK, SDA, CS, NC, FAULT, ILIM**.
6. Ölçümde ne gördüğünü seç; program pinin **genel** anlamını ve sıradaki ölçüm bölgesini açıklar.
7. **Datasheet ara**: yazılan model için çevrimiçi üretici belgesi araması açar (internet gerekir).
8. **Soru metnini kopyala**: gözlemlerden düzenlenmiş bir soru hazırlayıp ChatGPT sohbetine yapıştırmana yardımcı olur; otomatik olarak sohbet göndermez.
9. Ölçüm geçmişini yerelde sakla. JSON dışa ve geri yükleme bu yeni **traceChecks** alanını da kapsar.

### Teşhis sınırları
Uygulama **belirtilen entegre koduna ait gerçek pin numarasını veya farklı üretici varyantının pin görevini otomatik tespit etmez**. Üretici datasheet'indeki *Pin Functions/Pin Description* tablosu şarttır. Aynı hatta bağlı bir entegre besleme pinindeki düşük ohm, tek başına entegre kısa devresi değildir. GND'nin GND'ye kısa olması normaldir. CC kaynağın akım sınırına ulaştığını gösterir, kesin kısa değildir.

### Ölçüm güvenliği
- Direnç/süreklilik/diyot için **enerjiyi kesip kondansatörleri güvenli boşalt**.
- Şemadan doğrulanmamış seri noktayı ayırmış gibi yorumlama; rastgele sökme.
- Bilinmeyen hatta gerilim/akım enjekte etme. Kısa devre bulmak için aşırı güç uygulama.
- Sınırlarını bilmeden MOSFET, SW düğümü, PG pull-up veya IC pinine harici gerilim bağlama.
- Uygulama verileri yalnızca cihazda tutulur; kayıt/yedeklere gizli kurum verisi yazma.

## Korunan V4.3 özellikleri
Beşli alt menü, hızlı işlem kısayolları, sekiz arıza karar ağacı, adım kontrol listesi, görsel hat haritası ve fotoğraf işaretleri, çoklu besleme Vaka Dosyası, 18 malzeme/8 ölçüm cihazı bilgisi, 27 terimlik sözlük, RF hesaplayıcılar, ilk açılış rehberi, kayıt ve JSON yedek.

## Genel referanslar
- [Texas Instruments — LMR60406-Q1 datasheet, Pin Functions](https://www.ti.com/lit/pdf/SNAS871): VIN, EN, PG, FB, SW, BOOT gibi pinlerin **örnek bir regülatördeki** görevleri.
- [Texas Instruments — LMR664xx datasheet](https://www.ti.com/mx/lit/gpn/lmr66410): bazı pinlerin çok işlevli olabileceği ve VCC/NC farkları.
- [Analog Devices — Locating Shorts on Power Planes of Multi-Layer PCBs](https://www.analog.com/cn/resources/technical-articles/locating-shorts-on-power-planes-of-multi-layer-pcbs.html): karmaşık çok katmanlı kartlarda kısa arama ve zarar vermeme ilkeleri.

Belge metinleri kopyalanmamıştır. Programdaki öneriler özgün Türkçe genel açıklamalardır.

## Test
Chromium telefon görünümünde 320, 360, 390 ve 430 px: etkileşimli kaynak/yük ayrımı, VIN/GND/PG pin açıklaması, ölçüm değiştirince yönlendirmenin değişmesi, kayıt saklama, sayfayı yeniden açma, JSON yedek dışa çıkarma, eski alt menüler, yatay taşma ve JS hataları kontrol edilmiştir. Gerçek donanımda teşhis ve Android APK kurulumu yapılmadı.
