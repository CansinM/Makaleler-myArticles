# ORM (Object-Relational Mapping)

ORM (Nesne-İlişkisel Eşleme), nesne tabanlı yazılım ile ilişkisel veritabanları arasında bir köprü görevi gören önemli bir tekniktir.

## ORM Nedir?

ORM (Object-Relational Mapping), nesne yönelimli programlama dilleri ile ilişkisel veritabanları arasındaki dönüşümü otomatikleştiren bir programlama teknolojisidir. Basitçe söylemek gerekirse, ORM veritabanı yapısını bir nesne gibi ele alarak, geliştiricinin doğrudan veritabanı sorguları yazmak yerine sanki bellek içindeki nesnelerle çalışır gibi veritabanını yönetmesini sağlar. Uygulama ile veritabanı arasında bir katman oluşturarak, geleneksel SQL sorgularının diline bağlı kalmadan verileri nesneler aracılığıyla okumak ve yazmak mümkün olur. ORM, bu sayede nesne-ilişkisel uçurum (*impedance mismatch*) olarak bilinen ve nesne modelleri ile tablo yapıları arasındaki uyuşmazlıktan doğan sorunları gidermeye yardımcı olur.

Bir ORM aracı kullanıldığında, veritabanındaki tablolar genellikle yazılım içinde karşılık gelen sınıflar (*class*) veya nesneler olarak temsil edilir. Her bir tablo satırı, o sınıfın bir nesnesine (örneğin bir “kayıt” nesnesine) denk gelir. Bu modellemede ilişkisel veritabanlarındaki birincil anahtar-yabancı anahtar ilişkileri de nesneler arasındaki ilişkiler (örneğin nesne referansları veya koleksiyonlar) şeklinde yansıtılır. ORM araçları, bu eşlemeyi gerçekleştirerek uygulama kodu içinde SQL sorguları yazmadan veritabanı işlemleri yapmamıza olanak tanır.

## ORM'nin Avantajları ve Dezavantajları

### Avantajlar

- **Daha Az Kod ve Hızlı Geliştirme**: ORM, tekrarlayan SQL sorguları yazma ihtiyacını azaltarak geliştiricinin yazması gereken kod miktarını önemli ölçüde düşürür. Bu sayede uygulama geliştirme süreci hızlanır ve verimlilik artar.
- **Bakım ve Sürdürülebilirlik**: Veritabanı erişiminin tek bir katmanda soyutlanması, kodun bakımını kolaylaştırır. Veritabanı değişiklikleri merkezi olarak ORM katmanında yapılabilir.
- **Güvenlik**: Birçok ORM aracı, parametreli sorgular veya benzeri mekanizmalar kullanarak SQL enjeksiyonu riskini azaltır.
- **Veritabanı Bağımsızlığı**: ORM’ler farklı veritabanı sistemlerini destekleyebilir. Örneğin PostgreSQL, MySQL veya MSSQL gibi farklı sistemlere bağlanmak mümkün olabilir.

### Dezavantajlar

- **Soyutlama ve Performans Aşınması**: ORM araçları yüksek seviyeli bir soyutlama sağladığından, bazen ek performans maliyeti getirebilir. ORM ile yazılan işlemin veritabanında nasıl işlendiğini bilmek önemlidir.
- **Öğrenme Eğrisi ve Sihirli Yöntemler**: ORM kütüphaneleri, özellikle gelişmiş özellikleriyle, öğrenmesi zaman alabilen “sihirli” yapılar içerebilir. Yanlış veya dikkatsiz kullanımda beklenmedik sonuçlar doğabilir (örneğin, *N+1* sorgu problemi gibi).
- **Tüm Durumlara Uygun Olmama**: ORM’ler yaygın *CRUD* (Create, Read, Update, Delete) işlemlerini kolaylaştırsa da, çok karmaşık veya optimize edilmesi gereken sorgularda bazen yetersiz kalabilir.
- **Hafıza Tüketimi**: ORM, veritabanından çekilen verileri nesnelere yükler. Büyük veri setlerinin nesnelere çevrilip uygulama belleğine alınması bellek tüketimini artırabilir.

## ORM'nin Kullanım Alanları

ORM’ler günümüzde pek çok yazılım projesinde kullanılmaktadır. Özellikle web uygulamaları ve kurumsal uygulamalar ORM’nin en sık görüldüğü alanlardır. Popüler web geliştirme çerçevelerinin birçoğu kendi ORM çözümüyle birlikte gelir. Örneğin:

- **Django** – Python
- **Laravel** – PHP
- **Ruby on Rails** – Ruby
- **Entity Framework** – .NET
- **Hibernate** – Java

### Tipik Kullanım Alanları

- **Veri Tabanı İşlemleri Yoğun Uygulamalar**: İçerik yönetimi, e-ticaret siteleri gibi sürekli veri okuma/yazma yapılan uygulamalarda ORM büyük kolaylık sağlar.
- **Çoklu Veritabanı Desteği Gereken Durumlar**: Uygulamanın birden fazla veritabanı türünü desteklemesi gerekiyorsa, ORM kullanmak iş yükünü azaltır.
- **Hızlı Prototipleme ve Agile Geliştirme**: Hızlı geliştirme döngülerinde, veritabanı şemasının sık değiştiği projelerde ORM ve migration araçları sayesinde veritabanı değişikliklerini yönetmek kolaylaşır.
- **Ekip Çalışması ve Kod Tutarlılığı**: ORM, herkesin aynı soyutlama ile veritabanına erişmesini sağlayarak tutarlı ve okunabilir bir kod tabanı oluşturur.

---

# Migration (Veritabanı Göçleri)

## Migration Nedir?

Migration (veritabanı göçü), yazılım projelerinde veritabanı şemasındaki (tablolar, kolonlar, ilişkiler vb.) değişiklikleri yönetmek ve takip etmek için kullanılan bir versiyonlama tekniğidir. Migration’lar, veritabanına eklenen bir tablo, değiştirilen bir kolon veya oluşturulan bir indeks gibi her şema değişikliğini adım adım kaydeden ve gerektiğinde bu değişiklikleri ileri veya geri almayı sağlayan betiklerdir.

Geleneksel yöntemlerde, bir veritabanı değişikliği yapmak manuel olarak SQL `ALTER` komutları çalıştırmayı ve ekip üyelerine bu değişiklikleri iletmeyi gerektirirdi. Ancak migration araçları bu süreci otomatize eder ve yapılan değişiklikleri takip edilebilir hale getirir. Migration’lar, veritabanı için bir "versiyon kontrol sistemi" işlevi görerek, tıpkı Git veya SVN gibi değişikliklerin izlenmesini sağlar. Böylece uygulamanın kodunda yapılan güncellemelerle veritabanındaki değişiklikler senkronize ve geri izlenebilir hale gelir.

## Veritabanı Yönetiminde Migration'ın Önemi

Migration kullanmanın sağladığı başlıca avantajlar şunlardır:

- **Ekip Senkronizasyonu**: Birden fazla geliştiricinin çalıştığı projelerde, veritabanı şema değişiklikleri migration dosyaları aracılığıyla paylaşılır. Böylece ekip üyeleri, migration dosyasını çalıştırarak kendi veritabanlarını güncelleyebilir. Bu, manuel bildirimlere olan ihtiyacı ortadan kaldırır.
- **Versiyon Kontrolü ve Geri Alabilme**: Migration’lar zaman damgası veya sıralı numaralar ile versiyonlanır. Böylece istenilen bir versiyona geri dönmek (*rollback*) mümkün olur. Yanlış yapılan bir değişiklik hızlıca geri alınabilir.
- **Otomasyon ve DevOps Entegrasyonu**: Sürekli entegrasyon (*CI/CD*) süreçlerinde, migration’lar otomatik olarak çalıştırılarak veritabanının kodla uyumlu hale getirilmesi sağlanır.
- **Belgeleme**: Migration dosyaları, veritabanında zaman içinde hangi değişikliklerin yapıldığını kaydeder. Bu sayede, tabloların nasıl evrildiği takip edilebilir ve veritabanı yapısının belgelenmesi sağlanır.

## ORM ile Migration Kullanımı

Birçok modern ORM aracı, kendi migration mekanizmalarıyla birlikte gelir veya popüler framework'lerle entegre çalışır. Örneğin:

- **Laravel (PHP) - Eloquent ORM**: Laravel, migration kavramını "veritabanınız için versiyon kontrolü" olarak tanımlar. Yeni bir migration oluşturmak için `php artisan make:migration` komutu kullanılır. Değişiklikler PHP koduyla tanımlanır ve `php artisan migrate` komutuyla veritabanına uygulanır.
- **Django (Python) - Django ORM**: Django, migration sürecini güçlü bir şekilde destekler. `models.py` içindeki değişiklikleri algılar ve `python manage.py makemigrations` komutuyla otomatik migration dosyaları oluşturur. Daha sonra `python manage.py migrate` komutu ile bu değişiklikler veritabanına uygulanır.
- **Entity Framework (C#) - Code First Migrations**: .NET dünyasında, Entity Framework'ün *Code-First* yaklaşımı migration desteği sunar. Geliştirici, modelde yaptığı değişiklikleri `Add-Migration` komutu ile migration dosyasına dönüştürür ve `Update-Database` komutuyla veritabanına uygular.
- **Diğer Framework'ler**: *Ruby on Rails*'in *Active Record*’u, *Elixir Phoenix Framework* vb. birçok araç, migration süreçlerini destekler.

#### Sonuç

ORM ile entegre çalışan migration’lar, yazılım geliştirme sürecinde veritabanı değişikliklerini yönetmeyi kolaylaştıran kritik bir bileşendir. Özellikle sık sık yeni özellikler eklenen ve buna bağlı olarak veritabanı şeması değişen projelerde, migration kullanımı hem geliştirme sürecinde hem de bakım aşamasında büyük avantajlar sağlar.

---

# ORM Araçları

Piyasada farklı programlama dilleri ve platformlar için geliştirilmiş birçok ORM aracı bulunmaktadır. Bu bölümde yaygın olarak kullanılan dört ORM aracını ele alacağız:

- **Eloquent ORM (Laravel için)** – PHP dünyasından, Laravel framework’ünün varsayılan ORM katmanı.
- **Django ORM** – Python dünyasında Django çerçevesinin dahili ORM’i.
- **Entity Framework** – Microsoft .NET platformu için güçlü bir ORM.
- **Dapper (Micro ORM)** – .NET ekosisteminde hafif ve performanslı bir “mikro” ORM.

Her bir aracı kısaca tanıtıp temel özelliklerini inceleyelim.

## Eloquent ORM (Laravel)

Eloquent, Laravel framework’ünün bünyesinde gelen ve Active Record tasarım desenini kullanan bir ORM’dir. Active Record deseni, her bir model sınıfının veritabanındaki bir tabloya karşılık gelmesi ve bu sınıfın örneklerinin tablo satırlarını temsil etmesi mantığına dayanır. Laravel’de bir Eloquent modeli tanımlandığında, genellikle modelin adıyla eşleşen bir veritabanı tablosu ve modelin özellikleriyle eşleşen tablo kolonları olur.

### Eloquent ORM’nin Dikkat Çeken Özellikleri

- **Kolay ve Anlaşılır Söz Dizimi**: Eloquent, PHP dilinin ifade gücünü kullanarak zincirlenebilir (*fluent interface*) metodlar sunar.
- **İlişki Yönetimi**: Eloquent, tablolar arası ilişkileri (bir-çok, çok-çok, bir-bir) model sınıfları arasında kolayca tanımlamaya izin verir.
- **Görev Kolaylaştırıcılar**: Yumuşak silme (*soft delete*), otomatik zaman damgaları (*timestamps*), toplu atama koruması (*mass assignment protection*) gibi gelişmiş özellikler sunar.
- **Query Builder ile Entegrasyon**: Eloquent modeli, Laravel’in alt düzey sorgu oluşturucusunu (*Query Builder*) miras alır.

Eloquent, Laravel ile tam entegre olduğu için Laravel projelerinde varsayılan ORM’dir. Sağladığı yüksek seviyeli API sayesinde hızlı uygulama geliştirme imkanı sunar. Ancak, çok karmaşık sorgular veya yüksek performans gerektiren durumlar için Laravel, ham SQL kullanmayı da destekler.

## Django ORM

Django ORM, Python tabanlı Django framework’ünün dahili olarak sağladığı nesne-ilişkisel eşleme katmanıdır. Django ORM, Active Record tarzına benzer bir yaklaşım sergiler: Bir model sınıfı, veritabanında bir tabloyu temsil eder ve her model örneği o tabloda bir satıra karşılık gelir.

### Django ORM’nin Öne Çıkan Özellikleri

- **Otomatik Admin ve Form Entegrasyonu**: Django’da tanımlanan modeller, otomatik olarak admin panelinde görüntülenebilir ve Django form yapısıyla entegre edilebilir.
- **Zengin Sorgu API’si**: Pythonic bir şekilde SQL sorguları yazmadan veri çekme, filtreleme ve düzenleme işlemleri yapılabilir.
- **İlişki ve JOIN İşlemleri**: Model ilişkileri (*ForeignKey, ManyToManyField*) kullanılarak tablolar arası bağlantılar kolayca kurulabilir.
- **Migration Desteği**: Django ORM, `makemigrations` ve `migrate` komutlarıyla veritabanı şeması değişikliklerini yönetmeyi sağlar.
- **Veritabanı Bağımsızlığı**: PostgreSQL, MySQL, SQLite ve Oracle gibi çeşitli veritabanlarını destekler.

## Entity Framework (EF)

Entity Framework (EF), .NET platformu için Microsoft tarafından geliştirilen bir ORM teknolojisidir. EF, özellikle C# diliyle ilişkisel veritabanlarına nesne yönelimli bir erişim sağlar. EF, *Active Record* yerine *Unit of Work* ve *Repository* desenlerini benimser.

### Entity Framework’ün Temel Özellikleri

- **LINQ Desteği**: .NET’in güçlü *Language Integrated Query* (LINQ) yapısı desteklenir.
- **Değişiklik Takibi**: EF’nin `DbContext` nesnesi üzerinden çekilen nesneler izlenerek yapılan değişiklikler otomatik olarak algılanır.
- **İlişki Yönetimi**: One-to-One, One-to-Many, Many-to-Many ilişkileri tanımlamak mümkündür.
- **Çoklu Veritabanı Desteği**: SQL Server, PostgreSQL, MySQL, SQLite ve Oracle gibi farklı veritabanlarıyla çalışabilir.
- **Zengin Ekosistem**: EF, Azure desteği, üçüncü parti uzantılar ve performans iyileştirme araçları sunar.

Entity Framework, .NET dünyasında veri erişimi için yaygın bir seçimdir. Özellikle güçlü tip kontrolü, LINQ desteği ve Microsoft’un sağladığı güncellemeler sayesinde kurumsal projelerde sıklıkla tercih edilir.

## Dapper (Micro ORM)

Dapper, .NET dünyasında yaygın olarak kullanılan ve Stack Overflow ekibi tarafından geliştirilen, performans odaklı bir "mikro ORM" çözümüdür. Entity Framework gibi tam teşekküllü ORM’lerin aksine, Dapper yalnızca veri eşleme işlemini yapar ve ek özellikler sunmaz.

### Dapper’ın Öne Çıkan Özellikleri

- **Yüksek Performans**: Neredeyse doğrudan *ADO.NET DataReader* performansına eşittir.
- **Basit Kullanım**: Doğrudan SQL sorguları yazmayı gerektirir, ancak veriyi nesnelere bağlar.
- **Hafif Yapı**: Nesne takibi, lazy load gibi karmaşık özellikleri içermez.
- **Esneklik**: Karmaşık SQL sorgularını doğrudan optimize etmek için uygundur.

Dapper, özellikle büyük ölçekli ve yüksek performans gerektiren projelerde tercih edilir. Özellikle çok büyük veri setlerinin sık sık işlendiği projelerde EF yerine Dapper kullanılabilir. Ancak Dapper, ORM’lerin sunduğu ek özelliklerden yoksun olduğu için, hibrit yaklaşımlar ile EF ve Dapper birlikte kullanılabilir.

### Sonuç

ORM araçları, geliştirme sürecini hızlandırmak ve veri erişim katmanını yönetilebilir hale getirmek için kritik öneme sahiptir. Hangi ORM aracının seçileceği, kullanılan programlama dili, projenin ihtiyaçları ve performans gereksinimlerine bağlıdır:

- **Laravel kullananlar için**: Eloquent en iyi entegrasyonu sunar.
- **Python/Django projeleri için**: Django ORM, yerleşik ve güçlü bir çözümdür.
- **.NET projelerinde**: EF, yüksek seviyeli bir ORM olarak geniş özellikler sunarken, Dapper performans gerektiren durumlarda daha hızlıdır.

Her ORM’nin avantajları ve sınırlamaları vardır. Doğru seçim, projenin gereksinimlerine bağlıdır.

---

# CQRS (Command Query Responsibility Segregation)

## CQRS Nedir?

CQRS (*Command Query Responsibility Segregation* – Komut ve Sorgu Sorumluluğu Ayrımı), bir yazılım mimari desenidir. Bu desen, veri okuma (*query*) ve veri yazma/değiştirme (*command*) işlemlerinin kullandığı modelleri tamamen birbirinden ayırmayı önerir. Başka bir deyişle, komutlar (*command*) sistemi değiştirirken sorgular (*query*) sadece veri okumaya hizmet eder. CQRS, bu iki işlemi farklı yapılarla ele alarak sistemin daha ölçeklenebilir ve yönetilebilir olmasını sağlar.

CQRS fikri, Bertrand Meyer’in “Command-Query Separation” ilkesine dayanır. Bu ilkeye göre bir metod ya bir şeyi değiştirmeli ya da bir şey döndürmelidir; ikisini birden yapmamalıdır. CQRS bu yaklaşımı uygulama mimarisi seviyesine taşır. Greg Young tarafından popüler hale getirilen CQRS, özellikle yüksek ölçekli, yoğun yazma-okuma trafiği olan sistemlerde büyük fayda sağlar.

## CQRS'nin Temel Bileşenleri

CQRS deseninde iki ana model bulunur:

- **Yazma Modeli (Command Model)**: Komutları alır, iş kurallarını uygular ve veritabanında değişiklik yapar (*insert, update, delete* işlemleri).
- **Okuma Modeli (Query Model)**: Kullanıcı sorgularına hızlı yanıt vermek için optimize edilmiştir. Veritabanından veri okuma işlemlerini gerçekleştirir ancak sistemi değiştirmez.

Bu iki model genellikle ayrı katmanlar, hatta ayrı servisler olarak tasarlanır. Örneğin bir e-ticaret sisteminde sipariş oluşturma/güncelleme gibi işlemler (*command*) farklı bir veri modeli kullanırken, raporlama veya ürün arama gibi işlemler (*query*) daha optimize bir veri modelinden okunabilir. Hatta bu modellerin veritabanları bile farklı olabilir. Yazma işlemi için normalleştirilmiş bir OLTP veritabanı, okuma için denormalize edilmiş bir OLAP veritabanı veya hızlı okuma için *cache* ya da NoSQL veritabanları kullanılabilir.

## CQRS'nin Avantajları

- **Performans ve Ölçeklenebilirlik**: Okuma ve yazma işlemleri ayrıldığı için, her biri kendi ölçekleme stratejisine sahip olabilir. Örneğin, okuma trafiği yüksekse, okuma modelini ayrı sunuculara çoğaltarak ölçeklendirmek mümkündür.
- **Farklı Veri Şemaları Kullanımı**: Sorgular genellikle farklı veri yapılarına ihtiyaç duyar. CQRS ile okuma modelinde denormalize edilmiş, indekslenmiş ya da *cache*'lenmiş veriler kullanılabilir.
- **Net Sorumluluk Ayrımı**: Kod bazında, komutları işleyen kısım ile sorguları yanıtlayan kısım tamamen ayrıdır. Bu, sistemin bakımını kolaylaştırır ve hata ayıklamayı daha basit hale getirir.
- **Event Sourcing ile Uyum**: CQRS, genellikle *Event Sourcing* ile birlikte kullanılır. *Event Sourcing*, sistemdeki her değişikliği bir olay (*event*) olarak saklar ve bu olaylardan okuma modelleri oluşturulabilir.

## CQRS'nin Dezavantajları

- **Artan Mimari Karmaşıklık**: CQRS, geleneksel CRUD tabanlı sistemlere göre daha fazla bileşen gerektirir. Küçük ve orta ölçekli projelerde bu ek karmaşıklık fayda yerine maliyet getirebilir.
- **Veri Tutarsızlığı Riskleri**: Okuma ve yazma modelleri farklı veri kaynaklarında olabilir ve senkronizasyon sürecinde kısa süreli tutarsızlıklar yaşanabilir.

## ORM ile CQRS İlişkisi

ORM ve CQRS birbirinden bağımsız kavramlar gibi görünse de, bir arada kullanıldığında dikkat edilmesi gereken noktalar vardır:

- **Tek Bir ORM Kullanımı**: Klasik ORM kullanımı, tek bir model üzerinden hem okuma hem yazma yapmaya yöneliktir. Ancak CQRS, bu modeli ikiye böldüğü için ORM katmanını da ayrı ele almak gerekir.
- **Farklı ORM Stratejileri**: Yazma tarafında güçlü iş kuralları, *transaction* yönetimi ve değişiklik takibi gerektiğinden **Entity Framework** gibi ORM’ler tercih edilebilir. Okuma tarafında ise performans için **Dapper** gibi hafif ORM’ler veya doğrudan SQL sorguları kullanılabilir.
- **Ayrı DbContext Kullanımı**: ORM destekliyorsa, yazma modeli için tam bir *DbContext* tanımlanırken, okuma modeli için sadece ihtiyaca uygun sorgular döndüren hafif bir *DbContext* oluşturulabilir.
- **Farklı Veritabanları Kullanımı**: CQRS ile okuma ve yazma modelleri için farklı veritabanları kullanılabilir. Örneğin, yazma işlemleri **PostgreSQL** gibi ilişkisel bir veritabanında tutulurken, okuma işlemleri **Elasticsearch** veya bir **Redis Cache** üzerinden sağlanabilir.

Gerçek hayatta, örneğin büyük bir finans uygulamasında para transferi ve hesap güncellemeleri (*command*) **Entity Framework** ile yapılırken, müşteriye gösterilecek hesap ekstresi ve raporlamalar (*query*) **Dapper** veya optimize SQL ile çekilerek hem performans kazanılmış hem de kod bazında sorumluluklar ayrılmış olabilir.

## CQRS Kullanım Senaryoları

CQRS’nin avantajlarından yararlanılabilecek bazı kullanım senaryoları şunlardır:

- **Yüksek Okuma-Yazma Oranı Olan Sistemler**: Okuma operasyonlarının yazma operasyonlarından çok daha fazla olduğu sistemlerde, okuma modelini ayrı ölçeklemek büyük performans kazancı sağlar. Örneğin, bir blog sisteminde içerik okuma işlemleri, içerik yazma işlemlerinden çok daha sık gerçekleşir.
- **Kompleks İş Kuralları Olan Sistemler**: Sipariş yönetimi gibi çok aşamalı işlemler içeren sistemlerde, CQRS komutları işleyen kısmı daha bağımsız ve esnek hale getirir.
- **Farklı Veri Kaynakları Kullanımı**: Bazı projelerde yazma verisi ilişkisel bir veritabanında tutulurken, arama ve analiz için farklı sistemler kullanılabilir. Örneğin, bir e-ticaret sitesinde siparişler ilişkisel veritabanında tutulurken, ürün listeleme işlemleri Elasticsearch üzerinden yapılabilir.
- **Event Sourcing ile Birlikte Kullanım**: Eğer sistem değişiklikleri olaylar (*event*) olarak kaydediliyorsa, CQRS doğal bir uyum sağlar. Okuma modelleri bu olaylardan türetilebilir ve farklı projeksiyonlar oluşturulabilir.

### Sonuç

CQRS, özellikle büyük ölçekli ve karmaşık sistemlerde ölçeklenebilirlik, performans ve bakım kolaylığı sağlayan güçlü bir mimari desendir. ORM araçları CQRS ile birlikte kullanılabilir, ancak genellikle her iki taraf için en uygun veri erişim stratejisini belirlemek daha verimli olur. Yazma tarafında güçlü ORM’ler (**Entity Framework, NHibernate**), okuma tarafında ise hafif ve performans odaklı araçlar (**Dapper, NoSQL**) kullanmak en yaygın yaklaşımdır. 

CQRS, küçük projelerde ek karmaşıklık getirebileceğinden her durumda kullanılmadan önce gereksinimler dikkatlice değerlendirilmelidir.

---

# Authentication ve Authorization (Kimlik Doğrulama ve Yetkilendirme)

## Kimlik Doğrulama (Authentication) ve Yetkilendirme (Authorization) Nedir?

Yazılım güvenliğinde iki temel kavram olan kimlik doğrulama ve yetkilendirme, genellikle birbirleriyle karıştırılır, ancak farklı işlevleri vardır:

- **Kimlik Doğrulama (Authentication)**: Bir kullanıcının veya sistemin iddia ettiği kişi olduğunu doğrulama işlemidir. Yani “Sen kimsin?” sorusunun cevabını bulur. Örneğin, bir web sitesine giriş yaparken kullanıcı adı ve şifre kontrolü kimlik doğrulama mekanizmasıdır.
- **Yetkilendirme (Authorization)**: Doğrulanmış bir kullanıcının belirli kaynaklara veya işlemlere erişim izni olup olmadığını belirler. Yani “Neleri yapabilirsin?” sorusuna yanıt verir. Örneğin, bir kullanıcının yönetici paneline erişememesi yetkilendirme ile kontrol edilir.

Basit bir örnek olarak, bir havalimanı güvenlik kontrolünü düşünelim:
- **Kimlik doğrulama**, sizin gerçekten bilette yazan kişi olup olmadığınızı teyit eder.
- **Yetkilendirme**, yalnızca biletinizdeki uçağa ait kapıya gitmenize izin verir.

## ORM ile Authentication ve Authorization Yönetimi

ORM doğrudan kimlik doğrulama veya yetkilendirme yapmaz, ancak bu süreçlerde kullanılan verilerin yönetiminde kritik bir rol oynar.

### Kullanıcı Veri Modeli

Kimlik doğrulama ve yetkilendirme süreçleri için kullanıcı bilgileri (kullanıcı adı, e-posta, parola özeti, roller vb.) veritabanında saklanır. ORM, bu verilerin yönetilmesini sağlar:

- **Django ORM**: *User* modeli, kullanıcı bilgilerini yönetmek için kullanılır.
- **Laravel (Eloquent ORM)**: *User* modeli kimlik doğrulama mekanizması ile entegredir.
- **.NET (Entity Framework)**: *Identity Framework* ile kullanıcı ve rol tablolarını yönetir.

### Giriş Yapma (Login) Süreci

Bir kullanıcı giriş yapmaya çalıştığında, genellikle şu adımlar izlenir:

1. Kullanıcıdan gelen kimlik bilgileri alınır.
2. Kullanıcı adı ile eşleşen kayıt ORM aracılığıyla sorgulanır.
3. Kullanıcı bulunduğunda, şifre doğrulama işlemi yapılır.
4. Şifre doğruysa, kullanıcı giriş yapmış kabul edilir ve oturum/tokensaklanır.

ORM, özellikle 2. ve 4. adımlarda devreye girerek, kullanıcı verilerinin güvenli bir şekilde saklanmasını ve sorgulanmasını sağlar.

### Rol Tabanlı Erişim (RBAC) ve ORM

Yetkilendirme genellikle roller ve izinler aracılığıyla yönetilir. Kullanıcıların belirli kaynaklara erişimini düzenlemek için roller veritabanında saklanır:

- **Django ORM**: *User* modeli ile *Group* modeli arasında *ManyToMany* ilişkisi bulunur. Kullanıcının yetkileri *is_authenticated* ve *is_staff* gibi özelliklerle kontrol edilir.
- **Laravel (Eloquent ORM)**: Kullanıcı modelinde *isAdmin()* gibi metotlar tanımlanabilir. Laravel’in *Gate/Policy* mekanizması yetkilendirme işlemlerini destekler.
- **.NET Identity Framework**: Kullanıcı-rol ilişkisi *Entity Framework* ile tanımlıdır ve yetkilendirme *UserManager.IsInRoleAsync(user, "Admin")* gibi metotlarla yapılır.

### ORM’nin Yetkilendirme ve Kimlik Doğrulamadaki Faydaları

- **Parola hash’lerinin güvenli saklanması**: ORM, şifreleme kütüphaneleriyle entegre çalışarak kullanıcı şifrelerinin güvenli bir şekilde saklanmasını sağlar.
- **Kullanıcı işlemlerinin kolay yönetimi**: ORM, kullanıcı oluşturma, güncelleme ve silme işlemlerini hızlandırarak kimlik yönetimini kolaylaştırır.
- **Yetkilendirme için optimize edilmiş sorgular**: ORM’nin sunduğu ilişki sorgulama özellikleri, bir kullanıcının yetkilerini hızlıca kontrol etmeyi sağlar.

---

# OAuth ve OpenID

Modern web uygulamalarında, kullanıcıların harici hesaplarıyla (Google, Facebook, GitHub vb.) oturum açmaları veya bir uygulamanın başka bir uygulama adına veri çekmesi gibi senaryolar sıkça karşılaşılır. **OAuth 2.0** ve **OpenID Connect (OIDC)** bu noktada devreye giren iki önemli protokoldür. Bu bölümde OAuth ve OpenID Connect’in ne olduğunu, farklarını ve ORM ile nasıl kullanılabileceğini inceleyeceğiz.

## OAuth Nedir?

**OAuth (Open Authorization)**, kullanıcıların bir hizmete, başka bir hizmet üzerindeki hesaplarını kullanarak güvenli bir şekilde erişim izni vermesini sağlayan bir yetkilendirme protokolüdür. Örneğin, bir web sitesine "Google ile Giriş Yap" seçeneğini kullandığınızda, OAuth 2.0 protokolü devreye girer. Forum sitesi, Google hesabınızın şifresini görmeden, Google’dan sizi doğrulamasını ve temel bilgilerinizi almasını sağlar.

**OAuth bir kimlik doğrulama protokolü değildir, bir yetkilendirme protokolüdür.** Kullanıcıyı bir sağlayıcıya (örneğin Google) doğrulatır ancak asıl yaptığı işlem, o sağlayıcıdan bir erişim jetonu (*access token*) alıp bunu üçüncü taraf uygulamaya vermektir. Üçüncü taraf uygulama, bu token’ı kullanarak kullanıcının belirlenen verilere erişmesini sağlar.

Örneğin, bir fotoğraf baskı uygulaması, Google Photos hesabınızdaki resimlere erişmek istiyorsa, sizi Google’a yönlendirir ve izin ister. Siz izin verdiğinizde OAuth token alır ve bu token ile yalnızca fotoğraflara erişebilir, ancak hesabınızda başka işlemler yapamaz.

### OAuth 2.0 Akışları

OAuth 2.0, farklı yetkilendirme akışlarına sahiptir. En yaygın kullanılan **Authorization Code Flow** süreci şöyledir:

1. Uygulama, kullanıcıyı OAuth sağlayıcısına yönlendirir.
2. Kullanıcı oturum açar ve istenen izinleri onaylar.
3. Sağlayıcı, uygulamaya geçici bir yetki kodu (*authorization code*) ile döner.
4. Uygulama, bu kodu sağlayıcıya gönderip bir erişim token’ı alır.
5. Uygulama bu token ile API çağrılarını yapabilir.

Genellikle OAuth sağlayıcılarının sunduğu kütüphaneler, bu süreci geliştirici adına yönetir.

## OpenID Connect ve OAuth Arasındaki Farklar

**OpenID Connect (OIDC), OAuth 2.0 üzerine inşa edilmiş bir kimlik doğrulama katmanıdır.** OAuth yetkilendirme için kullanılırken, OpenID Connect kimlik doğrulama için geliştirilmiştir. 

### Ana Farklar

| **Özellik**            | **OAuth 2.0** | **OpenID Connect** |
|------------------------|--------------|------------------|
| **Amaç**              | Yetkilendirme | Kimlik Doğrulama |
| **Erişim Sağlar**     | API’lere erişim token’ı sağlar | Kullanıcı kimlik bilgilerini döndürür |
| **Çıktı**             | *Access Token* (kaynaklara erişim için) | *ID Token* (kullanıcı bilgileri için) |
| **Kullanım Alanı**    | Kullanıcının verilerine erişim izni almak | Kullanıcının kimliğini doğrulamak |

### OpenID Connect ile ID Token Kullanımı

OIDC, OAuth 2.0’ın yetkilendirme akışlarını kullanır ancak ek olarak bir **ID Token** kavramı getirir. **ID Token**, genellikle *JSON Web Token (JWT)* formatındadır ve kullanıcının benzersiz kimliği, adı, e-postası gibi bilgileri içerir. 

Örneğin, "Google ile Giriş Yap" seçeneğini kullandığınızda arka planda OpenID Connect çalışır. 
- **Access Token**, Google API’larına erişmek için kullanılır.
- **ID Token**, kullanıcının kimliğini doğrulamak için kullanılır.

OpenID Connect ayrıca standart API uç noktaları ekleyerek, OAuth 2.0’ı kimlik doğrulama için daha yapılandırılmış hale getirir. Örneğin `/userinfo` uç noktası ile kullanıcının ek profil bilgileri alınabilir.

## ORM ile OAuth ve OpenID Connect Kullanımı

ORM, OAuth veya OpenID Connect’in kimlik doğrulama sürecinde doğrudan yer almaz ancak kullanıcı bilgilerini saklamak ve yönetmek için kullanılır. Örneğin:

- OAuth/OpenID sağlayıcısından gelen kullanıcı bilgileri, **ORM kullanılarak veritabanında saklanabilir.**
- Kullanıcı ilk kez giriş yaptığında, **OAuth sağlayıcısındaki kimlik bilgileri ile yerel kullanıcı kayıtları eşleştirilebilir.**
- Kimlik doğrulama sonrası uygulama içinde bir **kullanıcı oturumu oluşturmak için ORM’den sorgular çalıştırılabilir.**

### Örnek Senaryolar

1. **Kimlik Doğrulama İçin OpenID Connect Kullanımı**
   - Kullanıcı, uygulamaya Google ile giriş yapmak istediğinde OAuth sağlayıcısına yönlendirilir.
   - Google’dan alınan **ID Token**, kullanıcının kimliğini doğrulamak için kullanılır.
   - ID Token içinde bulunan kullanıcı kimliği, ORM kullanılarak yerel veritabanında saklanabilir.

2. **Yetkilendirme İçin OAuth Kullanımı**
   - Kullanıcı, bir üçüncü taraf servisten veri almak için giriş yapar.
   - OAuth ile bir **Access Token** alınır ve bu token API çağrılarında kullanılır.
   - Kullanıcı verileri ORM kullanılarak kaydedilebilir veya güncellenebilir.

### Sonuç

**OAuth 2.0 ve OpenID Connect, modern web uygulamalarında güvenli kimlik doğrulama ve yetkilendirme sağlamak için kritik protokollerdir.** 

- **OAuth 2.0**, yetkilendirme için kullanılır ve bir uygulamaya belirli verilere erişim izni vermek için kullanılır.
- **OpenID Connect**, OAuth 2.0 üzerine kimlik doğrulama katmanı ekleyerek kullanıcıların kimliğini doğrulamak için kullanılır.

ORM, bu süreçlerde kullanıcı bilgilerini saklamak, yetkilendirme verilerini yönetmek ve kimlik doğrulama sürecini desteklemek için kullanılır. OAuth veya OpenID Connect entegrasyonu ile kullanıcı kimlik doğrulama ve yetkilendirme işlemleri kolaylaşır, güvenli hale gelir ve veri yönetimi daha verimli olur.


