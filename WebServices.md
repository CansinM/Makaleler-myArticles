# Client/Server (İstemci/Sunucu Modeli)

## Tanım ve Açıklama
İstemci/Sunucu (Client/Server) modeli, bir hizmeti talep eden istemci (client) ile bu talebi karşılayan sunucu (server) arasındaki iş bölümüne dayanan yaygın bir dağıtık uygulama mimarisidir. Bu modelde sunucu, belirli kaynakları veya hizmetleri ağ üzerinden paylaşır; istemci ise bu hizmetleri kullanmak için sunucuya istek gönderir. 

İstemci, sunucudan bir işlem veya veri talep ederek iletişimi başlatır; sunucu da gelen isteği işleyip uygun cevabı döndürür. Bu istek-cevap (request-response) etkileşimi sayesinde istemciler, sunucunun sunduğu hizmetlerden yararlanır ve sunucu da kendi kaynaklarını birden çok istemciyle paylaşabilir.

İstemci/Sunucu mimarisinde sunucu ve istemci rolleri belirgindir:
- **Sunucu**, bir veya daha fazla istemciye belirli bir hizmeti sağlar.
- **İstemci**, bu hizmetlere ihtiyaç duydukça istek gönderir.

Bu modelde, çoğunlukla tek bir sunucu çok sayıda istemciye aynı anda hizmet verebilir. Örneğin, bir web sunucusu aynı anda birçok tarayıcıdan gelen sayfa isteklerini yanıtlayabilir. İstemci ile sunucu arasındaki iletişim belirli protokoller çerçevesinde gerçekleşir; bu protokoller iletişimin dilini ve kurallarını tanımlar. Örneğin:
- Bir **e-posta istemcisi**, sunucuyla **SMTP, IMAP** gibi protokoller üzerinden iletişim kurar.
- Bir **web tarayıcısı (istemci)**, web sunucusuna **HTTP/HTTPS** protokolü ile istek gönderir.
- Bir **veritabanı istemcisi**, SQL sorguları ile bir **veritabanı sunucusuna** bağlanır.

İstemci/Sunucu modeli, küçük uygulamalardan büyük ölçekli sistemlere kadar birçok alanda kullanılır. Örneğin, çevrimiçi oyunlar, e-ticaret siteleri, finans sistemleri ve veri merkezleri bu model üzerine inşa edilmiştir.

---

## Örnekler

- **Web Tarayıcısı ve Web Sunucusu**: İnternet tarayıcınız (Chrome, Firefox vb.), bir web sitesine erişmek için o sitenin barındığı sunucuya istek gönderir. Sunucu, sayfanın HTML içeriğini tarayıcıya iletir.
- **E-posta İstemcisi ve E-posta Sunucusu**: Outlook veya Gmail gibi bir e-posta istemcisi, e-posta sunucusuna bağlanarak mesajları alır ve gönderir.
- **Dosya Paylaşımı**: Bir FTP istemcisi, dosya sunucusuna bağlanarak paylaşılan dosyalara erişebilir.
- **Veritabanı Sunucusu**: Uygulamalar, bir veritabanı sunucusuna SQL sorguları göndererek veri çekebilir.
- **Çevrimiçi Oyunlar**: Oyun istemcisi, oyun sunucusuna bağlanarak oyun içi işlemleri yönetir.

---

## Avantajlar ve Dezavantajlar

### ✅ Avantajlar
- **Merkezi Yönetim**: Tüm veriler ve işlemler merkezi bir sunucuda kontrol edilebilir.
- **Güvenlik**: Sunucular güvenlik politikaları ile korunduğu için verilerin korunması daha kolaydır.
- **Ölçeklenebilirlik**: Yeni istemciler eklenerek sistem genişletilebilir.
- **Kaynakların Verimli Kullanımı**: Sunucu yüksek güçlü bir makinedir ve birçok istemciyle kaynaklarını paylaşabilir.
- **Kolay Bakım ve Güncelleme**: Yazılım güncellemeleri merkezi olarak yönetilebilir.

### ❌ Dezavantajlar
- **Tek Nokta Arızası**: Sunucu çökmesi tüm istemcileri etkileyebilir.
- **Aşırı Yüklenme Riski**: Çok fazla istemci aynı anda istek gönderdiğinde sunucu zorlanabilir.
- **Yüksek Maliyet**: Sunucu donanımı, yazılımı ve bakım giderleri yüksektir.
- **Bağımlılık**: İstemciler sunucuya bağlı olduğu için sunucuda oluşan bir hata tüm istemcileri etkileyebilir.

---

## Karşılaştırmalar

| **Özellik**           | **İstemci/Sunucu** | **Eşler Arası (P2P)** |
|----------------------|------------------|------------------|
| **Merkezi Yönetim**   | ✔ Evet            | ❌ Hayır           |
| **Güvenlik**         | ✔ Daha güvenli    | ❌ Daha zayıf       |
| **Ölçeklenebilirlik** | ✔ Yüksek          | ❌ Düşük            |
| **Kurulum Kolaylığı** | ❌ Daha karmaşık   | ✔ Daha basit       |
| **Bağımsız Çalışma**  | ❌ Sunucuya bağlı  | ✔ Sunucu gerektirmez |

**Özetle:** İstemci/Sunucu modeli, büyük ölçekli sistemlerde güvenlik ve yönetim avantajları sunarken, P2P daha esnek ve düşük maliyetlidir ancak güvenlik zafiyetleri barındırabilir.

---

# Web Servisleri

## Tanım ve Açıklama
Web servisi, bir uygulamanın internet üzerinden bir başka uygulamaya makine-okunur formatta hizmet sunmasını sağlayan bir yazılım bileşenidir. Başka bir deyişle, web servisleri iki makinenin (veya yazılımın) ağ üzerinden birbiriyle iletişim kurmasına olanak tanıyan arayüzlerdir. Bu iletişim genellikle HTTP gibi web protokolleri kullanılarak yapılır ve veriler XML veya JSON gibi standart formatlarda taşınır. 

Web servisleri, farklı platform veya dillerde yazılmış yazılımlar arasında uyumluluk (interoperability) sağlayarak, sistemlerin birbirinden bağımsız çalışmasını mümkün kılar. Örneğin, bir hava durumu servisi, kendi veritabanındaki bilgileri JSON formatında isteyen herhangi bir uygulamaya sunabilir. Web servislerinin temel özelliği, ağ üzerindeki farklı uygulamalar arasında belirlenmiş standart mesajlaşma protokolleriyle (örn. HTTP üzerindeki SOAP veya REST çağrıları) veri alışverişi yapmalarıdır. 

Web servisleri genellikle bir istemci-sunucu modeli içinde çalışır:
- **Sunucu**, belirli bir URL veya uç nokta üzerinden istekleri dinler.
- **İstemci**, bu uç noktaya uygun formatta istek gönderir.

Örneğin, SOAP tabanlı bir web servisinde servis arabirimi **WSDL (Web Services Description Language)** dosyası ile tanımlanır. REST tabanlı web servisleri ise HTTP metodları (GET, POST, PUT, DELETE) üzerinden çalışarak, genellikle JSON formatında veri döndürür. 

Web servisleri platformdan bağımsızdır; servis ve istemci farklı işletim sistemlerinde veya farklı dillerde yazılmış olabilir. Bu bağımsızlık sayesinde oldukça esnek ve yeniden kullanılabilir entegrasyonlar mümkün olur. Günümüzde web servisleri denince akla başlıca iki yaklaşım gelir: **SOAP (Simple Object Access Protocol)** ve **REST (Representational State Transfer)** tabanlı servisler. SOAP sıkı standartlara sahip bir protokol iken, REST bir mimari stildir. 

---

## Örnekler

- **Hava Durumu Servisi**: Bir şehir bilgisini alıp o şehrin güncel hava durumu verilerini döndüren bir web servisi düşünün. Örneğin AccuWeather veya Meteoroloji Genel Müdürlüğü gibi servisler, belirli bir konumun sıcaklık, nem, tahmin gibi verilerini JSON veya XML formatında sunar.
- **Ödeme Entegrasyonu**: E-ticaret siteleri, ödeme işlemlerini gerçekleştirmek için PayPal veya Stripe gibi üçüncü taraf ödeme sağlayıcılarının web servislerini kullanır.
- **Harita Servisi**: Google Maps gibi harita sağlayıcıları web servis arayüzleri sunar. Bir uygulama, Google Maps API’ına istek yaparak iki konum arasındaki mesafeyi veya rotayı alabilir.
- **Sosyal Medya API’leri**: Twitter, Facebook gibi platformlar, geliştiriciler için web servisleri sunar. Örneğin bir uygulama, Twitter’ın web servisine istekte bulunarak belirli bir hashtag ile atılmış son tweet’leri JSON formatında çekebilir.
- **Kurumsal Uygulamalar**: Büyük şirketler iç sistem entegrasyonlarında web servislerini kullanır. Örneğin, bir stok takip sistemi ile satış sistemi web servisler aracılığıyla haberleşebilir.

---

## Avantajlar ve Dezavantajlar

### ✅ Avantajlar
- **Heterojen Sistemler Arasında Uyum**: Farklı programlama dilleri ve platformlarda çalışabilir.
- **Esneklik ve Yeniden Kullanılabilirlik**: Aynı web servisi farklı projelerde veya müşterilerde tekrar kullanılabilir.
- **Modüler Geliştirme**: Uygulamalar küçük hizmet bileşenlerine bölünebilir.
- **Standart Protokoller Kullanımı**: HTTP, JSON, XML gibi yaygın teknolojiler üzerine inşa edildiği için geliştirmesi kolaydır.
- **Ölçeklenebilirlik**: Durumsuz (stateless) olarak tasarlandığında, yük dengeleme ile yüksek ölçeklenebilirlik sağlar.
- **Güvenlik**: OAuth 2.0, API Key ve HTTPS gibi standart güvenlik önlemleri uygulanabilir.

### ❌ Dezavantajlar
- **Ağ Bağımlılığı**: Çalışması için sürekli internet bağlantısı gerekir.
- **Performans Yükü**: XML tabanlı SOAP protokolü, JSON’a kıyasla daha yavaş olabilir.
- **Ağ Trafiği ve Bant Genişliği**: Tüm isteklerin HTTP üzerinden gitmesi ek ağ trafiği oluşturur.
- **Güvenlik Riskleri**: API’lerin yetkisiz erişimlere karşı korunması gerekir.
- **Versiyonlama Zorlukları**: Güncellemeler sırasında geriye dönük uyumluluğu sağlamak karmaşık olabilir.

---

## Karşılaştırmalar

| **Özellik**           | **Web Servisi** | **API** |
|----------------------|------------------|------------------|
| **Ağ Bağımsızlığı**   | ❌ Gereklidir     | ✔ Gerekli olmayabilir |
| **Standartlar**      | ✔ HTTP, XML, JSON gibi standartları kullanır | ❌ Herhangi bir protokol olabilir |
| **Kullanım Alanı**   | ✔ Ağ üzerinden çalışan sistemler | ✔ Her türde uygulama |
| **Veri Formatı**     | ✔ JSON, XML      | ✔ JSON, XML, Binary |

**Özetle:** Web servisleri API’lerin bir alt kümesidir. API’ler genel bir yazılım arayüzü iken, web servisleri ağ üzerinden çalışan API’lerdir.

### SOAP vs REST Karşılaştırması
| **Özellik**  | **SOAP** | **REST** |
|-------------|---------|---------|
| **Tanım**  | XML tabanlı sıkı standartlara sahip bir protokol | HTTP metodlarını kullanan esnek bir mimari stil |
| **Veri Formatı** | XML | JSON, XML |
| **Durum Yönetimi** | Stateful veya Stateless olabilir | Stateless olmalıdır |
| **Güvenlik** | WS-Security gibi ek güvenlik katmanları sağlar | HTTPS, OAuth gibi standart güvenlik önlemleri kullanır |
| **Kullanım Alanı** | Bankacılık, Telekom gibi güvenli ve standartlaştırılmış sistemler | Web API’leri, Mobil uygulamalar, Mikro servisler |

REST, günümüzde daha hafif ve esnek olduğu için web tabanlı API’lerde yaygın olarak tercih edilmektedir. SOAP ise finans ve güvenlik gerektiren sistemlerde daha çok kullanılır.

---

# Stateless ve Stateful

## Tanım ve Açıklama
Stateless (durumsuz) ve Stateful (durumlu) kavramları, bir sistemin veya protokolün işlem sırasında **durum bilgisini tutup tutmaması** ile ilgilidir.

- **Stateless (Durumsuz)**: Sistem, kendisiyle yapılan önceki etkileşimlerin bilgisini **saklamaz**. Her isteği **bağımsız olarak işler** ve istemci her istekte gerekli tüm bilgileri tekrar göndermek zorundadır.
- **Stateful (Durumlu)**: Sistem, önceki işlemleri **hatırlar** ve her yeni isteği geçmiş etkileşimlere bağlı olarak değerlendirir.

Bu kavramlar, özellikle istemci-sunucu iletişiminde büyük önem taşır. Örneğin:
- **HTTP protokolü doğası gereği stateless’tir**. Bir web sunucusu, istemcinin ardışık isteklerini bağımsız olarak ele alır.
- **Bir kullanıcının web sitesine giriş yapması** stateful bir durum oluşturur. Kullanıcı giriş yaptıktan sonra sunucu oturum bilgisini saklar ve sonraki isteklerde bu oturuma göre hareket eder.

Özetle:
- **Stateless**: Her istekte durum sıfırlanır.
- **Stateful**: Sistem, istemcinin bağlamını hatırlar.

---

## Örnekler

### Stateless Örnekleri
- **HTTP**: Her istekte istemcinin kim olduğu bilinmez, bu yüzden her istek bağımsızdır.
- **RESTful API**: Her API çağrısı kimlik doğrulama ve gerekli verilerle yapılmalıdır.
- **DNS (Alan Adı Sistemi)**: Her alan adı çözümleme isteği bağımsızdır.
- **Basit Web Servisleri**: Örneğin, bir çeviri servisi her istekte metni ve hedef dili istemci tarafından alır.

### Stateful Örnekleri
- **Banka Oturumu**: İnternet bankacılığı giriş yaptıktan sonra oturum bilgisini saklar.
- **Online Alışveriş Sepeti**: Kullanıcı sepete ürün eklediğinde sunucu bu durumu saklar.
- **Çok Adımlı İşlemler**: Örneğin, uçak bileti rezervasyonu gibi süreçler.
- **Oyun Sunucuları**: Oyuncunun ilerleme durumu, oturum boyunca sunucuda tutulur.

---

## Avantajlar ve Dezavantajlar

### ✅ Stateless Avantajları
- **Ölçeklenebilirlik**: İstekler bağımsız olduğu için herhangi bir sunucuya yönlendirilebilir.
- **Düşük Bellek Kullanımı**: Sunucu istemci için ek veri saklamaz.
- **Kolay Yük Dengeleme**: Herhangi bir sunucu gelen isteği işleyebilir.
- **Basitlik ve Dayanıklılık**: Bir isteğin başarısız olması diğerlerini etkilemez.

### ❌ Stateless Dezavantajları
- **Kimlik Doğrulama Yükü**: Her istekte tekrar kimlik bilgisi gönderilmelidir.
- **Ağ Trafiği Artışı**: Fazladan veri taşıma ihtiyacı doğar.
- **Gerçek Zamanlı Uygulamalar İçin Uygun Değildir**: Örneğin, video akışı ve chat uygulamaları stateful olmalıdır.

### ✅ Stateful Avantajları
- **Daha İyi Kullanıcı Deneyimi**: Kullanıcı bilgileri saklanarak oturum devamlılığı sağlanır.
- **Bağlam Bazlı Kararlar**: Örneğin, hatalı giriş denemeleri sayılabilir.
- **Performans Artışı**: Veritabanı bağlantıları gibi işlemler sürekli açık tutulabilir.

### ❌ Stateful Dezavantajları
- **Ölçeklenmesi Zordur**: Sunucu her istemci için veri saklamak zorundadır.
- **Kaynak Kullanımı Artar**: Uzun süre açık kalan oturumlar sunucu belleğini doldurabilir.
- **Karmaşıklık**: Oturum yönetimi ve yük dengeleme ek karmaşıklık getirir.

---

## Karşılaştırmalar

| **Özellik**           | **Stateless** | **Stateful** |
|----------------------|-------------|-------------|
| **Bağımsız İşlem**   | ✔ Evet       | ❌ Hayır      |
| **Ölçeklenebilirlik** | ✔ Yüksek     | ❌ Daha zor  |
| **Bellek Kullanımı**  | ✔ Düşük      | ❌ Yüksek    |
| **Bağlam Koruma**     | ❌ Yok        | ✔ Var       |
| **Gerçek Zamanlı Kullanım** | ❌ Uygun değil | ✔ Uygun    |

**Özetle:**
- **Stateless**, ölçeklenebilir ve hafif sistemler için uygundur.
- **Stateful**, oturum yönetimi ve kullanıcı bağlamı gerektiren durumlarda tercih edilir.

Günümüz sistemlerinde **hibrit yaklaşımlar** kullanılır. Örneğin, HTTP stateless olmasına rağmen çerezler (cookies) veya oturum yönetimi sayesinde stateful hale getirilebilir.

---

# SOAP ve REST (RESTful) Karşılaştırması

## Tanım ve Açıklama

SOAP (Simple Object Access Protocol) ve REST (Representational State Transfer), web servislerinin tasarımı ve uygulanmasında kullanılan iki ana yaklaşımdır.

- **SOAP**: 1990’larda geliştirilmiş, **XML tabanlı bir mesajlaşma protokolüdür** ve web servisleri için bir dizi standart kural tanımlar.
- **REST**: Bir protokol değil, **Roy Fielding tarafından tanımlanmış bir mimari stildir** ve özellikle **HTTP protokolünü** kullanarak **kaynak odaklı bir tasarımı** teşvik eder.

SOAP katı standartları ve XML mesajlarını temel alan bir protokolken, REST prensiplere dayalıdır ve genellikle HTTP üzerinde **JSON/XML dönüşleriyle** gerçekleştirilir.

### SOAP’ın Detayları

- SOAP mesajları **XML zarfı** (SOAP Envelope) içinde taşınır.
- **Taşıma katmanından bağımsızdır** (HTTP, SMTP, TCP vb.).
- **WSDL (Web Services Description Language)** ile hizmet tanımları yapılır.
- **WS-* standartları (WS-Security, WS-Transaction vb.)** ile güvenlik, hata yönetimi ve iş süreçleri desteklenir.
- **Stateful olabilir**: Oturum yönetimi yapabilir.

### REST’in Detayları

- REST, **HTTP metodlarını (GET, POST, PUT, DELETE) doğal olarak kullanır**.
- **Kaynak tabanlıdır** ve her kaynak benzersiz bir URI ile temsil edilir.
- Veri formatı esnektir (**JSON, XML, HTML, CSV** vb. kullanılabilir).
- **Uniform interface (tekdüzen arayüz)** ilkesi sayesinde API’ler tutarlı olur.
- **Stateless (durumsuz)** olduğu için her istek bağımsızdır.

## Örnekler

### SOAP Servis Örneği

SOAP üzerinden bir uçuş arama servisi isteği şu şekilde olabilir:

```xml
<soapenv:Envelope>
  <soapenv:Body>
    <ns:SearchFlightsRequest>
      <ns:from>IST</ns:from>
      <ns:to>JFK</ns:to>
      <ns:date>2025-04-01</ns:date>
    </ns:SearchFlightsRequest>
  </soapenv:Body>
</soapenv:Envelope>
```

Yanıt da XML formatında döner.

### REST Servis Örneği

RESTful bir uçuş arama servisi isteği:

```
GET /flights?from=IST&to=JFK&date=2025-04-01 HTTP/1.1
Host: api.flights.com
Accept: application/json
Authorization: Bearer <token>
```

Yanıt genellikle JSON formatında döner:

```json
[
  {"flightNo": "XY123", "departure": "IST", "arrival": "JFK", "date": "2025-04-01", "price": 500},
  {"flightNo": "XY456", "departure": "IST", "arrival": "JFK", "date": "2025-04-01", "price": 450}
]
```

## Avantajlar ve Dezavantajlar

| Özellik           | SOAP                                   | REST                                   |
|------------------|--------------------------------------|--------------------------------------|
| **Veri Formatı**  | Sadece XML                           | JSON, XML, HTML, CSV vb.             |
| **Performans**   | XML şişkinliği nedeniyle ağır        | Hafif, hızlı ve bant genişliği dostu |
| **Standartlar**  | WSDL ve WS-* standartlarına sahip   | Standart yok, esneklik var           |
| **Güvenlik**     | WS-Security desteği                 | SSL/TLS ve OAuth gibi ek mekanizmalar |
| **Ölçeklenebilirlik** | Stateful olabilir, ölçekleme zor | Stateless olduğu için kolay ölçeklenebilir |
| **Kullanım Alanı** | Bankacılık, kurumsal sistemler     | Mobil, web API’leri, mikro servisler |

## Sonuç

- **REST**, modern web ve mobil uygulamalarda **hızlı geliştirme, hafiflik ve esneklik** sunduğu için daha yaygın kullanılmaktadır.
- **SOAP**, **güvenlik, işlem bütünlüğü ve kurumsal standartlar** açısından avantajlıdır ve genellikle bankacılık, sigorta, telekomünikasyon gibi alanlarda tercih edilmektedir.
- Projeye bağlı olarak **REST veya SOAP arasında seçim yapılmalıdır**.

---

# Host (Ana Bilgisayar)

## Tanım ve Açıklama

Host (ana bilgisayar), bir bilgisayar ağına bağlı olan ve diğer cihazlarla iletişim kurabilen herhangi bir cihazı ifade eder. Ağ bağlamında host kavramı, hem istemci hem sunucu makineleri kapsar – yani veri gönderen veya alan tüm uç sistemler birer host’tur. Örneğin evinizde internete bağlı dizüstü bilgisayarınız da bir host’tur, bir web sitesine hizmet veren sunucu da bir host’tur. Bir host’un temel özelliği, ağa erişimi sağlayan bir **IP adresine sahip olmasıdır**. 

Ağ üzerindeki yönlendiriciler, anahtarlar gibi cihazlar ise genelde **"host" sayılmaz** çünkü onlar son kullanıcı işlemi yapmaz, sadece iletim yaparlar (onlara **düğüm (node)** denir). Bu ayrım şöyle özetlenebilir:
- **Her host bir ağ düğümüdür, fakat her ağ düğümü host değildir.**

Host terimi, bilgisayar ağlarının ilk zamanlarından gelen bir kavram olup, **ARPANET ve Internet**’in gelişiminde **"network host"** olarak anılmıştır. Günümüzde host dendiğinde, **kullanıcıların doğrudan kullandığı veya sunucu işlevi gören tüm cihazlar** kastedilir: **PC’ler, sunucular, akıllı telefonlar, IoT cihazları vb.**

Bir **host**, ağdaki diğer host’larla belirli protokoller aracılığıyla iletişim kurar (**ör. TCP/IP**). İnternet üzerindeki her host’a **bir veya daha fazla IP adresi** atanmıştır ve bu adresler üzerinden **veri paketleri alma/gönderme işlemi** yapılır.

### Host ve İstemci/Sunucu İlişkisi
- **İstemci Host**: Başka bir host’tan hizmet alan cihaz.
- **Sunucu Host**: Bir hizmeti sağlayan ve istemcilerden gelen talepleri yanıtlayan cihaz.
- **Çift Yönlü Host**: Hem istemci hem de sunucu rolü üstlenen cihazlar.

Bir akıllı telefon **internette gezinirken istemci host’tur**, ancak aynı cihaz bir **hotspot açarak** ağ trafiğini yönlendirdiğinde **sunucu host haline** gelebilir.

### Host ve IP Adresleri
Host kavramı **IP adresleriyle** doğrudan ilişkilidir:
- **Her host’un bir IP adresi vardır** (IPv4 veya IPv6).
- **Hostname (makine adı)**, bir host’a atanan ve DNS üzerinden çözümlenen isimdir.
- **Hostlar**, OSI modelinin **transport (taşıma) katmanında** TCP gibi protokollerle iletişim kurar.

### Host ve Sanallaştırma
- **Fiziksel Host**: Gerçek donanım üzerinde çalışan bir makine.
- **Sanal Host**: Sanallaştırma yazılımı ile çalışan sanal makineler (VM, Container vb.).
- **Host & Guest Ayrımı**: Sanallaştırmada, fiziksel sunucuya **host (ana bilgisayar)**, üzerinde çalışan sanal makinelere **guest (misafir bilgisayar)** denir.

## Örnekler

| **Host Türü** | **Örnek** |
|--------------|----------|
| **Kişisel Bilgisayar** | İnternete bağlı bir masaüstü PC veya dizüstü |
| **Sunucu Makine** | Web sunucusu, veritabanı sunucusu |
| **Akıllı Telefon** | Mobil veri veya Wi-Fi ağına bağlı bir telefon |
| **IoT Cihazı** | Akıllı termostat, akıllı ev cihazları |
| **Sanal Makine** | AWS EC2 instance, Azure VM |
| **Ağ Yazıcısı/Kamera** | IP üzerinden erişilebilen yazıcı veya güvenlik kamerası |

## Avantajlar ve Dezavantajlar

### **Host Tabanlı (Ana Bilgisayar Merkezli) Ağların Avantajları**
✔ Merkezi yönetim kolaylığı sağlar.
✔ Güvenlik politikalarını merkezi uygulama imkanı sunar.
✔ Büyük veri işlemede verimli olabilir.

### **Host Tabanlı Ağların Dezavantajları**
✘ Ana sistem çökerse tüm ağ etkilenebilir.
✘ Sunucu üzerinde aşırı yük olabilir.
✘ Kullanıcı deneyimi, merkezi sistemin performansına bağlıdır.

### **Self-Hosting Avantaj/Dezavantajları**
- **Kendi host’unu barındırma** (**self-hosting**) ile tam kontrol sağlanır ancak bakım ve güvenlik sorumluluğu artar.
- **Bulut hizmetleri** (AWS, Azure vb.), yönetim yükünü azaltır ancak veri kontrolü üçüncü tarafa geçer.


| **Kavram** | **Tanım** |
|----------|-----------|
| **Host** | Ağa bağlı, IP adresine sahip her uç cihaz. |
| **Sunucu (Server)** | Bir hizmeti sağlayan host. |
| **İstemci (Client)** | Bir hizmeti talep eden host. |
| **Node (Düğüm)** | Ağa bağlı herhangi bir cihaz (router, switch dahil). |
| **Mainframe/Terminal** | Mainframe, tüm işlemleri yapan ana host; terminal, bağlı basit cihaz. |
| **Container vs. Host** | Bir fiziksel host üzerinde çalışan birden fazla sanal container olabilir. |

## Sonuç

Host kavramı, **ağ altyapısında temel bir yer tutar** ve **cihazların fonksiyonlarını, adreslenebilirliğini ve iletişimini belirler**. **İnternet ve yerel ağlar** üzerindeki tüm cihazlar **host** olarak tanımlanabilir ve **istemci, sunucu, sanal veya fiziksel host gibi çeşitli roller üstlenebilir**. Günümüzde, **dağıtık host sistemleri ve bulut çözümleri** yaygınlaşarak merkezi host sistemlerine göre daha esnek ve ölçeklenebilir çözümler sunmaktadır.

---

## Kaynaklar

1. [Client-Server Model - Wikipedia](https://en.wikipedia.org/wiki/Client%E2%80%93server_model#:~:text=The%20client%E2%80%93server%20model%20is%20a,therefore%2C%20initiate%20communication%20sessions%20with)
2. [What is Client-Server Network? - Zenarmor](https://www.zenarmor.com/docs/network-basics/what-is-client-server-network#:~:text=The%20client,clients%20at%20the%20same%20time)
3. [Host (Network) - Wikipedia](https://en.wikipedia.org/wiki/Host_(network)#:~:text=Network%20hosts%20that%20participate%20in,resources%20in%20an%20equipotent%20manner)
4. [Definition of Host - TechTarget](https://www.techtarget.com/searchnetworking/definition/host#:~:text=A%20host%20is%20a%20computer,receive%20data%2C%20services%20and%20applications)
5. [Web Services - Wikipedia](https://en.wikipedia.org/wiki/Web_service#:~:text=A%20web%20service%20,either)
6. [Stateful vs Stateless - Red Hat](https://www.redhat.com/en/topics/cloud-native-apps/stateful-vs-stateless#:~:text=A%20stateless%20application%20or%20process,term%20requests)
7. [SOAP vs REST - AWS](https://aws.amazon.com/compare/the-difference-between-soap-rest/#:~:text=SOAP%20is%20an%20older%20technology,also%20called%20RESTful%20web%20services)
8. [SOAP vs REST - Stackify](https://stackify.com/soap-vs-rest/#:~:text=middleware%20such%20as%20ICE%20and,security%2C%20trust%2C%20and%20other%20elements)
