# 🔐 .NET Authentication API

Bu proje, .NET Core Web API kullanılarak geliştirilen basit ve güvenli bir kimlik doğrulama servisidir. Frontend veya mobil uygulamaların kullanıcı kaydı ve oturum açma işlemlerini gerçekleştirmesi için temel bir altyapı sunar. Giriş işlemi sonrası JWT (JSON Web Token) üretir ve kullanıcıya geri döner.

## 🚀 Özellikler

- Kullanıcı Kaydı (POST /auth/register)
- Kullanıcı Girişi ve Token Üretimi (POST /auth/login)
- (Opsiyonel) Oturum Sonlandırma (POST /auth/logout)
- JWT ile kimlik doğrulama
- Postman ile test edilebilir API
- Entity Framework Core ile SQLite veya SQL Server Express desteği

## 🛠️ Kullanılan Teknolojiler

- .NET 7 / .NET 8 (Web API)
- Entity Framework Core
- SQLite / SQL Server Express
- JWT (System.IdentityModel.Tokens.Jwt)
- Swagger (OpenAPI) ile dokümantasyon
- Postman Collection (test için)

## 🗂️ Proje Yapısı

```
AuthenticationApi/
├── Controllers/
│   └── AuthController.cs
├── Models/
│   ├── User.cs
│   └── DTOs/ (RegisterDto, LoginDto)
├── Services/
│   └── AuthService.cs
├── Helpers/
│   └── JwtService.cs
├── Data/
│   └── AppDbContext.cs
├── Program.cs
└── appsettings.json
```

## 🔄 API Endpointleri

| Endpoint             | Method | Açıklama                     |
|----------------------|--------|------------------------------|
| /auth/register       | POST   | Yeni kullanıcı kaydı         |
| /auth/login          | POST   | Giriş ve JWT üretimi         |
| /auth/logout         | POST   | (Opsiyonel) Oturumu kapatma  |

## 🧪 Test

Postman veya Swagger UI üzerinden tüm endpoint’ler test edilebilir. Projeye ait .json Postman Collection dosyası /docs klasöründe mevcuttur.

## ⚙️ Kurulum

1. Projeyi klonla:
   git clone https://github.com/kullaniciAdi/AuthenticationApi.git

2. Gerekli NuGet paketlerini yükle:
   dotnet restore

3. Migration ve veritabanı oluştur:
   dotnet ef database update

4. Uygulamayı başlat:
   dotnet run

## 🔐 JWT Bilgisi

Başarılı giriş sonrası aşağıdaki formatta bir JWT token döner:

```json
{
  "token": "eyJhbGciOiJIUzI1NiIsInR..."
}
```

Bu token Authorization header’ına şu şekilde eklenerek kullanılabilir:

Authorization: Bearer eyJhbGciOi...

## 📄 Lisans

MIT License
