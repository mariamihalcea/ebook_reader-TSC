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
https://docs.google.com/spreadsheets/d/1pr6Jj2wNiM2Fy9qMTXgbCBihdkyLsLs35BX2MHcexNk/edit?usp=sharing


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


##  5. Alte detalii relevante

La realizarea PCB-ului am intampinat si doua erori de Copper Width, desi aveam  dimensiunile corespunzatoare, asa ca le-am aprobat.
![image](https://github.com/user-attachments/assets/ab8d10f1-d4ad-4f12-891e-48c0aa6ba1ee)
<br>
si doua erori din cauza dimensiunii gaurilor din mufa USB, pe care de asemenea le am aprobat
![image](https://github.com/user-attachments/assets/e986b8fc-3912-48eb-a5c1-30f2c936a163)




---
