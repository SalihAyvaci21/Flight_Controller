#  STM32F405RGT Flight Controller & Development Board

Bu proje, **STM32F405RGT6 (64-pin)** mikrodenetleyicisi tabanlı bir uçuş kartı ve aynı zamanda **entegre ST-LINK** programlayıcısı ile bir geliştirme kartı olarak kullanılabilecek bir donanım platformudur.  

Kart, uçuş modlarını kontrol etmek için kritik sensörler ve genişletilebilir pin yapısıyla tasarlanmıştır. Hem uçuş kontrolü hem de genel gömülü sistem geliştirme için idealdir.



## ✨ Özellikler

- **MCU**: STM32F405RGT6 (Cortex-M4, 1MB Flash, 192KB SRAM, 64-pin LQFP)
- **ST-LINK v2.1**: Dahili programlayıcı (STM32F103CBT tabanlı)
- **Sensörler**:
  - MPU-9250 (9 Eksen IMU - Gyro, Accelerometer, Magnetometer)
  - BMP180 (Barometrik basınç ve sıcaklık sensörü)
  - DHT11 (Nem ve sıcaklık sensörü)
  - (MPU9250 + BMP180 kombinasyonu Türkiye’de kolay bulunabilir)
- **Kablosuz Haberleşme**:
  - **nRF24L01**: Yer istasyonu ile veri alışverişi
  - **GPS**: Neo-8Q (Pin-to-Pin uyumlu M8N alternatifi)
  - Harici anten çıkışı (değiştirilebilir)
- **GPIO**:
  - 4x LED (Uçuş modları için): `PA0`, `PA1`, `PA2`, `PA3`
  - 2x Güç LED’i (3.3V & 5V)
  - Buzzer: `PA8`
  - PWM Çıkışları: `PA0` - `PA3`
  - Boot & Reset düğmeleri
  - Programlama pinleri: `PA13`, `PA14` (SWD)
  - UART4 (ST-LINK üzerinden): `PC10` (TX), `PC11` (RX)
  - Çoğu GPIO **boşta bırakıldı**, kullanıcı entegrasyonu için hazır

---

## 📡 Kablosuz Özellikler

| Bileşen        | Açıklama                                    |
|----------------|---------------------------------------------|
| **nRF24L01**   | Yer istasyonu ile haberleşme için           |
| **Neo-8Q GPS** | Konumlandırma ve uçuş rotası takibi         |
| **Anten Çıkışı**| Harici anten bağlantısı, değiştirilebilir   |

---

## 🛠️ Kullanım Senaryoları

- 🚁 Drone/UAV uçuş kontrolü
- 🧑‍💻 STM32 geliştirme platformu
- 📡 Kablosuz veri iletimi prototipleri
- 📦 Sensör entegrasyonu için araştırma & eğitim projeleri

---

## 🔌 Pinout & Peripherals

| Fonksiyon             | Pinler             |
|-----------------------|---------------------|
| Uçuş Modu LED’leri    | PA0, PA1, PA2, PA3  |
| Güç LED’leri          | 3.3V, 5V            |
| Buzzer                | PA8                 |
| Boot & Reset Butonları| GPIO kontrollü      |
| PWM Çıkışları         | PA0 - PA3           |
| SWD Programlama       | PA13, PA14          |
| UART4 (ST-LINK)       | PC10 (TX), PC11 (RX)|
| GPS                   | Harici bağlantı     |
| nRF24L01              | SPI bağlantısı      |

---

## ⚙️ Programlama & Debug

- **ST-LINK Dahili**
  - STM32F103CBT tabanlı entegre ST-LINK
  - SWD pinleri dışarı alınmıştır (`PA13`, `PA14`)
  - STM32CubeProgrammer veya OpenOCD ile uyumlu
- **UART Debugging**
  - UART4 üzerinden ST-LINK’e bağlantı

---

## 📦 Entegrasyon & Genişletilebilirlik

- Tüm kritik uçuş sensörleri **entegre edilmiştir**  
- Çoğu GPIO boşta bırakılmıştır – ek donanımlar ve özel modüller için kullanılabilir
- Geliştiriciler kendi devrelerini veya sensörlerini kolayca entegre edebilir

---

## 🚀 Başlarken

1. USB üzerinden bilgisayara bağlanın (ST-LINK otomatik tanınır)
2. STM32CubeProgrammer ile firmware yükleyin
3. Harici sensörleri ve modülleri GPIO’lara bağlayın
4. UART4 ile seri haberleşmeyi başlatın

---

## 📃 Lisans

Bu proje tamamen açık kaynaklıdır. İsteyen herkes geliştirme ve entegrasyon yapabilir.

---

## 📝 Notlar
- MPU9250 ve BMP180 Türkiye’de kolay bulunabilir ve birlikte modül olarak satılmaktadır.
- GPS için Neo-8Q kullanılmıştır; Pin-to-Pin uyumlu M8N de kullanılabilir.
