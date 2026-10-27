# Yer İstasyonu

LoRa yer istasyonu kartı: bilgisayara USB ile bağlanır, COM port olarak görünür ve
E220-900T30S modülü üzerinden 868 MHz LoRa ile haberleşir.

```
USB  ->  USB-UART dönüştürücü  ->  E220-900T30S (LoRa, 30 dBm)  ->  SMA anten
```

## Kartlar

| Klasör | USB-UART | Durum |
|---|---|---|
| [`cp2102n/`](cp2102n/) | CP2102N (QFN-24) | Tasarım bitti |
| `ch340g/` | CH340G (SOIC-16) | Yakında |

Her klasörde KiCad 10 projesi (`.kicad_pro`, `.kicad_sch`, `.kicad_pcb`) ve
`uretim/` altında Gerber, PDF ve alışveriş listesi var.

## Açmak için

KiCad 10 ile `.kicad_pro` dosyasını açın. Şema ve PCB, kullandıkları sembol ve ayak
izlerini kendi içinde taşır; ek kütüphane kurmadan açılır.
