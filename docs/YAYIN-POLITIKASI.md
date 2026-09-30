# Yayın ve doğrulama politikası

## Durum etiketleri

**Planlanan:** Taban ve hedefler belirlenmiştir; kullanılabilir ISO veya test sonucu iddia edilmez.

**Kaynaklar yayımlandı, ISO bağlantısı bekleniyor:** Kaynak deposu, yapılandırma, üretim hashleri ve mevcut test kayıtları yayımlanmıştır; halka açık ISO indirme bağlantısı henüz yoktur. Makine okunur karşılığı `sources_published_iso_pending` olarak tutulur.

**Test adayı:** ISO ve üretim kaydı vardır; kapsamlı test süreci tamamlanmamıştır. İndirme verilecekse bu durum indirme bağlantısının yanında görünür olmalıdır.

**Yayımlandı:** Sürüm kaydı, indirilecek dosya, son ISO SHA-256'sı ve test sınırları birlikte yayımlanmıştır. Bu etiket bütün donanımlarda başarı veya güvenlik garantisi değildir.

Ürün desteğinin bitmesi, proje dosyasının çevrimiçi olmasından ayrı izlenir. ISO'nun bulunması o Windows tabanının güncel olduğu anlamına gelmez.

## Birbirinden ayrılan doğrulamalar

| Kontrol | Neyi gösterir? | Neyi göstermez? |
| --- | --- | --- |
| Güvenilir referansla kaynak Microsoft ISO SHA-256 eşleşmesi | Başlangıç dosyasının referansla aynı olması | Sonradan özelleştirilmiş imajın davranışı |
| Son üretilen ISO SHA-256 kaydı | Tam olarak hangi yayın dosyasının kastedildiği | Dosyanın zararsız veya resmî Microsoft ürünü olması |
| Arşiv boyut/MD5/SHA-1 metadata eşleşmesi | Arşiv kayıtlarının yayın bilgileriyle tutarlılığı | Bağımsız tam dosya SHA-256 hesabının yapılmış olması |
| İndirilmiş dosyanın tamamında SHA-256 eşleşmesi | İndirilen kopyanın yayın referansına uygunluğu | Kurulum/uyumluluk veya zararlı yazılım taraması |
| Kurulum ve uygulama testleri | Raporlanan ortam ve senaryolarda elde edilen sonuçlar | Raporlanmayan donanım, uygulama ve uzun dönem sonuçları |

Katalogdaki UMAY/KIZILELMA/ALP ER TUNGA doğrulama düzeyleri ilgili alt depoların mevcut kayıtlarından aktarılır; katalog oluşturulması yeni bir ISO doğrulama koşusu değildir.

## Her ISO için kayıt

Son dosya adı, bayt boyutu ve SHA-256; kaynak ISO kimliği; Windows edisyonu/sürümü/tam yapı numarası; dil ve mimari; araç sürümleri; kaldırma/ayar listesi; geri ekleme koşulları; doğrudan indirme adresi; test ortamı ve bilinen başarısızlıklar birlikte kaydedilir. Kaynak ve son ISO hash'leri karıştırılmaz.

Sanal makine testinde hipervizör sürümü, BIOS/UEFI, vCPU, konuk RAM, depolama ve ek sürücüler kaydedilir. Kurulum medyası ile özel otomatik test medyası ayrı tutulur. Sadece VM'de başarılı olan sonuç, gerçek bilgisayarda yapılmış gibi yazılmaz.

## Yayın yerlerini birlikte güncelleme

Yeni ISO veya doğrulama sonucu yayımlanırken alt deponun **README**, **Releases açıklaması**, makine okunur sürüm kaydı ve hash listeleri birlikte kontrol edilir. Çatı kataloğunun README ve SURUMLER.json dosyaları da buna göre güncellenir. Kaynak arşivleri ile kurulum ISO'ları açıkça ayrılır.

HAKANLAR çatısının bir katalog yayını, yeni Windows ISO yayını değildir. Bu paketteki RELEASE-NOTES.md yalnız katalog için hazırlanmış bir taslaktır; otomatik Release oluşturulmaz, mevcut alt depo etiketlerine dokunulmaz.

## Kullanım ve lisans sınırı

Bu katalog Windows lisansı, ürün anahtarı, etkinleştirme aracı veya ISO dağıtım hakkı sağlamaz. Windows, NTLite ve diğer araçların kullanım koşulları ayrıca geçerlidir. Çatı depoya Windows kurulum dosyası eklenmez. Proje belgelerine otomatik olarak üçüncü taraf Windows dosyalarını kapsayan bir açık kaynak lisansı atanmaz.
