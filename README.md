# Kart Arıza PRO V5.1 — Akıllı Devre Takibi

**Türkçe, telefona uygun, tek HTML dosyasında çevrimdışı çalışabilen elektronik ve RF arıza arama sihirbazı.** Yalnızca genel teknik yöntemler kullanılır; şirketlere ait özel bilgiler, dahili kart isimleri veya kurum içi test değerleri bulunmaz.

## Kullanım / dosyalar

- **Telefon HTML:** [index.html](index.html) — indirip tarayıcıda aç.
- **Android uygulama içeriği:** [app/src/main/assets/index.html](app/src/main/assets/index.html) — aynı dosya; APK derlemesi GitHub Actions'ta ayrı süreçtir.
- **V4.4 ayrıntılı özellik arşivi:** [arsiv/Kart_Ariza_PRO_V4_4.html](arsiv/Kart_Ariza_PRO_V4_4.html). V5 sade tasarımdır; V4.4'ün tüm araçları yeni ekrana taşınmamıştır.

## V5.1 ile gelenler

- **Gerçek hat yoluna dayalı sıradaki parça yönlendirmesi:** Senin girdiğin ve doğruladığın sıra üzerinden, güvenli şekilde ayrılmış seri noktada *yük tarafı* şüpheliyse sonraki kayıtlı elemana; *kaynak tarafı* şüpheliyse önceki elemana dönmeyi önerir. Tıklayınca bir sonraki inceleme seçilir; bağlantı türü yeniden doğrulanır.
- **Yeni parça takınca CC tekrar başladı** ayrı akışı: değeri, yönü, lehim pedlerini, aşırı gerilim ve aynı besleme hattındaki diğer yükleri inceletir; aynı parçayı tekrar tekrar değiştirerek güç vermeyi önermez.
- **İsteğe bağlı karşılaştırmalı ölçüm alanları:** Kaynak, yük ve sağlam kart için enerjisiz GND direncini Ω biriminde kaydeder; değerlerin düşük olmasına bakarak otomatik parça arızası ilan etmez.
- **Ölçüm geçmişi:** Vaka kayıtlarında eski/yeni sonuçları ve notları açılabilir bir bölümde karşılaştır.
- **Yedek geri yükleme:** V5 veya V5.1 JSON dosyasını 1 MB sınırıyla seçip mevcut vakalarla (benzersiz vaka kimliği kullanarak) birleştir. Farklı kimlikli eski kayıtlar korunur.
- **V5 kayıt anahtarı korunur:** `kart-ariza-pro-v5` sayesinde önceki V5 vakaları erişilebilir kalır.

## Sade telefon arayüzü

Ana sayfada yalnızca **Kısa devre ara / Besleme arızası / RF sinyal arızası / Ölçüm kayıtları** butonları var. Alt menü: **Ana Sayfa / Arıza Bul / Pin Rehberi / Kayıtlar**.

Kısa devre sihirbazı sırasıyla:
1. Hattı (ör. 5 V) seçer.
2. Belirtiyi (ör. CC) sorar.
3. Kullanıcının **gerçek şemadan doğruladığı** eleman sırasını ister. Temsili hat yalnızca *Örnek hat yolu yükle* düğmesiyle görünür.
4. Kontrol noktasını ve elemanın seri/paralel bağlantısını sorar.
5. Gerçekte yapılan müdahaleyi (yalnızca ölçüm, seri ayırma, paralel eleman kaldırma) sorar.
6. Sonuç ile opsiyonel kaynak/yük/sağlam ölçümlerini alır.
7. Kısa kontrol adımlarını, olası yönü ve varsa **bir sonraki kayıtlı elemanı** gösterir.

## Güvenlik / sınırlar

- **CC akım sınırıdır; kesin kısa devre kanıtı değildir. Düşük Ω da tek başına arıza kanıtı değildir.**
- Enerjisiz direnç/süreklilik testi yap, kondansatörlerde depolanan yükü güvenle boşalt.
- Seri elemanı yalnızca gerçekten şemadan doğrulanmış ve güvenle ayrılmışsa *ayrıldı* diye işaretle.
- Bilinmeyen devreye rastgele voltaj/akım enjekte etme, modülleri gelişigüzel sökme.
- Yazılım gerçek şemayı otomatik okumaz; sadece kullanıcının belirttiği yol üzerinden **koşullu teknik öneri** üretir.
- Entegre pin adlarının anlamı geneldir. **Üretici datasheet'i olmadan gerçek ayak numarası ve işlevi kesinleştirilemez.**
- Gizli şirket kartlarını, şemalarını, kodlarını, ölçümlerini veya fotoğraflarını bu uygulamaya girme; JSON yedeklerini paylaşırken incele.
- Kayıtlar yerel tarayıcı/uygulama depolamasında tutulur; veriyi silmeden önce yedek al.

## Doğrulama

Chromium mobil emülasyonunda **320 / 360 / 390 / 430 piksel** genişliklerde; seri hat kaynak/yük dallanması, yeni elemana geçme, paralel eleman + yeni parçanın CC'ye dönmesi, not/ölçüm geçmişi, sayfa yeniden açma, JSON yedek dışa/içe alma ve yatay taşma kontrol edildi. JavaScript sayfa hatası görülmedi. Gerçek fiziksel PCB üzerinde teşhis veya gerçek APK kurulum testi yapılmadı.

[GitHub Actions ile APK derleme durumunu incele](../../actions).
