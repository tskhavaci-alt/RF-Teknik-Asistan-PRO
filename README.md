# Kart Arıza PRO V5 — Mobil Arıza Sihirbazı

Telefon ekranı için hazırlanmış **tek dosyalık, çevrimdışı, Türkçe elektronik ve RF arıza arama yardımcısı**. Genel eğitim/arıza arama yöntemleri içerir; herhangi bir şirketin gerçek kartları, kurum içi ölçümleri, özel şemaları veya gizli test bilgileri bulunmaz.

## Hemen aç
- **V5 web HTML:** [index.html](index.html)
- **Android HTML:** [app/src/main/assets/index.html](app/src/main/assets/index.html) — birebir aynı dosya
- **Önceki tam gelişmiş sürüm:** [V4.4 arşivi](arsiv/Kart_Ariza_PRO_V4_4.html). V4.4'teki fotoğraflı harita, çoklu hat Vaka Dosyası, hesaplayıcılar ve detaylı sözlük bu dosyada korunmuştur; **sade V5 ekranına henüz taşınmamıştır.**

## V5'te ne değişti?
- Dört büyük butonlu sakin ana ekran: **Kısa Devre Ara, Besleme Arızası, RF Sinyal Arızası, Ölçüm Kayıtları**
- Alt sabit menü: **Ana Sayfa, Arıza Bul, Pin Rehberi, Kayıtlar**
- Uzun sayfa yerine **7 adımlık, bir ekranda bir soru** yaklaşımı
- Kullanıcının kendi kart yolunu yazabilmesi: Giriş → Koruma → Regülatör → Ferrit/0Ω → Yük. Örnek yol yalnızca düğmeyle yüklenir.
- **Seri ve paralel eleman ayrımı:** Seri ferrit güvenle ayrılmışsa kaynak/yük tarafını sorar; paralel C ayrılmışsa kısa kayboldu mu diye sorar.
- Sonuca göre tek ekranlık **Sıradaki Kontrol** önerisi: kaynak tarafına dön, yük kolunu incele, parça/pedleri doğrula veya bağlantıyı yeniden kontrol et.
- **Aynı vakada yeni ölçüm**, tarihli yerel geçmiş, son vakaya devam et, JSON yedeği ve vakayı kopyalayıp sohbetten değerlendirme.
- **12 genel pin kısaltması**: VIN, VOUT, VCC, GND, EN, PG, FB, SW, BST, RESET, CLK, NC; modele özel datasheet araması.

## Kullanım: 5 V hattında CC örneği
1. Kısa Devre Ara → **5 V** → **CC**.
2. Kart şemasından doğruladığın besleme yolunu sırayla gir veya ekranı görmek için açıkça *Örnek hat yolu yükle* seç.
3. İnceleyeceğin seri ferrit/0Ω elemanını seç ve **Seri** işaretle.
4. Enerji kesilmişken ve yalnızca şemadan doğrulanmışsa **Seri ayırma noktasını güvenle açtım** seçeneğini işaretle.
5. Enerjisiz ölçümden sonra **Kısa YÜK tarafında kaldı** dersen, program sonraki yük kolundaki C, koruma elemanı ve IC besleme noktalarını kontrol etmeyi önerir.
6. **Kaynak tarafında kaldı** seçersen geri kaynağa döner. Paralel C için farklı sonuç ekranı vardır.
7. Ölçümünü kaydet ve sonraki noktaya geç.

## Güvenlik ve doğru yorum
- Program kart şemasını kendiliğinden görmez, elemanların gerçek sırasını bulmaz ve kesin arızalı parça ilan etmez.
- **CC (Constant Current) akım sınırlama durumudur; her zaman kısa devre değildir. Düşük ohm da tek başına kısa kanıtı değildir.**
- Direnç ve süreklilik ölçümü yalnızca **güç kapalı**, kapasitör yükleri güvenle boşaltılmış devrede yapılmalıdır.
- Elemanın seri/paralel olup olmadığını gerçek şemadan doğrulamadan ayırma/kaldırma işlemi yapma. Bilmiyorsan uygulamadaki **Bilmiyorum / Henüz ayırmadım** seçeneklerini kullan.
- Bilmediğin bir hatta voltaj/akım enjekte etme. Parçaları tekrar takarken değer, yön, gerilim/akım sınırı ve pad hasarını kontrol et.
- Pin kodları **genel açıklamadır**. Entegre modeli girilince otomatik gerçek pin eşleştirmesi yapılmaz; üretici datasheet'i gereklidir.
- Gizli işyeri devrelerini, fotoğraflarını, kodlarını ve dahili değerlerini kayıt sistemine veya açık GitHub deposuna ekleme.

## Depolama / sürüm uyumluluğu
V5 vakaları tarayıcıda `kart-ariza-pro-v5` anahtarı altında saklanır ve JSON olarak dışa aktarılır. Eski V4.4 verileri yeni anahtar ile **üzerine yazılmaz**, ancak otomatik içe aktarılmaz; eski sürümün kayıtlarını gerektiğinde [V4.4 arşiv dosyasında](arsiv/Kart_Ariza_PRO_V4_4.html) açabilirsin. Tarayıcı verilerinin temizlenmesi yedeksiz kayıtları silebilir.

## Test
Yerel Chromium tarayıcısında 320 / 360 / 390 / 430 px mobil genişliklerde kısa devre sihirbazı, seri elemanda kaynak/yük yönlendirmesi, paralel parçayı kaldırma sonuçları, belirsiz topoloji, RF/besleme dalı, kayıt/yeniden açma, pin menüsü, yatay taşma ve sayfa JS hataları test edilmiştir. Gerçek elektronik kart üzerinde doğrulama veya Android APK kurulum testi yapılmamıştır.

**Not:** GitHub'a HTML yüklenmesi Android APK'nın yeniden üretildiği anlamına gelmez. Derleme durumunu [Actions](../../actions) sayfasında ayrıca kontrol et.
