# Recapitulare discuție proiect Solar Automatizat

## Context
Acest fișier sumarizează ideile și deciziile discutate pentru proiectul solar automatizat, ca notițe constante pe parcursul dezvoltării.

---

## 1. Evoluția proiectului

- Pornim cu un prototip funcțional bazat pe ESP32, senzori de temperatură și umiditate, pompe controlate prin releu.
- Ulterior, vom implementa un server local sau cloud cu API care să colecteze datele și să ruleze un model ML pentru predicții și optimizări.
- În ultima fază, vom integra alimentarea cu panouri solare și baterii, asigurând un sistem autonom și eco-friendly.

---

## 2. Managementul energiei

- Inițial, alimentarea se face din rețea pentru stabilitate în timpul dezvoltării.
- ESP32 și senzori pot fi conectați la rețea, pompele alimentate prin baterie încărcată de panou solar (sistem hibrid).
- Pentru eficiență energetică, ESP32 va folosi deep sleep între măsurători.
- Se recomandă folosirea controller-ului solar pentru gestionarea încărcării bateriei și protecții hardware adecvate.

---

## 3. Deep Sleep pe ESP32

- ESP32 va intra în modul deep sleep pentru a reduce consumul energetic, trezindu-se periodic pentru a citi senzori și a transmite date.
- Trezirea se face pe timer sau pe evenimente externe (ex: semnal de la senzor).
- După trezire, programul reia execuția din `setup()`, deci logica trebuie să țină cont de restart.

---

## 4. Colectarea datelor

- Datele vor fi colectate la intervale regulate, la fiecare 10 minute, pentru a obține o monitorizare relevantă și pentru a evita falsurile sau datele redundante.

---

## 5. API & Machine Learning

- Colectarea datelor de la senzori va fi făcută periodic, pentru a asigura un set de date suficient de mare și diversificat.
- Modelul ML va fi dezvoltat în Python, pe server, cu ajutorul unui API care primește date, face predicții și trimite comenzi.
- Inițial, prototipul poate stoca date local, urmând ca în faza avansată să se mute pe server.

---

## 6. Întrebări și decizii viitoare

- Optimizarea numărului și poziției senzorilor (un senzor per plantă sau mai puțini pentru zone).
- Gestionarea erorilor hardware (ex: fir rupt, senzor defect). (un senzor are mereu curentul peste 0A, de exemplu 4 mA);
- Alegerea finală între releu sau alte soluții de drivere pentru pompe.
- Dimensionarea corectă a bateriei și panourilor solare.

---
