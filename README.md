
# 🛍️ OpenCart AWS E-Ticaret Projesi

Bu proje, OpenCart tabanlı bir e-ticaret sitesinin Amazon Web Services (AWS) üzerinde barındırılması, yapılandırılması ve ölçeklenmesini kapsamaktadır. Projede EC2, RDS ve Auto Scaling servisleri kullanılmıştır.

---

## 📌 Bileşenler

- **OpenCart v4.1.0.3**
- **EC2**: Web sunucusu (Apache + PHP)
- **RDS (MySQL)**: Veritabanı sunucusu
- **Auto Scaling & Load Balancer**
- **Amazon VPC**

---

## ☁️ AWS Üzerinde Kurulum Adımları

### 1. EC2 Üzerinde Apache ve PHP Kurulumu

```bash
sudo yum update -y
sudo yum install -y httpd php php-mysqlnd php-gd php-mbstring php-xml unzip
sudo systemctl start httpd
sudo systemctl enable httpd
````

### 2. OpenCart Kurulumu

```bash
# OpenCart zip dosyasını EC2'ye yükleyin
scp -i "asd.pem" "C:\Users\bycyc\Downloads\opencart-4.1.0.3.zip" ec2-user@34.230.46.179:/home/ec2-user/

# Dosyaları açın ve dizine taşıyın
cd /var/www/html
sudo unzip /home/ec2-user/opencart-4.1.0.3.zip
sudo cp -r upload/* .
sudo cp config-dist.php config.php
sudo cp admin/config-dist.php admin/config.php
sudo chown -R apache:apache /var/www/html
sudo chmod -R 755 /var/www/html
```

### 3. RDS MySQL Veritabanı

* AWS RDS üzerinden bir MySQL veritabanı oluşturun.
* EC2 instance'ının IP'sine RDS Security Group üzerinden 3306 portunu açın.
* Veritabanı bağlantısını test edin:

```bash
mysql -h <rds-endpoint> -u admin -p
```

### 4. OpenCart Web Arayüzünden Kurulum

* Tarayıcıdan EC2 IP’sine gidin: `http://<EC2-IP>`
* Kurulum ekranında RDS bilgilerini girin (host, kullanıcı, şifre, veritabanı).
* Kurulumdan sonra güvenlik için install klasörünü silin:

```bash
sudo rm -rf /var/www/html/install
```

---

## 🔁 Auto Scaling

* VPC oluşturun, içinde 2 veya daha fazla farklı **Availability Zone** barındıran subnet'ler tanımlayın.
* EC2 Launch Template oluşturun (gerekli instance, AMI, güvenlik grubu).
* Auto Scaling Group ayarlayın, Load Balancer ile ilişkilendirin.

---

## 📁 Dosya Yapısı

```
/var/www/html/
├── admin/
├── catalog/
├── config.php
├── admin/config.php
└── ...
```

---

## 👤 Geliştirici

**Ömer Doğan**
**Youtube:**
