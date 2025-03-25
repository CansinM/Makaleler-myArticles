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

![Unicode vs UTF](https://i.sstatic.net/6C0C6.png)

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

