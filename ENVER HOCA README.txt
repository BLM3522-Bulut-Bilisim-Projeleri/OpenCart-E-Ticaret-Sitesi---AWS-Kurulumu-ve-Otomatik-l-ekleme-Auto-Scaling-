Bu projede aşağıdaki adımları gerçekleştirdim:

- OpenCart platformunu hazır olarak edindim. PHP, HTML ve CSS tabanlı bu dosyaları EC2 sunucusuna kurarak çalıştırdım.
- AWS RDS üzerinde MySQL veritabanı oluşturdum ve OpenCart yapılandırma dosyaları üzerinden bağlantı sağladım.
- Auto Scaling Group yapılandırarak sistemin trafiğe göre EC2 instance sayısını otomatik olarak artırmasını sağladım.
- Security Group ayarları yaparak gerekli port (80, 443, 3306) izinlerini verdim.
- **Bu projeyi ücretsiz AWS kullanım sınırlarıyla** gerçekleştirdim. Bu yüzden **sunucularım şu anda aktif değil**.
- **Yük testi yapmadım**, sadece kurulum ve bağlantı kontrollerini gerçekleştirdim.