# Kaynaklar

**Erişim/kontrol tarihi: 30 Eylül 2026.** Teknik ürün iddiaları için Microsoft ve Intel'in kendi belgeleri kullanılmıştır. Proje durumu ve test sonuçları alt depolardaki yayın kayıtlarına dayanır; bu katalog hazırlanırken testler yeniden koşturulmamıştır.

| Kaynak | Kullanım |
| --- | --- |
| [Windows 10 sürüm bilgileri](https://learn.microsoft.com/en-us/windows/release-health/release-information) | Sürüm/yapı ayrımı, eski sürümler ve 22H2 |
| [Windows 11 sürüm bilgileri](https://learn.microsoft.com/en-us/windows/release-health/windows11-release-information) | Yapı aileleri, 24H2 ve LTSC destek ayrımı |
| [Windows 11 Home ve Pro yaşam döngüsü](https://learn.microsoft.com/tr-tr/lifecycle/products/windows-11-home-and-pro) | Home/Pro için sürüm bazında destek sonu |
| [Windows 10 destek sonu](https://learn.microsoft.com/en-us/lifecycle/announcements/windows-10-end-of-support) | Normal desteğin 14 Ekim 2025'te sona ermesi |
| [Windows 10 bireysel ESU](https://www.microsoft.com/en-US/windows/extended-security-updates) | Kontrol tarihinde 12 Ekim 2027 bitişi ve kayıt koşulları |
| [Microsoft ESU yaşam döngüsü SSS](https://learn.microsoft.com/en-us/lifecycle/faq/extended-security-updates) | Ticari ESU yılları ve 2028 sınırı |
| [Windows 11 IoT Enterprise LTSC 2024](https://learn.microsoft.com/en-us/windows/iot/iot-enterprise/whats-new/windows-11-iot-enterprise-ltsc-2024) | 24H2 tabanı, aylık bakım, özel amaçlı kullanım |
| [Windows IoT asgari gereksinimleri](https://learn.microsoft.com/en-us/windows/iot/iot-enterprise/Hardware/System_Requirements) | IoT LTSC tercih edilen 4 GB / isteğe bağlı 2 GB RAM |
| [Windows 11 gereksinimleri](https://www.microsoft.com/en-us/windows/windows-11-specifications) | Genel 4 GB RAM ve diğer donanım koşulları |
| [Intel hibrit mimari ve Windows](https://www.intel.com/content/www/us/en/support/articles/000088749/processors/intel-core-processors.html) | Windows 10/11 ve Thread Director ayrımı |
| [Windows 10 UMAY README](https://github.com/ozelturktarkan/Windows-10-UMAY/blob/main/README.md) | Yayın, kaldırma kapsamı, 1.024 MiB VM ve doğrulama sınırları |
| [Windows 10 KIZILELMA README](https://github.com/ozelturktarkan/Windows-10-KIZILELMA/blob/main/README.md) | Temel masaüstü hedefi, revizyon/test ayrımı, tam dosya doğrulama kaydı |
| [Windows 10 ALP ER TUNGA sürümü](https://github.com/ozelturktarkan/Windows-10-ALP-ER-TUNGA/blob/main/SURUM.json) | r4 kaynak yayını, ISO boyutu/hashleri, henüz olmayan indirme bağlantısı |
| [ALP ER TUNGA kullanıcı testi](https://github.com/ozelturktarkan/Windows-10-ALP-ER-TUNGA/blob/main/r4-Kullanici-Testi.json) | Beş temel uygulama için kullanıcı bildirimi ve sınırları |

## Katalog oluşturulurken okunan README dosyalarının Git blob kimlikleri

- Windows 10 UMAY README: `4813a32da549e36ad7c452ff3ade3b4a2c3bf065`
- Windows 10 KIZILELMA README: `28d0a11cec97c8909c0d6f594c9c29ede551f212`

ALP ER TUNGA `SURUM.json` Git blob kimliği: `86beff116a0352ccb5ea6c56e0f595522f95baf3`; kullanıcı testi: `34c441452e9f6ecde144baf258e78fa5c4ba2c43`.

Bunlar kaynak dosyalarının Git kimlikleridir; ISO hash'i veya bağımsız güvenlik sertifikası değildir. Alt depolar daha sonra güncellenebilir.

## Yayımlama yardımcısının API kaynakları

[GitHub CLI API](https://cli.github.com/manual/gh_api) · [GitHub CLI oturum açma](https://cli.github.com/manual/gh_auth_login) · [Depo oluşturma API'si](https://docs.github.com/en/rest/repos/repos#create-a-repository-for-the-authenticated-user) · [Git ağaçları](https://docs.github.com/en/rest/git/trees) · [Git commit'leri](https://docs.github.com/en/rest/git/commits) · [Git referansları](https://docs.github.com/en/rest/git/refs)
