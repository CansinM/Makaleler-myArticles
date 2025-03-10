# Postman ve API Geliştirme Sürecindeki Rolü

## Giriş

### Postman Nedir?
Postman, API geliştirme, test etme ve dökümantasyon süreçlerini kolaylaştıran popüler bir araçtır. API çağrılarının oluşturulmasını, yönetilmesini ve test edilmesini sağlar. Postman, geliştiricilere hem manuel hem de otomatik test süreçlerini kolaylaştırma imkânı sunar.

### API Nedir ve Neden Önemlidir?
API (Application Programming Interface), farklı yazılımların birbirleriyle iletişim kurmasını sağlayan arayüzdür. API’ler, uygulamalar arasında veri alışverişini standart hale getirir ve yazılım geliştirme sürecinde büyük bir öneme sahiptir. Örneğin, bir rezervasyon sisteminde müşteri bilgilerine erişmek, yeni rezervasyon oluşturmak veya var olan rezervasyonu güncellemek API’ler aracılığıyla gerçekleştirilir.

### Postman’ın API Geliştirme Sürecindeki Rolü
Postman, API'leri test etmek, doğrulamak, belgeleme oluşturmak ve entegrasyon süreçlerini yönetmek için kullanılan bir araçtır. API çağrıları oluşturmak, parametreler ve başlıklar (headers) eklemek, yanıtları incelemek ve hata ayıklamak için güçlü bir arayüz sunar. Ayrıca, koleksiyonlar (collections) oluşturarak çağrıları gruplamak ve paylaşmak mümkündür.

---

## API Çağrılarında Temel Bileşenler

### Params (Parametreler)
API çağrılarına dinamik değerler eklemek için **Params** sekmesi kullanılır. Örneğin, belirli bir müşteriyi getirmek için `id=3` parametresi eklenebilir.

### Headers (Başlıklar)
Headers, API çağrılarında kimlik doğrulama (Authorization), içerik tipi (Content-Type) gibi bilgileri içeren kısımdır.

### Body (İçerik)
POST, PUT ve PATCH çağrılarında **Body** bölümü kullanılarak JSON, XML veya başka formatlarda veri gönderilebilir.

**Örnek:**
```json
{
    "name": "Cansin Memis",
    "email": "cansin@example.com"
}
```

### Status (Durum Kodları)
Her API çağrısının bir **status code** (durum kodu) bulunur. Bu kodlar API çağrısının başarılı olup olmadığını gösterir.

- **200 OK** – Başarılı bir GET isteği
- **201 Created** – Başarılı bir POST isteği (Yeni bir kaynak oluşturuldu)
- **400 Bad Request** – Hatalı istek (Eksik veya yanlış parametre)
- **401 Unauthorized** – Yetkisiz erişim
- **404 Not Found** – Kaynak bulunamadı
- **500 Internal Server Error** – Sunucu hatası

---

## Postman Kullanımı

> Örnekler, [RESTful Booker](https://restful-booker.herokuapp.com/apidoc/index.html) API'si üzerinden gerçekleştirilecektir.

### Koleksiyonlar (New Collections)
Postman, API çağrılarını organize etmek için **koleksiyonlar** kullanır. Koleksiyonlar, farklı API isteklerini içeren klasörler gibi düşünülebilir. Bu koleksiyonlar sayesinde API'ler daha düzenli hale gelir ve belirli bir projeye ait çağrılar tek bir yerde tutulabilir.

---

## API Çağrıları ve Metodlar

### GET Metodu
GET metodu, API'den veri almak için kullanılır.

**Örnek:**
```http
GET https://restful-booker.herokuapp.com/booking/:id
```
- Params sekmesinde **Path Variable** kısmı açılır.
- **Key:** `id`, **Value:** İstenen rezervasyon ID’si girilir.
  
📌 **Bu işlemi gerçekleştirdiğinizde, girilen ID’ye ait rezervasyon bilgileri JSON formatında dönecektir.**

---

### POST Metodu
POST metodu, API'ye veri göndermek ve yeni kayıtlar oluşturmak için kullanılır.

**Örnek:**
```http
POST https://restful-booker.herokuapp.com/booking
```
- Headers:
  - **Key:** `Content-Type`, **Value:** `application/json`
- Body (raw/JSON formatında):
```json
{
    "firstname" : "Cansin",
    "lastname" : "Memis",
    "totalprice" : 5555,
    "depositpaid" : true,
    "bookingdates" : {
        "checkin" : "2025-01-01",
        "checkout" : "2025-01-01"
    },
    "additionalneeds" : "Kahvalti"
}
```
📌 **Bu isteği gönderdiğinizde, belirtilen rezervasyon detaylarıyla yeni bir rezervasyon oluşturulacaktır.**

#### Token Alma (POST)
```http
POST https://restful-booker.herokuapp.com/auth
```
- Headers:
  - **Key:** `Content-Type`, **Value:** `application/json`
- Body:
```json
{
    "username" : "admin",
    "password" : "password123"
}
```
📌 **Bu isteği göndererek bir oturum açma token’i oluşturabilirsiniz. Geri dönen token’i sonraki isteklerde yetkilendirme için kullanabilirsiniz.**

---

### PUT Metodu
PUT metodu, var olan bir veriyi tamamen güncellemek için kullanılır.

**Örnek:**
```http
PUT https://restful-booker.herokuapp.com/booking/:id
```
- Params sekmesinde **Path Variable** kısmı açılır.
- **Key:** `id`, **Value:** Güncellenecek rezervasyonun ID’si.
- Headers:
  - **Content-Type:** `application/json`
  - **Accept:** `application/json`
  - **Cookie:** `token=abc123`  **("abc123" yerine oluşturduğumuz token yazılır)**
- Body:
```json
{
    "firstname" : "James",
    "lastname" : "Brown",
    "totalprice" : 111,
    "depositpaid" : true,
    "bookingdates" : {
        "checkin" : "2018-01-01",
        "checkout" : "2019-01-01"
    },
    "additionalneeds" : "Breakfast"
}
```
📌 **Bu isteği kullanarak mevcut bir rezervasyonun tüm bilgilerini güncelleyebilirsiniz. Güncellenen bilgiler tamamen eski verinin yerine geçecektir.**

---

### PATCH Metodu
PATCH metodu, belirli alanları güncellemek için kullanılır. PUT'tan farklı olarak sadece bazı alanları değiştirmek mümkündür.

**Örnek:**
```http
PATCH https://restful-booker.herokuapp.com/booking/:id
```
- Headers:
  - **Content-Type:** `application/json`
  - **Accept:** `application/json`
  - **Cookie:** `token=abc123`
- Body:
```json
{
    "firstname" : "James",
    "lastname" : "Brown"
}
```
📌 **Bu isteği kullanarak yalnızca belirtilen alanları güncelleyebilirsiniz. PUT metodu tüm veriyi değiştirmeye odaklanırken, PATCH yalnızca seçili alanları değiştirir.**

---

### DELETE Metodu
DELETE metodu, belirli bir veriyi API üzerinden silmek için kullanılır.

**Örnek:**
```http
DELETE https://restful-booker.herokuapp.com/booking/:id
```
- Headers:
  - **Content-Type:** `application/json`
  - **Cookie:** `token=abc123`
 
📌 **Bu isteği gerçekleştirdiğinizde, belirtilen ID’ye sahip rezervasyon sistemden tamamen silinecektir.**

---
