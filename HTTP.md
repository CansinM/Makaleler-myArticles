# HTTP Nedir?

**HTTP (HyperText Transfer Protocol)**, World Wide Web’in temel iletişim protokolüdür ve web tarayıcıları ile web sunucuları arasında veri iletişimini sağlar. İstemci-sunucu modeli üzerine kuruludur: İstemci (örn. tarayıcı) bir HTTP isteği gönderir, sunucu bu isteğe uygun bir HTTP yanıtı döndürür.  

HTTP, **stateless (durumsuz)** bir protokoldür – yani her istek-yanıt bağımsızdır, sunucu önceki isteklerin bilgisini tutmaz; bu da web’in ölçeklenebilirliğini artırır. İstek ve yanıt mesajları **basit metin formatındadır** (başlık ve gövde bölümleriyle), bu da insanların daha iyi okuyup anlamasını mümkün kılar.  

HTTP, **uygulama katmanı** bir protokoldür ve genellikle **TCP** üzerinden çalışır (HTTPS için **TLS ile şifrelenmiş TCP** kullanılır). Bir HTTP istemcisi bir **URL’ye** istek yaptığında, sunucuyla bir **TCP bağlantısı** kurulur, istek mesajı gönderilir ve sunucudan gelen yanıt alınır; tarayıcı bu yanıtı işleyerek kullanıcıya sonucu gösterir.  

İlk tasarlandığında, her isteğin ayrı bağlantı açıp kapattığı **bağlantısız** bir iletişim modeli vardı. Ancak **HTTP/1.1** ile **kalıcı bağlantılar** desteği geldiğinden, çoğunlukla bir TCP bağlantısı üzerinde birden çok istek art arda gönderilebilir hale gelmiştir.  

HTTP, başlangıçta yalnızca **hipermetin (HTML) iletimi** için tasarlanmış olsa da, **geliştirilebilir yapısı** sayesinde resimler, videolar, ses dosyaları gibi her türlü medyanın transferinde ve **web servislerinin (API’lerin) haberleşmesinde** de temel araç haline gelmiştir.

---

# HTTP Kapsamları

**HTTP protokolü**, günümüzde internet üzerindeki veri alışverişinin omurgasını oluşturur. Özellikle **web sayfalarının yüklenmesi** ve **web servislerinin (REST API’lerin) iletişimi** HTTP üzerinden gerçekleşir. **Web tarayıcıları, arama motorları ve e-posta istemcileri** gibi pek çok uygulama, sunucularla iletişim kurmak için HTTP’yi kullanır.  

Web’de yaptığımız her işlem – bir **sayfa görüntüleme, form gönderme, dosya indirme** gibi – **HTTP istek/yanıt mekanizması** üzerinden yürütülür. HTTP’nin geliştirilip **standart hale getirilmesi**, internet üzerindeki **bilgiye erişimi ve paylaşımı** kolaylaştırarak **World Wide Web’in yaygınlaşmasında** temel bir rol oynamıştır.  

HTTP protokolü, yalnızca **tarayıcı ve web uygulamaları arasındaki iletişimde değil**, aynı zamanda **mobil uygulamaların sunucularla haberleşmesi** ve **Nesnelerin İnterneti (IoT) cihazlarının veri göndermesi** gibi birçok farklı alanda da kullanılır.  

Örneğin:  
- **Bir mobil uygulama**, arka planda **REST API çağrıları** yaparak verileri güncelleyebilir.  
- **Bir akıllı cihaz**, sunucusuna **telemetri verileri** gönderirken yine HTTP protokolünü kullanabilir.  

Kısacası, HTTP, **web ve web dışı ortamlarda** istemci ile sunucu arasında **standart bir iletişim dili** olarak kritik bir rol oynar.  

Bu önemi şu örneklerden anlayabiliriz:  
- **Bir web sitesine eriştiğinizde**, tarayıcınız sunucudan üç haneli HTTP durum kodları ve içerikler alır.  
- **Arama motoru botları**, HTTP üzerinden siteleri tarar ve dizine ekler.  
- **CDN (İçerik Dağıtım Ağları)** gibi ara katmanlar, önbellekleme işlemlerini HTTP mekanizmalarıyla gerçekleştirir.  

Modern internet uygulamalarının büyük bir bölümü **HTTP olmadan çalışamaz hale gelmiştir**. Nitekim, *“HTTP olmasaydı, küresel ağ (WWW) var olamazdı”* demek, abartı sayılmaz.

---

# HTTP/1.1, HTTP/2 ve HTTP/3 Karşılaştırmaları

İlk web protokolü olan **HTTP**, yıllar içinde performans ve güvenlik ihtiyaçlarına cevap verebilmek için **evrim geçirmiştir**. Günümüzde yaygın olarak üç ana sürüm kullanılmaktadır: **HTTP/1.1, HTTP/2 ve en yeni nesil HTTP/3**.  

HTTP’nin temel semantiği (istek yöntemleri, durum kodları, başlıklar vb.) bu sürümler arasında büyük ölçüde aynı kalmıştır. Ancak farklar, **iletim katmanındaki teknik iyileştirmelerden** kaynaklanmaktadır. Aşağıda bu sürümlerin karşılaştırması yapılmıştır.  

## HTTP/1.1 (1997)  

- **Metin tabanlı** bir protokoldür ve her TCP bağlantısı üzerinde **aynı anda yalnızca tek bir isteği işleyebilir**.  
- **Head-of-line blocking** sorunu yaşanır: Bir istek tamamlanmadan sonraki istekler işlenemez.  
- Tarayıcılar, birden çok paralel TCP bağlantısı açarak bu kısıtı aşmaya çalışır, ancak bu durum **ağ ve sunucu üzerinde ek yük oluşturur**.  
- **Kalıcı bağlantılar (keep-alive)** ve **chunked transfer encoding** gibi iyileştirmeler sunulmuştur.  
- **Host başlığı**, tek bir IP adresi üzerinde **birden fazla sanal sunucu (virtual host)** barındırmaya olanak tanır.  
- **Önbellek kontrolü için gelişmiş HTTP başlıkları** eklenmiştir.  
- **HTTPS, TLS/SSL ile opsiyonel olarak sağlanır**. Çoğu web sitesi **port 443 üzerinden TLS ile** veya **port 80 üzerinden TLS olmadan** çalışabilir.  
- **Gerçek anlamda paralel istek işleme mümkün değildir**.  

## HTTP/2 (2015)  

- **HTTP/1.1’in performans sınırlamalarını** çözmek için tasarlanmıştır.  
- **Metin tabanlı yerine ikili format (binary framing) kullanır**.  
- **Multiplexing desteği** ile **tek bir TCP bağlantısı üzerinden birden fazla isteğin aynı anda iletimine** olanak tanır.  
- **Header sıkıştırma (HPACK algoritması)** sayesinde gereksiz başlık verileri minimize edilerek iletim yükü azaltılmıştır.  
- **Önceliklendirme mekanizması**, istemcinin kritik kaynakları öncelikli almasına izin verir.  
- **Server push desteği** ile **sunucu, istemci talep etmeden bazı kaynakları gönderebilir**.  
- **HTTP/2 bağlantıları genellikle TLS (HTTPS) üzerinden gerçekleştirilir**.  
- **TCP kullanmaya devam ettiği için** paket kaybı durumunda tüm paralel istekleri etkileyen bir blokaj yaşanabilir.  

## HTTP/3 (2022)  

- **QUIC protokolü** üzerine inşa edilmiştir ve **TCP yerine UDP tabanlıdır**.  
- **Multiplexing**, TCP seviyesinde değil, QUIC üzerinde sağlanır.  
- **Paket kaybı durumunda sadece ilgili akış bekler, diğerleri etkilenmez** (HTTP/2’de tüm paralel istekler bekleyebilirdi).  
- **Daha hızlı bağlantı kurulumu** sağlar, çünkü **TCP’nin üçlü el sıkışma mekanizmasını (3-way handshake) ortadan kaldırır**.  
- **TLS 1.3 şifrelemesi zorunludur** ve **0-RTT ile gecikme minimize edilir**.  
- **Bağlantı kopmalarında hızlı yeniden bağlanma desteği** sunar (mobil cihaz ağ değiştirdiğinde bağlantı devam eder).  
- **Henüz tam yaygınlaşmamıştır**, bazı **ağ cihazları ve eski sistemler** QUIC trafiğini desteklemeyebilir.  

---

## HTTP Sürümlerinin Karşılaştırma Tablosu  

| Özellik         | HTTP/1.1 | HTTP/2 | HTTP/3 |
|---------------|---------|--------|--------|
| **Çıkış Yılı** | 1997    | 2015   | 2022   |
| **Bağlantı Türü** | TCP     | TCP    | QUIC (UDP) |
| **Metin/İkili Format** | Metin   | İkili  | İkili  |
| **Multiplexing** | ❌ Yok  | ✅ Var | ✅ Var |
| **Head-of-Line Blocking** | ✅ Var  | ✅ TCP seviyesinde | ❌ Yok (QUIC ile çözüldü) |
| **Önbellek ve Sıkıştırma** | Temel  | HPACK (Header sıkıştırma) | QPACK (Gelişmiş sıkıştırma) |
| **Şifreleme (TLS)** | Opsiyonel | Genellikle zorunlu | Zorunlu (TLS 1.3) |
| **Bağlantı Hızı** | Yavaş (TCP handshake) | Orta (TLS+TCP) | Hızlı (0-RTT, QUIC) |
| **Sunucu Push** | ❌ Yok  | ✅ Var | ✅ Var |
| **Mobil Uyum** | Zayıf  | Orta  | Güçlü (Bağlantı kopmaları sorun yaratmaz) |
| **Destek Durumu** | Yaygın | Yaygın | Giderek artıyor |

---

**Sonuç:**  
HTTP protokolü, zaman içinde **güvenlik, hız ve verimlilik açısından önemli iyileştirmeler geçirmiştir**. **HTTP/1.1**, temel web iletişiminde kritik bir rol oynadı ancak paralel işlem kısıtları nedeniyle **HTTP/2’ye** geçiş sağlandı. **HTTP/2**, multiplexing ile performansı artırsa da **TCP’nin sınırlamalarına bağlı kaldı**. **HTTP/3**, **UDP tabanlı QUIC protokolü ile yeni bir çağ başlatarak** mobil cihazlar, medya akışı ve düşük gecikmeli iletişim için ideal bir çözüm sundu.  

HTTP/3’ün tam olarak yaygınlaşması biraz zaman alabilir ancak **modern web için en hızlı ve güvenli HTTP sürümü olma potansiyeline sahiptir**.

---

# Güvenlik Protokolleri (HTTPS, TLS, SSL ve Diğer Mekanizmalar)

**HTTPS**, **HTTP protokolünün şifreli versiyonudur**. HTTP iletişimi, **TLS/SSL** adı verilen bir güvenlik katmanı üzerinden geçirilerek korunur. Bu sayede, istemci ile sunucu arasındaki veriler **üçüncü taraflar tarafından okunamaz hale gelir**.  

HTTP, verileri **düz metin olarak** ilettiği için **ağ trafiği izlenebilir** ve hassas bilgiler çalınabilir. Örneğin:  
- **Şifresiz bir HTTP bağlantısında**, gönderilen **şifreler** veya **kredi kartı bilgileri** ağ üzerindeki kötü niyetli kişilerce görülebilir.  
- **HTTPS kullanıldığında** ise iletişim **şifrelenir, bütünlük korunur** ve **karşı tarafın kimliği doğrulanır**.  

Bu nedenle günümüzde:  
- **Bankacılık ve e-ticaret siteleri** başta olmak üzere **tüm kritik web siteleri ve API’ler** **HTTPS** kullanır.  
- **Google**, HTTPS kullanımını bir **sıralama faktörü** olarak değerlendirir.  
- **Modern tarayıcılar**, HTTPS olmayan siteleri **"Güvenli Değil"** şeklinde işaretler.  

---

## **TLS ve SSL: Şifreleme Katmanı**

**HTTPS’in temelini TLS protokolü oluşturur.**  

- **TLS (Transport Layer Security)**, eski adıyla **SSL (Secure Sockets Layer)**, istemci ile sunucu arasında **şifreli bir iletişim kanalı kurmayı sağlayan** protokoldür.  
- **SSL 3.0** sürümünden sonra daha güvenli hale getirilerek **TLS 1.0** olarak yeniden adlandırılmıştır.  
- Günümüzde en yaygın sürümler **TLS 1.2** ve **TLS 1.3**’tür.  

Bir sunucuya **HTTPS** ile bağlanıldığında:  
1. **Sunucu**, tarayıcıya **dijital sertifikasını** sunar.  
2. Bu sertifika, güvenilir bir **Sertifika Otoritesi (CA)** tarafından imzalanmış olmalıdır.  
3. **Tarayıcı, sertifikanın geçerliliğini kontrol eder**:  
   - Güvenilir bir CA tarafından imzalanmış mı?  
   - Alan adı sertifikayla eşleşiyor mu?  
   - Sertifikanın süresi geçmiş mi? 
4. **Sertifika doğrulandıktan sonra, istemci ile sunucu arasında "TLS el sıkışması" (handshake) başlar**.  

---

## **TLS El Sıkışması (TLS Handshake)**
TLS el sıkışma süreci şu adımlardan oluşur:  

1. **Tarayıcı (istemci)**, **"Client Hello"** mesajıyla **desteklediği şifreleme algoritmalarını** sunucuya bildirir.  
2. **Sunucu (server)**, **"Server Hello"** mesajıyla **kullanacağı şifreleme yöntemini ve sertifikasını** gönderir.  
3. **Tarayıcı, sertifikayı doğrular** ve bir **ön-master anahtarını şifreleyerek** sunucuya yollar.  
4. **Sunucu, bu veriyi çözerek ortak bir oturum anahtarı elde eder.**  
5. **Tüm HTTP verileri artık bu oturum anahtarı ile simetrik olarak şifrelenir.**  

🔹 **TLS 1.3 ile bu süreç optimize edilmiştir:**  
- **Önceki TLS sürümlerinde 2-3 round-trip süren handshake**, artık **tek bir round-trip’te** tamamlanmaktadır.  
- **0-RTT** özelliği sayesinde bağlantı daha hızlı kurulur.  

---

## **HTTPS ve Dijital Sertifikalar**

- **SSL/TLS sertifikaları**, genellikle web sitesi sahipleri tarafından güvenilir otoritelerden (CA) satın alınır.  
- **Sertifika türleri** şunlardır:  
  - **Domain Validation (DV)** → Yalnızca alan adının kontrol edildiğini gösterir.  
  - **Extended Validation (EV)** → Şirkete ait ek kimlik bilgileri içerir, tarayıcıda şirket adı yeşil bar olarak görüntülenebilir.  
- **Sertifikalar, ortadaki adam saldırılarına (MITM) karşı koruma sağlar**.  

💡 Örneğin, tarayıcı **"example.com"** için bir sertifika aldığında, sertifika alan adıyla eşleşmelidir. Aksi halde **güvenlik uyarıları** görüntülenir.

---

## **HTTP Güvenliğini Artıran Mekanizmalar**

🔹 **HSTS (HTTP Strict Transport Security)**  
- **Bir sitenin yalnızca HTTPS üzerinden erişilmesini zorunlu kılar**.  
- Sunucu, **Strict-Transport-Security** başlığı göndererek tarayıcıya, **"Beni şu kadar süre boyunca sadece HTTPS üzerinden iste"** der.  
- Tarayıcı, **HTTP üzerinden gelen istekleri otomatik olarak HTTPS’e yönlendirir**.  
- **Protokol düşürme saldırılarına** karşı koruma sağlar.  

🔹 **Content Security Policy (CSP)**  
- **XSS (Cross-Site Scripting) saldırılarını önlemeye yardımcı olur**.  
- **Hangi içeriklerin nereden yüklenebileceğini** sınırlar.  

🔹 **X-Frame-Options**  
- **Clickjacking saldırılarını engeller**.  
- **Başka sitelerin iframe içinde sayfanızı gömmesini önler**.  

🔹 **X-Content-Type-Options**  
- **Tarayıcının MIME türlerini tahmin etmesini engeller**.  
- **MIME tipi saldırılarını önler**.  

🔹 **Güvenli Çerezler (Secure & HttpOnly Cookies)**  
- **Çerezler (cookies), Set-Cookie başlığı ile tarayıcıya gönderilir**.  
- **Secure flag** → Çerezler **yalnızca HTTPS üzerinden gönderilir**.  
- **HttpOnly flag** → Çerezlere **JavaScript tarafından erişilmesini engeller**.  
- **Bu önlemler, cookie çalınması riskini azaltır**.  

---

# HTTP Yöntemleri (Metotları)

**HTTP protokolü**, istemcinin sunucu üzerinde hangi işlemi gerçekleştirmek istediğini belirtmek için çeşitli **istek yöntemleri (metotları)** tanımlar. Her HTTP yöntemi, farklı bir işlem için kullanılır ve belirli kurallara sahiptir.  

Aşağıda en yaygın **HTTP metotları** ve **amaçları** açıklanmaktadır:  

---

## **1. GET**  
- **Belirtilen bir kaynaktan veri almak için kullanılır**.  
- **Tarayıcıdaki sayfa istekleri genellikle GET ile yapılır**.  
- **GET istekleri gövde içermez**, veriler **URL içindeki sorgu parametreleriyle** iletilir.  
- **Sunucuda değişiklik yapmamalıdır**, yani **güvenli (safe)** ve **idempotent** kabul edilir.  
- **Örnek:**  
  - Bir web sayfasını yüklemek.  
  - Bir API’dan veri çekmek → `/users?name=John`.  

---

## **2. POST**  
- **Sunucuya veri göndermek veya yeni bir kaynak oluşturmak için kullanılır**.  
- **Form verilerinin gönderilmesi, bir API'ye yeni kayıt eklenmesi gibi işlemler POST ile yapılır**.  
- **Veriler URL yerine isteğin gövdesinde taşınır**.  
- **POST idempotent değildir**, yani **aynı POST isteği birden fazla kez yapılırsa** yinelenen işlemler oluşabilir.  
- **Örnek:**  
  - Kullanıcı kaydı oluşturmak → `/users` (JSON verisi ile birlikte).  
  - Bir ödeme işlemi başlatmak.  

---

## **3. PUT**  
- **Belirtilen bir URI'deki kaynağı tamamen güncellemek veya oluşturmak için kullanılır**.  
- **İstemci, gönderdiği veriyle kaynağın mevcut içeriğini tamamen değiştirir**.  
- **PUT idempotent’tir**, yani **aynı PUT isteği birden fazla kez yapılırsa, sonuç değişmez**.  
- **Örnek:**  
  - `/products/123` URL'sine PUT isteği gönderildiğinde, ürün bilgileri tamamen yenilenir.  

---

## **4. DELETE**  
- **Belirtilen kaynağı sunucudan silmek için kullanılır**.  
- **DELETE idempotent’tir**, yani aynı DELETE isteği tekrarlandığında, silinen bir kaynağın tekrar silinmesi mümkün olmaz (genellikle 404 döner).  
- **Örnek:**  
  - `/users/123` → Kullanıcıyı silmek.  

---

## **5. PATCH**  
- **Bir kaynağın kısmi olarak güncellenmesi için kullanılır**.  
- **PUT’un aksine, yalnızca değiştirilecek alanlar gönderilir**.  
- **PATCH idempotent değildir**, yani aynı değişiklik birden fazla kez yapılırsa sonuç değişebilir.  
- **Örnek:**  
  - `/users/123` → Sadece e-posta adresini güncellemek.  

---

## **6. HEAD**  
- **GET metoduna benzer, ancak sadece HTTP başlıklarını döndürür, gövde içermez**.  
- **Bir kaynağın var olup olmadığını veya metadata bilgilerini kontrol etmek için kullanılır**.  
- **Örnek:**  
  - Bir dosyanın var olup olmadığını kontrol etmek.  

---

## **7. OPTIONS**  
- **Sunucuya, belirli bir kaynak için hangi HTTP metotlarının ve başlıkların desteklendiğini sormak için kullanılır**.  
- **Genellikle CORS (Cross-Origin Resource Sharing) preflight isteklerinde tarayıcılar tarafından otomatik olarak gönderilir**.  
- **Sunucu, yanıtında `Allow: GET, POST, ...` gibi desteklediği metodları listeler**.  
- **Örnek:**  
  - `/users/123` → Desteklenen metodları öğrenmek için OPTIONS isteği yapmak.  

---

## **8. CONNECT**  
- **İstemci ile hedef sunucu arasında bir tünel açmak için kullanılır**.  
- **Özellikle HTTP proxy sunucularında, TLS trafiğini yönlendirmek için kullanılır**.  
- **Örnek:**  
  - HTTPS üzerinden bir siteye bağlanırken proxy sunucusunun TLS tüneli kurması.  

---

## **9. TRACE**  
- **HTTP isteğinin, sunucuya ulaşana dek geçtiği ara noktaları ve değişiklikleri test etmek için kullanılır**.  
- **Sunucu, isteği aynen geri döndürerek, istemciye herhangi bir değişiklik olup olmadığını gösterir**.  
- **Güvenlik nedeniyle genellikle devre dışı bırakılır (XST - Cross Site Tracing saldırısı nedeniyle)**.  
- **Örnek:**  
  - Sunucuya gelen isteğin, istemci tarafından aynen geri alınıp alınmadığını görmek.  

---

## **RESTful API Tasarımlarında HTTP Metotları**  

REST mimarisinde **CRUD işlemleri** HTTP metodlarına haritalanır:  

| CRUD İşlemi  | HTTP Metodu |
|-------------|------------|
| **Create**  | POST       |
| **Read**    | GET        |
| **Update**  | PUT / PATCH |
| **Delete**  | DELETE     |

Sunucu, her **isteğe uygun HTTP durum kodları** ile yanıt döndürmelidir:  

- **200 OK** → Başarılı GET isteği.  
- **201 Created** → Yeni kaynak oluşturuldu (POST, PUT).  
- **204 No Content** → Başarıyla işlendi, ancak yanıt içeriği yok (DELETE, PUT).  
- **400 Bad Request** → Hatalı veya eksik istek.  
- **404 Not Found** → İstenen kaynak bulunamadı.  
- **500 Internal Server Error** → Sunucu hatası.  

---

# HTTP Başlıkları (Headers) ve Önbellekleme Mekanizmaları

HTTP istek ve yanıt mesajları, sadece ham veriyi değil, o veriye dair ek bilgileri taşıyan **başlıklar (headers)** içerir. Her bir HTTP başlığı, **isim-değer** çiftinden oluşur ve mesajın başlık bölümünde iletilir. İstemci ve sunucu, bu başlıklar aracılığıyla istek ve yanıtlar hakkında ek bilgiler paylaşır. Örneğin:

* `Content-Type` başlığı, sunucunun gönderdiği içeriğin **MIME türünü** (`text/html`, `application/json` gibi) belirtir.
* `Content-Length` başlığı, gövdenin boyutunu **bayt cinsinden** ifade eder.
* `User-Agent` başlığı, isteği yapan **tarayıcının tanım bilgilerini** taşır.

HTTP/1.1'de başlık isimleri büyük-küçük harf duyarsız metin olarak iletilirken, HTTP/2 ile başlıklar **binary hale getirilmiş** ve performans için **sıkıştırılmıştır**. Başlıklar, amaçlarına göre **istemci başlıkları (request headers)** ve **sunucu başlıkları (response headers)** olarak ayrılır. Örneğin:

* `Accept-Language` bir istemci başlığıdır ve tarayıcının tercih ettiği **dili** iletir.
* `Set-Cookie` ise bir sunucu başlığıdır ve tarayıcıya bir **cookie** depolatır.

Ayrıca, `Cache-Control`, `Date` gibi hem istek hem de yanıtta görülebilen özel **genel başlıklar** da bulunur. Başlıklar, protokolün esnekliğini artıran en önemli unsurlardandır. Kimlik doğrulama (`Authorization: Bearer ...`), yetkilendirme, içerik anlaşması (`Accept` başlıkları) ve önbellekleme gibi birçok mekanizma başlıklar üzerinden yürütülür.

## Önbellekleme (Caching) Mekanizmaları

Önbellekleme (caching) mekanizmaları, HTTP'de başlıklar yardımıyla kontrol edilir. Önbelleğin amacı, aynı kaynağa yapılan tekrarlı isteklerde sunucuyu tekrar yormadan, daha önce alınmış bir yanıtı saklayıp tekrar kullanmaktır. Örneğin, tarayıcınız bir resmi ilk kez indirdiğinde onu diskinde veya belleğinde tutabilir. Aynı resim kısa süre içinde tekrar istenirse, ağdan indirmek yerine hızlıca yerelden yükler. Bu, hem kullanıcı için daha hızlı bir deneyim sağlar, hem de sunucu yükünü ve bant genişliği tüketimini azaltır. HTTP, önbellek kontrolü için birkaç önemli başlık tanımlar:

* **`Cache-Control`:** En önemli önbellek başlığıdır. İstek ve yanıtlarda kullanılabilir. "Direktif" denilen parametreler alır. Örneğin, `Cache-Control: max-age=600` yanıtı, ilgili kaynağın 600 saniye (10 dakika) boyunca taze kabul edilebileceğini belirtir. Diğer yaygın direktifler şunlardır:
    * `no-cache`: Önbelleğe alındıysa bile her seferinde sunucuyla doğrula.
    * `no-store`: Hiç saklanmasın.
    * `public`: Herkes önbelleğe alabilir (proxy'ler dahil).
    * `private`: Sadece tarayıcı kendi önbelleğine alabilir.
* **`Expires`:** HTTP/1.0'dan gelen bir başlıktır. Sunucu, yanıtı önbellekte tutmak için belirli bir son kullanma tarihi belirtebilir (GMT formatında). Örneğin, `Expires: Tue, 28 Feb 2023 22:22:22 GMT`. Tarayıcı bu tarihi geçmediyse içerik taze kabul edilir. HTTP/1.1 ile `Cache-Control` çıktığından beri, `Expires` çoğunlukla geri uyumluluk için bulunur ve `max-age` varken göz ardı edilir.
* **`ETag`:** "Entity Tag" anlamına gelir. Sunucunun bir kaynağın belirli bir sürümüne atadığı benzersiz bir kimliktir (genellikle bir hash veya sürüm numarası). Örneğin, bir dosyanın `ETag` değeri `"abc123"` olsun. Tarayıcı bu dosyayı önbelleğe aldığında `ETag`'ini saklar. Sonraki istekte sunucuya `If-None-Match: "abc123"` başlığıyla gider. Sunucu tarafta dosya değişmemişse `ETag` aynı kalır, bu durumda sunucu `304 Not Modified` yanıtı döner ve tarayıcıya önbelleğindekini kullanmasını söyler. Dosya değişmişse yeni `ETag` ile birlikte normal `200 OK` yanıtı gelir. `ETag`, çok hassas doğrulama sağlar (bayt düzeyinde değişiklik olsa bile anlaşılır).
* **`Last-Modified`:** Sunucu, kaynağın en son ne zaman değiştiğini tarih başlığı olarak iletebilir. Örneğin, `Last-Modified: Wed, 20 Jan 2023 16:20:22 GMT`. Tarayıcı bunu saklar ve sonraki istekte `If-Modified-Since` başlığı ile kendi bildiği son değişim zamanını sunucuya iletir. Sunucu, kaynağın o tarihten beri değişmediğini görürse yine `304 Not Modified` döndürür; değiştiyse yeni içeriği `200 OK` ile döndürür. `Last-Modified`, saniye çözünürlükte doğrulama sunar. `ETag` kadar hassas olmayabilir, ancak desteklemesi kolaydır. Genellikle `ETag` ile birlikte veya `ETag` yoksa alternatif olarak kullanılır.
* **`Vary`:** Bir kaynağın önbelleğe alınmasında hangi istek başlıklarının ayırt edici olduğunu belirtir. Örneğin, sunucu hem İngilizce hem Türkçe içerik döndürebilen bir sayfa için `Vary: Accept-Language` başlığını gönderebilir. Bu durumda tarayıcı, önbelleğinde bu sayfanın iki versiyonunu ayrı tutar: biri `Accept-Language: en` ile alınmış İngilizce versiyon, diğeri `Accept-Language: tr` ile alınmış Türkçe versiyon. `Vary` olmadan tarayıcı tek bir kopyayı önbelleğe alır ve farklı dil isteyen birine yanlış dili gösterebilirdi. Benzer şekilde, `Vary: Accept-Encoding` çoğunlukla sunucu cevabının sıkıştırılmış olup olmadığını ayırt etmek için kullanılır.

Yukarıdaki başlıklar sayesinde HTTP, önbellek mekanizmasını istemci ve proxy'ler ile koordineli bir şekilde çalıştırır. Örneğin, tarayıcı bir resmi ilk aldığında sunucu `Cache-Control: max-age=86400` (1 gün) göndermiş olsun. Tarayıcı 1 gün boyunca o resmi yeniden istemez, kendi önbelleğinden kullanır. 1 gün sonra kullanıcı tekrar resmi isterse, tarayıcı bu sefer sunucuya `If-Modified-Since` ile sorar. Sunucu tarafında resim güncellenmemişse, `304` ile hızlıca cevap verip "bendeki değişmedi, sende varsa kullan" der. Tarayıcı da önbelleğindeki (eski fakat sunucu onaylı) kopyayı gösterir, böylece ağdan resim indirilmemiş olur. Bu işlem, kullanıcıya sezdirilmeden milisaniyeler içinde gerçekleşir, sayfa hızlanır. Önbellekleme, doğru kullanıldığında web performansını ciddi oranda artırır: sunucu trafiğini azaltır, sayfa yükleme sürelerini düşürür ve çevrimdışı senaryolarda bile içerik gösterebilmeyi mümkün kılar.

## İçerik Sıkıştırma

Önbellekleme dışında, HTTP başlıklarıyla yapılan optimizasyonlardan biri de içerik sıkıştırmadır. İstemci, sunucuya desteklediği sıkıştırma formatlarını `Accept-Encoding` başlığı ile bildirir (`gzip`, `deflate`, `br` gibi). Sunucu, içerik uygunsa cevabı örneğin `gzip` olarak sıkıştırıp `Content-Encoding: gzip` başlığıyla gönderir. Bu sayede metin içerikler genellikle %70-80 oranında daha küçük aktarılabilir, bu da daha hızlı yükleme demektir. Tarayıcı sıkıştırılmış içeriği alıp açarak kullanıcıya sunar. Modern web trafiğinde metin tabanlı içeriklerin neredeyse tamamı `gzip` veya `brotli` ile sıkıştırılmış olarak iletilir.

---

# HTTP Durum Kodları ve Anlamları

HTTP durum kodları, sunucunun bir isteğe verdiği yanıtı sayısal olarak ifade eden üç haneli kodlardır. İstemci (tarayıcı veya API istemcisi), yapılan isteğin başarılı olup olmadığını veya bir yönlendirme/hata olup olmadığını bu kodlar sayesinde anlar. HTTP durum kodları 5 ana kategoriye ayrılır:

## 1xx - Bilgilendirici (Informational)

* İsteğin alındığını ve işlenmeye devam edildiğini gösteren geçici bilgilendirme yanıtlarıdır.
* Bu kodlar tarayıcıda genellikle kullanıcıya gösterilmez.
* **Örnekler:**
    * **100 Continue:** İstemcinin büyük bir isteği göndermeden önce sunucudan "devam et, uygun" onayı almasını sağlar.
    * **101 Switching Protocols:** İstemcinin protokol değiştirme talebinin sunucu tarafından kabul edildiğini belirtir (örneğin, WebSocket protokolüne geçişte).
    * **103 Early Hints:** Tarayıcıya sayfa yüklenirken önden bazı ipuçları vermek için kullanılır.

## 2xx - Başarılı (Success)

* İstek başarıyla işlendiğinde dönen kodlardır.
* **Örnekler:**
    * **200 OK:** İsteğin sorunsuz gerçekleştiğini ifade eder.
    * **201 Created:** Genellikle bir POST isteğinin sonucu sunucuda yeni bir kaynak oluşturulduysa döner.
    * **202 Accepted:** İsteğin alındığını ama henüz işlenmediğini (asenkron işlem) gösterir.
    * **204 No Content:** İsteğin başarıyla işlendiğini ancak dönecek içerik olmadığını belirtir (genelde DELETE veya PUT sonrası kullanılabilir).
    * **206 Partial Content:** Parçalı içerik iletimi için kullanılır.

## 3xx - Yönlendirme (Redirection)

* İstenen kaynağın başka bir yerde olduğunu veya farklı bir şekilde erişilmesi gerektiğini belirtir.
* Tarayıcı bu kodları alır almaz genellikle otomatik olarak yeni adrese yönlenir.
* **Örnekler:**
    * **301 Moved Permanently:** Kaynağın kalıcı olarak yeni bir URI'ye taşındığını gösterir.
    * **302 Found (Moved Temporarily):** Kaynağın geçici olarak başka bir yerde olduğunu belirtir.
    * **304 Not Modified:** İstemci bir kaynağın zaten kendisinde olduğunu sorduğunda, sunucu değişmediğini anlar ve 304 döner.
    * **307 Temporary Redirect:** Aynı metodu koruyarak geçici yönlendirme yapar.
    * **303 See Other:** Tipik olarak bir POST sonrası GET ile almaya yönlendirir.

## 4xx - İstemci Hataları (Client Errors)

* İstemcinin hatalı bir istek yaptığı durumlarda döner.
* İsteğin sunucu tarafından işlenemediğini veya işlenmesinin reddedildiğini gösterir.
* **Örnekler:**
    * **400 Bad Request:** İstemci isteğinde bir hata olduğunu belirtir (sözdizimi hatası, geçersiz parametre vb.).
    * **401 Unauthorized:** İsteğin kimlik doğrulaması gerektirdiğini ifade eder.
    * **403 Forbidden:** İsteğin anlaşıldığını ancak yetki olmadığından reddedildiğini belirtir.
    * **404 Not Found:** İstemcinin istediği kaynağın sunucuda bulunamadığını gösterir.
    * **405 Method Not Allowed:** İstenen kaynağın o HTTP metodunu desteklemediğini belirtir.
    * **408 Request Timeout:** İstemcinin isteği çok uzun sürdüyse kesildiğini gösterir.
    * **429 Too Many Requests:** İstemcinin kısa sürede çok fazla istek yaptığını (rate-limit aşıldığını) belirtir.

## 5xx - Sunucu Hataları (Server Errors)

* İsteğin sunucu tarafında başarısız olmasıyla ortaya çıkan hatalardır.
* İstemci doğru bir istek yapmıştır ama sunucu tarafında bir sorun engel olmuştur.
* **Örnekler:**
    * **500 Internal Server Error:** Genel bir sunucu hata mesajıdır.
    * **501 Not Implemented:** İstenen özelliğin sunucuda desteklenmediğini belirtir.
    * **502 Bad Gateway:** Bir ara sunucu (proxy veya gateway) üzerinden gelen isteklerde, ara sunucunun asıl sunucudan geçerli yanıt alamadığında verdiği hatadır.
    * **503 Service Unavailable:** Sunucunun geçici olarak hizmet veremediğini gösterir.
    * **504 Gateway Timeout:** Bir ara sunucunun asıl sunucudan zamanında yanıt alamadığı durumları ifade eder.

#### HTTP Durum Kodlarının Önemi

* HTTP durum kodları, tarayıcıların ve istemcilerin sunucu ile iletişiminin dilidir.
* Geliştiriciler için de durum kodları vazgeçilmez bir teşhis aracıdır.
* SEO açısından da önemlidir.

---

# HTTP'nin Web Performansı Üzerindeki Etkileri

HTTP protokolünün tasarımı ve sürümleri, web'in hızı ve verimliliği üzerinde doğrudan etkilidir. İlk dönemlerde HTTP/1.x ile bir web sayfasını yüklemek, her bir kaynak (CSS, JS, resim vb.) için ayrı ayrı istekler ve bağlantılar gerektiriyordu. HTTP/1.1'de persistent connection özelliği gelse de aynı anda bir bağlantı üzerinde tek istek işlenebildiği için tarayıcılar genelde birden fazla paralel bağlantı açmak zorunda kalıyordu (genelde tarayıcı başına aynı domaine 6 bağlantı limiti vardı). Bu, sunucu ve istemciye ekstra maliyet getiren bir durumdu; özellikle TLS kullanıldığında her bağlantı ayrı handshake yaptığı için gecikmeler artıyordu. Performansı artırmak için web geliştiricileri değişik teknikler kullandılar: Sprite imajlar (birden çok küçük ikonu tek resimde birleştirip tek seferde indirme), CSS/JS birleştirme (dosya sayısını azaltma) veya domain sharding (varlıkları farklı alan adlarına bölerek daha fazla paralel bağlantı açılmasını sağlama) gibi yöntemler HTTP/1.1'in kısıtlarını aşmaya yönelikti. Ancak bunlar karmaşık çözümlerdi ve bazı yan etkilere sahipti.

## HTTP/2'nin Getirdiği İyileştirmeler

HTTP/2'nin gelişiyle, web performansında önemli iyileşmeler mümkün oldu. Multiplexing sayesinde tarayıcı, aynı bağlantıda tüm dosya isteklerini paralel yapabildiği için yukarıda bahsedilen "her bağlantıda tek istek" kuralı ortadan kalktı. Bu, sayfa yüklenirken kritik kaynakların bloklanmadan inmesine imkan tanıdı. Örneğin eski HTTP/1.1 ile bir CSS dosyası indirirken diğer istekler sırada beklerken, HTTP/2 ile CSS, JS ve resimler aynı anda akmaya başlayabilir. Bunun sonucunda özellikle yüksek gecikmeli bağlantılarda sayfa yükleme süreleri belirgin ölçüde azaldı. Ayrıca HTTP/2'nin header sıkıştırması, çok sayıda küçük isteğin olduğu senaryolarda (örn. 100 adet küçük resmi yüklerken her birinde tekrarlayan header'lar gönderilmesi) büyük bant genişliği tasarrufu sağladı. Sunucu itmesi (server push), bazı durumlarda gerekli kaynakların istemci istemeden gönderilmesiyle ilk yükleme süresini azaltabildi (her ne kadar tarayıcı desteği ve kullanım alanı kısıtlı olsa da). Özetle HTTP/2, protokol seviyesinde pek çok optimizasyon yaparak web performansını arttırmıştır. Günümüz sitelerinde eski alışkanlıklar (varlık birleştirme gibi) yerine HTTP/2'nin çoklu istek avantajını kullanacak stratejiler tercih edilir – örneğin ayrı ayrı küçük dosyalar tutmak, zira hepsi tek bağlantıda paralel gelebiliyor.

## HTTP/3 ve QUIC'in Avantajları

HTTP/2'nin getirdiği iyileştirmelere rağmen, taşıma katmanı olarak TCP'nin limitleri devam ediyordu. Özellikle paket kaybı olan ortamlarda, HTTP/2'nin tek bir bağlantı üzerindeki tüm akışları bir TCP bağlantısına mahkum etmesi bir dezavantajdı: TCP seviyesinde bir paket kaybı olduğunda, o paketin ait olduğu akış dışındaki akışlar da beklemek zorunda kalıyordu. Hatta ekstrem durumlarda paket kaybı çok fazlaysa, paralel birden çok TCP bağlantısı olan HTTP/1.1'in daha iyi performans verdiği bile görülebiliyordu. İşte HTTP/3 bu sorunu çözmek üzere UDP tabanlı QUIC'i devreye soktu. QUIC, her bir akışı ayrı güvenilir kanallar gibi ele alıp, kayıp veya gecikme durumunu akış bazında yönettiğinden, özellikle yüksek gecikme (ör. uydu interneti) veya mobil ağ koşullarında HTTP/3 bağlantıları daha akıcıdır. Google ve Cloudflare gibi şirketlerin gerçek dünya testlerinde, HTTP/3'ün HTTP/2'ye kıyasla sayfa yükleme süresini belirli koşullarda yüzlerce milisaniye düşürdüğü gözlemlenmiştir. Örneğin Cloudflare'ın yaptığı bir karşılaştırmada, HTTP/3 destekleyen bir siteyi yüklerken HTTP/3 bağlantısının HTTP/2'ye göre anlamlı ölçüde daha hızlı olduğu (küçük bir site için ~200ms, içerik ağırlıklı bir site için ~300ms kazanım) raporlanmıştır. Bu kazanımlar mesafe arttıkça (ör. kullanıcı ile sunucu arası coğrafi mesafe büyüdükçe) daha da belirgin hale gelmektedir.

## Diğer Performans Optimizasyonları

HTTP'nin sunduğu diğer performans özellikleri de geliştiriciler için önemlidir. Önbellekleme başlıklarının doğru kullanımı, performansa çok büyük katkı sağlar (bkz. önceki bölüm). Bir kez alınan ve sık değişmeyen bir kaynağı (CSS, imaj vs.) uzun süre önbellekte tutmak, sayfa yenilemelerinde veya sonraki ziyaretlerde hız artışı sağlar. İçerik sıkıştırma da aynı şekilde, sayfa boyutlarını dramatik biçimde düşürerek daha hızlı iletim sağlar – modern web'de HTTP üzerinden gelen metin içeriklerin neredeyse tamamı gzip veya brotli ile sıkıştırılmıştır. Tarayıcılar ve sunucular bunu otomatik halleder ve kullanıcı daha küçük paketler aldığı için sayfalar daha hızlı yüklenir.

## TLS ve Performans

HTTP/1.1 döneminde TLS şifrelemesi, ekstra el sıkışma gecikmeleri ve CPU yükü demekti; ancak günümüzde TLS performansı oldukça iyileşmiştir. TLS 1.3 ile el sıkışma süresi kısaldı (1-RTT veya 0-RTT), kriptografik işlemler donanım hızlandırma ile destekleniyor. Ayrıca HTTP/2 ve HTTP/3, genellikle TLS zorunlu olarak geldiğinden, protokolün performans iyileştirmeleri ile güvenlik beraber kazanılmış oldu. Yani artık "HTTPS yavaşlatır" argümanı geçerli değil – aksine H2/H3 kullanan HTTPS siteleri, eski HTTP/1 kullanıp şifreleme yapmayan sitelerden çoğu durumda daha hızlı bile olabiliyor. Kaldı ki güvenlik, performanstan ödün verilecek bir alan olmaktan çıktı; hem tarayıcılar hem sunucular şifrelemeyi optimize edecek şekilde evrim geçirdi.

## Sonuç

Özetle, HTTP protokolündeki gelişmeler web'in hızını doğrudan etkilemiştir. HTTP/1.1'den HTTP/2'ye geçişle birlikte web sayfalarının yüklenme sürelerinde ciddi azalmalar görüldü. HTTP/3 ile ağ koşullarına dayanıklılık ve gecikme konularında ek iyileşmeler sağlandı. Doğru kullanılan önbellek ve sıkıştırma politikaları sayesinde gereksiz veri iletimi azaltıldı. Bu ilerlemeler, kullanıcılara daha hızlı ve akıcı bir web deneyimi, sunuculara da daha verimli kaynak kullanımı olarak yansıdı. Web geliştiricileri için önemli olan, HTTP'nin bu özelliklerini ve araçlarını (durum kodları, başlıklar, yeni protokol avantajları vb.) tam anlamıyla kullanarak hem performansı hem güvenliği en iyi hale getirmektir. Böylece protokol seviyesindeki kazanımlar, uygulama seviyesinde de gerçek bir fark yaratacaktır.

---

## Kaynakça

1. [HTTP Nedir? - Haktan Bozer](https://haktanbozer.com.tr/nedir/http-nedir/)
2. [HTTP/1.1, HTTP/2 ve HTTP/3 Karşılaştırması - Java Code Geeks](https://www.javacodegeeks.com/2023/03/http-1-1-vs-http-2-vs-http-3-key-differences.html)
3. [HTTP/3 Performans Analizi - Request Metrics](https://requestmetrics.com/web-performance/http3-is-fast/)
4. [HTTP/2 ve HTTP/3 Arasındaki Farklar - Hiz Hosting](https://www.hizhosting.com/blog/http-2-ve-http-3-protokolleri-arasindaki-farklar/)
5. [HTTP/2 ve HTTP/3 Performans Karşılaştırması - Hiz Hosting](https://www.hizhosting.com/blog/http-2-ve-http-3-performans-karsilastirmasi/)
6. [HTTP/3 - Wikipedia](https://en.wikipedia.org/wiki/HTTP/3)
7. [Mozilla Developer Network (MDN) - HTTP Genel Bakış](https://developer.mozilla.org/en-US/docs/Web/HTTP/Overview)
8. [Mozilla Developer Network (MDN) - HTTP Headers](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers)
9. [Mozilla Developer Network (MDN) - HTTP Caching](https://developer.mozilla.org/en-US/docs/Web/HTTP/Caching)
10. [HTTP Durum Kodları - Türkçe Wikipedia](https://tr.wikipedia.org/wiki/HTTP_durum_kodlar%C4%B1)
11. [HTTP Durum Kodları ve Anlamları - Sempeak](https://www.sempeak.com/blog/http-durum-kodlari-ve-anlamlari)
12. [HTTP ve Güvenlik - HTTP Strict Transport Security (HSTS)](https://en.wikipedia.org/wiki/HTTP_Strict_Transport_Security)
13. [TLS ve SSL Nedir? - Türk Ticaret](https://www.turkticaret.net/blog/tls-nedir-nasil-calisir-https-tls-ve-ssl/)
14. [TLS Güvenliği - Altunhost](https://www.altunhost.com/blog/tls-nedir/)
15. [HTTP Metotları - Bayram Alacam](https://www.bayramalacam.com/2024/02/10/http-metotlari-temel-bilgiler-ve-kullanim-alanlari/)
16. [HTTP Headers ve Önbellekleme - Protocol Guard](https://protocolguard.com/resources/what-are-http-headers/)
17. [HTTP Headers - Bunny.net](https://bunny.net/academy/http/what-are-http-request-and-response-headers/)
18. [HTTP/1 vs HTTP/2 vs HTTP/3 - Dev.to](https://dev.to/accreditly/http1-vs-http2-vs-http3-2k1c)
19. [CoreSEO - HTTP Durum Kodları](https://www.coreseo.io/blog/http-durum-kodlari-nelerdir)
20. [Web Performansında HTTP Caching - Request Metrics](https://requestmetrics.com/web-performance/http-caching/)


