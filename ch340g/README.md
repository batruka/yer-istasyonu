# Yer İstasyonu — CH340G sürümü

> **Çalışma devam ediyor.** PCB yerleşimi ve yolları bitmedi; bu klasörden üretim yapmayın.

```
USB-C (Pololu breakout)  ->  CH340G (USB-UART)  ->  E220-900T30S (LoRa, 30 dBm)  ->  SMA anten
```

CP2102N sürümünden farkı: takım kuralına uymak için SOP'tan küçük kılıf kullanılmadı.
QFN CP2102N yerine SOIC-16 CH340G, çıplak USB-C yerine Pololu breakout, SOT-23-6 ESD
yerine SOT-23 ESD var.

## Ana parçalar

| Ref | Parça | Not |
|---|---|---|
| U3 | CH340G | USB-UART, SOIC-16; +3V3 ile beslenir (VCC = V3) |
| Y1, C15, C16 | 12 MHz kristal + 2 x 22 pF | CH340G saat kaynağı |
| U2 | E220-900T30S | LoRa modülü, VBUS'tan (5V) beslenir |
| U1 | AMS1117-3.3 | +3V3: CH340G ve J1 başlığı |
| U4 | PJDLC05 | USB D+/D− ESD koruma (SOT-23) |
| J3 | Pololu USB 2.0 Type-C breakout (usb07b) | CC 5.11k dirençleri breakout üzerinde |
| J4 | BWSMA-KWE-Z001 | Dik açılı SMA |
| J2, J5 | Pin başlığı | M0 / M1 seçimi |

Dosya adları tarihsel sebeple `yer istasyonu CH340N.*`; kartta CH340G kullanılıyor.

## Tasarım kuralları (projede ayarlı)

- Sinyal yolu 0.3 mm, boşluk 0.25 mm
- VBUS ve GND ("Guc" sınıfı) 1.2 mm
- Via 2.6 / 1.6 mm (1 mm perçin için)
- J1/J2/J5 ve J3 ayak izleri perçinli: delik 1.6 mm, ped 2.25 mm

## Yapılacaklar

- [ ] Kart sınırı (Edge.Cuts)
- [ ] Anten yolu (E220 pin 18 → J4)
- [ ] Şema ile PCB'yi eşitle (F8): C12, C13, C14 PCB'de yok; PCB'deki C5, C6 şemada yok
- [ ] ERC: bir güç ağı sürülmüyor (#PWR013), PWR_FLAG gerekebilir
- [ ] DRC temizliği, ardından Gerber / PDF
