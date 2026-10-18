# Kart Arıza Rehberi — Elektronik ve RF

Bu depo genel elektronik/RF kartlarda arıza arama için hazırlanmış sade Türkçe bir HTML rehberidir. Gerçek kurum, proje, özel kart kodu veya kurum içi test değerleri içermez.

## Başlangıç
Telefon ya da bilgisayarda kök dizindeki `index.html` dosyasını tarayıcıda açın. İnternet gerekmez. Android APK projesinin kullandığı aynı içerik `app/src/main/assets/index.html` dosyasındadır.

## Sürüm: geliştirilmiş rehber
- İlk ekranda 4 temel arıza: kısa devre/CC, besleme kaybı, RF sinyal kaybı, aralıklı arıza.
- “Diğer arızalar” açıldığında 4 ek başlık: PLL/LO kilit, VNA S11/S21/faz, ADC/AGC, spur/gürültü.
- Her başlıkta ölçüme göre sonraki kontrol noktası değişen seçenekler.
- Kısa devre dalında seri/paralel eleman ve kaynak/yük tarafı ayrımı.
- Ölçülen ile sağlam kartta beklenen değeri birlikte not etme.
- Yöntem araması, tarayıcıda yerel kayıt, JSON yedek dışa aktarımı.
- Haricî JavaScript, kullanıcı girişi, otomatik veri aktarımı veya sunucu gerektirmez.

## Kullanım uyarısı
Bu uygulama kartın şemasını otomatik okumaz, kesin arızalı bileşen tespit etmez. Öneriler genel yöntemlerdir; ölçüm sınırları, ESD önlemleri, devre topolojisi ve cihaz güvenliği kullanıcı tarafından doğrulanmalıdır. Direnç ölçerken kart enerjisiz olmalıdır. Bilinmeyen hatta rastgele voltaj uygulanmamalıdır. Özel/gizli teknik bilgi kaydedilmemelidir.

Yerel depolamadan silinen kayıtlar yedek alınmadıysa kurtarılamayabilir.
