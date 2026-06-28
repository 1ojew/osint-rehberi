<img width="1024" height="765" alt="image" src="https://github.com/user-attachments/assets/17c82956-1ce5-49fe-9125-9a6641271ddc" />


## 📍 İçindekiler
1.  [AŞAMA 1: PLANLAMA & YÖNLENDİRME (Strateji ve Güvenlik)](#aşama-1-planlama--yönlendirme-strateji-ve-güvenlik)
    * [OpSec Güvenliği (Teknik)](#-opsec-güvenliği-teknik)
    * [Etik Sınırlar ve Yasal Çerçeve](#️-etik-sınırlar-ve-yasal-çerçeve)
2.  [AŞAMA 2: BİLGİ TOPLAMA (Ham Veri Edinme)](#aşama-2--bilgi-toplama-ham-veri-edinme)
    * [Arama ve Sızıntı Analizi](#-arama-ve-sızıntı-analizi)
    * [Sosyal Medya İstihbaratı (SOCMINT)](#️-sosyal-medya-istihbaratı-socmint)
    * [Teknik Altyapı Taraması](#-teknik-altyapı-taraması)
    * [Alan Adı ve DNS Geçmişi](#-alan-adı-ve-dns-geçmişi)
    * [Kurumsal İstihbarat (Business/Corporate INT)](#-kurumsal-istihbaratı-businesscorporate-int)
    * [Resmi Kayıt İstihbaratı (Public Records INT)](#️-resmi-kayıt-istihbaratı-public-records-int)
    * [Web Arşivleme](#-web-arşivleme)
    * [Görüntü Tersine Arama (IMINT)](#️-görüntü-tersine-arama-imint)
    * [Coğrafi Veri Toplama (GEOINT)](#-coğrafi-veri-toplama-geoint)
    * [Havacılık İstihbaratı (AVINT)](#️-havacılık-istihbaratı-avint)
    * [MARINT (Denizcilik İstihbaratı)](#-marint-denizcilik-istihbaratı)
    * [FININT (Finansal İstihbarat) & Kripto OSINT](#-finint-finansal-istihbarat--kripto-osint)
    * [SIGINT (Sinyal İstihbaratı - Halka Açık Yönü)](#-sigint-sinyal-istihbaratı---halka-açık-yönü)
3.  [AŞAMA 3: İŞLEME & DEĞERLENDİRME (Veriyi Ayıklama)](#aşama-3-⚙️-işleme--değerlendirme-veriyi-ayıklama)
4.  [AŞAMA 4: ANALİZ & ÜRETİM (Noktaları Birleştirme)](#aşama-4--analiz--üretim-noktaları-birleştirme)
    * [Ustalık Seviyesi: Analitik Metodoloji](#️-ustalık-seviyesi-analitik-metodoloji-en-kritik-adım)
    * [Bilişselyanlılıklar (Cognitive Biases) ve Yönetimi](#-bilişsel-yanlılıklar-cognitive-biases-ve-yönetimi)
    * [Yapılandırılmış Analitik Teknikler (SATs)](#️-yapılandırılmış-analitik-teknikler-sats)
5.  [AŞAMA 5: YAYIM (Raporlama)](#aşama-5--yayim-raporlama)
6.  [ÖNERİLEN KİTAPLAR VE İLERİ OKUMALAR](#📚-önerilen-kitaplar-ve-ileri-okumalar)
7.  [AKADEMİK VAKA ANALİZİ: "OPERASYON: GÖLGE AĞ"](#🎓-akademik-vaka-analizi-operasyon-gölge-ağ)




# TÜRKÇE OSINT Rehberi!




**İstihbarat Döngüsü ve Uygulama Aşamaları**

## AŞAMA 1: PLANLAMA & YÖNLENDİRME (Strateji ve Güvenlik)

Görev hedeflerinin netleştirildiği, gerekli kaynakların belirlendiği, etik sınırların çizildiği ve operasyonel güvenliğin sağlandığı stratejik başlangıç aşamasıdır.


### Operasyonel Güvenlik -OpSec Güvenliği 

Operasyonel Güvenlik, görevin temel taşıdır. 

- IP, dijital iz gizlemek için VPN Kullanımı! Tavsiye `Proton VPN`, `Mulvad VPN` gibi güven duyulan ("Kill Switch" ve "Split Tunneling" özelliği ve "No Log Policies" politikasında hizmet veren servisler!) 

- Kullandığın işletim sisteminin Gereksiz telemetry ve veri toplama izinlerini kapatma-kaldırma!

- Kullandığın "Tarayıcı ve İşletim Sistemini" sürekli güncel tut!


  
  **Sanalizasyon ve Ayrıştırma:** Kişisel bilgisayardan izole bir ortamda (`Tails`, `Whonix`, `Unix` ve `Qubes Os` vb.) gibi açık kaynak ve gizliliğin ön planda olduğu işletim sistemlerinde araştırma yapmak için `VirtualBox` veya `VMware` gibi sanal makine kullanımları kritiktir. 
    
 


- **İletişim Güvenliği**

Bir OSINT operasyonunun başarısı, en zayıf halkası kadar güçlüdür ve bu halka genellikle iletişimdir. Bir kaynakla, hedefle veya ekip üyesiyle kurulan temasın gizliliği, operasyonun bütününü korumak için esastır. Bu noktada Uçtan Uca Şifreleme (End-to-End Encryption - E2EE), bir lüks değil, temel bir gerekliliktir.

Kullanabileceğiniz uygulamalar::

`Signal`,`Element` uygulamaları ve `Telegram`'ın (Secret Chat) özelliği !
`WhatsApp` (Meta verilerini topladığı için önermiyorum.) 


- **Pretty Good Privacy (PGP / GPG) Şifrelemesi**

E-posta veya dosyalar gibi daha geleneksel iletişim kanallarında yüksek güvenlik sağlamak için PGP (veya ücretsiz alternatifi GPG) kullanılır.
Bu sistem, asimetrik şifrelemeye dayanır. Çalışma mantığı şudur:

Her kullanıcının iki anahtarı vardır: Biri Genel Anahtar (Public Key), diğeri Özel Anahtar (Private Key).

  Genel Anahtar: Dijital bir asma kilittir. Bunu herkese (veya sadece iletişim kurmak istediğiniz kişiye) güvenle verebilirsiniz.
  Özel Anahtar: O kilidi açan tek anahtardır. Bunu asla kimseyle paylaşmazsınız ve güvende tutarsınız.

Birine gizli bir bilgi göndermek istediğinizde, onun size verdiği Genel Anahtarı (asma kilidini) kullanarak mesajınızı veya dosyanızı kilitlersiniz. Bu kilitlenmiş mesajı artık sadece ve sadece kendi Özel Anahtarına sahip olan o kişi açabilir.

Bu yöntem, mesajın sadece hedeflenen alıcı tarafından okunmasını garanti altına alır. `Kleopatra` kullanabilirsiniz.


-  **Gizli Arama ve Geniş Arama:** Araştırmalarda `DuckDuckGo`, `Brave Search`, `Starpage` gibi gizliliğe odaklı arama motorları ve `Firefox` veya `Tor Browser` gibi güvenli tarayıcılar kullanılmalıdır.
    
- **Sahte Profiller:** OSINT çalışmaları için sahte profil (sock puppet) oluştururken kullanılacak e-posta servisleri, operasyonun önemine göre üçe ayrılır:

1.  **Hızlı ve Tek Kullanımlık Profiller:** Basit, hızlı ve "kullan-at" mantığıyla açılacak hesaplar için `temp-mail`, `Guerrilla Mail` veya benzeri geçici e-posta servisleri kullanılabilir. Bu servisler, e-postaları kısa bir süre saklar ve kalıcı bir kimlik sağlamaz.
    
2.  **Kalıcı Ama Gizli Profiller (Aliasing):** Eğer profillerinizin kalıcı olmasını ancak ana e-posta adresinizin (örneğin ana ProtonMail adresinizin) ifşa olmamasını istiyorsanız, `SimpleLogin` veya `AnonAddy` gibi e-posta takma adı (aliasing) servisleri idealdir. Bu servisler, oluşturduğunuz her sahte profil için ayrı bir "maske" e-posta adresi yaratır ve gelen postaları güvenli ana kutunuza iletir.
    
3.  **Önemli ve Yüksek Güvenlikli Operasyonlar:** Tespit edilmemenin kritik olduğu, dikkat çekmemek ve doğal akışta istihbarat toplamak gereken önemli konularda, tamamen bağımsız ve güvenli servislere ihtiyaç duyulur. Bu durumda `ProtonMail`, `Tuta Mail` ve `Posteo Mail` gibi uçtan uca şifreleme sunan, anonimliğe önem veren servisler tercih edilmelidir. Alternatif olarak, (çok yüksek teknik OpSec bilgisi gerektirse de) kendi sunucunuza bağlı bir e-posta adresi de kullanılabilir.
    
-   Yapay zeka ile üretilmiş, gerçek hayatta olmayan kişi fotoğrafı üreten bir site: [thispersondoesnotexist.com](https://thispersondoesnotexist.com/). Sahte profillerinizde kullanabilirsiniz.
    
-   **Teknik İlişkilendirmeyi (Attribution) Kırmak:** Akıllı hedefler sizi sadece IP'nizden tanımaz. Tarayıcıdaki parmak izinize (`Browser Fingerprint`) odaklanırlar: Kullandığınız yazı tipleri (fonts), ekran çözünürlüğünüz, tarayıcı eklentileriniz... Milyonlarca insan arasında sizi "benzersiz" yapan bir imzadır bu.
    
    -   **Nasıl Çözebiliriz:** KOYUN SÜRÜSÜNE KARIŞACAĞIZ. Dünyada en çok kullanılan çözünürlük, font ve işletim sistemi kombinasyonunu kullanmak gibi.
        
    -   **EK OLARAK:**
        
        -   Tarayıcılarınızın kendine has özel gizlilik ayarlarını maksimum düzeyde kullanın (örneğin Firefox'ta `privacy.resistFingerprinting` ayarını aktifleştirmek).
            
        -   Güvenilir olmayan kaynaklarda (`.onion` uzantılı siteler gibi) arama yaparken tarayıcınızı tam ekran modunda kullanmamaya çalışın. Siteler genellikle ekran çözünürlüğünüzü loglayarak sizi parmak iziyle tanıyabilir.

        Bu tarz sitelerden "https://coveryourtracks.eff.org/" web parmak izinizi test edebilirsiniz.

     
   -   **Site ve Kaynak Güvenilirliği (Klon / Sahte Site Tespiti):** Araştırma sırasında karşılaşılan her web sitesi güvenli veya doğru bilgiye sahip olmayabilir. Bazı siteler, popüler platformların veya haber kaynaklarının birebir kopyası (klonu) olarak tasarlanmış olabilir.

Bu tür sitelerin amacı operasyonunuzu sabote etmektir:

-   **Yanlış Bilgi (Dezenformasyon):** Sizi kasıtlı olarak yanlış bir sonuca yönlendirmek.
    
-   **Deşifre Etme (Tuzak):** Sahte bir giriş (login) ekranı veya IP logger aracılığıyla sahte kimliğinizi (sock puppet) ve gerçek IP adresinizi ele geçirmek.
    
-   **Dolandırıcılık ve Kötü Amaçlı Yazılım:** Kredi kartı bilgilerinizi çalmak veya cihazınıza zararlı yazılım (malware) bulaştırmak.
    

Bir siteye güvenmeden veya bir dosyayı açmadan önce şu araçlarla hızlı bir güvenlik kontrolü yapmak kritik bir OpSec adımıdır:

-   **`VirusTotal`:** Sadece indirdiğiniz şüpheli dosyaları değil, aynı zamanda URL'leri de taramak için kullanılır. Onlarca antivirüs motorunun veritabanını kullanarak bir adresin veya dosyanın kötü amaçlı olarak etiketlenip etiketlenmediğini saniyeler içinde gösterir.
    
    -   [virustotal.com](https://www.virustotal.com/gui/home/upload)
        
-   **`PhishTank`:** Bir sitenin, bilinen bir "Oltalama" (Phishing) sitesi olup olmadığını kontrol eden, topluluk tarafından beslenen devasa bir veritabanıdır.
    
    -   [phishtank.com](https://phishtank.com/index.php)
        
-   **`ScamAdviser`:** Özellikle e-ticaret veya hizmet sitelerinin güvenilirliğini analiz eder. Sitenin yaşı, sahibi, konumu ve kullanıcı yorumlarına göre bir güven puanı oluşturur.
    
    -   [scamadviser.com](https://www.scamadviser.com)
        

**Ek Manuel Kontroller:**

-   **URL'yi Gözle İncele:** Adres çubuğunu dikkatle okuyun. `google.com` yerine `go0gle.com` veya `googIe.com` (büyük 'i' harfi) gibi "typosquatting" tuzakları var mı?
    
-   **SSL Sertifikası:** Tarayıcıdaki kilit simgesine tıklayarak sertifikanın kime (hangi şirkete) ve ne zaman düzenlendiğini hızlıca kontrol edin.
            

###  Etik Sınırlar ve Yasal Çerçeve

Araştırmanın "kırmızı çizgilerini" (hangi bilgilerin toplanıp toplanmayacağını) belirlemek. Özel hayatın gizliliğine ve yerel/uluslararası yasalara (KVKK, GDPR vb.) uymak kritiktir.

___

## AŞAMA 2: BİLGİ TOPLAMA (Ham Veri Edinme)

###  Arama ve Sızıntı Analizi

-   **OSINT Framework:** Bir toplama aracı değil, belirli bir hedef için hangi aracın veya veri kaynağının kullanılacağını gösteren devasa bir dizin ve yol haritasıdır.
    
    -   [osintframework.com](https://osintframework.com)
        
    -   Alternatif:(https://bellingcat.gitbook.io/toolkit)
        
-   **Dev Referans GitHub Kaynakları:** Alanında en çok kabul gören ve sürekli güncellenen araç ve kaynak koleksiyonları.
    
    -   [github.com/jivoi/awesome-osint](https://github.com/jivoi/awesome-osint)
        
    -   [github.com/tracelabs/awesome-osint](https://github.com/tracelabs/awesome-osint)
        
    -   [github.com/cipher387/osint\_stuff\_tool\_collection](https://github.com/cipher387/osint_stuff_tool_collection)
        
    -   [https://github.com/Astrosp/Awesome-OSINT-For-Everything](https://github.com/Astrosp/Awesome-OSINT-For-Everything)
        
-   **Google Dork ve Meta-Arama Motorları:** Gelişmiş arama operatörleriyle gizli dosya, veritabanı ve sızıntıları bulma.
    
    -   Örnek kullanım:([https://exposingtheinvisible.org/guides/google-dorking/](https://exposingtheinvisible.org/guides/google-dorking/))
        
    -   `Dogpile` ([dogpile.com](https://www.dogpile.com/)) bir "metasearch engine" yani meta-arama motorudur. Google, Bing, Yahoo gibi birden fazla arama motorunun sonuçlarını birleştirir.
        
-   **Sızıntı Veritabanları:** `Dehashed`, `HaveIBeenPwned`, `LeakCheck.io`, `IntelligenceX`, `Socradar.io`.
    
-   **Dark Web Taraması:** `.onion` siteleri ve yeraltı forumlarındaki sızıntı ve çalıntı verilerin taranması (`Tor Browser` gerektirir).
    

> 🚩 **Not:** Bu araçlar yalnızca halka açık verileri analiz eder. Erişim her zaman etik ve yasal sınırlar içinde olmalıdır.

###  Sosyal Medya İstihbaratı (SOCMINT)

Sosyal medya profillerinden ve ağlarından (arkadaş listeleri, beğeniler, etiketlenmiş fotoğraflar, paylaşımlar) ham veri toplama.

-   **Kullanıcı Adı Taraması:** `Sherlock`, `Maigret`, `WhatsMyName` (Kullanıcı adlarını birçok platformda tarar).
    
-   **Twitter (X) Odaklı Analiz:** `Twint` (Gelişmiş Twitter veri çekme/arşivleme aracı), `Followerwonk` (Twitter biyografi analizi ve takipçi karşılaştırma).
    
-   **Telefon Numarası Analizi:** `PhoneInfoga`, `GetContact`, `CallerID` (Telefon numarasından operatör, ülke ve sosyal medya bağlantılarını bulur).
    
    > **Not:** `GetContact` ve `CallerID` gibi ücretli servisler, isim/telefon/geçmiş adres gibi detaylı kişisel kayıtlar sunabilir.
    
-   **Yüz Arama:** `FaceCheck.id` (Yüz fotoğrafından diğer sosyal medya profillerini veya benzer görüntüleri bulur).
    
-   **Otomatize Arama:** `Seekr-OSINT` (Reddit, Telegram, X gibi platformlarda otomatize arama) ve `SpiderFoot` (Bir hedef için birçok kaynaktan otomatik veri toplar ve ilişkileri haritalar).
    
    > **Not:** SpiderFoot'un `sfp_google`, `sfp_bing`, `sfp_twitter`, `sfp_facebook` gibi modülleri; sızdırılmışsa telefon rehber kayıtlarını, hesap bilgilerini ve sosyal medya profillerini doğrudan getirebilir.
    
-   **Meta İçerik Kütüphanesi:** Meta'nın Facebook ve Instagram verilerine (öncelikli olarak akademik) erişim aracı.
    
Harika bir seçim. Bu iki araç, rehberinizdeki **Kriptografi** ve **Steganografi** başlıkları için sektör standardı sayılan, mükemmel ve birbirini tamamlayan araçlardır.

Rehberinize eklemeniz için bu araçların ne işe yaradığını ve OSINT/CTF bağlamında nasıl konumlandırılacağını açıklayan bir bölüm hazırladım:

___

###  Kriptografi & Steganografi (Gizlenmiş Veriyi Ortaya Çıkarma)

OSINT araştırmalarında veya CTF yarışmalarında, aradığınız bilgi (flag) her zaman açık metin (plaintext) olarak karşınıza çıkmaz. Bazen şifrelenmiş bir metin (kriptografi) veya bir resim dosyası gibi masum görünen bir verinin içine gizlenmiş (steganografi) olabilir.

Bu bölümde, bu iki yaygın engeli aşmak için kullanılan iki temel aracı inceleyeceğiz.

#### 1\. dCode.fr (Kriptografi için İsviçre Çakısı)

-   **URL:** `https://www.dcode.fr/`
    
-   **Kullanım Amacı:** **Kriptografi.** (Şifrelenmiş veya Kodlanmış Metinleri Çözmek)
    
-   **Açıklama:** dCode, karşılaştığınız "anlamsız" görünen bir metin bloğunun ne olduğunu anlamak ve çözmek için başvuracağınız ilk yerdir. Yüzlerce farklı şifreleme yöntemini (Sezar, Vigenère, Atbash gibi), kodlamayı (Base64, Hex, Morse Kodu, ASCII gibi) ve tarihi alfabeyi tanıyan devasa bir çevrimiçi kütüphanedir.
    
-   **En Güçlü Özelliği:** **Otomatik Tanımlayıcı (Cipher Identifier).** Elinizdeki şifreli metni (ciphertext) ana sayfadaki "Chiffrement Inconnu" (Bilinmeyen Şifre) kutusuna yapıştırdığınızda, dCode bunun hangi yöntemle şifrelenmiş olabileceğini sizin yerinize analiz eder ve olası çözümleri listeler.
    
-   **OSINT/CTF Senaryosu:** Bir hedefin web sitesinin kaynak kodunda \`\` şeklinde bir yorum satırı buldunuz. Bunun anlamsız olduğunu biliyorsunuz. dCode'a yapıştırdığınızda, bunun **Base64** ile kodlandığını ve "gizli parola: 12345" anlamına geldiğini size saniyeler içinde söyleyecektir.
    

___

#### 2\. Aperi'Solve (Steganografi Uzmanı)

-   **URL:** `https://aperisolve.fr/`
    
-   **Kullanım Amacı:** **Steganografi.** (Dosyaların İçine Gizlenmiş Verileri Bulmak)
    
-   **Açıklama:** Aperi'Solve, özellikle resim dosyalarına odaklanan bir çevrimiçi steganografi analiz platformudur. Bir görselin içine gizlenmiş başka dosyaları, metinleri veya ipuçlarını bulmak için tasarlanmıştır.
    
-   **En Güçlü Özelliği:** **Hepsi Bir Arada Analiz.** Siz dosyayı yüklediğinizde, Aperi'Solve arka planda otomatik olarak `zsteg`, `steghide`, `outguess`, `exiftool`, `binwalk`, `foremost` ve `strings` gibi en popüler adli bilişim (forensics) ve steganografi araçlarını çalıştırır. Görüntünün farklı renk katmanlarını analiz eder, meta verilerini (EXIF) döker ve içinden çıkarılabilecek gizli dosyaları listeler.
    
-   **OSINT/CTF Senaryosu:** Bir CTF sorusunda size sadece bir `.png` veya `.jpg` dosyası verildi. Görüntüde hiçbir ipucu yok. Resmi Aperi'Solve'a yüklediğinizde, "Strings" sekmesinde bir parola, "Binwalk" sekmesinde ise resmin içine gömülmüş (embedded) bir `.zip` dosyası bulabilirsiniz.



-
###  Teknik Altyapı Taraması

-   **Altyapı Tespiti:** `Whois` (Alan adı sahiplik bilgisi).
    
-   **Recon Çerçeveleri:** `Recon-ng` (Web tabanlı keşif için modüler bir çerçeve), `TheHarvester` (E-postaları, alt alan adlarını, çalışan isimlerini ve portları toplar).
    
-   **Cihaz/Servis Tarama:** `Shodan`, `Censys` (İnternete bağlı cihazları, portları ve servisleri tarar).
    
    > **Shodan Filtreleri İpucu:**
    
    > -   Ülke: `country:"ÜLKE KODU"`
    >     
    > -   Şehir: `city:"Şehir Adı" country:"ÜLKE KODU"`
    >     
    > -   Koordinat: `geo:"ENLEM,BOYLAM", "KM-ARALIĞI"` (Koordinatı Google Haritalar URL'sinden alabilirsiniz. Ülke kodları için: [nationsonline.org](https://www.nationsonline.org/oneworld/country_code_list.htm))
    >     
    
-   **Teknoloji Tespiti:** `Wappalyzer` (eklenti), bir web sitesinin kullandığı teknolojileri (sunucu, CMS, analiz araçları) tespit eder. `BuiltWith` ([builtwith.com](https://builtwith.com)) ise o sitenin tarihsel olarak (geçmişte) hangi teknolojileri kullandığını da gösteren devasa bir veritabanıdır. İkisi birbirinin tamamlayıcısı ve en önemli "Teknoloji Tespiti" araçlarıdır.
    
-   **Zafiyet Veritabanı:** `Exploit-DB`, `GGTFOBins`  sistemlerin bilinen zafiyetlerini (exploit) aramak için kullanılır. Örneğin, önce `Shodan`, `Censys` veya `Wappalyzer` ile bir hedef (sunucu, servis, yazılım) bulursunuz. Sonra, bulduğunuz o yazılımın (örn: `Apache 2.4.51`) bilinen bir zafiyeti var mı diye `Exploit-DB`'ye bakarsınız.
    

###  Alan Adı ve DNS Geçmişi

Bir web sitesinin geçmişte hangi IP/sunucularda barındığını veya hangi teknolojileri kullandığını görmek.

-   **Sunucu Geçmişi:** `Netcraft`.
    
-   **DNS Kayıtları:** `DNSDumpster`, `SecurityTrails` (Geçmiş DNS kayıtları ve alt alan adları).
    
-   **DNS Sorgusu:** `nslookup` (Ters DNS sorguları).
    

###  Kurumsal İstihbarat (Business/Corporate INT)

Şirket yapılarını, kilit personeli, e-posta formatlarını ve mali durumu araştırmak.

-   **Personel ve Yapı:** `LinkedIn` (Sales Navigator), `Crunchbase`.
    
-   **E-posta Kalıpları:** `Hunter.io`, `Snov.io`.
    
-   **E-posta Doğrulama:** `holehe` (E-posta adreslerinin hangi platformlarda kayıtlı olduğunu kontrol eder).
    

###  Resmi Kayıt İstihbaratı (Public Records INT)

Devletler, belediyeler veya resmi kurumlar tarafından tutulan halka açık kayıtları (dava dosyaları, tapu kayıtları, patentler, ticari markalar, siyasi bağışlar) araştırmak.

-   **Araçlar:** Ulusal/yerel mahkeme portal siteleri, tapu ve kadastro veritabanları, patent ofisi arama motorları (örn: `Google Patents`), resmi gazeteler.
    
-   **Kişi Arama Motorları (People Search):** `Pipl`, `Intelius`, `People Finder` hizmetleri.
    

###  Web Arşivleme

-   **Araçlar:** `Wayback Machine`, `Archive.today` (Silinmiş veya değiştirilmiş web sayfalarının geçmiş sürümlerine erişim sağlar).
    

###  Görüntü Tersine Arama (IMINT)

-   **Araçlar:** `Google Lens`, `TinEye`, `PimEyes`, `Yandex Images`, `Bing Images`, `PhotoSherlock` (Görselin kaynağını veya benzerlerini bulur).
    
    > **İpucu:** "Reverse Image Search" gibi tarayıcı eklentileri bu servisleri tek tıkla kullanabilir.
    

###  Coğrafi Veri Toplama (GEOINT)

-   **Analiz:** Fotoğraf ve videolardaki ipuçlarından (gölgeler, mimari, trafik işaretleri) çekim yerini tespit etmek.
    
-   **Canlı Kameralar / Wi-Fi:** `Insecam.org`, `Shodan` (webcam filtresi), `Wigle.net` (Dünya çapında Wi-Fi ağ haritaları).
    
-   **Araçlar:** `Geospy`, `Google Earth Studio`, `Google Earth Pro` (Cetvel ve Zaman Aracı), `Creepy` (Sosyal medya paylaşımlarından konum verisi toplar), `SunCalc.org`, `Twilight Map` ([in-the-sky.org/twilightmap.php](http://in-the-sky.org/twilightmap.php)) (gölge analizi), `PeakVisor` (dağ/tepe tespiti), `MapDevelopers` (Draw Circle Tool).
    
-   **Araç Plakaları:** Araç plakalarının hangi ülkeye ait olduğunu tarihsel olarak depolayan bir veritabanı: [worldlicenseplates.com](http://www.worldlicenseplates.com/).
    
    > **İpucu:** `MapDevelopers` veya `Google Earth Pro` ile belirli bir geo-koordinat etrafında (örn. 5km yarıçaplı) bir daire çizerek arama alanını daraltma pratiği yapın.
    
-   **Pratik:** Lokasyon bulmak için **`GeoGuessr`** oyunu ile pratik yapabilirsiniz. Mükemmeldir!
    

###  Havacılık İstihbaratı (AVINT)

-   **Uçuş Takibi:** `Flightradar24`, `FlightAware`, `ADS-B Exchange` (Gerçek zamanlı veya geçmiş uçuş hareketleri, rotalar ve sahiplik bilgileri).
    
-   **Rotalar / Tasarımlar:** `Airlineroutemaps.com`, `Airlinersgallery.smugmug.com` (Havayolu rota haritaları ve uçak kuyruk tasarımları).
    

###  MARINT (Denizcilik İstihbaratı)

Küresel tedarik zincirini ve gemi hareketlerini (AIS verileri) takip etmek.

-   **Araçlar:** `MarineTraffic`, `VesselFinder`, `FleetMon` (Gemilerin konumu, rotası, sahipliği ve yük durumu).
    

### ₿ FININT (Finansal İstihbarat) & Kripto OSINT

Siber suç ve dolandırıcılık analizlerinde paranın (özellikle kripto paranın) takip edilmesi.

-   **Blockchain Gezginleri:** `Etherscan` (Ethereum), `Blockchair`, `BlockCypher`.
    
-   **Cüzdan Analizi:** `Wallet Explorer` (İşlem geçmişlerini ve cüzdanların bilinen borsalarla ilişkisini analiz eder).
    

###  SIGINT (Sinyal İstihbaratı - Halka Açık Yönü)

Halka açık radyo frekanslarını, uydu sinyallerini ve IoT cihaz iletişimini izlemek.

-   **Araçlar:** `SDR (Software Defined Radio)` donanımları, `RadioReference.com` (frekans veritabanları), `Cel-Mapper` (baz istasyonu konumları).
    

___

## AŞAMA 3:  İŞLEME & DEĞERLENDİRME (Veriyi Ayıklama)

-   **Metadata Analizi:** `ExifTool`,`pic2map` vb. 
    
-   **Video Doğrulama:** `InVID`, `WeVerify` (Videolardan meta veri çıkarır, karelere ayırır \[tersine arama için\] ve manipülasyon \[deepfake\] tespiti sağlar).
    
-   **Veri Temizleme:** `OpenRefine` (Büyük miktarda metin, sızıntı veya tablo verisini temizler, çift kayıtları siler ve formatları birleştirerek analize hazırlar).
    
-   **Görsel Netleştirme:** Photoshop bilginiz yoksa, `unblur` veya `deblur` araçlarıyla bulanık ve net bilgi elde edilemeyen fotoğrafları netleştirebilirsiniz.
    

___

## AŞAMA 4:  ANALİZ & ÜRETİM (Noktaları Birleştirme)

İşlenmiş bilgileri birleştirme, hipotezler kurma, varsayımları sorgulama ve sonuca ulaşma aşaması. _Ustalık bu aşamada kazanılır._

-   **Bağlantı Analizi:** `Maltego`, `Obsidian.md` (Farklı veri noktalarını \[kişi, e-posta, şirket, IP\] birleştirip aralarındaki gizli ilişkileri görselleştirir).
    
-   **Coğrafi Konum Analizi:** `ipinfo.io`, `iplocation.net` (IP adresinden coğrafi konum çıkararak analizi derinleştirme).
    
-   **Veri Yönetimi:** `CherryTree` (Toplanan verileri birleştirmek için gelişmiş bir not defteri).
    
-   **Zaman Çizelgesi Analizi (Timeline Analysis):** Toplanan tüm verileri (sosyal medya paylaşımları, web sitesi güncellemeleri, uçuş kayıtları) kronolojik bir sıraya dizerek olayların akışını anlama ve örüntüleri ortaya çıkarma.
    
-   **Yapay Zeka ile Fikir Üretme:** Toplanan ham verileri özetlemek, ilişkileri sorgulamak veya potansiyel saldırı senaryoları oluşturmak için `GPT`, `Gemini`, `DeepSeek` gibi yapay zeka araçlarından faydalanma.
    

###  Ustalık Seviyesi: Analitik Metodoloji (En Kritik Adım)

Araçlar veriyi toplar, ancak "Usta" analist o veriden doğru sonucu çıkarır. Bu, beynimizin bize kurduğu tuzakları (Bilişsel Yanlılıklar) bilmekle başlar.

-   **Gerçek OSINT Vaka Analizleri (Nasıl Yapılır):** Analiz tekniklerinin gerçek dünyada nasıl uygulandığını görmek için Bellingcat'in vaka incelemeleri ve "Nasıl yapılır" rehberleri incelenmelidir.
    
    -   ([https://www.bellingcat.com/category/resources/how-tos/](https://www.bellingcat.com/category/resources/how-tos/))
        

###  Bilişsel Yanlılıklar (Cognitive Biases) ve Yönetimi

Analizdeki en büyük düşman, analistin kendi beynidir. Amaç, **Doğrulama Ön Yargısı** (_Confirmation Bias_ - sadece kendi hipotezimizi doğrulayan kanıtları aramak) ve **Çıpalama** (_Anchoring_ - ilk öğrenilen bilgiye takılıp kalmak) gibi analitik tuzakları aktif olarak engellemektir.

###  Yapılandırılmış Analitik Teknikler (SATs)

Bilişsel yanlılıkları yenmek ve karmaşık verileri işlemek için kullanılan standartlaşmış düşünme metodolojileridir. Amaç, hipotezleri test etmek ve varsayımları sorgulamaktır.

-   **Örnek Teknikler:**
    
    -   **ACH (Analysis of Competing Hypotheses):** En olası senaryoyu bulmak için kanıtları tüm hipotezlere karşı sistemli bir şekilde puanlama tekniği. (Amaç, en az yanlış olanı bulmaktır.)
        
    -   **Devil's Advocacy (Şeytanın Avukatlığı):** Mevcut ana hipotezi çürütmek için aktif olarak karşı kanıtlar aramak.
        
    -   **Indicators / Signposts (Göstergeler):** Belirli bir hipotezin doğru olup olmadığını anlamak için gelecekte izlenmesi gereken spesifik olayları veya veri noktalarını belirlemek.
        
-   **Detaylı SATs Makaleleri (Akademik Kaynaklar):**
    
    -   ([https://www.cia.gov/resources/csi/static/Tradecraft-Primer-apr09.pdf](https://www.cia.gov/resources/csi/static/Tradecraft-Primer-apr09.pdf))
        
    -   ([https://www.rand.org/content/dam/rand/pubs/research\_reports/RR1400/RR1408/RAND\_RR1408.pdf](https://www.rand.org/content/dam/rand/pubs/research_reports/RR1400/RR1408/RAND_RR1408.pdf))
        

___

## AŞAMA 5:  YAYIM (Raporlama)

Sonuçları bir karar vericiye (müşteri, yönetici, okuyucu) net, anlaşılır, kanıta dayalı ve eyleme geçirilebilir bir formatta (rapor, sunum, brifing) sunma aşamasıdır.

-   **Modern OSINT Uygulamaları:** Veri çekme, işleme ve görselleştirme için `Python` (`Jupyter Notebooks`), `R` veya `API`'ler kullanarak süreçleri otomatize etme ve tekrarlanabilir raporlar üretme.
    

___

##  ÖNERİLEN KİTAPLAR VE İLERİ OKUMALAR

-   **_OSINT Techniques: Resources for Uncovering Online Information_** **— Michael Bazzell**
    
      
    
    Sektördeki en temel ve kapsamlı kaynaklardan biri olarak kabul edilir. Bazzell, yöntemlerini sürekli günceller. (2024 baskısı itibarıyla ~590 sayfa.)
    
-   **_Open Source Intelligence Methods and Tools: A Practical Guide to Online Intelligence_** **— Nihad A. Hassan & Rami Hijazi**
    
      
    
    2018’de yayınlanmış, OSINT döngüsünün her aşaması için pratik araçlar ve yöntemler sunan güçlü bir rehber.
    
-   **_Deep Dive: Exploring the Real-world Value of Open Source Intelligence_** **— Rae L. Baker**
    
      
    
    2023’te yayınlanmış bu kitap, OSINT’in modern ve güncel yönlerini, özellikle kurumsal dünyadaki değerini ele alır.
    

___

##  AKADEMİK VAKA ANALİZİ: "OPERASYON: GÖLGE AĞ"

### Senaryo: "Operasyon: Gölge Ağ"

**Hedef:** "Ph03nix\_7" kod adlı kurgusal bir tehdit aktörünün kimliğini, operasyonel konumunu ve para aklama yöntemlerini, birden fazla istihbarat disiplinini (IMINT, MARINT, FININT, Teknik INT) çapraz doğrulayarak (cross-corroborate) tespit etmek.

**Başlangıç Kanıtları:**

1.  **Persona:** `Ph03nix_7` (Dark Web forum kullanıcı adı)
    
2.  **Görsel Kanıt:** Hedefin Twitter'da paylaştığı tek bir fotoğraf. Mesaj: "Another day at the office..." Fotoğraf, bir pencereden görünen _belirsiz_ bir liman/sahil şeridi manzarası içeriyor.
    
3.  **Finansal İz:** Fidye için kullanılmış (artık terk edilmiş) bir Bitcoin (BTC) cüzdan adresi.
    

___

### Analiz Aşamaları ve Kullanılan Uzman Araçları

**1\. Aşama: Keşif ve Görüntü Analizi (IMINT & Automation)**

Analist, `Ph03nix_7` personasını haritalamak için **`SpiderFoot`** gibi bir otomasyon çerçevesi başlatır. Paralel olarak, fotoğrafa odaklanır:

-   **IMINT (Görsel Arama):** Fotoğraftaki belirsiz liman manzarası **`Google Lens`** veya **`Yandex Images`** ile aratılır. Sonuçlar geneldir (binlerce liman fotoğrafı) ve spesifik bir konum (GEOINT) **tespit edilemez.** Bu, analistin coğrafi konum için başka bir yol bulması gerektiği anlamına gelen ilk "çıkmaz sokak"tır.
    
-   **IMINT (Meta Veri Analizi):** Fotoğraf **`ExifTool`** ile analiz edilir:bash exiftool Ph03nix\_tweet.jpg
    
-   **BULGU (Pivot 1):** Twitter, GPS ve kamera modeli gibi verilerin çoğunu temizlemiştir. Ancak, `Date/Time Original` (Orijinal Tarih/Saat) meta verisi korunmuştur: **`2024-10-26 14:30:12`**. Analist bu zaman damgasını (timestamp) kritik bir veri olarak not eder.
    

**2\. Aşama: Pivot Noktası (Google Dorking & Tehdit İstihbaratı)**

GEOINT'in başarısız olması nedeniyle dijital ayak izleri daha da kritik hale gelir. Analist, hedefin geçmişteki OpSec hatalarını bulmak için **`Google Dorking`** kullanır.

-   Spesifik bir dork ile yıllar önce paylaşılan bir kod dökümünü (paste) ortaya çıkarır:
    
    ```
    intext:"Ph03nix_7" "gmail.com" site:pastebin.com
    ```
    
-   **BULGU (Pivot 2):** Kodun yorum satırında şu bilgi bulunur:
    
    ```
    # Author: James Hawkins &lt;james.hawkins.dev@gmail.com&gt;
    ```
    
    Persona artık gerçek bir kimlikle ilişkilendirilmiştir.
    
-   Bu e-posta adresi, **`IntelligenceX`** gibi derin bir tehdit istihbaratı arşivinde aratılır. Bir veri sızıntısında (`MyFitnessPal`) bu e-postayla birlikte kaydedilen tarihsel bir IP adresi (`81.149.x.x`) bulunur.
    

**3\. Aşama: Altyapı ve Kurumsal Doğrulama (Passive DNS & Corporate INT)**

Analist, bulunan IP ve ismi doğrulamak için altyapı araçlarına yönelir:

-   IP adresi, **`SecurityTrails`** (veya `RiskIQ PassiveTotal`) gibi bir Pasif DNS platformunda analiz edilir. IP'nin tarihsel kayıtlarının olmaması, bunun bir sunucu değil, "Londra" konumlu bir ev interneti (Residential ISP) olduğunu teyit eder.
    
-   "James Hawkins" ismi, `LinkedIn` ve **`theHarvester`** kullanılarak 'SecureData Solutions Ltd.' adlı bir şirketle ilişkilendirilir.
    
-   Analist, **`Offshore Leaks Database`** (ICIJ) veya ilgili ülkenin (örn. Kıbrıs, BVI) **Resmi Ticaret Sicili** (Corporate Registry) kayıtlarını inceler.
    
-   **BULGU (Pivot 3):** "James Hawkins"in bu şirketin kurucu yöneticisi olduğu ve şirketin resmi adresinin **"Limassol Marina, Kıbrıs"** olduğu tespit edilir.
    

**4\. Aşama: "WOW" Anı - Çapraz Doğrulama (IMINT + GEOINT + MARINT)**

Bu, senaryonun akademik zirvesidir. Analistin elinde iki ayrı, bağımsız ve _doğrulanmamış_ veri vardır:

1.  **Fotoğraftan (Adım 1):** Zaman Damgası: `26 Ekim 2024, 14:30:12`
    
2.  **Resmi Kayıtlardan (Adım 3):** Konum: `Limassol Marina, Kıbrıs`
    

-   **Hipotez:** James Hawkins, 26 Ekim saat 14:30'da Limassol Marina'daki ofisindeydi ve o fotoğrafı çekti.
    
-   **Test (Denizcilik İstihbaratı - MARINT):** Analist, **`MarineTraffic`** platformunu açar.
    
-   **Eylem:** "Playback" (Tekrar Oynat) özelliği kullanılır. Konum `Limassol Marina` ve tarih/saat `26 Ekim 2024, 14:30` (UTC'ye çevrilerek) olarak ayarlanır.
    
-   **BULGU (ŞAŞIRTICI ANI):** `MarineTraffic` kaydı, o tarih ve saatte, devasa ve benzersiz (örn. yeşil gövdeli) **"MV Evergreen" konteyner gemisinin**, tam olarak "SecureData Solutions Ltd." şirketinin ofisinin bulunduğu rıhtımın önünden geçmekte olduğunu gösterir.
    
-   **Nihai Doğrulama (IMINT):** Analist, Adım 1'deki "belirsiz" fotoğrafa geri döner. Pencere yansımasındaki o "belirsiz lekenin", `MarineTraffic`'ten silüeti doğrulanan **"MV Evergreen" gemisinin gövdesi** ile mükemmel bir şekilde eşleştiğini fark eder.
    

**5\. Aşama: Finansal Analiz ve Görselleştirme (FININT)**

Artık kimliği ve konumu (hem dijital hem fiziksel olarak) doğrulanan hedefin finansal izleri incelenir:

-   **`Blockchair`** kullanılarak BTC cüzdanının işlem geçmişi incelenir. Paranın bir karıştırıcıya (mixer) gittiği, ancak cüzdana ilk test fonunun KYC (Müşterini Tanı) gerektiren `Coinbase` gibi bir borsadan geldiği görülür.
    
-   Bu karmaşık ilişki ağı (E-posta -> Sızıntı IP -> Şirket -> MARINT ile Doğrulanan Konum -> BTC Cüzdanı -> KYC'li Borsa), **`Maltego`** kullanılarak görselleştirilir. Bu, hedefin birden fazla kritik OpSec hatasını gösteren ve davayı sonuçlandıran somut bir analitik ürün (rapor) oluşturur.
    

___

### Bilgilendirme

Burada önerilen tüm kaynaklar, yöntemler ve araçlar bilgilendirme amaçlıdır. Bunları daha detaylı öğrenmek için kendi araştırmanızı yapınız. OSINT konusunda gelişmek istiyorsanız, alternatif senaryoları incelemeli, uygulamalı ve daha derin araştırmalar yapmalısınız.
