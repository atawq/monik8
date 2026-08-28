# ⚡ monik8 ⚡

<p align="center">
  <img src="https://img.shields.io/badge/Exploit-SecureROM-ff4757?style=for-the-badge&logo=apple" alt="Exploit">
  <img src="https://img.shields.io/badge/SoC-A12%20%7C%20A13%20%7C%20S4%20%7C%20S5-2ed573?style=for-the-badge&logo=cpu" alt="SoCs">
  <img src="https://img.shields.io/badge/Hardware-RP2040%20%7C%20RP2350-1e90ff?style=for-the-badge&logo=raspberrypi" alt="Hardware">
  <img src="https://img.shields.io/badge/License-MIT-ffa502?style=for-the-badge" alt="License">
</p>

<p align="center">
  <b>monik8</b>, Apple'ın <b>A12, A13, S4 ve S5</b> yongalarında (SoC) Donanımsal BootROM/SecureROM seviyesinde kod çalıştırma imkanı sunan kalıcı ve geri alınamaz (unpatchable) bir tethered exploit aracıdır.
</p>

---

## 👨‍💻 Geliştiriciler & Katkıda Bulunanlar

<div align="center">

| Geliştirici | Rol | Bağlantı |
| :--- | :--- | :--- |
| 🛡️ **atawq** | Core Exploit Architect & Hardware Research | [GitHub Profile](https://github.com/atawq) |
| ⚡ **KuzeyMonik** | Firmware Integration & Tooling Lead | [GitHub Profile](https://github.com/KuzeyMonik) |

</div>

---

## 📌 Genel Bakış

**monik8**, Synopsys DesignWare USB 2 denetleyicisindeki donanımsal mantık hatası ile DFU modundaki aygıt yazılımı yapılandırma açığını birleştirir. Cihaz DFU modundayken özel USB veri paketleri gönderilerek USB bellek tamponu taşırılır ve SecureROM seviyesinde ham kod çalıştırma hakkı elde edilir.

* 🟢 **Donanımsal Düzey:** Donanım salt okunur (read-only) silisyuma kazındığı için yazılım güncellemeleriyle **kapatılamaz**.
* 🛡️ **Secure Enclave Güvenliği:** Parolalar ve SEP (Secure Enclave Processor) verilerine dokunmaz; cihaz şifreleme zinciri korunur.
* ⚡ **Hızlı Çalışma:** Exploit süreci donanım kontrolcüsü (RP2040/RP2350) üzerinde **1.5 ila 2 saniye** içerisinde tamamlanır.

---

## 🎯 Desteklenen Cihazlar & İşlemciler

### 📱 A12 Bionic
- iPhone XR
- iPhone XS / XS Max
- iPad Air (3. Nesil)
- iPad mini (5. Nesil)
- iPad (8. Nesil)
- Apple TV 4K (2. Nesil)

### 📱 A13 Bionic
- iPhone 11 / 11 Pro / 11 Pro Max
- iPhone SE (2. Nesil)
- iPad (9. Nesil)

### ⌚ S4 & S5 SoCs
- Apple Watch Series 4 & Series 5
- Apple Watch SE (1. Nesil)
- HomePod mini

> ⚠️ **Not:** A11 ve öncesi cihazlar checkm8 mimarisi kullanır; A14 ve sonrası cihazlar ise DART koruması nedeniyle kapsam dışındadır.

---

## 🛠️ Gereksinimler

Exploit, bilgisayar üzerindeki standart USB sürücülerinin sınırlarını aşan hassas USB zamanlamaları gerektirdiğinden harici bir mikrodenetleyici kartı gerektirir:

| Gereksinim | Detay / Önerilen Kartlar |
| :--- | :--- |
| 🎛️ **Donanım** | Raspberry Pi Pico (RP2040) / Pico 2 (RP2350) / Waveshare RP2040-Zero / TINY2350 |
| 🔌 **Kablo** | USB Data Kablosu (Pico $\rightarrow$ Target Apple Device) |
| 💻 **Yazılım** | Python 3.8+, `libusb`, `pyusb` |

---



# Derleme betiğini çalıştırın
chmod +x build_release.sh
./build_release.sh
