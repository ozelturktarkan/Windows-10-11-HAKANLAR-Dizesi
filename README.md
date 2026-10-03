# Windows 10/11 HAKANLAR Dizesi

**Her amaca tek bir ISO değil; kullanım amacına göre, neyin değiştiği açıkça belgelenmiş Windows profilleri.**

Windows 10/11 **HAKANLAR Dizesi**, sanal makine laboratuvarlarından düşük donanımlı masaüstlerine ve daha güçlü bilgisayarlara uzanan bir Windows özelleştirme ailesidir. “Dürüstçe kırpılmış” yaklaşımımız, yalnızca az RAM tüketmek değil; kaldırılanları, korunanları, geri eklenebilenleri ve test edilmemiş noktaları açıkça göstermektir.

Bu depo ailenin **tanıtım, seçim ve yayın kataloğudur**. Windows kurulum dosyalarını barındırmaz. Her yayımlanan profilin kendi kaynak deposu, değişiklik listesi, test raporu ve ISO doğrulama kaydı bulunur. HAKANLAR, Microsoft'un resmî bir ürün ailesi değildir.

> **Yayın durumu — 1 Ekim 2026:** Windows 10 yayınları aşağıdaki bağlantılarda. Windows 11 kaynak depoları açıldı: UMAY hazırlanıyor; diğer dört profilin XML, tema/kurulum ekleri ve ISO hashleri yayımlandı. Windows 11 büyük ISO bağlantıları ve kesin revizyon kurulum testleri bekleniyor.

## Ailenin mantığı

| Profil | Tasarım yönü | Proje hedefi olan bellek sınıfı |
| --- | --- | --- |
| **UMAY** | Sanal makine ve yazılım denemeleri; en agresif sadeleştirme | 1 GB+ |
| **KIZILELMA** | Çok düşük kaynak tüketimi; Windows 10'da temel masaüstü, Windows 11 taslağında VM/test | 2 GB+ |
| **ALP ER TUNGA** | Daha geniş Pro işlevleri; düşük/orta donanım sınıfı | 4 GB+ |
| **ERTÜRK** | Uygulama uyumluluğu ve kaynak kullanımı arasında denge | 8 GB+ |
| **ULUTÜRK** | Daha güçlü donanımda sınırlı müdahale ve geniş işlev kümesi | 16 GB+ |

Bu değerler **Microsoft'un asgari gereksinimleri değildir**. İş yükü, sürücüler, disk ve güvenlik ayarları sonucu değiştirir. VM satırlarında bellek, konuk işletim sistemine ayrılan RAM'dir; ana bilgisayarın ayrıca kaynağa ihtiyacı vardır. Windows 11 UMAY'ın 1 GB ve Windows 11 KIZILELMA'nın 2 GB hedefleri henüz doğrulanmamış, resmî bellek alt sınırlarının altında kalan deneylerdir. [Donanım notları](docs/TEKNIK-NOTLAR.md#bellek-hedefi).

## Windows 10 ailesi

| Profil | Seçilen taban | Mimari / ana yapı ailesi | Hedef donanım | Yayın durumu |
| --- | --- | --- | --- | --- |
| **UMAY** | Home, sürüm 1607 | x86 / 14393 | 1 GB+; VM/test | Yayımlandı; sınırlar aşağıda |
| **KIZILELMA** | Home, sürüm 1607 | x86 / 14393 | 2 GB+; HDD, SSD tercih edilir | Yayımlandı; sınırlar aşağıda |
| **ALP ER TUNGA** | Pro, sürüm 1607 | x64 / 14393 | 4 GB+; SSD | [ISO ve kaynaklar yayımlandı](https://github.com/ozelturktarkan/Windows-10-ALP-ER-TUNGA) |
| **ERTÜRK** | Pro, sürüm 1909 | x64 / 18363 | 8 GB+; SSD | [r2 ISO ve kaynakları yayımlandı](https://archive.org/details/windows-10-erturk) |
| **ULUTÜRK** | Pro, sürüm 22H2 | x64 / 19045 | 16 GB+; SSD | [r2 kaynakları yayımlandı](https://github.com/ozelturktarkan/Windows-10-ULUTURK); [ISO yüklendi; işleniyor](https://archive.org/details/windows-10-uluturk) |

Sürüm adları ve yapı aileleri farklı alanlardır; örneğin **1909 sürüm**, **18363 yapı ailesidir**. [Microsoft sürüm kaydı](https://learn.microsoft.com/en-us/windows/release-health/release-information).

### Windows 10 UMAY

**Sanal bilgisayarlar ve yazılım denemeleri için.** Home 1607 x86 tabanını çok agresif biçimde sadeleştirir. Günlük kullanım için güvenli veya uzun dönem kararlı olduğu iddia edilmez. Amaç, denemeler için küçük bir çalışma ortamı oluştururken bakım ve kurulum altyapısını gelişigüzel yok etmemektir.

Mevcut proje kaydında WMI, MSI, PowerShell, DISM/CBS/WinSxS ve Windows Update altyapısının korunduğu belirtilir. Otomatik güncellemeler için `NoAutoUpdate=1` kullanılır; çevrimiçi güncelleme davranışının kapsamlı testi tamamlanmış değildir. Her kaldırılan bileşenin sorunsuz geri eklenebileceği söylenmez.

**Bellek:** 1 GB+ hedefi için mevcut depoda VirtualBox, BIOS, 1 vCPU ve 1.024 MiB RAM ile kurulum kaydı bulunur. Bu, tüm yazılımlar ve hipervizörler için genel garanti değildir.

**[GitHub / kaynaklar ve testler](https://github.com/ozelturktarkan/Windows-10-UMAY)** · **[Windows 10 UMAY.iso indir](https://archive.org/download/windows-10-umay/Windows%2010%20UMAY.iso)** · [Releases](https://github.com/ozelturktarkan/Windows-10-UMAY/releases)

**Arşiv doğrulama düzeyi:** Alt depodaki kayda göre boyut, MD5, SHA-1 ve HTTP erişimi denetlendi. Archive kopyasının tamamı bu kayıtta yeniden indirilip SHA-256 hesaplanmadı. [Doğrulama kaydı](https://github.com/ozelturktarkan/Windows-10-UMAY/blob/main/reports/ARCHIVE-DOGRULAMA.json).

### Windows 10 KIZILELMA

**UMAY'ın daha kullanışlı, temel masaüstü odaklı kardeşi.** Home 1607 x86 tabanında, çok düşük donanımlı bilgisayarlar için sade bir masaüstü hedefler. Yerel arama, temel metin/görsel uygulamaları, medya oynatma ve yazdırma gibi gündelik işlevler UMAY'a göre daha fazla korunur.

**Donanım hedefi:** 2 GB+ RAM ve HDD; imkân varsa SSD. Bu bir kullanım hedefidir; gerçek 2 GB HDD bilgisayarda uzun dönem kararlılık testi tamamlanmış değildir. Son Genişlet revizyonunda kurulum testi tekrarlanmadı; önceki revizyondaki kurulum testleri ve son ISO içerik doğrulaması ayrı belgelenmiştir.

Mevcut KIZILELMA sürümünde Defender kaldırılmış, güvenlik duvarı korunmuştur; işlev testleri güvenlik sertifikası değildir.

Windows Update hizmeti başlangıçta kapalıdır; bakım altyapısı korunur ve masaüstündeki yönetim aracıyla hizmet açılıp kapatılabilir. Bu özellik, destek dışı Home 1607 tabanına yeni bir güvenlik desteği kazandırmaz.

**[GitHub / kaynaklar ve testler](https://github.com/ozelturktarkan/Windows-10-KIZILELMA)** · **[Windows 10 KIZILELMA.iso indir](https://archive.org/download/windows-10-kizilelma/Windows%2010%20KIZILELMA.iso)** · [Releases](https://github.com/ozelturktarkan/Windows-10-KIZILELMA/releases/tag/v1.0-genislet)

**Arşiv doğrulama düzeyi:** Mevcut raporda 2.645.475.328 baytın tamamının okunarak SHA-256, SHA-1 ve MD5 eşleşmesinin doğrulandığı kayıtlıdır. [Tam dosya doğrulaması](https://github.com/ozelturktarkan/Windows-10-KIZILELMA/blob/main/ISO-DOGRULAMA.json). Hash eşleşmesi güvenlik taraması değildir.

### Windows 10 ALP ER TUNGA — yayımlandı

**Pro işlevlerini daha fazla koruyan, eski x64 bilgisayarlar için profil.** Windows 10 Pro 1607 x64 (14393.0) tabanı; **4 GB+ RAM ve SSD** hedeflenir. Geçerli sürüm **r4 Mağazasız**dır.

Microsoft Store ve Store Purchase App kaldırıldı; **Edge Legacy, Fotoğraflar, Hesap Makinesi, Ses Kaydedici ve Paint korunur**. Kullanıcı bu beş uygulamanın test VM’sinde çalıştığını bildirdi. Firefox veya yeni Edge imaja gömülmedi. Edge Legacy’nin bütün güncel sitelerle uyumluluğu doğrulanmış değildir.

Cortana kapalı, yerel arama çalışır. Güvenlik duvarı, isteğe bağlı Hyper-V ve elle Windows güncelleme/bileşen yükleme altyapısı korunur. Otomatik güncellemeler Pro üzerinde ilkeyle kapatılır. Defender kaldırılmıştır; üçüncü taraf antivirüs gömülmez. Kaldırma listesi ve korunan işlevler alt depoda ayrıntılıdır.

**[GitHub / kaynaklar ve testler](https://github.com/ozelturktarkan/Windows-10-ALP-ER-TUNGA)** · [Kaynak paketi, imleç ve arka plan](https://github.com/ozelturktarkan/Windows-10-ALP-ER-TUNGA/releases/tag/v1.0-r4) · [Kullanıcı uygulama testi](https://github.com/ozelturktarkan/Windows-10-ALP-ER-TUNGA/blob/main/r4-Kullanici-Testi.json)

**[Windows 10 ALP ER TUNGA ISO indir](https://archive.org/download/windows-10-alp-er-tunga/Windows%2010%20ALP%20ER%20TUNGA.iso).** Yerel üretim kaydı: `Windows 10 ALP ER TUNGA.iso`, **3.623.372.800 bayt**. Son ISO SHA-256:

```text
fb47bb5ed1e12f4a4e1f9083b02de34b6118bab9ef7477f12946e5a1f2a36c41
```

[Sürüm ve hash kaydı](https://github.com/ozelturktarkan/Windows-10-ALP-ER-TUNGA/blob/main/SURUM.json). Alt deponun [Archive kaydına](https://github.com/ozelturktarkan/Windows-10-ALP-ER-TUNGA/blob/main/Archive-Dogrulama.json) göre boyut/SHA-1/MD5 eşleşti; tam Archive dosyasının yeniden SHA-256 hesabı yapılmış sayılmaz. Fiziksel donanım, Hyper-V çalıştırma, elle güncelleme ve uzun dönem kararlılık test edilmiş sayılmaz; 1607 Pro tabanına güncel güvenlik desteği kazandırılmaz.

### Windows 10 ERTÜRK — r2 yayımlandı

Windows 10 Pro 1909 x64, 18363.959; **8 GB+ RAM ve SSD** hedefi. Kurulum testi 4 GB RAM ile yapıldı. Store/Store Purchase App kaldırıldı; temel uygulamalar, yerel arama ve Edge Legacy korundu. Dört efektli profil, Türk bayrağı imleci ve ortak arka plan kullanılır. Ses için kullanıcı onayı ve VM ayarı/sorun giderici müdahalelerinin sınırı test raporundadır.

**[GitHub / kaynaklar ve testler](https://github.com/ozelturktarkan/Windows-10-ERTURK)** · [r2 kaynak paketi](https://github.com/ozelturktarkan/Windows-10-ERTURK/releases/tag/v1.0-r2). **[ERTÜRK ISO indir](https://archive.org/download/windows-10-erturk/Windows%2010%20ERT%C3%9CRK.iso)**. Archive boyut/SHA-1/MD5 eşleşti ve HTTP erişimi doğrulandı; tam Archive SHA-256 hesabı yapılmadı. [Denetim kaydı](https://github.com/ozelturktarkan/Windows-10-ERTURK/blob/main/Archive-Dogrulama.json).

1909 kaynak ISO'sunun boyut/SHA-1/MD5 değerleri Archive metaverisiyle, gömülü WIM üretim kaynağıyla eşleşti. **Resmî Microsoft hash referansı bulunamadığından Microsoft özgünlüğü bağımsız doğrulanmadı.** [Kaynak bağlantısı ve tam rapor](https://github.com/ozelturktarkan/Windows-10-ERTURK/blob/main/KAYNAK-ISOLAR.md).

### Windows 10 ULUTÜRK — r2 ISO yüklendi

Windows 10 Pro 22H2 x64, 19045.2965; **16 GB+ RAM ve SSD** hedefi. Kurulum testi 4 GB RAM / 1 vCPU ile yapıldı. Store ve temel uygulamalar korundu. MyDock 5.10.1, Türkçe dil dosyaları, otomatik gizlenen görev çubuğu ve dört efektli profil bulunur. Üçüncü taraf dock ikilileri GitHub paketinde yoktur; yeniden üretim için hash ile tanımlanan arşiv ayrıca gerekir.

**[GitHub / kaynaklar ve testler](https://github.com/ozelturktarkan/Windows-10-ULUTURK)** · [r2 kaynak ve Türkçe dil paketleri](https://github.com/ozelturktarkan/Windows-10-ULUTURK/releases/tag/v1.0-r2). **[ULUTÜRK ISO yüklendi](https://archive.org/details/windows-10-uluturk)**; proje sahibine göre Archive işlemesi sürüyor. Dosya listesinde 5.161.299.968 baytlık ISO görünüyor; boyut/SHA-1/MD5 son r2 kaydıyla eşleşti. Doğrudan indirme erişimi ve tam dosya SHA-256 hesabı ayrıca doğrulanmadı. [Durum kaydı](https://github.com/ozelturktarkan/Windows-10-ULUTURK/blob/main/Archive-Durumu.json). r1 kurulumu denetlendi; r2 yalnız üç dil dosyasını değiştirir ve ikinci kurulum yapılmadı. Güvenlik tercihleri ve test sınırları alt depoda açıklanır; güncel güvenlik/ESU garantisi verilmez.

**22H2 x64v1 kaynak ISO'sunun SHA-256 değeri Microsoft'un resmî Türkçe 64-bit tablosuyla eşleşti.** Verilen Archive 22H2 sayfasındaki farklı ISO, birebir üretim kaynağı olarak sunulmaz. [Hashler, indirme referansları ve WIM bağlantısı](https://github.com/ozelturktarkan/Windows-10-ULUTURK/blob/main/KAYNAK-ISOLAR.md).

## Windows 11 ailesi

**1 Ekim 2026:** Beş profilin kaynak ve hashleri yayımlandı. UMAY 21H2 Home r2, KIZILELMA 22H2 Home, ALP ER TUNGA 23H2 Pro, ERTÜRK ve ULUTÜRK 25H2 Pro tabanındadır. Beş ISO'nun yerel üretim doğrulaması mevcut; bu kesin revizyonların kurulum testleri ve büyük ISO indirme bağlantıları bekleniyor.

| Profil | Taban / yapı | Ana hedefi | Kaynaklar ve durum |
| --- | --- | --- | --- |
| **UMAY** | Home 21H2 x64 / 22000.194 | Sanal Bilgisayarlar (Çalışması için sanal makinaya en az 3çekirdek + 4gb bellek verin!) | [Windows-11-UMAY](https://github.com/ozelturktarkan/Windows-11-UMAY) — r2 kaynak ve hashleri yayımlandı; kurulum testi ve ISO bağlantısı bekleniyor |
| **KIZILELMA** | Home 22H2 x64 / 22621.525 | Çok Eski Donanımlı Bilgisayarın ilk Denemesi gereken sürüm | [Windows-11-KIZILELMA](https://github.com/ozelturktarkan/Windows-11-KIZILELMA) — r2 kaynak ve hashleri yayımlandı; ISO bağlantısı bekleniyor |
| **ALP ER TUNGA** | Pro 23H2 x64 / 22631.2428 | Eski 2. ve 11. nesil i3-i5-i7 ve eşdeğer amd işlemcilerin denemesi gereken sürüm | [Windows-11-ALP-ER-TUNGA](https://github.com/ozelturktarkan/Windows-11-ALP-ER-TUNGA) — r1 kaynak ve hashleri yayımlandı; ISO bağlantısı bekleniyor |
| **ERTÜRK** | Pro 25H2 x64 / 26200.6584 | 12. nesil ve üzeri işlemcilerin denemesi gereken sürüm | [Windows-11-ERTURK](https://github.com/ozelturktarkan/Windows-11-ERTURK) — r1 kaynak ve hashleri yayımlandı; ISO bağlantısı bekleniyor |
| **ULUTÜRK** | Pro 25H2 x64 / 26200.6584 | ERTÜRK sürümünün temel olarak aynısı, artı olarak görsellik iyileştirmesi ve mac görünümü eklendi | [Windows-11-ULUTURK](https://github.com/ozelturktarkan/Windows-11-ULUTURK) — r1 kaynak ve hashleri yayımlandı; ISO bağlantısı bekleniyor |

RAM sayıları proje hedefidir; doğrulanmış alt sınır değildir. UMAY'ın önceki IoT/LTSC planı bırakıldı. KIZILELMA r2 kendi duvar kâğıdı ve bayrak imlecini içerir; ALP ER TUNGA/ERTÜRK/ULUTÜRK ortak arka planı kullanır. ULUTÜRK ayrıca Türkçe MyDock ve otomatik gizlenen görev çubuğu içerir.

Beş profilde Defender Antivirus, SmartScreen, Store ve Store Purchase App kaldırılmıştır. TPM/Secure Boot/RAM temiz kurulum ekleri kaynak depolarındadır. UMAY r2 ayrıca 21 tüketici uygulamasını kaldırır ve dört efektli ilk oturum profilini uygular; özel arka plan, imleç ve dock içermez. Diğer dört profilde tema ekleri vardır; dört efekt profilinin uygulandığı iddia edilmez. Ölçülmüş hız artışı henüz yoktur. Pro sanallaştırma yükleri korunur; bu, çalışma testi anlamına gelmez.

Önceki LTSC denemesinde 3 vCPU ile kurulum ilerlemiş, sonrasında siyah ekran yeniden görülmüştür. Kesin VM çözümü olarak sunulmaz. [Güncel sanal makine yönergesi](https://github.com/ozelturktarkan/Windows-11-KIZILELMA/blob/main/docs/SANAL-MAKINE.md) ağ kablosu, optik medya ve katılımsız kurulum ayrımını açıklar.

## Windows 11 kaynak paketleri

Kaynak ZIP'leri Windows ISO'su değildir. XML, kurulum ekleri, ayrı indirilebilir arka plan/imleç ve hash kayıtları alt depolardadır. ULUTÜRK'ün dock EXE/DLL dosyaları GitHub'da yoktur; Türkçe dil dosyaları ve gereken yükün hash manifesti paylaşılır. Son ISO test ve indirme durumunu her alt deponun README'sinden kontrol edin.

## Dürüstçe kırpma ilkeleri

**Neyi kaldırdığımızı açıklıyoruz.** Bir bileşeni devre dışı bırakmak, paketini kaldırmak ve bütün dosyalarını silmek farklı işlemlerdir. Değişiklik listesinde bunlar birbirine karıştırılmaz.

**Geri eklemeyi vaat değil test konusu yapıyoruz.** Güncelleme, dil ve isteğe bağlı bileşen altyapısını korumak hedeftir; başarılı senaryolar, kaynak sürümü ve bilinen sınırlarla birlikte yayımlanır. Güncellemelerin kullanıcı denetiminde olması, güvenlik güncellemelerinin gereksiz olduğu anlamına gelmez.

**Ölçmediğimizi sonuç diye yazmıyoruz.** Açılış, boşta RAM, yük altındaki davranış, uygulama uyumluluğu ve uzun dönem kararlılık ayrı testlerdir. Başka Windows modlarının bütün sürümleri hakkında genelleyici iddialar yerine kendi kaldırma listemizi ve sonuçlarımızı gösteriyoruz.

## İndirmeden önce

Yayımlanan ISO'nun SHA-256 değerini ilgili alt depodaki kayıtla karşılaştırın. Kaynak Microsoft ISO'sunun hash'i, özelleştirilmiş son ISO'nun hash'i ve arşivden indirilen kopyanın doğrulaması ayrı kayıtlardır. GitHub'ın **Source code ZIP/TAR** dosyaları Windows kurulum ISO'su değildir.

Bu katalog hazırlanırken Windows ISO'ları yeniden indirilmedi veya kurulum testine alınmadı; mevcut alt depo kayıtlarının kapsamı aktarıldı. Windows 10 UMAY/KIZILELMA/ALP ER TUNGA'nın güvenlik bileşenleri ve destek sınırları kendi README dosyalarında açıklanır.

[Makine tarafından okunabilir katalog](SURUMLER.json) · [Teknik notlar](docs/TEKNIK-NOTLAR.md) · [Yayın/doğrulama politikası](docs/YAYIN-POLITIKASI.md) · [Kaynaklar](docs/KAYNAKLAR.md) · [Katalog yayın notu taslağı](RELEASE-NOTES.md)
