# brewingsystem
Design of the electronics etc. for my homebrewery

# Parts

* Pt100 4-wire Class A

http://www.omega.co.uk/pptst/PRS-3-100.html

* AD7124-8BCPZ 24 bit ADC

Chip: 

http://uk.farnell.com/analog-devices/ad7124-8bcpz/adc-24bit-19-2ksps-spi-lfcsp-32/dp/2490565 

Evaluation board: 

http://uk.farnell.com/analog-devices/eval-ad7124-8sdz/eval-brd-ad7124-8-24bit-sigma/dp/2490578

* LMP91200 Analogue front end to pH sensor (needs ADC)

Chip:

http://uk.farnell.com/texas-instruments/lmp91200mt-nopb/analogue-front-end-ph-sensing/dp/2496273

* MAX13433EESD+ RS485 TXRX, 16MBPS

Chip:

http://uk.farnell.com/maxim-integrated-products/max13433eesd/rs485-txrx-16mbps-5-5v-nsoic-14/dp/2511596

* 8 circuit DIP Switch (for specifying modbus address)

http://uk.farnell.com/multicomp/mcdha-08tqr/dip-switch-8-pos-spst-flush-slide/dp/2422607

* RJ45 Jack

http://uk.farnell.com/multicomp/mtj-881x1/modular-jack-tht-r-a-rj45-8p8c/dp/2112501

* Ethernet cable for connecting the RS-485 sensors.  Look for cat5e STP.

* PQLYT 40A SSR

http://www.aliexpress.com/store/product/PQLYT-100-QUALITY-actually-max-40A-SSR-input-3-32VDC-output-24-480VAC-solid-state-relay/808493_1984942532.html

* Ultrasound distance module (for sensing level, and deriving volume from) 

http://www.ebay.co.uk/itm/181954043101




* Wifi modules 

| Chip Name     | Cost          | Arch 	         | Features   |
| ------------- | ------------- | -------------- | ---------- |
| ESP8266       | $2 / module   | Tensilica RISC |            | 


```
+------------------------+
|                        |
|                        |
|  Raspberry Pi running  |
|  modbus library        |
|                        |
|                        |
|                        |
+-----------+------------+
            |
            |
    +-------+--------+
    |                |
    | RS485 chip     |
    | attached to    |
    | Pi UART        |
    |                |
    +-------+--------+
            |
   +--------+----------+
   |                   |
   | RS485 PID         |
   | with SSR and temp |
   | probe             |
   |                   |
   +--------+----------+
            |
            |
   +--------+----------+
   | RS485 volume      |
   | sensor            |
   |                   |
   +-------------------+

``` 

# Software to use


## Modbus 

* https://github.com/karlp/fmb-demo for STM32 chips

## Firmware

* http://libopencm3.org/wiki/Main_Page for providing the ability to write code for different STM32 chips
