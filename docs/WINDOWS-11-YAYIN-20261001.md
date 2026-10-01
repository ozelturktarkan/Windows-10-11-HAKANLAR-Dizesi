## Windows 11 ailesi

**1 Ekim 2026:** Beş profilin kaynak depoları açıldı. UMAY 21H2 Home hazırlık aşamasında; KIZILELMA 22H2 Home, ALP ER TUNGA 23H2 Pro, ERTÜRK ve ULUTÜRK 25H2 Pro tabanındadır. Dört ISO'nun yerel üretim doğrulaması mevcut; bu kesin revizyonların kurulum testleri ve büyük ISO indirme bağlantıları bekleniyor.

| Profil | Taban / yapı | RAM hedefi | Kaynaklar ve durum |
| --- | --- | --- | --- |
| **UMAY** | Home 21H2 x64 / 22000.194 | 1 GB+ | [Windows-11-UMAY](https://github.com/ozelturktarkan/Windows-11-UMAY) — Hazırlanıyor |
| **KIZILELMA** | Home 22H2 x64 / 22621.525 | 2 GB+ | [Windows-11-KIZILELMA](https://github.com/ozelturktarkan/Windows-11-KIZILELMA) — r2 kaynak ve hashleri yayımlandı; ISO bağlantısı bekleniyor |
| **ALP ER TUNGA** | Pro 23H2 x64 / 22631.2428 | 4 GB+ | [Windows-11-ALP-ER-TUNGA](https://github.com/ozelturktarkan/Windows-11-ALP-ER-TUNGA) — r1 kaynak ve hashleri yayımlandı; ISO bağlantısı bekleniyor |
| **ERTÜRK** | Pro 25H2 x64 / 26200.6584 | 8 GB+ | [Windows-11-ERTURK](https://github.com/ozelturktarkan/Windows-11-ERTURK) — r1 kaynak ve hashleri yayımlandı; ISO bağlantısı bekleniyor |
| **ULUTÜRK** | Pro 25H2 x64 / 26200.6584 | 16 GB+ | [Windows-11-ULUTURK](https://github.com/ozelturktarkan/Windows-11-ULUTURK) — r1 kaynak ve hashleri yayımlandı; ISO bağlantısı bekleniyor |

RAM sayıları proje hedefidir; doğrulanmış alt sınır değildir. UMAY'ın önceki IoT/LTSC planı bırakıldı. KIZILELMA r2 kendi duvar kâğıdı ve bayrak imlecini içerir; ALP ER TUNGA/ERTÜRK/ULUTÜRK ortak arka planı kullanır. ULUTÜRK ayrıca Türkçe MyDock ve otomatik gizlenen görev çubuğu içerir.

Üretilen dört profilde Defender Antivirus, SmartScreen, Store ve Store Purchase App kaldırılmıştır. Tema ve TPM/Secure Boot/RAM temiz kurulum ekleri kaynak depolarındadır. Geniş hizmet budaması, dört efekt profilinin uygulandığı veya ölçülmüş hız artışı iddia edilmez. Pro sanallaştırma yükleri korunur; bu, çalışma testi anlamına gelmez.

Önceki LTSC denemesinde 3 vCPU ile kurulum ilerlemiş, sonrasında siyah ekran yeniden görülmüştür. Kesin VM çözümü olarak sunulmaz. [Güncel sanal makine yönergesi](https://github.com/ozelturktarkan/Windows-11-KIZILELMA/blob/main/docs/SANAL-MAKINE.md) ağ kablosu, optik medya ve katılımsız kurulum ayrımını açıklar.

## Windows 11 kaynak paketleri

Kaynak ZIP'leri Windows ISO'su değildir. XML, kurulum ekleri, ayrı indirilebilir arka plan/imleç ve hash kayıtları alt depolardadır. ULUTÜRK'ün dock EXE/DLL dosyaları GitHub'da yoktur; Türkçe dil dosyaları ve gereken yükün hash manifesti paylaşılır. Son ISO test ve indirme durumunu her alt deponun README'sinden kontrol edin.

