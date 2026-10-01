# Teknik notlar ve iddiaların sınırı

**Kontrol tarihi: 30 Eylül 2026.** Bu belge kullanıcı tarafından seçilen tabanları değiştirmez; tanıtım metnindeki tasarım hedefleriyle doğrulanabilen teknik olguları ayırır. Kaynak listesi: [KAYNAKLAR.md](KAYNAKLAR.md).

## Sürüm ile yapı numarası

1607, 1909, 22H2 ve 24H2 birer sürüm etiketidir. Ana yapı aileleri sırasıyla ilgili ürüne göre farklıdır. Windows 10 için 1607 → 14393, 1909 → 18363, 22H2 → 19045; Windows 11 için 21H2 → 22000, 22H2 → 22621, 23H2 → 22631, 24H2 → 26100 eşleştirmesi kullanılır. Güncelleme revizyonunu gösteren nokta sonrası sayı ISO yayımlanırken ayrıca kaydedilecektir. Kaynak: [Windows 10](https://learn.microsoft.com/en-us/windows/release-health/release-information), [Windows 11](https://learn.microsoft.com/en-us/windows/release-health/windows11-release-information).

## İşlemci nesli bir Windows sürümü zorunluluğu değildir

“2–11. nesil için 1909; 12. nesil ve sonrası için 22H2 zorunludur” sonucu çıkarılmaz. Bu aralıklar yalnız proje test grubu tercihleridir. 1909'un seçilmesi, aynı işlemcide daha yeni Windows sürümlerinin çalışmadığını veya daha yavaş olduğunu göstermez. İlgili kararın dayanağı karşılaştırmalı test olmalıdır.

Windows 10 hibrit Intel işlemcilerde çalışabilir; Intel'in açıklaması Windows 11'in Thread Director yeteneklerinden daha kapsamlı yararlandığı yönündedir. Bu, hibrit desteğin Windows 10'a ilk kez yalnız 22H2 ile geldiği anlamına gelmez. Kaynak: [Intel, Performance Hybrid Core Architecture](https://www.intel.com/content/www/us/en/support/articles/000088749/processors/intel-core-processors.html).

“Homojen çekirdekler” ifadesi “bütün çekirdekler her anda aynı frekansta ve aynı görevdedir” şeklinde kullanılmaz. Katalog herhangi bir işlemci neslinin tüm modellerini aynı donanım gibi ele almaz; işlemci, anakart, sürücü ve iş yükü birlikte değerlendirilir.

## LTSC güncellemesiz Windows değildir

Windows 11 IoT Enterprise LTSC 2024, 24H2 tabanına dayanır. Özellik tabanının uzun süre sabit kalması, güvenlik/bakım güncellemelerinin alınmadığı anlamına gelmez; Microsoft aylık kalite güncellemeleri tanımlar. IoT LTSC için destek sonu Microsoft'un sürüm tablosunda **10 Ekim 2034** olarak verilir. Normal Windows 11 Enterprise LTSC 2024 ile IoT sürümünün destek süreleri karıştırılmaz. Kaynak: [IoT ürün açıklaması](https://learn.microsoft.com/en-us/windows/iot/iot-enterprise/whats-new/windows-11-iot-enterprise-ltsc-2024), [sürüm tablosu](https://learn.microsoft.com/en-us/windows/release-health/windows11-release-information).

IoT Enterprise LTSC özel amaçlı, sabit işlevli cihazlar için konumlandırılır. Yalnız “hafif olduğu” gerekçesiyle her kullanımın lisans açısından uygun olduğu sonucu çıkarılmaz; kullanım koşulları ayrıca incelenmelidir. “Bütün UWP ve servisler Microsoft tarafından çekirdekten söküldü”, “21H2 VM'lerde kararsızdır” veya “bütün Guest Additions sürümleri tam uyumludur” gibi bu proje için ölçülmemiş genellemeler yapılmaz.

<a id="bellek-hedefi"></a>

## Bellek hedefi ile resmî gereksinim aynı şey değildir

Windows 11 Home/Pro için Microsoft'un yayımladığı genel bellek alt sınırı **4 GB**'dır; işlemci, depolama, TPM ve diğer gereksinimler ayrıca vardır. Windows 11 IoT Enterprise LTSC donanım tablosunda tercih edilen bellek **4 GB**, özel isteğe bağlı yapılandırmanın alt sınırı **2 GB** olarak gösterilir. Kaynak: [Windows 11 gereksinimleri](https://www.microsoft.com/en-us/windows/windows-11-specifications), [IoT gereksinimleri](https://learn.microsoft.com/en-us/windows/iot/iot-enterprise/Hardware/System_Requirements).

Bu nedenle Windows 11 UMAY için **1 GB**, Windows 11 KIZILELMA için **2 GB** yalnız deneysel proje hedefidir. Bu hedefler, desteklenen resmî donanım sınıfı veya doğrulanmış kullanılabilirlik olarak sunulmaz. Başarılı bir açılış testi bile kurulum, güncelleme veya uygulama yükü başarısını kendiliğinden kanıtlamaz.

Windows 10 UMAY'ın 1.024 MiB VM kaydı, farklı Windows 11 UMAY tabanına aktarılmış bir test sayılmaz. 4/8/16 GB sınıfları da Windows'un zorunlu RAM miktarı değil, bu proje tarafından seçilen hedeflerdir.

<a id="windows-11-virtualbox"></a>

## Windows 11: VirtualBox açılış ve gereksinim uyarıları

**Ön test kaydı: 1 Ekim 2026.** Ana bilgisayarda Windows 11 bulunması, sanal makineye yeterli işlemci, RAM veya sanal TPM'nin otomatik olarak verildiği anlamına gelmez. Microsoft'un genel Windows 11 VM gereksinimleri en az **2 sanal işlemci, 4 GB RAM, 64 GB disk**, Secure Boot yeteneği ve sanal TPM içerir. [Microsoft VM gereksinimleri](https://learn.microsoft.com/en-us/windows/whats-new/windows-11-requirements#virtual-machine-support).

Windows 11 UMAY hazırlığındaki Türkçe **Enterprise LTSC 2024, 26100.1742** denemesinde iki ayrı belirti gözlendi:

| Yapılandırma | Gözlem |
| --- | --- |
| 1 sanal işlemci | Kurulum açıldı, ardından sistem gereksinimleri uyarısı çıktı. Hangi kontrolün reddettiği günlükten ayrıştırılmadı; 1 işlemci zaten genel VM alt sınırını karşılamıyor. |
| 2 sanal işlemci, x2APIC açık | Windows başlamadan UEFI aşamasında takılma yeniden gözlendi; günlük `DXE_AP` noktasında kaldı. |
| 3 sanal işlemci, x2APIC açık | Aynı ISO ile kurulum ekranı açıldı; kullanıcı yeniden denemenin işe yaradığını bildirdi. |

Bu test **VirtualBox 7.2.20 r175154**, Windows 11 ana bilgisayar ve **NEM/Windows Hypervisor** çalıştırma yolu üzerindedir. VirtualBox projesindeki açık [#799 hata bildirimi](https://github.com/VirtualBox/virtualbox/issues/799), benzer ortamda tam 2 işlemciyle takılma ve 3 işlemciyle açılma tarif eder. Bu bir kullanıcı hata bildirimidir; tüm VirtualBox sürümleri ve bilgisayarlar için doğrulanmış genel kural değildir.

**Benzer durumda:** Sanal makineyi tamamen kapatın. VirtualBox → Ayarlar → Sistem → İşlemci bölümünde **3 işlemciyi deneyin**; ana bilgisayarın fiziksel çekirdek kapasitesini aşmayın. Bizim denemedeki diğer ayarlar **4.096 MiB RAM, 64 GiB dinamik sanal disk, UEFI, TPM 2.0, Secure Boot ve I/O APIC açık** şeklindedir. [Oracle sistem ayarları](https://docs.oracle.com/en/virtualization/virtualbox/7.2/user/working-with-vms.html). Bu çözüm için ana bilgisayarın Hyper-V/VBS ayarları değiştirilmedi.

**Testin sınırı:** Deneme medyasında önceden eklenmiş WinPE `LabConfig` atlatma komutları vardı; bu kayıt onların çalıştığını veya atlatmasız bir kurulumun doğrulandığını göstermez. İşlemci karşılaştırmasında ISO değiştirilmedi. Tam kurulum, IoT edisyon geçişi, etkinleştirme ve uzun dönem kararlılık bu ön testle doğrulanmış sayılmaz. Buradaki 4 GB test ayarı, UMAY'ın deneysel 1 GB hedefinin gerçekleştiği anlamına gelmez.

Bu belirtiler tek başına ISO bozukluğu kanıtı değildir. Sorun sürerse konu açarken **Windows/VirtualBox sürümünü, VM işlemci/RAM/UEFI/TPM ayarlarını, tam hata metnini ve ISO SHA-256 karşılaştırma sonucunu** belirtin; günlük paylaşmadan önce kişisel dosya yollarını ve diğer özel bilgileri ayıklayın.

## Güncelleme desteği: 30 Eylül 2026 görünümü

| Taban | Resmî durumun katalog açısından anlamı |
| --- | --- |
| Windows 10 Home/Pro 1607 ve Pro 1909 | Destek dışı eski tabanlar; korunan Update altyapısı yeni güvenlik desteği sağlamaz. |
| Windows 10 Home/Pro 22H2 | Normal destek 14 Ekim 2025'te sona erdi; uygun cihazlarda ESU ayrı koşullarla devam edebilir. |
| Windows 11 Home 21H2 | Home/Pro desteği 10 Ekim 2023'te sona erdi. |
| Windows 11 Pro 22H2 | Home/Pro desteği 8 Ekim 2024'te sona erdi. |
| Windows 11 Pro 23H2 | Home/Pro desteği 11 Kasım 2025'te sona erdi. |
| Windows 11 Pro 24H2 | Home/Pro desteği 13 Ekim 2026'da sona eriyor; “uzun vadeli nihai güncel taban” değildir. |
| Windows 11 IoT Enterprise LTSC 2024 | Ayrı LTSC yaşam döngüsü; aylık bakım güncellemeleri ve 2034'e uzanan destek. |

Kaynaklar: [Windows 10 sürümleri](https://learn.microsoft.com/en-us/windows/release-health/release-information), [Windows 10 destek sonu](https://learn.microsoft.com/en-us/lifecycle/announcements/windows-10-end-of-support), [Windows 11 Home/Pro](https://learn.microsoft.com/tr-tr/lifecycle/products/windows-11-home-and-pro), [Windows 11 sürüm tablosu](https://learn.microsoft.com/en-us/windows/release-health/windows11-release-information). Destek tarihleri Microsoft'un ürün/kanal takvimidir; bir özelleştirilmiş ISO için sertifika veya destek garantisi değildir.

### Windows 10 ESU için 2027 ifadesi

Kontrol tarihinde Microsoft'un **güncel bireysel ESU sayfası 12 Ekim 2027** bitişini belirtmektedir. Bazı eski metinlerdeki 13 Ekim 2026 tarihini güncel bilgi gibi tekrarlamak yerine bu kayıt kullanılmıştır. Uygun 22H2 edisyonu, gerekli güncellemeler ve programa kayıt koşulları geçerlidir; yalnızca ISO indirmek ESU kaydı değildir. Kaynak: [Microsoft bireysel ESU](https://www.microsoft.com/en-US/windows/extended-security-updates).

Ticari kullanım için ESU ayrı bir programdır. Microsoft yaşam döngüsü tablosu, uygun ticari Windows 10 edisyonları için üçüncü yıl sonunu **10 Ekim 2028** olarak gösterir. Bu tarih bütün bireysel kullanıcıların koşulsuz hakkı gibi sunulmaz. Kaynak: [Microsoft ESU yaşam döngüsü SSS](https://learn.microsoft.com/en-us/lifecycle/faq/extended-security-updates).

Windows 10 ULUTÜRK henüz üretilmediğinden, özelleştirilmiş imaj üzerinde ESU'ya kayıt ve güncelleme kurulumu doğrulanmış değildir.

## KIZILELMA adının iki koldaki anlamı

İlk planda Windows 10 KIZILELMA temel günlük masaüstüne, Windows 11 KIZILELMA ise VM/test laboratuvarına yöneliktir. Bu fark gizlenmemiş, iki açıklama ayrı korunmuştur. Aile adı bir özellik eşitliği veya aynı kararlılık seviyesi sertifikası değildir.

Windows 11 bölümündeki son iki başlıkta geçen “Windows 10 ERTÜRK” ve “Windows 10 ULUTÜRK” yazım hataları, belirtilen Windows 11 tabanlarına uygun olarak **Windows 11 ERTÜRK / ULUTÜRK** biçiminde düzeltilmiştir.

## Oyun, mağaza ve güvenlik iddiaları

“Anti-cheat uyumu tam”, “hiçbir UWP yükü yok”, “en hafif”, “en kararlı” ve “bütün mimarileri eksiksiz yönetir” ifadeleri test raporu yerine kullanılmaz. Uygulama/oyun adı ve sürümü, kullanılan Windows güncelleme seviyesi, donanım ve test tarihi kaydedilmelidir. Rakip modlar hakkında sürüm bağımsız olumsuz genellemeler yerine kendi bileşen listemiz açıklanır.

Kaldırılan güvenlik bileşenleri her profilde açıkça gösterilir. Güncellemeyi kullanıcı denetimine almak ile destek dışı/güncellenmeyen sistemi güvenli ilan etmek farklı şeylerdir. Bu katalog hiçbir profili güvenlik sertifikalı ilan etmez.
