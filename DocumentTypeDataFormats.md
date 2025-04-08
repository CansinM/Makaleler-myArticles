# 1. Temel Kavramlar

Bilgi teknolojileri dünyasında dijital veriler, belirli kurallar ve yapılar çerçevesinde temsil edilir. Bu verilerin en temel yapı taşları ise **bit**, **byte** ve **sayı sistemleri**dir. Aşağıda bu kavramlara ve bilgisayar sistemlerinde kullanım alanlarına detaylı bir şekilde değinilmiştir.

---

## Bit ve Byte

Bir **bit** (*binary digit*), bilgisayarda verinin en küçük birimidir ve yalnızca iki durumu ifade eder: **0 veya 1**. Bu iki durum, dijital devrelerde elektrik sinyalinin varlığı veya yokluğu, doğru/yanlış, açık/kapalı gibi karşılıklarla yorumlanabilir. Bitler, bilgisayar işlemcilerinde **transistörler** aracılığıyla işlenir. Bir transistör, elektrik akımını kontrol eden yarı iletken bir yapıdır ve dijital bilgi akışını düzenleyen temel bileşenlerden biridir.

Bir **byte**, 8 bitlik bir veri grubudur. Yani bir byte, 2⁸ = **256 farklı değeri** temsil edebilir. Byte'lar, karakterleri, renkleri, komutları ve daha birçok veriyi temsil etmekte kullanılır.

---

## Sayı Sistemleri

Dijital sistemlerde farklı sayı sistemleri kullanılarak veriler daha verimli ve anlamlı biçimlerde temsil edilir. Bu sayı sistemlerinin her biri, farklı tabanlara dayanır ve belirli kullanım alanlarına sahiptir.

---

### İkili (Binary) Sayı Sistemi

**Binary sistem**, yalnızca iki rakam içerir: **0 ve 1**. Bilgisayarların donanım düzeyinde anlayabildiği tek sayı sistemi budur. Her bir binary basamak, bir **bit** olarak adlandırılır.

**Örnek Kullanımlar:**

- Elektrik sinyalleri (var/yok)
- Mantıksal işlemler (True/False)
- Sayısal işlemcilerde temel veri işleme

---

### Sekizlik (Octal) Sayı Sistemi

**Octal sistem**, 0’dan 7’ye kadar toplam **8 farklı rakam** içerir (0-7). Genellikle üç bitlik binary gruplarının daha okunabilir bir formatta gösterilmesi amacıyla kullanılır.

**Örnek Kullanımlar:**

- Linux dosya izinleri (örneğin: `755`, `700`)
- Düşük seviyeli programlama işlemleri

---

### Onluk (Decimal) Sayı Sistemi

**Decimal sistem**, günlük hayatta da kullandığımız 0'dan 9’a kadar **10 rakamı** içerir (0-9). Bilgisayarlarda kullanıcı arayüzlerinde, IP adreslerinde ve renk kodlarında sıkça karşımıza çıkar.

**Örnek Kullanımlar:**

- IPv4 adresleri (örneğin: `192.168.1.1`)
- RGB renk değerleri (örneğin: `255, 255, 0`)

---

### Onaltılık (Hexadecimal) Sayı Sistemi

**Hexadecimal sistem**, 16 farklı sembolden oluşur: **0-9** arasındaki rakamlar ve **A-F** arasındaki harfler  
(**A:10, B:11, C:12, D:13, E:14, F:15**). Bu sistem, dört bitlik binary gruplarını daha kompakt ve okunabilir biçimde göstermek için tercih edilir.

**Örnek Kullanımlar:**

- Renk kodları (örneğin: `#3C7A9E`)
- Bellek adresleme
- IPv6 adresleri
- Karakter kodlama sistemlerinde (örneğin: Unicode karakterleri)

![Binary,Decimal, Hexadecimal](https://miro.medium.com/v2/resize:fit:772/1*z3FENZfyAEoC_133kTra3w.jpeg)

---
# 2. Karakter Kodlama Setleri

Bilgisayar sistemlerinde verilerin doğru bir şekilde işlenebilmesi için metinsel veriler belirli kodlama standartlarına göre temsil edilir. Bu kodlama sistemleri, karakterlerin sayısal karşılıklarını belirleyerek dijital ortamda kullanılabilir hale getirir. Aşağıda karakter kodlama tarihçesi, temel standartlar ve Unicode dönüşümü detaylı şekilde ele alınmaktadır.

---

## Karakter Kodlama (Encoding)

**Karakter kodlama**, harf, rakam, sembol gibi karakterlerin bilgisayarın anlayabileceği **ikili (binary) formatlara** dönüştürülmesidir.  
Bu işlem sayesinde farklı platformlar arasında metinlerin doğru bir şekilde iletilmesi ve yorumlanması mümkün olur.

---

## ASCII Standardı

**ASCII** (*American Standard Code for Information Interchange*), 1960’lı yıllarda geliştirilen ilk yaygın karakter kodlama sistemlerinden biridir.

- 7 bitlik yapısıyla toplam **128 karakter** tanımlar.  
- Bu karakterlerin **33’ü kontrol karakteri** (0–31) ve **95’i yazdırılabilir karakterlerdir** (32–126).  
- ASCII, İngilizce alfabesi için yeterlidir ancak Türkçe gibi özel karakterler içeren diller için yetersiz kalır.

![ASCII Table](https://media.geeksforgeeks.org/wp-content/uploads/20240304094301/ASCII-Table.png)

---

## Latin-1 (ISO-8859-1)

**Latin-1**, ISO (International Organization for Standardization) tarafından geliştirilen ve ASCII'nin genişletilmiş hali olan bir karakter setidir.

- 8 bitlik (1 byte) yapıya sahiptir ve **256 karakter** içerir.  
- **Batı Avrupa dillerini destekler** ancak **Türkçe karakterleri içermez**.  
- Yaygın olarak `ISO-8859-1` veya **ISO Latin-1** olarak adlandırılır.

---

## Latin-5 (ISO-8859-9)

**Latin-5**, **Türkçe diline uyumlu** bir karakter setidir.

- `ISO-8859-9` olarak da bilinir.  
- 8 bitlik yapıda olup **256 karakter** içerir.  
- İlk 128 karakter, ASCII ile aynıdır; ikinci 128 karakterde **Türkçe karakterler** yer alır.

---

## Latin-9 (ISO-8859-15)

**Latin-9**, Latin-1’in güncellenmiş bir versiyonudur.

- `ISO-8859-15` olarak bilinir.  
- **Euro (€)** simgesi gibi yeni sembolleri içerir.  
- **Türkçeye tam olarak uyumlu değildir**.  
- 8 bitlik yapıda, **256 karakter** içerir.

---

## Windows-1254

**Windows-1254**, Microsoft tarafından geliştirilmiş, **Türkçe karakterlere uyumlu** bir karakter setidir.

- 8 bitlik, **256 karakter** içerir.  
- ASCII karakter seti ile **uyumludur**.  
- Özellikle **Windows tabanlı uygulamalar** ve bazı web sistemleri tarafından kullanılmıştır.

---

## Unicode Standardı

Tek bir karakter setinin tüm dilleri destekleyememesi, karakter karışıklıklarına ve veri kayıplarına yol açmıştır.  
Bu sorunu çözmek amacıyla **Unicode standardı** geliştirilmiştir.

- Unicode, tüm dillerin karakterlerini kapsayan **evrensel bir kodlama sistemidir**.  
- Unicode **Konsorsiyumu** tarafından geliştirilir ve sürekli güncellenir.  
- Amaç, farklı platformlar, diller ve sistemler arasında **karakter uyumluluğunu sağlamak** ve **veri bütünlüğünü korumaktır**.

---

### Unicode Mimarisi

- Unicode, **17 düzlem (plane)** içerir. Her düzlem **65.536 kod noktası** barındırır.  
- Toplamda **1.114.112 farklı karakter** tanımlanabilir.  
- Her karakter, **Kod Noktası (Code Point)** adı verilen benzersiz bir sayısal değerle temsil edilir.  
- Kodlama genellikle **onaltılık (hexadecimal)** sistemle yapılır ve `U+0045`, `U+10FFFF` gibi gösterilir.

**Kod Yapısı Örneği:**  
`U+00C7 → Ç harfi`  
- `00` : Düzlem numarası  
- `00C7` : Kod noktası

| Düzlem Numarası | Onaltılık Aralık | Resmi Adı                                        | Kısa Açıklama                                                              |
|-----------------|-----------------|--------------------------------------------------|----------------------------------------------------------------------------|
| 0               | U+0000 - U+FFFF | Temel Çok Dilli Düzlem (Basic Multilingual Plane - BMP) | En sık kullanılan karakterler, modern dillerin çoğu.                        |
| 1               | U+10000 - U+1FFFF| Ek Çok Dilli Düzlem (Supplementary Multilingual Plane - SMP) | Tarihi yazı sistemleri, müzik ve matematik sembolleri, emoji.               |
| 2               | U+20000 - U+2FFFF| Ek İdeografik Düzlem (Supplementary Ideographic Plane - SIP) | Nadir kullanılan Çince, Japonca ve Korece ideografları.                    |
| 3               | U+30000 - U+3FFFF| Üçüncül İdeografik Düzlem (Tertiary Ideographic Plane - TIP) | Daha da nadir kullanılan Çince, Japonca ve Korece ideografları.             |
| 4-13            | U+40000 - U+DFFFF| Atanmamış (Unassigned)                             | Gelecekteki karakterler için ayrılmış.                                    |
| 14              | U+E0000 - U+EFFFF| Ek Özel Amaçlı Düzlem (Supplementary Special-purpose Plane - SSP) | Dil etiketleri, varyasyon seçiciler gibi özel amaçlı karakterler.         |
| 15              | U+F0000 - U+FFFFF| Ek Özel Kullanım Alanı - A (Supplementary Private Use Area - A) | Kullanıcı tanımlı karakterler için ayrılmış.                               |
| 16              | U+100000 - U+10FFFF| Ek Özel Kullanım Alanı - B (Supplementary Private Use Area - B) | Kullanıcı tanımlı karakterler için ayrılmış.                               |

---

## Unicode Konsorsiyumu

**Unicode Konsorsiyumu**, Unicode standardını geliştiren ve sürdüren kuruluştur.

- Üyeleri arasında **Microsoft**, **Google**, **Apple** gibi teknoloji şirketleri yer alır.  
- Konsorsiyumda yazılımcılar, dilbilimciler ve çeşitli alanlardan uzmanlar görev alır.

---

## UTF Kodlama Türleri

Unicode karakterlerini sistemlere aktarabilmek için farklı kodlama biçimleri geliştirilmiştir.  
Bu biçimlere **UTF (Unicode Transformation Format)** denir.

---

### UTF-32

- **Sabit uzunluktadır**: Her karakter **4 byte (32 bit)** yer kaplar.  
- Kodlaması kolaydır ancak **bellek kullanımı yüksektir**.

---

### UTF-16

- **Değişken uzunluktadır**: Karakterler **2 veya 4 byte** ile kodlanır.  
- **Uygun bellek kullanımı sağlar**, ancak bazı durumlarda **çözümlenmesi zordur**.

---

### UTF-8

- **En çok kullanılan Unicode kodlama biçimidir**.  
- **Değişken uzunluktadır**: Karakterler **1 ile 4 byte** arasında temsil edilir.  
- **ASCII ile geriye uyumludur** ve **gereksiz bellek kullanımını azaltır**.  
- Web, e-posta, API veri formatlarında **yaygın olarak kullanılır**.

| Karakter Sistemi | UTF-32                 | UTF-16             | UTF-8        |
|------------------|------------------------|--------------------|--------------|
| Uzunluk          | 4 Byte (32 Bit)        | 2 veya 4 Byte (16 veya 32 Bit) | 1-4 Byte (8-32 Bit) |
| S                | `00000000 00000000` <br> `00000000 01010011` | `00000000 01010011` | `01010011`   |
| Hello            | 20 Byte (160 Bit)      | 10 Byte (80 Bit)   | 5 Byte (40 Bit) |
| ©                | `00000000 00000000` <br> `00000000 10101001` | `00000000 10101001` | `11000010 10101001` |
| 😎               | `00000000 00000001` <br> `11110110 00001110` | `11011000 00111101` <br> `11011110 00001110` | `11110000 10011111` <br> `10011000 10001110` |

| UNICODE                                                  | UTF-32, UTF-16 ve UTF-8                                                               |
|----------------------------------------------------------|---------------------------------------------------------------------------------------|
| Standarttır                                              | Unicode standardının uygulanış biçimleridir                                           |
| Karakter ve sembolleri temsil eden bir karakter kodlama standardıdır | Unicode standardını uygulayan karakter kodlama sistemleridir                               |
| Her karakter benzersiz sayılarla (code point) ifade edilir <br> Örneğin: U+0042, U+005A, U+1F353 gibi | Farklı uzunluktaki byte bloklarıyla karakterler temsil edilir. <br> Örneğin: 01000001, 00000000 01000101 gibi |
| Tüm dillere ait karakter ve sembolleri bir arada toplayan bir standarttır. | Unicode standardındaki karakterleri bilişim sistemlerinde depolamak ve iletmek için oluşturulmuş sistemlerdir. |

---

# 3. Doküman Tipleri ve Veri Formatları

Bilgisayar sistemlerinde bilgilerin saklanması, işlenmesi ve paylaşılması farklı doküman tipleri ve veri formatları aracılığıyla gerçekleştirilir.  
Bu formatlar, verilerin nasıl temsil edileceğini, nasıl yorumlanacağını ve hangi amaçlarla kullanılacağını belirler.  
Bu bölümde yaygın doküman türleri, veri formatları ve serileştirme kavramı detaylı şekilde ele alınmaktadır.

---

## Doküman Tipi Nedir?

Doküman tipi, bir belgenin içeriğini, yapısını ve biçimini tanımlayan kavramdır.  
Verilerin nasıl görüntüleneceği ve işleneceği hakkında bilgi verir.  
Çoğu zaman dosya uzantılarıyla ilişkilidir (`.html`, `.xml`, `.json`, `.md`, `.sql` gibi).

**Yaygın Doküman Tipleri:**

- **İşaretleme dilleri**: `.html`, `.xml`, `.md`, `.latex`  
- **API ve konfigürasyon dosyaları**: `.xml`, `.json`, `.yaml`  
- **Veritabanı ve yedekleme**: `.sql`, `.db`  
- **Günlük dosyaları**: `.log`  
- **Dokümantasyon ve kılavuzlar**: `.md`, `.pdf`, `.docx`

---

## Düz Metin (Plain Text)

Düz metin dosyaları, biçimlendirme içermeyen, sadece karakterlerden oluşan sade metin dosyalarıdır.

- Genellikle `.txt` uzantısı kullanılır.  
- Yazı tipi, boyutu, rengi gibi stil özellikleri içermez.  
- Resim, tablo, bağlantı gibi zengin içerikleri barındırmaz.

**Kontrol karakterleri:**

- `\n` : Yeni satır  
- `\r` : Taşıma işareti  
- `\t` : Sekme  
- `\b` : Geri silme  
- `\f` : Sayfa kesme

---

## İşaretleme Dilleri (Markup Languages)

İşaretleme dilleri, metin belgelerini yapılandırmak ve biçimlendirmek için kullanılan dillerdir.  
Genellikle etiketler (tags) içerir.

- Her etiket, içeriğin nasıl gösterileceğini belirtir.  
- Yaygın örnekler: **HTML**, **XML**, **Markdown**, **LaTeX**

**Örnek Etiketler:**

- `<p>` : Paragraf  
- `<h1>` : Başlık  
- `<img>` : Görsel  
- `<a>` : Bağlantı

---

## Veri Formatı

Veri formatları, verilerin dijital olarak nasıl depolandığını ve iletildiğini tanımlar.  
Sistemler arasında veri alışverişi yapılmasını sağlar ve organize, taşınabilir, okunabilir yapı sunar.

**Yaygın veri formatları:**

- JSON  
- XML  
- YAML  
- CSV

---

## Veri Serileştirme (Serialization)

Veri serileştirme, bir nesnenin ya da veri yapısının **byte dizisine dönüştürülmesi** sürecidir.  
Bu işlemle veriler disk üzerinde saklanabilir veya ağ üzerinden başka sistemlere iletilebilir.

**Serileştirme Süreci:**

- Nesne/Veri → Byte akışı (serialization)  
- Byte akışı → Nesne/Veri (deserialization)

**Kullanım Alanları:**

- Veritabanına veri kaydetme  
- Dosyaya yazma  
- Web servisleri ile veri alışverişi  
- API iletişimi  

**Kullanılan formatlar:** JSON, XML, YAML, BSON

![VeriSerialiation](https://upload.wikimedia.org/wikipedia/commons/f/f4/Serialization.jpg)

---

## HTML (HyperText Markup Language)

Web sayfalarının yapısını tanımlayan işaretleme dilidir.  
**Programlama dili değildir.**

**Sayfa bölümleri örnekleri:**

- `<header>`, `<nav>`, `<section>`, `<footer>`

**Sık kullanılan HTML etiketleri:**

- `<h1>`, `<h2>`, `<h3>` : Başlıklar  
- `<p>` : Paragraf  
- `<img>` : Resim  
- `<a>` : Bağlantı  
- `<ul>`, `<ol>`, `<li>` : Listeler  
- `<form>`, `<input>`, `<select>` : Form elemanları

---

## XML (Extensible Markup Language)

- Metin tabanlı ve okunabilir bir işaretleme dilidir.  
- Verileri saklamak, taşımak ve yapılandırmak için kullanılır.  
- API’ler, veri transferi, konfigürasyon dosyalarında sıkça tercih edilir.

---

## JSON (JavaScript Object Notation)

- Hafif, metin tabanlı, programlama dillerinden bağımsız bir veri formatıdır.  
- Nesne ve dizi yapıları içerir.  
- API’lerde, web ve mobil uygulamalarda yaygın olarak kullanılır.  
- Sosyal medya entegrasyonlarında da tercih edilir.

---

## YAML (YAML Ain’t Markup Language)

- Yapılandırma ve veri paylaşımı için kullanılan sade ve okunabilir bir veri formatıdır.  
- Etiket kullanılmaz, **girintiler (indentation)** ile yapı tanımlanır.  
- JSON ve XML’e göre **daha okunaklıdır**.  
- **DevOps**, konfigürasyon dosyaları, mikroservis altyapılarında yaygındır.

---

## Markdown

- Metin belgelerini biçimlendirmek amacıyla geliştirilmiş **hafif bir işaretleme dili**dir.  
- HTML ve PDF gibi biçimlere kolayca dönüştürülebilir.  
- Biçimlendirme için `#`, `*`, `-`, `[ ]`, `![]()` gibi işaretler kullanılır.

---

## SQL (Structured Query Language)

- İlişkisel veritabanlarında kullanılan **standart sorgu dilidir**.  
- Veri oluşturma, okuma, güncelleme ve silme (CRUD) işlemleri yapılabilir.

**SQL Dosyaları:**

- `.sql` uzantısıyla kaydedilir.  
- Veritabanı yedekleme, geri yükleme, tablo ve şema tanımları içerir.  
- Metin editörleri ve veri tabanı IDE’leri ile açılabilir.

---

## CSV (Comma-Separated Values)

- Veriler **virgüllerle ayrılmış satırlar** halinde saklanır.  
- Excel, veritabanı ve analiz araçlarında yaygın olarak kullanılır.

**Alternatif ayırıcılar:** `;`, `\t`, `|`, `:` gibi karakterler

---

## LOG Dosyaları

- Uygulama, sistem veya ağ olaylarını kayıt altına alan **günlük dosyalarıdır**.  
- Metin tabanlıdır ve genellikle şu formatta tutulur:  
  `Tarih - Saat - Olay Türü - Açıklama`

**Kullanım Alanları:**

- Hata izleme (error logs)  
- Uygulama izleme  
- Web sunucu kayıtları  
- Güvenlik olayları

---

# 4. API (Application Programming Interface)

Modern yazılım dünyasında sistemlerin birbiriyle iletişim kurabilmesi büyük önem taşır.  
Bu iletişim, genellikle farklı platformlarda çalışan uygulamaların veri alışverişinde bulunması ya da bazı işlevleri dışarıya açmasıyla gerçekleşir.  
İşte bu noktada **API** kavramı devreye girer.

---

## API Nedir?

**API (Application Programming Interface)**, Türkçesiyle **Uygulama Programlama Arayüzü**, yazılımların birbiriyle haberleşmesini sağlayan arayüzlerdir.

- Temel görevi, farklı uygulamalar arasında **veri alışverişini** ve **belirli işlevlerin dış sistemler tarafından kullanılmasını** mümkün kılmaktır.  
- API'ler, belirli bir sistemin veya uygulamanın işlevlerini dışa açarak, **diğer yazılımların bu işlevleri kullanabilmesine olanak tanır**.

---

## API’lerde XML ve JSON Kullanımı

API'ler, veri gönderimi ve alımı için genellikle **metin tabanlı veri formatlarını** kullanır.  
En yaygın kullanılan veri formatları: **XML** ve **JSON**.

- Karmaşık veri yapıları bile kolayca temsil edilebilir.  
- Farklı sistemler arasında **taşınabilir** hale gelir.

---

## Web API’ler

**Web API’leri**, internet üzerinden çalışan ve **HTTP/HTTPS** protokolleri ile erişilen API’lerdir.  
Günümüzde birçok yazılım sistemi bu tür API’leri kullanarak birbirine entegre olur.

**Yaygın Web API Türleri:**

- **RESTful API**:  
  Basit, hızlı ve hafif yapısıyla yaygın olarak kullanılır.  
  Genellikle **JSON** veya **XML** veri formatlarını destekler.

- **SOAP API**:  
  Daha katı kurallara sahiptir.  
  Özellikle **XML tabanlı** veri alışverişi için tercih edilir.  
  **Güvenlik ve doğrulama** konularında güçlüdür.

- **GraphQL**:  
  Kullanıcıya, hangi veriye ihtiyaç duyduğunu belirtme esnekliği sağlar.  
  Yalnızca **JSON formatında veri üretir ve tüketir**.

---

## API'nin Çalışma Yapısı

Bir API'nin temel çalışma prensibi **istemci (client)** ve **sunucu (server)** modeline dayanır:

1. **İstemci**, API’ye belirli bir istekte bulunur  
   (örneğin: ürün bilgisi sorgulama).
2. **API sunucusu**, isteği alır, işler ve sonucu uygun veri formatında  
   (genellikle **JSON** veya **XML**) istemciye geri gönderir.
3. **İstemci**, aldığı veriyi yorumlayarak kullanıcıya sunar veya kendi işlemlerinde kullanır.

Bu esnek yapı sayesinde;  
mobil uygulamalardan web sitelerine, IoT cihazlardan masaüstü yazılımlara kadar **birçok farklı sistem entegre** çalışabilir.

![API Structure](https://media.licdn.com/dms/image/v2/D5612AQF5552tf_aopg/article-cover_image-shrink_600_2000/article-cover_image-shrink_600_2000/0/1683632736875?e=2147483647&v=beta&t=svq3KPWaPWsorSEVmES9ytHbF38bN9kPkvDuSYjNAG8)

---

## API Kullanım Alanları

API'ler, yazılım dünyasının vazgeçilmez yapı taşlarındandır.  
Günümüzde sayısız alanda kullanılırlar:

- Web hizmetleri  
  *(hava durumu, döviz kuru, sosyal medya entegrasyonları)*

- Mobil uygulamalar  
  *(veri senkronizasyonu, konum servisleri)*

- Veri tabanı erişimi ve yönetimi

- E-ticaret sistemleri  
  *(ürün, stok ve sipariş bilgisi paylaşımı)*

- Ödeme sistemleri  
  *(banka API’leri, ödeme geçitleri)*

- Makine öğrenmesi ve yapay zeka servisleri

- IoT cihazları  
  *(cihaz kontrolü, veri toplama)*

---

# 5. XML (Extensible Markup Language)

**XML (Extensible Markup Language)**, verilerin **hiyerarşik ve anlamlı** bir biçimde temsil edilmesini sağlayan, **metin tabanlı bir işaretleme dilidir.**  
İlk olarak **SGML (Standard Generalized Markup Language)** yapısına dayandırılmış ve onun bir alt kümesi olarak geliştirilmiştir.

XML’in temel amacı, farklı sistemler arasında **platform bağımsız veri paylaşımını** mümkün kılmaktır.

---

## XML’in Temel Özellikleri

- **İnsan ve makine tarafından okunabilir** bir formattır.  
- Verileri **etiketler (tags)** ile yapılandırır.  
- **Kendi kendini tanımlayan** bir formattır; yani veri, anlamını taşıyan etiketiyle birlikte sunulur.  
- **DOM (Document Object Model)** sayesinde XML belgeleri programlama dilleriyle işlenebilir.  
- Belgeler **kontrollü ve kurallı** bir yapıya sahiptir.

---

## XML Yapısal Özellikleri

XML belgeleri, her zaman bir **kök (root) eleman** ile başlar ve iç içe geçmiş yapılarla (parent-child ilişkisi) **veri hiyerarşisi** oluşturulur.

#### XML Örnek Yapısı

Aşağıda, XML belgelerinde sıkça karşılaşılan iç içe geçmiş (nested) yapıların nasıl tanımlandığını gösteren bir örnek bulunmaktadır:

```xml
<root>
    <child1>
        <subelement1>Content 1</subelement1>
        <subelement2>Content 2</subelement2>
    </child1>
    <child1>
        <subelement3>Content 3</subelement3>
        <subelement4>Content 4</subelement4>
    </child1>
    <!-- Comment (Yorum satırı) -->
</root>
```

---

## XML’de Özel Karakterler

XML'de bazı karakterler doğrudan kullanılamaz çünkü belge yapısını bozabilir. Bu karakterler, özel kaçış dizileri ile temsil edilir:

| Karakter | XML Temsili  |
|----------|--------------|
| `<`      | `&lt;`       |
| `>`      | `&gt;`       |
| `&`      | `&amp;`      |
| `'`      | `&apos;`     |
| `"`      | `&quot;`     |

Bu özel karakterler, XML yapısının bozulmaması için **kaçış karakterleri** ile temsil edilir.

---

## Well-Formed ve Valid XML

- Bir XML belgesi **yapısal kurallara** uygunsa (örneğin tüm etiketler doğru kapanmışsa), bu belge **well-formed** olarak adlandırılır.
- Ek olarak belirli **kurallara veya şemalara** (DTD veya XSD) göre doğrulanabiliyorsa, belge **valid** kabul edilir.

---

## XML Veri Türleri

XML’in yapısı metin tabanlı olsa da, içerisinde tutulan veriler farklı veri türlerini temsil edebilir:

- Sayılar (`integer`, `decimal`)
- Metin (`string`, `character`)
- Tarih ve saat
- Boolean (`true` / `false`)

> Bu veri türleri genellikle **XSD şemaları** ile tanımlanır.

---

## Örnek XML Belgesi

```xml
<kitap>
    <baslik>Yapay Zeka</baslik>
    <yazar>İbrahim Yılmaz</yazar>
    <yayinevi>Bilim Yayınları</yayinevi>
    <fiyat>75.90</fiyat>
</kitap>
````
---

## Doküman Tipi Tanımlama (DTD)

**DTD (Document Type Definition)**, XML belgelerinin yapısını tanımlamak için kullanılan ilk standartlardan biridir.  
DTD ile şunlar tanımlanabilir:

- Hangi etiketlerin kullanılabileceği  
- Etiketlerin birbirleriyle olan ilişkileri  
- Öznitelikler (attributes) ve veri tipleri

> DTD sayesinde XML belgeleri **yapısal olarak kontrol edilebilir** ve **doğrulanabilir** hale gelir.

Tanımlar şu iki biçimde yer alabilir:

- **Internal DTD** → XML dosyasının içerisinde tanımlanır.  
- **External DTD** → Harici bir `.dtd` dosyası olarak tanımlanır ve XML dosyasına referans verilir.

### DTD’de Tanımlanabilecek Yapılar:

| Yapı          | Açıklama                          |
|---------------|-----------------------------------|
| `<!ELEMENT>`  | Element tanımlamaları             |
| `<!ATTLIST>`  | Öznitelik (attribute) tanımlamaları |
| `<!ENTITY>`   | Varlık (entity) tanımlamaları     |
| `<!NOTATION>` | Notasyon tanımlamaları            |

---

## XML Schema Definition (XSD)

**XSD**, XML belgelerinin yapısını ve içeriklerini daha ayrıntılı tanımlamak için kullanılan modern bir şemalandırma sistemidir.  
**W3C (World Wide Web Consortium)** tarafından geliştirilmiştir.

> XSD, DTD’ye göre **daha güçlü**, **esnek** ve **veri türlerini detaylı tanımlama** yeteneğine sahiptir.

### XSD ile Tanımlanabilen Yapılar:

- Element isimleri ve veri tipleri  
- Gerekli veya opsiyonel alanlar  
- Öznitelik tanımlamaları  
- İç içe geçmiş yapılar  
- Sayısal aralıklar, karakter uzunlukları  
- Düzenli ifade (regex) ile özel kısıtlamalar

> XSD tanımı da XML dosyası içinde veya ayrı bir `.xsd` dosyasında yapılabilir.

---

## XML Kullanım Alanları

XML, birçok platform, uygulama ve sektörde yaygın olarak kullanılmaktadır:

- **API sistemleri** (özellikle **SOAP tabanlı** sistemler)  
- **E-ticaret platformları** (ürün verisi güncellemeleri, varyantlar)  
- **Pazar yeri entegrasyonları** (örneğin: XML feed dosyaları)  
- **Sitemap dosyaları** (arama motoru optimizasyonu - SEO)  
- **Ofis dosyaları** (Office Open XML: `.docx`, `.xlsx`)  
- **RSS beslemeleri** (haber siteleri, bloglar vb.)  
- **Veri paylaşım sistemleri** (döviz kurları, hava durumu, namaz vakitleri)  
- **Veri tabanı entegrasyonları**  
- **Bankacılık ve finans sistemleri**  
- **Web sunucu konfigürasyonları** (Apache, Nginx, IIS)  
- **Mail sunucuları** (Postfix, Microsoft Exchange yapılandırmaları)  
- **Android Studio** (layout ve kaynak dosyaları XML tabanlıdır)

---

# 6. JSON (JavaScript Object Notation)

**JSON (JavaScript Object Notation)**, veri saklama ve veri alışverişi amacıyla kullanılan, hafif, okunabilir ve platform bağımsız bir veri formatıdır.  
Başlangıçta JavaScript tabanlı olarak geliştirilmiş olsa da, günümüzde neredeyse tüm programlama dilleri tarafından desteklenmektedir.

> JSON formatı, verileri **anahtar-değer çiftleri** ve **sıralı veri listeleri** şeklinde organize eder.

---

## JSON’un Temel Özellikleri

- Basit ve **insan tarafından okunabilir** bir yapıya sahiptir.  
- **Anahtar-değer (key-value)** çiftleriyle çalışır.  
- **Nesne (Object)** ve **dizi (Array)** yapısını destekler.  
- **UTF-8 karakter kodlamasını** kullanır.  
- Web tabanlı sistemler için **oldukça uygundur**.

---

## JSON Yapısal Özellikleri

JSON yapısı iki temel bileşenden oluşur:

### 1. Anahtar-Değer Çifti (Key-Value Pair)

``
"sehir": "İstanbul"
``
``
"plaka": 34
``
### 2. Sıralı Değer Listesi (Array):
``
"renkler": ["kırmızı", "beyaz", “siyah"]
``

---

### JSON Nesne ve Dizi Tanımı

- **JSON nesnesi** süslü parantez `{}` ile tanımlanır.  
- Anahtar-değer çiftleri arasında **virgül (`,`)** kullanılır.  
- **Dizi (Array)** ise köşeli parantez `[]` ile belirtilir.

### Örnek JSON Yapısı

Örnek JSON Yapısı:

```json
{
  "ad": "Murat",
  "no": 196,
  "hobiler": ["Okumak", "Yüzmek", "Gezmek"]
}
```

## Kurallar

- Anahtar isimleri mutlaka çift tırnak (`""`) içinde olmalıdır.
- Aynı nesne içinde aynı anahtar ismi birden fazla kez kullanılmamalıdır.
- JSON yapısı içindeki veriler farklı türlerde olabilir:

  ```json
  "futbolcu": ["Ali", 29, 1.88]
  ````
- Boş nesne: `{}`
- Boş dizi: `[]`

---

## JSON Kaçış Karakterleri (Escape Characters)

Bazı karakterler JSON içinde doğrudan kullanılamaz. Bu karakterler kaçış karakterleriyle temsil edilir:

| Karakter          | Kaçış Şekli |
|-------------------|--------------|
| "                 | \"           |
| \                 | \\           |
| /                 | \/           |
| Backspace         | \b           |
| New line          | \n           |
| Carriage Return   | \r           |
| Tab               | \t           |

---

## JSON Veri Türleri
JSON, aşağıdaki temel veri türlerini destekler:

- String (Metin): `"merhaba"`
- Number (Sayı): `42, 3.14`
- Boolean (Mantıksal): `true, false`
- Array (Dizi): `["elma", "armut", "muz"]`
- Object (Nesne): `{"ad": "Ali", "yas": 30}`
- null: `null`

---

## JSON Dosyası Oluşturma
JSON dosyaları genellikle .json uzantısıyla kaydedilir. Metin tabanlı olduğu için basit bir metin düzenleyiciyle oluşturulabilir. Ancak yapı hatalarına karşı bazı özel JSON editörleri veya IDE eklentileri kullanılabilir.

### Örnek: ogrenci.json
```json
{
    "isim": "Ayşe",
    "numara": 105,
    "bolum": "Bilgisayar Mühendisliği",
    "notlar": [90, 85, 78],
    "mezun": false
}
````

---

## JSON Kullanım Alanları
JSON, veri taşımak, saklamak ve yapılandırmak için pek çok alanda yaygın olarak kullanılmaktadır:

- API sistemleri: 
  - RESTful ve GraphQL API’lerde veri formatı olarak
- E-Ticaret: 
  - Ürün, kategori, sipariş bilgileri
- Pazar yeri entegrasyonları: 
  - Ürün akışları ve eşleşmeler
- Veri paylaşımı: 
  - Döviz kurları, hava durumu, film ve müzik verileri
- Veritabanı sistemleri: 
  - NoSQL veritabanlarında (MongoDB gibi)
- Finans sistemleri: 
  - İşlem ve kullanıcı kayıtları
- Konfigürasyon dosyaları: 
  - Web uygulamaları, framework ayarları
- IoT cihazları: 
  - Sensör verisi aktarımı, cihaz yönetimi

---

# 7. YAML (YAML Ain’t Markup Language)
YAML, okunabilirliği ön planda tutan, basit ve sade bir veri formatıdır. Adından da anlaşılacağı üzere, bir işaretleme dili değil, veri yapılarını sade bir biçimde ifade etmeye yarayan metin temelli bir formattır. Hiyerarşik veri yapılarının tanımlanmasında son derece kullanışlıdır.
YAML, özellikle yapılandırma dosyalarında ve konfigürasyon tanımlarında tercih edilen, esnek ve genişletilebilir bir sistem sunar.

## YAML’in Temel Özellikleri
- İnsan tarafından kolayca okunabilir.
- Hiyerarşik veri yapıları desteklenir.
- String, sayı, liste gibi farklı veri türlerini ifade edebilir.
- JSON ve XML’e alternatif olarak daha sade bir söz dizimine sahiptir.
- Girintilere dayalı yapısı sayesinde veri ilişkileri açık biçimde gösterilir.

## YAML Yapısal Özellikleri
- YAML’de yapılar girintiler yardımıyla oluşturulur. Alt-üst ilişki (hiyerarşi) girintilerle sağlanır.
- Genellikle 2 boşluk kullanılır.
- Boşluk kullanımı çok önemlidir. Hatalı girinti yapıları geçersiz dosyalara neden olabilir.
- String ifadeler için tırnak işareti zorunlu değildir, ancak özel karakterler içeriyorsa kullanılabilir.

**Örnekler:**
```yaml
ders: Kimya
ders: "Kimya"
ders: 'Bilişim Teknolojilerine Giriş'

no: 176
`````

**Liste (dizi) yapısı:**
```yaml
renkler:
  - Kırmızı
  - Beyaz
  - Siyah
`````

>YAML’de yorumlar # karakteri ile başlar

---

## YAML Veri Türleri
YAML şu temel veri türlerini destekler:

- Skaler (Scalar): Tekil veriler (string, sayı, boolean)
- Liste (Sequence): Sıralı veri dizileri (dizi)
- Anahtar-Değer Çifti (Mapping): Nesne benzeri yapılar (dictionary)

## YAML Dosyası Oluşturma
YAML dosyaları genellikle .yaml veya .yml uzantısı ile kaydedilir. Düz metin editörleriyle veya özel YAML editörleriyle oluşturulabilir. JSON’a göre daha sade ve okunaklı bir yapıya sahiptir.

### Örnek YAML Dosyası:
```yaml
kisi:
  ad: Zeynep
  yas: 28
  hobiler:
    - Müzik
    - Resim
    - Kamp
  universite:
    ad: İstanbul Teknik Üniversitesi
    bolum: Bilgisayar Mühendisliği
`````

---

## YAML Kullanım Alanları
YAML özellikle konfigürasyon dosyaları ve devops uygulamaları için yaygın olarak kullanılır:
- Yapılandırma uygulamaları:
  - Django (settings yapılandırmaları)
  - Jenkins (CI/CD konfigürasyonları)
  - Ansible (otomasyon senaryoları)
- Veri depolama ve aktarımı
- Docker Compose:
  - Ortam değişkenleri
  - Konteyner tanımlamaları
- Kubernetes:
  - Pod tanımları
  - Service ve Deployment tanımları
  
---

## JSON, XML ve YAML Karşılaştırması

| **Özellik**             | **JSON**                   | **XML**                    | **YAML**                    |
|----------------------|------------------------|------------------------|-------------------------|
| Okunabilirlik        | Orta                   | Düşük                  | Yüksek                  |
| Veri Yapısı          | Anahtar-Değer, Dizi    | Etiket yapısı          | Girinti ile hiyerarşi   |
| Dosya Boyutu         | Küçük                  | Büyük                  | Küçük                   |
| İnsan Okunabilirliği | Kısmen                 | Az                     | Yüksek                  |
| Destek               | Yaygın                 | Çok yaygın             | Özellikle DevOps'ta yaygın |
| Öğrenme Eğrisi       | Düşük                  | Yüksek                 | Düşük                   |

---

## Kaynakça

1. [BTK Akademi - Doküman Tipleri ve Veri Formatları](https://www.btkakademi.gov.tr/portal/course/dokuman-tipleri-ve-veri-formatlari-27901)
2. [Sayı Sistemleri Görseli](https://miro.medium.com/v2/resize:fit:772/1*z3FENZfyAEoC_133kTra3w.jpeg)
3. [ASCII Tablosu Görseli](https://media.geeksforgeeks.org/wp-content/uploads/20240304094301/ASCII-Table.png)
4. [Veri Formatları Karşılaştırması Görseli](https://i.sstatic.net/6C0C6.png)
5. [Serileştirme Görseli](https://upload.wikimedia.org/wikipedia/commons/f/f4/Serialization.jpg)
6. [API Genel Bakış](https://media.licdn.com/dms/image/v2/D5612AQF5552tf_aopg/article-cover_image-shrink_600_2000/article-cover_image-shrink_600_2000/0/1683632736875?e=2147483647&v=beta&t=svq3KPWaPWsorSEVmES9ytHbF38bN9kPkvDuSYjNAG8)
