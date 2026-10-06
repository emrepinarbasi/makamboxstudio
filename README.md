# MakamBox Studio 2.10.6

MakamBox Studio, Türk makam müziği kayıtlarında klasik MakamBox perde analizini koruyan; yönsel perde, kalış, glissando ve makamsal transkripsiyon incelemelerini aynı masaüstü uygulamasında birleştiren akademik araştırma yazılımıdır.

> English summary: MakamBox Studio is a GPL-3.0-or-later desktop application for classical MakamBox-compatible pitch histograms, directional pitch-event analysis, dwell/glissando measurements and Turkish-makam transcription.

## İndirme

GitHub Releases bölümündeki şu dosyalar son kullanıcı içindir:

| Dosya | Kullanım |
|---|---|
| `MakamBox-Studio-2.10.6-Windows-x64-Setup.exe` | Windows 10/11 x64 için kullanıcı hesabına kurulum |
| `MakamBox-Studio-2.10.6-Windows-x64-Portable.zip` | Kurulum yapmadan taşınabilir kullanım |
| `MakamBox-Studio-2.10.6-macOS.dmg` | macOS uygulama ve disk kalıbı paketi |
| `MakamBox-Studio-2.10.6-SHA256SUMS.txt` | İndirilen dosyaların bütünlük doğrulaması |
| `MakamBox-Studio-2.10.6-Source.tar.gz` | Bu sürümün kaynak kodu ve derleme tarifleri |
| `MakamBox-Studio-2.10.6-SBOM.spdx.json` | SPDX yazılım bileşen dökümü |

[2.10.6 sürüm sayfası](../../releases/tag/v2.10.6)

## Sistem gereksinimleri

- Windows 10 22H2 veya Windows 11, 64 bit x86-64
- Bu sürümdeki macOS DMG için Apple Silicon (arm64) Mac
- En az 4 GB RAM; uzun kayıtlar ve Large model için 8 GB veya üzeri önerilir
- Ses analizi için WAV, AIFF, AU veya MP3 dosyası
- Mikrofonla kayıt için Windows mikrofon izni
- Yapay zekâ modelini kullanmak isteyenlerde model boyutuna göre yaklaşık 210 MB, 620 MB veya 2,74 GB boş alan
- MuScriptor CPU yardımcısı için SSE4.2, AVX ve F16C destekli x64 işlemci; bu şart sağlanmıyorsa yerleşik F0 transkripsiyonunu seçin

Java 21, Node.js, LilyPond-WASM ve Windows MuScriptor yardımcısı pakete dahildir. Bilgisayara ayrıca Java veya Node kurmak gerekmez.

Windows ARM64 cihazlarında paket yerel ARM uygulaması değildir; Windows 11'in x64 öykünmesi üzerinden çalışabilir.

## macOS kurulumu

1. `MakamBox-Studio-2.10.6-macOS.dmg` dosyasını açın.
2. **MakamBox Studio.app** uygulamasını Uygulamalar klasörüne sürükleyin.
3. Uygulamayı Uygulamalar klasöründen başlatın.

Java, Node.js ve LilyPond-WASM macOS uygulamasına dahildir. Bu genel paket Apple tarafından noterlenmiş bir dağıtım değildir; Gatekeeper ilk açılışta geliştiriciyi doğrulayamadığını bildirirse Finder'da uygulamaya sağ tıklayıp **Aç** komutunu kullanın. SHA-256 değerini yayın dosyasıyla karşılaştırın.

## Windows kurulumu

### Kurucu

1. `MakamBox-Studio-2.10.6-Windows-x64-Setup.exe` dosyasını indirin.
2. Dosyanın SHA-256 değerini aşağıdaki yöntemle doğrulayın.
3. Kurucuyu çalıştırın. Uygulama yönetici yetkisi istemeden `%LOCALAPPDATA%\Programs\MakamBox Studio` konumuna kurulur.
4. Başlat menüsündeki **MakamBox Studio** kısayolunu açın.

Kurucu eski MakamBox Studio uygulama klasörünü temizleyerek 2.10.6'yı yerleştirir. Kişisel modeller ve tercihler uygulama klasörünün dışında tutulur.

### Taşınabilir paket

1. Portable ZIP'i Türkçe karakter içerebilen normal bir kullanıcı klasörüne çıkarın.
2. Klasör yapısını bozmadan `MakamBox Studio.exe` dosyasını çalıştırın.
3. `app`, `runtime` ve `resources` klasörlerini EXE'nin yanında bırakın.

### Kaldırma

Uygulamayı kapatın; Başlat menüsündeki kısayolu ve `%LOCALAPPDATA%\Programs\MakamBox Studio` klasörünü silin. İndirilen modelleri de kaldırmak isterseniz `%LOCALAPPDATA%\MakamBox Studio\models` klasörünü ayrıca silin.

### SmartScreen ve imza

2.10.6 ikilileri Authenticode sertifikasıyla imzalanmamıştır. Bu nedenle Windows SmartScreen “Windows bilgisayarınızı korudu” veya “Bilinmeyen yayıncı” uyarısı gösterebilir. Bu uyarı işletim sistemi uyumsuzluğu anlamına gelmez. Uygulamaya Windows 10 ve Windows 11 için Microsoft'un ortak `supportedOS` kimliği gömülüdür; “Windows 10 veya 11 olmalı” biçimindeki eski metin karşılaştırması kullanılmaz.

Bir yayını herkese açık dağıtırken en temiz çözüm EV/OV kod imzalama sertifikasıyla hem kurucuyu hem başlatıcıyı imzalamaktır.

## SHA-256 doğrulama

PowerShell'de:

```powershell
Get-FileHash .\MakamBox-Studio-2.10.6-Windows-x64-Setup.exe -Algorithm SHA256
Get-Content .\MakamBox-Studio-2.10.6-SHA256SUMS.txt
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
- Hedef perdenin renkli, diğer perdelerin mavi gösterimi
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
- [Windows kurulumu ve sorun giderme](docs/WINDOWS.md)
- [Kaynak koddan derleme](docs/BUILDING.md)
- [Yayın hazırlama](docs/RELEASING.md)
- [Kaynak ve sürüm kaydı](SOURCES.md)
- [Değişiklik günlüğü](CHANGELOG.md)

## Kaynak koddan derleme

### macOS

Gerekenler: JDK 21, Node.js, Xcode komut satırı araçları ve isteğe bağlı CMake/Ninja.

```sh
./build-muscriptor-helper.sh
./build-macos.sh
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

Çıktılar `outputs/MakamBox-Studio-2.10.6-GitHub-Release/` klasöründedir.

## Test durumu ve yayın kapısı

Kaynak analiz/test paketi 28 regresyon testi içerir. Çapraz derleme PE32+ x64 yapısını, paket bütünlüğünü ve bağımlılıkların varlığını doğrular. Çapraz derleme tek başına gerçek Windows davranışını kanıtlamaz. Kamuya açık sürümden önce temiz Windows 10 22H2 ve Windows 11 x64 makinelerinde şu denemeler yapılmalıdır:

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
