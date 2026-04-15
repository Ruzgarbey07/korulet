# korulet
Macro
Anhilatorpedal gibi bir makro programı yapmak istiyorum ancak bilgim sıfır. bununla ilgili ne yapmam gerekiyor. Bir çok deneme yaptım pythondan ancak çok fazla sonuç alamadım. Bazı şeyler oluyor ancak tam istediğim gibi yapamıyorum. ekrandaki belirli kısımları okumakla alakalı sistemi de kurmak istiyorum örneğin oyunda 17 skill var ve bunlar yüksek den düşük damageye doğru gidiyor. Bu skilleri kullandırmak istiyorum ama en yüksek damage vuran skill hangisiyse skill in bekleme süresi doldukça onu sonrasında devam etmesini istiyorum. Skill görselleri skill hazır olana kadar bekleme süresi boyunca görseli kararıyor ve bir yuvarlak şeklinde açılıyor. Bunu okuyup o skilleri kullanmak için gerekli olan sistemi vs. bunları nasıl yapabileceğime dair bir yönerge ve gerekli kodları istiyorum.

Bana önce manuel olarak makro girebileceğim bir uygulama yapmanı istiyorum. 
Sonra skillerin görsellerini yükleyebileceğim proje içerisinde dosya yolu oluşturmanı istiyorum.

Ek olarak örnek aldığım bir programın görselini ekledim. 
Düzenlemeye ihtiyacım var. 
Skillerin görsellerini ve skill isimlerini dosyaladım. Bunları sürükle bırak mantığıyla program içerisinde bir skill bar'a sürekleyip bırakarak skill dizilimini yapmak istiyorum.Görselde asas için kullanacağım skillerin listesi bulunuyor. bunu ben bilgisayarımda C:\Users\NLT Medical\Desktop\Rogue_skill\asas konumunda tutuyorum. Sürükle bırak sisteminde bu görsellerin görünmesi gerekiyor.  Ek olarak bu skill bar'ı ekranda nerede durduğunu okuması gereken alanı seçmek için bir seçenek eklemeni istiyorum. Bu seçenekte her seferinde mükemmel pozisyonlama yapamayacağımız için skill bar'ın olduğu geniş bir alanı seçip görüntü algılama ile skillerin yerlerini ve bekleme sürelerinin kontrolünü yapan sistemin skill konumlarını belirlediğimiz alan içerisinde otomatik olarak seçmesini istiyorum. Örnek bir sürükle bırak ekranı ekledim 2. fotoğrafta.
Skillerin alanı seçilip işlem tamamlandığında doğru çalışıyormu emin olmak için test ettirmek istiyorum. 

Ek olarak tasarım ve ui 'ı ekrana sığabilecek derecede küçültmeni rica edeceğim. Herşey çok büyük ekranıma sığmıyor. 

Son olarak bir sekme oluşturmanı ve oraya asas makro olarak isimlendirmeni, 
Atak süresi: kullanıcı seçmeli
minör aktif pasif (aktif olduğunda marko başladığı an 8,9,0 tuşlarına 1 ms süreyle sürekli basması ve makro durduğunda eş zamanlı minör de durması makro başladığında tekrar devam etmesi (pasif'e manuel olarak alınmadığı sürece makroyla eş zamanlı başlamsı ve durması) pasife alındığında çalışmaması gerekiyor.)
Makro Mantığı ve Skill Bar Kontrol Protokolü

Sistem Mimarisi:

Knight Online'da skill bar, Sekmeler (F1, F2, F3) ve Slotlar (1'den 8'e kadar) şeklinde iki katmanlı çalışır. Görüntü işleme sırasında şu hiyerarşi izlenmelidir:

1. Aktif Sekme Kontrolü:



Sistem aynı anda sadece bir sekmeyi (Örn: F1) aktif olarak görebilir ve o sekmedeki slotlara basabilir.

Eğer bir skill farklı bir sekmedeyse (Örn: F2), önce ilgili fonksiyon tuşuna (F2) basılmalı, ardından slot numarası gönderilmelidir.

2. Bekleme Süresi (Cooldown) Takibi:



Referans İzleme: F1'deki skillerin bekleme süresini kontrol etmek için ana bar yerine, 3. sütundaki statik ikonlar kontrol edilmelidir.

Mantık: Bu sütundaki ikonun kararmış (beakleme süresinde) olup olmadığına bakılır. İkon aydınlandığında skill kullanıma hazırdır.

3. Karar Mekanizması (Workflow):



Adım 1: 3. sütundaki ilgili skill ikonunun rengini/durumunu kontrol et.

Adım 2: Eğer skill hazırsa ve o anki aktif sekme (Örn: F1) skill'in bulunduğu sekme değilse, önce ilgili F tuşuna basarak sekmeyi değiştir.

Adım 3: Sekme doğrulandıktan sonra ilgili slot numarasına (1-8) basarak skill'i uygula.

Web uygulaması oluşturma sadece python kodu oluştur.

Sana web ile ilgili hiç bir şey oluşturmamanı istedim sadece python kodu oluştur.
