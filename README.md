# pora-PlatformIO

**PlatformIO** je odprtokodna, platformno odvisna razvojna knjižnica in okolje za razvoj vgrajenih sistemov.  
Omogoča razvoj, prevajanje, nalaganje kode in upravljanje knjižnic za mikrokrmilnike, kot so **ESP32**, **Arduino**, **STM32** itd.

V mojem projektu jo uporabljam za razvoj programske opreme za **tehtnico panjev**, ki temelji na **ESP32**, senzorju **HX711** in **load cellih**.

---

## Utemeljitev izbire

- omogoča delo z **ESP32 + HX711 in load celli** (vse, kar potrebujem za moj projekt)
- ima **vgrajeno upravljanje knjižnic** (npr. HX711)
- **prijaznejši debugging**
- je **neodvisna od operacijskega sistema** (Windows, Linux, macOS)
- podpira **razvoj več projektov hkrati**
- ogromno **zelo dobre dokumentacije** ter **velik community**
- **open-source**
- **integracija v Visual Studio Code**

---

## Prednosti

### 1. Celovit ekosistem

PlatformIO omogoča celovito razvojno okolje, ki združuje orodja za **upravljanje knjižnic**, **prevajanje**, **nalaganje kode** in **testiranje** v enem sistemu. Razvijalcem omogoča enostavnejše upravljanje odvisnosti in boljšo organizacijo projekta. To je prednost v primerjavi s tradicionalnimi razvojnimi orodji, kjer je pogosto potrebna ločena konfiguracija posameznih komponent razvojnega procesa.

#### Primer: Arduino IDE

- **knjižnice** → pogosto ročno nameščanje in slabše upravljanje verzij  
- **projektna struktura** → enostavna, a omejena  
- **pomanjkljivost sistemov za avtomatsko testiranje**

#### Primer: PlatformIO

- upravlja knjižnice  
- upravlja orodja za prevajanje  
- omogoča testiranje  
- deluje enako na vseh operacijskih sistemih  

---

### 2. Večplatformna podpora

Za razliko od nekaterih specializiranih IDE-jev, ki so vezani na določen operacijski sistem (npr. Windows), PlatformIO ponuja **enakovredno večplatformno podporo**.

#### Primer: Keil µVision

IDE za ARM (STM32, NXP) mikrokontrolerje, ki **nima uradne podpore za Linux ali macOS**.

---

### 3. Napredno upravljanje knjižnic

Z avtomatskim upravljanjem odvisnosti knjižnic PlatformIO poenostavi postopek vključevanja knjižnic v projekt. Ta funkcija zagotavlja, da se uporabljajo pravilne različice, kar zmanjšuje konflikte in napake, ki lahko nastanejo zaradi ročnega upravljanja odvisnosti, kar je pogosta težava v bolj ročno upravljanih okoljih.

#### Primer dodajanja knjižnice za HX711 brez PlatformIO (npr. Arduino IDE)

- ročno preneseš knjižnico HX711  
- jo kopiraš v mapo `libraries`  
- skrbiš, da je prava verzija  

#### Primer dodajanja knjižnice za HX711 s PlatformIO

V datoteko `platformio.ini` napišeš:

<img width="300" height="20" alt="image" src="https://github.com/user-attachments/assets/180dd55b-2637-4775-9a7f-012c773d52af" />

in PlatformIO sam prenese knjižnico, jo poveže s projektom in omogoča, da projekt brez težav deluje tudi na drugem računalniku.

## Slabosti

### 1. Strmejša krivulja učenja

Širok nabor funkcij PlatformIO je lahko sprva preobremenjujoč. Začetnikom se lahko zdi nastavitev in konfiguracija bolj zapletena v primerjavi z bolj preprostimi orodji, prilagojenimi arhitekturam ali ekosistemom z eno samo ploščo (mikrokrmilnikom).

#### Primer: V primerjavi z Arduino IDE, ki je zasnovan za hiter in enostaven začetek, PlatformIO zahteva več začetne konfiguracije.

### 2. Večja poraba virov
Ker je okolje bogato s funkcijami, lahko porabi več sistemskih virov v primerjavi z minimalističnimi orodji. To je lahko problematično na slabših računalnikih.

## Število uporabnikov
<img width="2515" height="459" alt="image" src="https://github.com/user-attachments/assets/8d755bc2-ccfa-407c-890f-ec5512835a88" />
<img width="1728" height="322" alt="image" src="https://github.com/user-attachments/assets/7fd088ab-5535-4c4a-8d26-c4695ea02a3c" />


## Časovna in prostorska zahtevnost

#### Časovne zahtevnosti ni, saj ne gre za algoritem.
#### Prostorska zahtevnost: PlatformIO približno 200–500 MB in Knjižnice	1–50 MB (odvisno od projekta)

## Vzdrževanje
Ekipa: PlatformIO LLC <br>
Odprtokodna platforma: glavna koda je na GitHubu
Vzdrževalci: ekipa razvijalcev, ki redno posodablja:
- Core (platformio-core)
- IDE razširitve (VS Code, Atom)
- Knjižnice in platforme (ESP32, Arduino, STM32…)

<img width="1688" height="510" alt="image" src="https://github.com/user-attachments/assets/e1cac1f2-12b2-4bd3-8886-e4bfae6728be" />

## Licenca
Apache License <br>
Version 2.0, January 2004 <br>
http://www.apache.org/licenses/

## Osnove platformIO

#### Ustvari projekt in izberi svoj board:
<img src="https://github.com/user-attachments/assets/e1f51838-9e2f-4cf2-948c-d93a693aad00" width="300px">

#### Funkcije (Build,Upload,Serial Monitor)
<img width="483" height="291" alt="image" src="https://github.com/user-attachments/assets/c88c7209-817d-4edf-8669-950bf05413e2" />


## Lastna uporaba
Namen moje uporabe je merjenje teže panjev. Za to uporabim load celle ki so povezani na HX711, ki pretvori analogno meritev v digitalni signal (sprememba teže) in ga posreduje mikrokrmilniku (ESP32), kjer se z ustrezno kalibracijo pretvori v meritev teže. To mertiev potem preko APIja shranim v podatkovno bazo ter jo kasneje prikažem v uporabniškem vmesniku (npr. spletni strani, android aplikaciji). 
<br>
<br>
<img src="https://github.com/user-attachments/assets/9ee300e6-ad68-4ebd-a1a9-df4e3a93787c" width="300px">
<img src="https://github.com/user-attachments/assets/01118939-83b6-4806-9ada-530aba85920e" width="300px">

<img width="1165" height="182" alt="image" src="https://github.com/user-attachments/assets/acc9f79e-e815-498c-89ec-208ecb03a024" />
<img width="400" alt="image" src="https://github.com/user-attachments/assets/cbd0d3c1-b37a-412f-a700-d74435084e3d" />
<img width="2426" height="959" alt="image" src="https://github.com/user-attachments/assets/5840895f-1f54-4982-ab10-7dc14f445244" />

# HX711 + ESP32: deli kode


#### Povezava HX711 s pini ESP32
  ```cpp
  HX711 cell;
  const int LOADCELL_DOUT_PIN = 26; // izhod podatkov iz HX711
  const int LOADCELL_SCK_PIN  = 27; // (Serial Clock) vhodni pin za uro
  ```
#### Nastavitev kalibracijskega faktorja
  ```cpp
  float calibration_factor = 129200;
  ```

#### Inicializacija HX711 in ničelna teža
  ```cpp
  void setup() {
    Serial.begin(115200);
  
    cell.begin(LOADCELL_DOUT_PIN, LOADCELL_SCK_PIN);
    cell.set_scale(); // brez faktorja
    cell.tare();      // resetira tehtnico na 0
  }
  ```

#### Meritev teže in pošiljanje na API
  ```cpp
  void loop() {
    cell.set_scale(calibration_factor); 
    float weight = cell.get_units(5);   // povprečje 5 vzorcev
    if(weight < 0) weight = 0.00;

    Serial.print("Kilogram:");
    Serial.println(weight); 
    api.postWeight(weight);         
    delay(100);
  }
  ```



