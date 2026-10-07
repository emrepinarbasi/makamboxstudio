# MakamBox Studio 2.10.9

MakamBox Studio, Türk makam müziği kayıtlarında klasik MakamBox perde analizini koruyan; yönsel perde, kalış, glissando ve makamsal transkripsiyon incelemelerini aynı masaüstü uygulamasında birleştiren akademik araştırma yazılımıdır.

> English summary: MakamBox Studio is a GPL-3.0-or-later desktop application for classical MakamBox-compatible pitch histograms, directional pitch-event analysis, dwell/glissando measurements and Turkish-makam transcription.

## İndirme

GitHub Releases bölümündeki şu dosyalar son kullanıcı içindir:

| Dosya | Kullanım |
|---|---|
| `MakamBox-Studio-2.10.9-Windows-x64-Setup.exe` | Windows 10/11 x64 için kullanıcı hesabına kurulum |
| `MakamBox-Studio-2.10.9-Windows-x64-Portable.zip` | Kurulum yapmadan taşınabilir kullanım |
| `MakamBox-Studio-2.10.9-macOS-Apple-Silicon-arm64-ADHOC-TEST.dmg` | macOS 13.5+ Apple Silicon (arm64) için yerel test paketi |
| `MakamBox-Studio-2.10.9-macOS-Intel-x86_64-ADHOC-TEST.dmg` | macOS 13.5+ Intel (x86_64) için yerel test paketi |
| `MakamBox-Studio-2.10.9-SHA256SUMS.txt` | İndirilen dosyaların bütünlük doğrulaması |
| `MakamBox-Studio-2.10.9-Source.tar.gz` | Bu sürümün kaynak kodu ve derleme tarifleri |
| `MakamBox-Studio-2.10.9-SBOM.spdx.json` | SPDX yazılım bileşen dökümü |

[2.10.9 sürüm sayfası](../../releases/tag/v2.10.9)

## 2.10.9 güncellemesinde öne çıkanlar

- Akademik Perde Editörü'ndeki nota gövdeleri, sürekli F0 eğrisini koruyan modern mavi/teal organik görünüme geçirildi.
- Tam-ses sınırlarında `+8 Hc`, aynı frekanstaki üst perdenin `−1 Hc` bemolü olarak yazılır. Örneğin `La +8 Hc`, `Si −1 Hc` olarak adlandırılır ve LilyPond'da `bfc` karşılığını kullanır.
- Bu enharmonik dönüşüm yalnız perde adlandırmasını ve notasyonu değiştirir; ölçülen frekans, C, Hc ve sapma değerleri aynen korunur.
- PDF raporundaki hedef perde olayları dinamik olarak sayfalanır; son olay dâhil bütün olaylar eksiksiz dışa aktarılır.
- Melodyne MIDI verisi yalnız olay zamanı ve bölütleme denetiminde kullanılır; MakamBox Studio'nun sürekli F0, C veya Hc ölçümü yerine geçirilmez.
- Windows 10/11 için kurulum ve portable paketler; macOS için birbirinden bağımsız Apple Silicon ve Intel paketleri hazırlanmıştır.

2.10.8 ile üretilmiş raporlar geriye dönük değiştirilmez. Yeni sayfalama ve enharmonik yazımı kullanmak için kaydı 2.10.9 ile yeniden analiz edip raporu yeniden dışa aktarın. Ayrıntılar [güncelleme kılavuzunda](UPDATE_2.10.9.md) ve [sürüm notlarında](RELEASE_NOTES_2.10.9.md) yer alır.

## Sistem gereksinimleri

- Windows 10 22H2 veya Windows 11, 64 bit x86-64
- **macOS 13.5 veya üzeri** çalıştıran Apple Silicon (arm64) ya da Intel (x86_64) Mac; işlemciye uygun DMG kullanılmalıdır
- En az 4 GB RAM; uzun kayıtlar ve Large model için 8 GB veya üzeri önerilir
- Ses analizi için WAV, AIFF, AU veya MP3 dosyası
- Mikrofonla kayıt için Windows mikrofon izni
- Yapay zekâ modelini kullanmak isteyenlerde model boyutuna göre yaklaşık 210 MB, 620 MB veya 2,74 GB boş alan
- MuScriptor CPU yardımcısı için SSE4.2, AVX ve F16C destekli x64 işlemci; bu şart sağlanmıyorsa yerleşik F0 transkripsiyonunu seçin

Java 21, Node.js, LilyPond-WASM ve Windows MuScriptor yardımcısı pakete dahildir. Bilgisayara ayrıca Java veya Node kurmak gerekmez.

Windows ARM64 cihazlarında paket yerel ARM uygulaması değildir; Windows 11'in x64 öykünmesi üzerinden çalışabilir.

## macOS kurulumu

1. M serisi Mac'te `MakamBox-Studio-2.10.9-macOS-Apple-Silicon-arm64-ADHOC-TEST.dmg`, Intel Mac'te `MakamBox-Studio-2.10.9-macOS-Intel-x86_64-ADHOC-TEST.dmg` dosyasını açın.
2. **MakamBox Studio.app** uygulamasını Uygulamalar klasörüne sürükleyin.
3. Uygulamayı Uygulamalar klasöründen başlatın.
4. **MakamBox Studio > Hakkında** bölümünde sürümün `2.10.9` olduğunu doğrulayın.

Java, Node.js ve LilyPond-WASM macOS uygulamasına dahildir. Genel yayın dosyası Developer ID ile hardened-runtime imzalıdır; uygulama ve DMG Apple tarafından noterlenip biletleri pakete zımbalanır. SHA-256 değerini yayın dosyasıyla karşılaştırın.

Kimlik bilgisi olmadan yerelde üretilen `ADHOC-TEST` son ekli Apple Silicon ve Intel DMG'leri yalnız geliştirici doğrulaması içindir. Gatekeeper tarafından engellenebilir; genel yayın veya son kullanıcı kurulumu için kullanılmamalıdır.

## Windows kurulumu

### Kurucu

1. `MakamBox-Studio-2.10.9-Windows-x64-Setup.exe` dosyasını indirin.
2. Dosyanın SHA-256 değerini aşağıdaki yöntemle doğrulayın.
3. Kurucuyu çalıştırın. Uygulama yönetici yetkisi istemeden `%LOCALAPPDATA%\Programs\MakamBox Studio` konumuna kurulur.
4. Başlat menüsündeki **MakamBox Studio** kısayolunu açın.
5. **Yardım > Hakkında** bölümünde sürümün `2.10.9` olduğunu doğrulayın.

Kurucu eski MakamBox Studio uygulama klasörünü temizleyerek 2.10.9'u yerleştirir. Kişisel modeller ve tercihler uygulama klasörünün dışında tutulur.

### Taşınabilir paket

1. Portable ZIP'i Türkçe karakter içerebilen normal bir kullanıcı klasörüne çıkarın.
2. Klasör yapısını bozmadan `MakamBox Studio.exe` dosyasını çalıştırın.
3. `app`, `runtime` ve `resources` klasörlerini EXE'nin yanında bırakın.

Uygulamayı doğrudan ZIP içinden çalıştırmayın. Çıkarılmış klasör USB belleğe taşınabilir; indirilen MuScriptor modelleri ise varsayılan olarak Windows kullanıcı profilindeki MakamBox Studio model klasöründe saklanır.

### Kaldırma

Uygulamayı kapatın; Başlat menüsündeki kısayolu ve `%LOCALAPPDATA%\Programs\MakamBox Studio` klasörünü silin. İndirilen modelleri de kaldırmak isterseniz `%LOCALAPPDATA%\MakamBox Studio\models` klasörünü ayrıca silin.

### SmartScreen ve imza

2.10.9 Windows ikilileri Authenticode sertifikasıyla imzalanmamıştır. Bu nedenle Windows SmartScreen “Windows bilgisayarınızı korudu” veya “Bilinmeyen yayıncı” uyarısı gösterebilir. Bu uyarı işletim sistemi uyumsuzluğu anlamına gelmez. Uygulamaya Windows 10 ve Windows 11 için Microsoft'un ortak `supportedOS` kimliği gömülüdür; “Windows 10 veya 11 olmalı” biçimindeki eski metin karşılaştırması kullanılmaz.

Bir yayını herkese açık dağıtırken en temiz çözüm EV/OV kod imzalama sertifikasıyla hem kurucuyu hem başlatıcıyı imzalamaktır.

## SHA-256 doğrulama

PowerShell'de:

```powershell
Get-FileHash .\MakamBox-Studio-2.10.9-Windows-x64-Setup.exe -Algorithm SHA256
Get-FileHash .\MakamBox-Studio-2.10.9-Windows-x64-Portable.zip -Algorithm SHA256
Get-Content .\MakamBox-Studio-2.10.9-SHA256SUMS.txt
```

macOS Terminal'de:

```sh
shasum -a 256 MakamBox-Studio-2.10.9-macOS-Apple-Silicon-arm64-ADHOC-TEST.dmg
shasum -a 256 MakamBox-Studio-2.10.9-macOS-Intel-x86_64-ADHOC-TEST.dmg
```

Hesaplanan değer ile `SHA256SUMS` dosyasındaki değer aynı olmalıdır.

## Hızlı başlangıç

1. **Ses aç…** ile kaydı yükleyin veya **Kaydet** ile mikrofon kaydı oluşturun.
2. Makamı, incelenecek perdeyi ve gerekiyorsa karar frekansını belirleyin.
3. **Analiz et** düğmesine basın; ilerleme yüzdesini bekleyin.
4. Akademik Perde Editörü, İnici–çıkıcı analiz, Perde olayları, Kalışlar ve Glissando analizi sekmelerini inceleyin.
5. PDF, PNG veya CSV çıktısını alın.
6. Makamsal Transkripsiyon sekmesinde ritimli/serbest yapıyı ve sınır modelini seçip **Transkripsiyon et** düğmesine basın; LilyPond, MIDI veya PDF çıktısı üretin.

Space tuşu çal/duraklat işlevindedir. Grafiklerde sıkıştırma hareketi yatay yakınlaştırma; iki parmak kaydırma zaman ve perde gezinmesidir.

## Başlıca özellikler

### Klasik MakamBox uyumluluğu

- MakamBox v1.0 ile uyumlu 40 ms YIN perde izi
- 1/3 Holderian koma histogramı
- L1 makam şablonu eşleştirmesi ve histogramdan karar perdesi
- İki kayıt, makam şablonu ve Arel–Ezgi–Uzdilek dâhil akort sistemi karşılaştırmaları
- C ve Hc birimleri; PDF/PNG/CSV dışa aktarımı

### Akademik perde ve olay analizi

- Seçilen makamın perde cetveli ve zaman eksenli bütün güvenilir nota blokları
- YIN izindeki geçici yarım/üçte-bir frekans yanılgılarını harmonik kanıt ve zamansal süreklilikle düzelten perde izi
- Perde sınırındaki çok kısa A–B–A salınımlarını azaltan kararlı olay bölütleme
- Gerçek Hz/C/Hc verisini değiştirmeden, pes kayıtların kalış bölgesini Yegâh–Nevâ arasında gösteren otomatik görsel oktav yerleşimi
- Gerçek F0 eğrisini izleyen, enerji/güvene göre gövde kalınlığı ve saydamlığı değişen modern mavi organik nota blokları
- Hedef perdenin turkuaz, seçili olayın belirgin çerçeveli, çalınan bloğun koyu/kalın gösterimi
- Seçilen perde için bağımsız alt/üst Hc toleransı
- Giriş, çıkış ve net yön bakımından inici, çıkıcı ve yatay/karma sınıflandırma
- Her basış, kalış, ortalama, süre, frekans, C ve Hc sapması
- Oynatma sırasında koyu/kalın etkin blok, otomatik yatay takip ve ayrıntı denetçisi
- Uzun seslerde vibrato işareti
- Grafikten karar frekansı seçimi

### Glissando

- Perdeye giriş, perdeden çıkış ve perdeden geçiş glissandoları
- Tiz yöne düz/çıkıcı ve pest yöne ters/inici izleme
- Süre, genişlik, yön, hız, tek yönlülük ve güven puanı
- Ani nota sıçraması ile hızlı/yavaş vibratoyu ayırmaya yönelik süzme
- Grafik ve raporda beyaz halolu kalın koyu-kırmızı gösterim

### Ses ve arayüz

- WAV, AIFF, AU ve MP3 açma
- Canlı dalga biçimli mikrofon kayıt penceresi; “Bu kaydı kullan” veya “Bu kaydı sil”
- Başlat, duraklat, durdur, saniyeye gitme ve %50–%125 perde-korumalı hız
- Dalga biçimi, melodik spektrogram, perde izi ve olay katmanları
- Yerel Windows dosya seçici, analiz yüzdesi ve uygulama içi kısayol menüsü
- Bütün çalışma sekmelerinde ortak **sol menüyü gizle/göster** denetimi
- Dar pencere yüksekliğinde sol menüyü dikey kaydırarak en alttaki denetimlere erişim

### Makamsal transkripsiyon ve LilyPond

- Otomatik, ritimli veya ritimsiz/serbest yapı
- Yerleşik F0 motoru; isteğe bağlı MuScriptor Small/Medium/Large sınır modelleri
- Gerçek frekans ile makam perdesinin birlikte eşlenmesi
- Yalnız resmî `turkish-makam.ly` tanımlarına dayanan 1, 4, 5 ve 8 Hc değiştirme işaretleri
- Tam-ses sınırlarında alt notanın +8 Hc yazımını aynı frekanstaki üst notanın −1 Hc bemolüyle gösteren enharmonik yazım (ör. La +8 Hc = Si −1 Hc)
- Makam donanımı, farklı nota uzunlukları, serbest yapıda ölçüsüz `cadenza`, anlamlı son sessizlikte puandorg
- Mikrotonal pitch-bend MIDI, LilyPond kaynağı ve çok sayfalı PDF
- Çalınan nota başını kırmızı gösteren, porte ve sayfa değiştiren yatay nota takibi

MuScriptor model ağırlıkları uygulamaya gömülmez. Kullanıcı seçtiğinde HTTPS ile indirilir, boyut ve SHA-256 doğrulanır. Ağırlıklar CC BY-NC 4.0 kapsamındadır; yalnız akademik ve ticari olmayan kullanım içindir. Kullanıcı analiz ettiği kayıt üzerinde gerekli haklara sahip olmalıdır.

## Proje ve katkı bilgisi

Bilge Miraç ATICI tarafından, Barış BOZKURT danışmanlığında geliştirilen GPL lisanslı MakamBox projesi temel alınmıştır. NeuralNote v2.0.0 ile uyumlu transkripsiyon bileşenleri ve LilyPond.org tarafından sunulan GNU LilyPond araçları eklenerek MakamBox Studio, Prof. Dr. Emre PINARBAŞI tarafından geliştirilmiştir. Uygulamanın akademik kullanım deneyimleri ve işlevsel değerlendirmeleri Arş. Gör. Dr. Naci PARLAR tarafından yürütülmektedir. 2026.

Ayrıntılı atıf, kaynak ve lisans bilgileri [AUTHORS.md](AUTHORS.md), [SOURCES.md](SOURCES.md) ve [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md) dosyalarındadır.

## Veri ve ağ kullanımı

Ses çözümleme, perde tespiti, raporlama ve LilyPond derleme yerel bilgisayarda yapılır. Uygulama ses dosyasını bir sunucuya göndermez. Ağ yalnız kullanıcı bir MuScriptor modelini ilk kez indirdiğinde kullanılır.

## Yöntem ve akademik sınırlar

Klasik perde analizi, MakamBox v1.0 yöntemini ayrı bir uyumluluk hattında çalıştırır. İnici–çıkıcı olay, kalış ve glissando analizleri bu klasik sonucu değiştirmeyen yeni modüllerdir. Otomatik sınıflandırmalar uzman kararını destekler; onun yerine geçmez. Karar perdesi, hedef toleransı, perde kimliği ve glissando eşikleri uzman tarafından doğrulanmalıdır.

Ayrıntılar:

- [Mimari](docs/ARCHITECTURE.md)
- [Türkçe kullanım kılavuzu](docs/USER_GUIDE_TR.md)
- [Rapor okuma kılavuzu](docs/REPORT_GUIDE_TR.md)
- [Uşşak Taksim I 2.10.8 gerçek kayıt doğrulaması](docs/VALIDATION_USSAK_2.10.8.md)
- [Tony/pYIN bağımsız karşılaştırma protokolü](docs/TONY_CONTROL_PROTOCOL_TR.md)
- [Melodyne olay-zamanı ve gerçek perde eğrisi kontrol protokolü](docs/MELODYNE_CONTROL_PROTOCOL_TR.md)
- [Windows kurulumu ve sorun giderme](docs/WINDOWS.md)
- [Kaynak koddan derleme](docs/BUILDING.md)
- [Yayın hazırlama](docs/RELEASING.md)
- [Kaynak ve sürüm kaydı](SOURCES.md)
- [Değişiklik günlüğü](CHANGELOG.md)

## Kaynak koddan derleme

### macOS

Gerekenler: JDK 21, Node.js, Xcode komut satırı araçları ve isteğe bağlı CMake/Ninja.

```sh
MACOS_TARGET_ARCH=arm64 ./build-muscriptor-helper.sh
MACOS_TARGET_ARCH=arm64 ./build-macos.sh

# Intel JDK 21'in gerçek x86_64 jpackage yolunu verin:
MACOS_TARGET_ARCH=x86_64 ./build-muscriptor-helper.sh
MACOS_TARGET_ARCH=x86_64 JPACKAGE_BIN=/intel-jdk-21/Contents/Home/bin/jpackage ./build-macos.sh
```

### Windows 10/11 paketini macOS üzerinde üretme

```sh
./build-windows-cross.sh
```

Betik şunları yapar:

- Zig, Temurin JRE ve Windows Node arşivlerini sabit SHA-256 ile doğrular.
- Java ana/test sınıflarını derler ve regresyon testlerini çalıştırır.
- CPU tabanlı `muscriptor-helper.exe` dosyasını x64 Windows için çapraz derler.
- Node ve LilyPond-WASM kaynaklarını paketler.
- Kurucu EXE, portable ZIP, kaynak arşivi, SPDX SBOM ve SHA-256 dosyası üretir.

Çıktılar `outputs/MakamBox-Studio-2.10.9-GitHub-Release/` klasöründedir.

## Test durumu ve yayın kapısı

Kaynak analiz/test paketi 34 regresyon testi içerir. Çapraz derleme PE32+ x64 yapısını, paket bütünlüğünü ve bağımlılıkların varlığını doğrular. Çapraz derleme tek başına gerçek Windows davranışını kanıtlamaz. Kamuya açık sürümden önce temiz Windows 10 22H2 ve Windows 11 x64 makinelerinde şu denemeler yapılmalıdır:

- Installer ve portable başlangıç
- Türkçe karakterli kullanıcı yolu
- MP3/WAV açma, mikrofon ve yavaş oynatma
- PDF/PNG/CSV rapor
- LilyPond PDF/MIDI
- Small MuScriptor modeli
- Eski sürüm üzerine kurulum ve kaldırma

## Lisans

MakamBox Studio, özgün MakamBox uyarlamaları nedeniyle GNU GPL sürüm 3 altında dağıtılır; yeni katkılar “GPL-3.0-or-later” olarak sunulur. Tam metin [LICENSE](LICENSE) dosyasındadır.

Üçüncü taraf bildirimleri [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md), tam kaynak revizyonları [SOURCES.md](SOURCES.md) ve lisans metinleri [licenses](licenses/) klasöründedir.
