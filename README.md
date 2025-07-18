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

---

STM32F405RGT Flight Controller & Development Board
This project is a hardware platform based on the STM32F405RGT6 (64-pin) microcontroller, designed as both a flight controller and a development board with an integrated ST-LINK programmer.

The board is equipped with critical sensors for flight modes and an extendable pin structure, making it ideal for both flight control and general embedded system development.

✨ Features
MCU: STM32F405RGT6 (Cortex-M4, 1MB Flash, 192KB SRAM, 64-pin LQFP)

ST-LINK v2.1: Built-in programmer (based on STM32F103CBT)

Sensors:

MPU-9250 (9-axis IMU - Gyroscope, Accelerometer, Magnetometer)

BMP180 (Barometric pressure and temperature sensor)

DHT11 (Humidity and temperature sensor)

(MPU9250 + BMP180 combo is widely available)

Wireless Communication:

nRF24L01: For data exchange with ground station

GPS: Neo-8Q (Pin-compatible with M8N alternative)

External antenna connector (replaceable)

GPIO:

4x LEDs (for flight modes): PA0, PA1, PA2, PA3

2x Power LEDs (3.3V & 5V)

Buzzer: PA8

PWM Outputs: PA0 - PA3

Boot & Reset buttons

Programming pins: PA13, PA14 (SWD)

UART4 (via ST-LINK): PC10 (TX), PC11 (RX)

Most GPIOs are left free for user integration

📡 Wireless Features
Component	Description
nRF24L01	Communication with ground station
Neo-8Q GPS	Positioning and flight route tracking
Antenna Out	External antenna connector, replaceable

🛠️ Use Cases
🚁 Drone/UAV flight control

🧑‍💻 STM32 development platform

📡 Wireless data transmission prototypes

📦 Research & educational projects for sensor integration

🔌 Pinout & Peripherals
Function	Pins
Flight Mode LEDs	PA0, PA1, PA2, PA3
Power LEDs	3.3V, 5V
Buzzer	PA8
Boot & Reset Buttons	GPIO controlled
PWM Outputs	PA0 - PA3
SWD Programming	PA13, PA14
UART4 (ST-LINK)	PC10 (TX), PC11 (RX)
GPS	External connection
nRF24L01	SPI interface

⚙️ Programming & Debug
Built-in ST-LINK

Based on STM32F103CBT

SWD pins exposed (PA13, PA14)

Compatible with STM32CubeProgrammer and OpenOCD

UART Debugging

Connected via UART4 to ST-LINK

📦 Integration & Expandability
All critical flight sensors are integrated

Most GPIOs are left free – ready for additional hardware or custom modules

Developers can easily integrate their own circuits or sensors

🚀 Getting Started
Connect to PC via USB (ST-LINK auto-detected)

Flash firmware using STM32CubeProgrammer

Connect external sensors and modules to GPIOs

Start serial communication via UART4

📃 License
This project is fully open-source. Anyone is free to develop and integrate.

📝 Notes
MPU9250 and BMP180 are widely available and often sold as combined modules.

Neo-8Q GPS is used; Pin-compatible M8N can also be used.
