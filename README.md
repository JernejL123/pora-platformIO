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

## Časovna in prostorska zahtevnost

## Vzdrževanje

##Lastna uporaba

