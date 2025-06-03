# 🌱 Proiect: Solar Automatizat Inteligent

## 🎯 Scopul proiectului

Construirea unui sistem complet automatizat pentru gestionarea unui solar, folosind senzori de mediu, microcontrolere (ESP32), o interfață IoT și inteligență artificială. Sistemul va putea monitoriza și controla udarea, ventilația, iluminarea și încălzirea în funcție de datele colectate și de predicțiile unui model ML. Pe termen lung, proiectul urmărește integrarea unui PCB personalizat și alimentarea prin panouri solare.

---

## 📦 Ce vreau să realizez

* Un **sistem modular** de automatizare pentru un solar (mini-sistem de test inițial)
* Senzori pentru **umiditate sol**, **temperatură**, **umiditate aer** și **nivel lumină**
* Control automat pentru:

  * **Pompa de apă** (udare inteligentă pe zone)
  * **Ventilator** (ventilare automată)
  * **Trapă** (servo pentru aerisire)
  * **Încălzire iarna** (radiator PTC)
* Un **dashboard IoT** pentru vizualizare și control remote
* Un **API Python** care primește date, folosește un model ML și returnează comenzi
* Un **PCB** proiectat pentru compactarea și integrarea hardware-ului
* Opțional: **alimentare cu panouri solare** și management inteligent al energiei

---

## 🧩 Componente hardware necesare

| Componentă                       | Descriere                             | Cantitate |
| -------------------------------- | ------------------------------------- | --------- |
| ESP32 DevKitC                    | Microcontroller WiFi & Bluetooth      | 1         |
| Senzor umiditate sol             | Capacitiv, non-coroziv                | 2-3       |
| Senzor temperatură/umiditate aer | DHT22 sau BME280                      | 1         |
| Senzor lumină                    | LDR + rezistor 10k sau BH1750 I2C     | 1         |
| Pompă de apă                     | 5V/12V, peristaltică/submersibilă     | 1         |
| Electrovalve                     | 12V, pentru zonare udare              | 2-3       |
| Ventilator                       | 5V/12V, controlat cu MOSFET sau releu | 1         |
| Servo motor                      | SG90 pentru trapă de aerisire         | 1         |
| Radiator PTC                     | Încălzire automată iarna (12V)        | 1         |
| MOSFET-uri logic-level           | IRL540N / IRLZ44N                     | 3-5       |
| Breadboard + fire                | Prototipare rapidă                    | 1         |
| Alimentare 5V/12V 5A             | Sursă pentru toată instalația         | 1         |
| Terminale / Conectori            | Pentru conectare senzori și actuatori | Mai multe |
| Panou solar + baterie            | Pentru alimentare autonomă            | Opțional  |

---

## 🛠️ Etapele proiectului

### 1. Prototip pe Breadboard

* Realizarea conexiunilor de bază între ESP32 și senzori/actuatori
* Scrierea codului în C++ (Arduino)
* Testarea funcționalităților (manual/automat)

### 2. Dashboard IoT

* Integrarea unui dashboard (Blynk, Adafruit IO, Thingspeak etc.)
* Vizualizare date în timp real
* Comenzi remote: udare, ventilare, etc.

### 3. Zonare & Automatizare

* Implementare zonare udare: electrovalve per zonă
* Control automat prin citiri de la senzori
* Pulverizare apă prin distribuitor central și pompă unică

### 4. Încălzire & Adaptare Sezonieră

* Adăugare radiator PTC pentru iarnă
* Logică: dacă temperatura < 10°C => pornește radiator
* Control prin MOSFET sau releu

### 5. API Python + Machine Learning

* Server local cu Flask/FastAPI care:

  * Primește date de la ESP32
  * Face predicții (ex: udare necesară?)
  * Trimite răspuns ESP32-ului
* Model ML antrenat (scikit-learn/TensorFlow) și salvat `.pkl` / `.h5`

### 6. PCB Design Final

* Proiectare schemă în KiCAD / EasyEDA
* Layout PCB + export gerber
* Testare pe placă reală
* Carcasă 3D printată (opțional)

### 7. Bonus: Alimentare Solară

* Panou solar + baterie reîncărcabilă
* Management consum și protecție
* Statistici de energie în dashboard

---

## ❓ Întrebări de explorat pe parcurs

* Cât de granulară trebuie să fie zonarea?
* Se poate învăța modelul ML din obiceiuri și condiții locale?
* E mai eficient un sistem centralizat sau distribuit pe plante?
* Pot fi înlocuite unele componente cu versiuni DIY?
* Cum fac sistemul ușor de replicat și de întreținut?

---

## 📁 Structură recomandată GitHub

```
/solar-automatizat-inteligent
├── hardware/
│   ├── breadboard_design.fzz
│   └── pcb_schematic.kicad_pcb
├── firmware/
│   └── main.ino
├── python-ml/
│   ├── model.pkl
│   ├── model_trainer.py
│   └── api_server.py
├── dashboard/
│   └── config_dashboard.json
├── docs/
│   └── README.md
└── README.md
```

---

> 🧠 Proiect realizat din pasiune, pentru învățare și extindere viitoare spre smart home. Va fi publicat pe GitHub și documentat pas cu pas.

---

✅ Spor la automatizat! Dacă ai ajuns până aici, ești pe drumul cel bun 🛠️🌞🌿
