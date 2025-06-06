# 🛒 OpenCart E-Ticaret Sitesi - AWS Kurulumu ve Otomatik Ölçekleme (Auto Scaling)

Bu proje, açık kaynaklı e-ticaret platformu **OpenCart**'ın Amazon Web Services (AWS) üzerinde barındırılması ve otomatik olarak ölçeklenebilir hale getirilmesini içermektedir. Projede bir EC2 sunucusu üzerinde OpenCart kurulmuş, MySQL veritabanı için RDS kullanılmış ve Auto Scaling yapısı kurulmuştur.

---

## 📌 Proje Amacı

Bu çalışmanın amacı, yüksek erişilebilirlik ve ölçeklenebilirlik özelliklerine sahip, tamamen bulut tabanlı bir e-ticaret sistemi oluşturmaktır. AWS servisleri kullanılarak kurulan sistem, trafiğe bağlı olarak kaynakları dinamik şekilde artırıp azaltabilir.

---

## 🚀 Kullanılan AWS Servisleri

| Servis | Açıklama |
|--------|----------|
| **EC2** | OpenCart'ın kurulduğu sanal sunucu |
| **RDS (MySQL)** | Veritabanı hizmeti |
| **Auto Scaling Group** | Trafiğe göre EC2 sayısını otomatik yönetir |
| **Elastic Load Balancer (Opsiyonel)** | Trafiği dağıtmak için |
| **VPC ve Subnet** | Ağ yapılandırması |
| **Security Groups** | Güvenlik duvarı ayarları |

---

## 🧱 Teknolojiler

- **OpenCart 4.1.0.3**
- **Amazon Linux 2**
- **Apache HTTP Server**
- **PHP 8.x**
- **MySQL 8.x (AWS RDS)**

---

## 📝 Kurulum Adımları

### 1. EC2 Sunucusu Kurulumu

- Amazon Linux 2 AMI seçildi.
- Güvenlik grubu ayarlarında **SSH (22)**, **HTTP (80)** ve **HTTPS (443)** portları açıldı.
- SSH bağlantısı sağlandı:
  ```bash
  ssh -i "asd.pem" ec2-user@34.230.46.179
