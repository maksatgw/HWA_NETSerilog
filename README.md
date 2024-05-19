# HWA Serilog Task

Serilog structured event data yapısını destekleyen, güçlü bir Log kütüphanesidir. Farklı hedeflere kaydetmeye olanak tanır. Bu projede default olarak gelen .net core api template'i üzerine gerekli implemantasyonlar yapılmış olup, log kayıtları task gereği txt dosyasına kaydedilmiştir. Ek olarak kaynaklardan yararlanarak bir log platformu olan SEQ'e logların gönderilmesi sağlanmıştır.

## Paketler

Serilog
```bash
dotnet add package Serilog.AspNetCore
```
Seq
```bash
dotnet add package Serilog.Sinks.Seq
```

## Kurulum

program.cs
```csharp
using Serilog;

var logger = new LoggerConfiguration().ReadFrom.Configuration(builder.Configuration).CreateLogger();
builder.Logging.ClearProviders();
builder.Logging.AddSerilog(logger);
```
appsettings.json
```json
"Serilog": {
    //Serilog ayarlamaları
}
```
## Kaynaklar

[Gençay Yıldız Serilog](https://www.gencayyildiz.com/blog/asp-net-core-serilog-ile-veri-loglama-ve-seq-ile-gorsellestirme/) -
[Nuray Kılıç Medium](https://medium.com/@nuraykilic/serilog-ile-net-6da-loglama-i%CC%87%C5%9Flemleri-89b04ef32303)
