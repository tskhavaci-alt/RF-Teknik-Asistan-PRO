# Kart Arıza PRO V4.1 — Mobil Elektronik ve RF Arıza Asistanı

Türkçe, telefona uygun, tek HTML dosyasında internetsiz çalışabilen genel elektronik/RF arıza arama yardımcısı. Şirketlere veya gizli kart tasarımlarına ait özel bilgi içermez.

## HTML'de incele
- Tarayıcı: [index.html](index.html)
- Android WebView kaynağı: [app/src/main/assets/index.html](app/src/main/assets/index.html)
- Bu iki HTML birebir aynı içerikle güncellenir. GitHub Actions APK derlemesi ayrı bir işlemdir.

## V4.1 — uygulama gibi menü
- Altta 5 sabit ana menü: **Ana Sayfa / Arıza Bul / Kütüphane / Araçlar / Kayıtlar**
- Sağ altta **＋ Hızlı İşlem**: 8 büyük buton (kısa devre, besleme, RF, hat haritası, ölçüm ekle, hesaplayıcı, malzeme ara, kayıt/yedek)
- Üstte yardım ve hızlı menü butonları
- Ana ekranda daha büyük erişim butonları, 6 ana kısayol kartı ve 6 yatay hızlı arıza düğmesi
- Teşhis adımlarında işaretlenebilir kontrol listesi, tamamlanma ilerlemesi ve sıfırlama
- Açılır menüde klavyeden Escape ile kapatma ve dokunmatik telefon düzeni

## V4'ten korunan özellikler
- 8 arıza türü ve sonucu değiştikçe değişen kontrol önerileri
- Kısa devre için seri/paralel malzeme ve kaynak/yük ayrımı
- Kullanıcının belirlediği ölçüm noktalarıyla görsel hat haritası
- Kart fotoğrafı ekleme ve üzerine manuel nokta işaretleme
- 18 elektronik malzeme rehberi, 8 ölçüm cihazı rehberi ve RF hesaplayıcıları
- Ölçülen/beklenen değer kaydı, yerel arşiv, JSON yedek dışa/içe aktarma

## Kullanım
1. Ana sayfada **Arıza incele** veya **＋ Hızlı İşlem** düğmesine bas.
2. Arıza türünü seç.
3. Güvenli ilk kontrolleri yap; her kontrolü tamamladığında işaretle.
4. Gözlemine uyan sonucu seç; sonraki kontrol önerisini oku.
5. Ölçümlerini kaydet. Gerekirse **Hat Haritası**nda kaynak/ayırma/yük noktalarını karşılaştır.

## Güvenlik ve gizlilik
- Bu yazılım otomatik arızalı eleman teşhisi veya gerçek şema analizi yapmaz.
- **Düşük ohm değeri tek başına kısa devre kanıtı değildir.**
- Direnç/diyot/süreklilik ölçerken kartın enerjisini kes; depolanan enerjiyi güvenle boşalt.
- Bilinmeyen hatta rastgele voltaj veya akım uygulama; RF/ölçü aletlerinin giriş sınırlarına uy.
- Gerçek şirket/kart fotoğrafı, gizli şema, dahili test verisi veya diğer özel bilgileri uygulamaya ve açık GitHub deposuna ekleme.
- Ölçümler ve isteğe bağlı fotoğraflar **yalnızca tarayıcı / uygulama yerel depolamasında** tutulur. Uygulama verilerini silmeden önce JSON yedeği al.

## Test kapsamı
Chromium üzerinde 320, 360, 390 ve 430 piksel ekranlarda: beşli alt menü, sekizli hızlı işlem menüsü, açma/kapatma, sekiz seçenek, teşhis kontrol listesi ve sıfırlama, ölçüm kaydı, V4 hat haritası, fotoğraf işareti, yedekleme ve hesaplayıcı regresyon testleri yapıldı. Testlerde yatay taşma ve JavaScript sayfa hatası görülmedi.

Gerçek Android APK kurulum testi yapılmadı; GitHub'a HTML yüklemek APK'nın başarıyla derlendiği anlamına gelmez.
