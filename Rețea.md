# 📡 Rețea și Conectivitate — Proiect Solar Automatizat

## ✅ Scop

Asigurarea unei conexiuni stabile între **ESP32** și **serverul local** (inițial un PC vechi, ulterior Raspberry Pi), astfel încât să se poată colecta date, trimite cereri API și controla sistemul automatizat.

---

## 🔁 Variante de conectare

### 🔹 1. Conectare prin Wi-Fi (ESP32 + Server Wireless)

- ESP32 se conectează la rețeaua Wi-Fi locală.
- Serverul are o **placă de rețea wireless** (internă sau stick USB).
- Ambele device-uri sunt în aceeași rețea (`192.168.x.x`) → pot comunica direct.

✅ **Avantaje**:
- Fără cabluri.
- Flexibilitate în plasarea serverului.
- Configurare simplă.

---

### 🔸 2. Conectare prin cablu LAN (Server pe fir + ESP32 pe Wi-Fi)

- ESP32 se conectează la router prin Wi-Fi.
- Serverul este conectat prin cablu Ethernet (LAN) la același router.

✅ **Avantaje**:
- Conexiune mai stabilă pentru server.
- Viteză mai mare (deși nu e esențială aici).
- Nu ai nevoie de placă Wi-Fi.

⚠️ **IMPORTANT**: Routerul NU trebuie să aibă conexiune la internet. Doar să ofere o rețea locală.

---

## 🔌 Dispozitive utile pentru conectivitate

| Tip adaptor         | Utilitate                                 | Când să-l folosești?                  |
|---------------------|--------------------------------------------|----------------------------------------|
| Stick Wi-Fi USB     | Adaugă Wi-Fi la serverul vechi             | Când nu ai placă wireless internă      |
| Adaptor LAN USB     | Adaugă port Ethernet la un PC fără LAN     | Dacă vrei conexiune stabilă pe fir     |
| Router fără internet| Creează rețea locală pentru testare        | Când vrei control complet fără internet|

---

## 🔐 Rețea privată vs. rețea publică

- Rețeaua în care rulează proiectul este **privată/locală**.
- ESP32 și serverul comunică **fără să aibă nevoie de internet**.
- Este **mai sigură**, mai ușor de controlat, perfectă pentru dezvoltare.

---

## 🧪 Accesarea serverului din terminal

- Serverul nu are nevoie de interfață grafică (doar terminal).
- Se poate accesa prin `ssh` din alt PC/laptop din aceeași rețea:
  ```bash
  ssh user@192.168.x.x

## 🔚 Concluzie

✅ Atât conexiunea Wi-Fi, cât și cea pe cablu LAN sunt valide.  
🔒 Rețeaua nu trebuie să fie publică sau conectată la internet.  
🔁 Este esențial ca ESP32 și serverul să fie în același LAN, fie el wireless sau cu fir.