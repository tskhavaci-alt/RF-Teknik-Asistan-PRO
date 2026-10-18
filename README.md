# Kart Arıza PRO V4.2 — Açıklamalı Mobil Elektronik ve RF Rehberi

Türkçe, mobil arayüzlü, çevrimdışı açılabilen ve **yeni başlayanlara neyin ne olduğunu anlatarak ilerleyen** genel elektronik/RF arıza yardımcısı.

## Dosyalar
- Tarayıcı için [index.html](index.html)
- Android WebView için [app/src/main/assets/index.html](app/src/main/assets/index.html)
- İki HTML aynı içeriktedir. Güncel APK için GitHub Actions derlemesi ayrıca kontrol edilmelidir.

## V4.2 ile gelenler
- **İlk açılış tanıtımı:** 4 kısa ekran; arıza seç → güvenli ölçüm → sonucu işaretle → kaydet. Tanıtım geçilebilir, bir defa gösterilir.
- **Her zaman yardım:** üstteki **?** düğmesi veya ana sayfanın **İlk defa mı kullanıyorsun?** kutusu.
- **Her arızada açıklama:** 8 arıza için **Bu ne demek? Neden ölçüyoruz?** metinleri.
- **Terim sözlüğü:** Kütüphane → Terim Sözlüğü, 27 terim ve uyarı notu. Örnekler: CC, CV, GND, Ω, PLL, VCO, LO, ADC, AGC, S11, S21, VNA, spur, ripple, ferrit.
- **Hat haritasını öğren:** Kaynak / ayırma / yük için basit örnek.
- **Hesaplayıcı açıklaması:** Hesaplamaların otomatik arıza teşhisi olmadığı belirtilir.
- **Önceki V4.1 özellikleri korunur:** alt mobil menü, büyük hızlı işlem butonları, sekiz arıza karar ağacı, işaretlenebilir kontrol listesi, 18 malzeme ve sekiz ölçüm cihazı rehberi, RF hesapları, fotoğraf işaretleme, kayıt ve JSON yedekleme.

## Kullanım
1. İlk açılıştaki rehberi oku veya **Şimdi geç** ile kapat.
2. **Arıza Bul** sayfasında yaşadığın sorunu seç.
3. Ekrandaki **Bu arıza ne demek?** açıklamasına göz at.
4. Güvenli kontrol adımlarını yaparak işaretle.
5. Sonucunla eşleşen butona bas; **Sıradaki kontrol** önerisini uygula.
6. **Ölçümü not et** ile veriyi kendi cihazına kaydet; gerekirse JSON yedeği al.

## Güvenlik, gizlilik ve kapsam
- Uygulama **otomatik PCB teşhisi, şema okuma veya arızalı parça bulma** yapmaz; ölçüme göre yöntem önerir.
- **CC**, laboratuvar kaynağının akım sınırlamaya girdiğini anlatır. **Her CC olayı kısa devre demek değildir.**
- Direnç, diyot ve süreklilik ölçmeden önce gücü kes; kapasitörleri güvenle boşalt.
- Gerilim sınırını bilmediğin hatta güç/akım enjekte etme; RF ve ölçüm cihazlarının giriş sınırlarını aşma.
- Şirket, özel şema, gizli kart fotoğrafı, ürün kodu, kurum içi veri ekleme.
- Ölçümler ve yüklenen fotoğraflar yerelde kalır; tarayıcı verileri temizlenirse yedeklenmeyen içerik kaybolabilir.

## Test
Chromium mobil testleri 320, 360, 390 ve 430 px genişliğinde geçti: rehber ileri/geri/atla/kapat ve tekrar aç; sekiz arızadan kısa devre akışı; 27 kelime araması; hesaplayıcı; kayıt oluşturma; hat haritası örneği; alt menü ve hızlı menü. Yatay taşma veya sayfa JavaScript hatası gözlenmedi. Gerçek telefona APK kurulum testi yapılmadı.
