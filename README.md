# OpenBook E-Reader 

## 1. Diagrama bloc
![image](https://github.com/user-attachments/assets/2d6b794d-7fdf-4951-9a27-24080243b14b)




**Descriere:**

- Microcontrollerul **ESP32-C6** este unitatea centrala care gestioneaza comunicarea cu toate modulele periferice.
- Display-ul e-paper este controlat de un circuit dedicat de comanda.
- Senzorul ambiental **BME688** masoara calitatea aerului si temperatura.
- Memoria externa NOR Flash (64MB) si cardul SD permit stocarea fisierelor (eBook-uri, configurari etc).
- RTC-ul **DS3231SN** asigura ora exacta in mod autonom, chiar si in lipsa alimentarii.
- Incarcarea bateriei Li-Po se face prin USB-C, cu protectie ESD si monitorizare a nivelului de incarcare (MAX17048).
- Butoanele fizice permit resetul sistemului si selectii de tip boot.

---

## 2. Bill Of Materials (BOM)
| Componenta | Link | Datasheet |
|-----------|--------------|-----------|
| BUTTON | [Model](https://industry.panasonic.com/global/en/products/control/switch/light-touch/number/evqpuj02k) | [Datasheet](https://www.lcsc.com/datasheet/lcsc_datasheet_2201121800_PANASONIC-EVQPUJ02K_C2936858.pdf) |
| CAPACITOR | [Model](https://componentsearchengine.com/part-view/R0402%201%25%20100%20K%20(RC0402FR-07100KL)/YAGEO) | [Datasheet](//efaidnbmnnnibpcajpcglclefindmkaj/https://www.resistor.com/assets/pdf/0402tstd.pdf) |
| CPH3225A | [Model](https://www.snapeda.com/parts/CPH3225A/Seiko+Instruments/view-part/?ref=eda) | [Datasheet](https://octopart.com/datasheet/cph3225a-seiko-25340571) |
| EVQPUJ02K | [Model](https://industry.panasonic.com/global/en/products/control/switch/light-touch/number/evqpuj02k) | [Datasheet](https://www.lcsc.com/datasheet/lcsc_datasheet_2201121800_PANASONIC-EVQPUJ02K_C2936858.pdf) |
| KP-1608SURCK | [Model](https://www.snapeda.com/parts/KP-1608SURCK/Kingbright/view-part/?ref=search&t=LED%200603) | [Datasheet](//efaidnbmnnnibpcajpcglclefindmkaj/https://media.elv.com/file/107153_led_surck1608_data.pdf) |
| USBLC6-2SC6Y | [Model](https://www.snapeda.com/parts/USBLC6-2SC6Y/STMicroelectronics/view-part/?ref=eda) | [Datasheet](https://www.digikey.com/en/htmldatasheets/production/1375342/0/0/1/usblc6-2sc6y) |
| SD0805S020S1R0 | [Model](https://ro.mouser.com/ProductDetail/KYOCERA-AVX/SD0805S020S1R0?qs=jCA%252BPfw4LHbpkAoSnwrdjw%3D%3D) | [Datasheet](https://www.alldatasheet.com/view.jsp?Searchword=SD0805S&sField=2) |
| PGB1010603MR | [Model](https://www.snapeda.com/parts/PGB1010603MR/Littelfuse/view-part/?ref=eda) | [Datasheet](https://www.alldatasheet.com/view.jsp?Searchword=Pgb1010603mr&gad_source=1&gbraid=0AAAAADcdDU8aYfZtfJfdZ9I5j6RwZ_cbA&gclid=Cj0KCQjwqcO_BhDaARIsACz62vOPBOBe0eOh5gDUFkkKl4JBcbmoFZYtJ8BOnbaWqr_BuUCcVWvbutAaAmGkEALw_wcB) |
| BD5229G-TR  | [Model](https://componentsearchengine.com/part-view/BD5229G-TR/ROHM%20Semiconductor) | [Datasheet](https://www.lcsc.com/datasheet/lcsc_datasheet_2201131330_ROHM-Semicon-BD5229G-TR_C962636.pdf) |
| XC6220A331MR-G | [Model](https://componentsearchengine.com/part-view/XC6220A331MR-G/Torex) | [Datasheet](https://www.alldatasheet.com/view.jsp?Searchword=Xc6220&gad_source=1&gbraid=0AAAAADcdDU8aYfZtfJfdZ9I5j6RwZ_cbA&gclid=Cj0KCQjwqcO_BhDaARIsACz62vPS06NB6tLgniZzfaVpKNu1m811BNk6AEPfg4DbP6f5S8QWA_pW_UQaAv-0EALw_wcB) |
| XC6220A331MR-G | [Model](https://componentsearchengine.com/part-view/XC6220A331MR-G/Torex) | [Datasheet](https://www.alldatasheet.com/view.jsp?Searchword=Xc6220&gad_source=1&gbraid=0AAAAADcdDU8aYfZtfJfdZ9I5j6RwZ_cbA&gclid=Cj0KCQjwqcO_BhDaARIsACz62vMO5_aHsn35cIZBK6oCFuB_WOxz_zKu4yOHJ69-EnaUd5Jfas_Avm8aAuk5EALw_wcB) |
| USB4110-GF-A  | [Model](https://componentsearchengine.com/part-view/USB4110-GF-A/GCT%20(GLOBAL%20CONNECTOR%20TECHNOLOGY)) | [Datasheet](//efaidnbmnnnibpcajpcglclefindmkaj/https://gct.co/files/drawings/usb4110.pdf) |
| Adafruit | [Model](https://eu.mouser.com/ProductDetail/Adafruit/4208?qs=PzGy0jfpSMtbScLbr0L5dw%3D%3D) | [Datasheet](https://www.arrow.com/en/manufacturers/adafruit-industries/datasheets) |
| Bobina | [Model](https://store.comet.srl.ro/Catalogue/Product/43497/) | [Datasheet](https://www.scribd.com/document/814581278/Datasheet-Bobina) |
| PFMF | [Model](https://www.mouser.co.uk/ProductDetail/EPCOS-TDK/B72520T0350K062?qs=dEfas%2FXlABIszF52uu7vrg%3D%3D) | [Datasheet](https://ro.mouser.com/c/ds/circuit-protection/thermistors/resettable-fuses-pptc/?m=Schurter&series=PFMF) |
| DMG2305UX-7 | [Model](https://componentsearchengine.com/part-view/DMG2305UX-7/Diodes%20Incorporated) | [Datasheet](//efaidnbmnnnibpcajpcglclefindmkaj/https://www.mouser.com/datasheet/2/115/DMG2305UX-266242.pdf?srsltid=AfmBOop22k34YTJJra1xubiU6LPiN4M4JlcWbRoSNdxSGFak8uWgXPpK) |
| Si1308EDL-T1-GE3 | [Model](https://componentsearchengine.com/part-view/SI1308EDL-T1-GE3/Vishay) | [Datasheet](https://www.alldatasheet.com/view.jsp?Searchword=Si1308edl&gad_source=1&gbraid=0AAAAADcdDU-px713ONYSnQ2O-gcwqYcFq&gclid=Cj0KCQjwqcO_BhDaARIsACz62vN_Nz3MJOc6J_03gnVBm7aSqC8v9wyP0VD-iRKP-gFrYgdhLi99I14aAlVJEALw_wcB) |
| R0402 | [Model](https://componentsearchengine.com/part-view/R0402%201%25%20100%20K%20(RC0402FR-07100KL)/YAGEO) | [Datasheet](//efaidnbmnnnibpcajpcglclefindmkaj/https://www.resistor.com/assets/pdf/0402tstd.pdf) |
| BME680 | [Model](https://www.snapeda.com/parts/BME680/Bosch/view-part/?welcome=home) | [Datasheet](//efaidnbmnnnibpcajpcglclefindmkaj/https://www.bosch-sensortec.com/media/boschsensortec/downloads/datasheets/bst-bme680-ds001.pdf) |
| SMD Solder | [Model](https://grabcad.com/library/solder-jumpers-1) | [Datasheet]() |
| W25Q512JVEIQ | [Model](https://www.snapeda.com/parts/ESP32-C6-WROOM-1-N8/Espressif+Systems/view-part/?ref=eda) | [Datasheet](//efaidnbmnnnibpcajpcglclefindmkaj/https://www.mouser.com/datasheet/2/949/W25Q512JV_SPI_RevB_06252019_KMS-2487502.pdf?srsltid=AfmBOoquExqDVgxEELF9CzuOGxHos0CD1nQDROHD6Eebdm2foNzqozqU) |
| ESP32-C6-WROOM-1-N8 | [Model](https://www.snapeda.com/parts/ESP32-C6-WROOM-1-N8/Espressif+Systems/view-part/?ref=eda) | [Datasheet](//efaidnbmnnnibpcajpcglclefindmkaj/https://www.mouser.com/catalog/specsheets/Espressif_ESP32_C6_WROOM_1%20_Datasheet_V0.1_PRELIMINARY_en.pdf?srsltid=AfmBOooHQKNitqODRaaPjoZInfWKTacDER1t5uRK6sKqT13TrzvVo_B7) |
| DS3231SN# | [Model](https://www.snapeda.com/parts/DS3231SN%23/Analog+Devices/view-part/?ref=eda) | [Datasheet](https://www.alldatasheet.com/view.jsp?Searchword=Ds3231sn%20datasheet&gad_source=1&gbraid=0AAAAADcdDU-Gy9URfMxGmqiPg7ci5L3wR&gclid=Cj0KCQjwqcO_BhDaARIsACz62vMkK3ETSnW2w7mo0Fa-wgWJGn89AxWCyIND6k5X8MmoPl6hv6VWwT8aAiS-EALw_wcB) |
| MAX17048G+T10 | [Model](https://www.snapeda.com/parts/MAX17048G+T10/Analog+Devices/view-part/?ref=eda) | [Datasheet](https://www.alldatasheet.com/view.jsp?Searchword=Max17048&gad_source=1&gbraid=0AAAAADcdDU8aYfZtfJfdZ9I5j6RwZ_cbA&gclid=Cj0KCQjwqcO_BhDaARIsACz62vNa9xrVfzjCjADRwXD0RBbo4Nret3ywwteDGLJKZui8ZL8KdVlTE7caAvQxEALw_wcB) |
| MCP73831T-5ACI/OT | [Model](https://www.mouser.co.uk/ProductDetail/Microchip-Technology/MCP73831T-5ACI-OT?qs=hH%252BOa0VZEiAcgAcEkuamXg%3D%3D) | [Datasheet](//efaidnbmnnnibpcajpcglclefindmkaj/https://ww1.microchip.com/downloads/en/DeviceDoc/MCP73831-Family-Data-Sheet-DS20001984H.pdf) |


## 3. Descriere hardware detaliata

###  Microcontroller – ESP32-C6
- Controleaza toate componentele externe prin GPIO, I2C, SPI.

### E-paper Display + Driver
- Controlat prin SPI, cu tensiune separata de alimentare si control.

###  RTC – DS3231SN
- Ceas in timp real cu precizie mare si backup pe baterie.
- Comunicatie I2C cu ESP32-C6.
- Folosit pentru afisarea orei si sincronizare evenimente programate.

### Card SD
- Legat la ESP32 prin SPI.
- Utilizat pentru incarcare/citire fisiere eBook, configurari etc.

###  Senzor mediu – BME688
- Comunica prin I2C.
- Masoara temperatura, presiune, umiditate si compusi volatili.

###  Conector USB-C
- Folosit pentru incarcare si posibila conectare seriala cu PC pentru debug.

##  4. Conexiuni ESP32-C6

| Componenta            | Pin ESP32-C6      | Interfata | Motiv utilizare                      |
|----------------------|-------------------|-----------|--------------------------------------|
| E-paper Display       | IO06, IO07, IO08  | SPI       | Transfer rapid de date catre display |
| Flash NOR             | IO10, IO11, IO12  | SPI       | Stocare externa rapida               |
| Senzor BME688         | IO18 (SDA), IO19 (SCL) | I2C   | Comunicare cu senzori               |
| RTC DS3231SN          | IO18, IO19        | I2C       | Reutilizeaza magistrala I2C         |
| MAX17048 (Baterie)    | IO18, IO19        | I2C       | Monitor baterie, I2C comun           |
| SD Card               | IO01, IO02, IO03  | SPI       | Citire fisiere eBook                 |
| Buton reset/boot      | IO00, EN          | GPIO      | Control boot si reset manual        |

---

## 5. Pasi de implementare

### 1. Analiza documentatiei initiale
Am analizat schematicul si layout-ul placii furnizate de profesor. Pe baza acestora, am recreat designul electronic in Fusion Electronics, atat schema electrica, cat si placa PCB.

### 2. Plasarea componentelor pe PCB
Am asezat componentele pe placa, urmarind o pozitionare si orientare optime, pentru a permite o rutare eficienta si functionala.

### 3. Rutarea traseelor
Traseele de alimentare au fost rutate manual pentru a asigura robustete si dimensiuni corecte. Conexiunile ramase au fost rutate automat, folosind functia de autorouting pe ambele straturi (top si bottom). Am adaugat polygon pour pentru a crea plane de masa pe ambele straturi.

### 4. Optimizarea layout-ului
Am folosit vias pentru a conecta planele de masa intre straturi si pentru a completa zonele neconectate. Am aplicat via stitching pentru a imbunatati integritatea electrica a designului.

### 5. Generarea modelului 3D al placii
Pe baza designului 2D, am generat modelul 3D al placii. Am cautat si importat manual fiecare componenta 3D, pozitionandu-le conform plasamentului din PCB-ul 2D. Pentru componenta *test pad*, neavand un model disponibil online, am creat manual unul pentru a reprezenta corect placa in ansamblu.

### 6. Integrarea in ansamblul final – OpenBook Enclosure
Am importat modelul 3D al placii in fisierul principal al carcasei (OpenBook Enclosure). Acolo am plasat toate componentele in carcasa finala pentru a asigura o potrivire corecta si functionala. Display-ul si bateria au fost desenate manual pentru a fi integrate in ansamblu si pentru a oferi o reprezentare cat mai realista a produsului final.
##  6. Alte detalii relevante

La realizarea PCB-ului am intampinat si doua erori de Copper Width, desi aveam  dimensiunile corespunzatoare, asa ca le-am aprobat.
![image](https://github.com/user-attachments/assets/ab8d10f1-d4ad-4f12-891e-48c0aa6ba1ee)
<br>
si doua erori din cauza dimensiunii gaurilor din mufa USB, pe care de asemenea le am aprobat
![image](https://github.com/user-attachments/assets/e986b8fc-3912-48eb-a5c1-30f2c936a163)




---
