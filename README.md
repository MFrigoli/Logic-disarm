# Logic-disarm

# 💣 Bomba Logica – Gioco Elettronico a Enigmi (Arduino)

Progetto didattico realizzato con **Arduino UNO**, ispirato ai giochi di disinnesco a tempo.  
Il giocatore deve risolvere una serie di enigmi logici prima che il countdown arrivi a zero.

Il sistema combina **logica di gioco, gestione del tempo, interfaccia utente e hardware elettronico**, ed è pensato come progetto universitario completo, corredato di manuale utente e manuale tecnico.

---

## 🎯 Obiettivi del progetto

- Progettare un sistema **interattivo embedded**
- Gestire **timer ad alta precisione (centesimi di secondo)**
- Integrare più dispositivi hardware (LCD, 7-segmenti, IR, buzzer, LED)
- Realizzare una **logica di gioco a stati**
- Produrre documentazione tecnica e utente professionale

---

## 🧩 Descrizione del gioco

Il gioco è composto da **più fasi sequenziali**:

1. **Enigma 1**  
   Inserimento di una risposta numerica corretta

2. **Enigma 2**  
   Secondo puzzle logico, anch’esso con risposta numerica

3. **Fase MISTERY**  
   Evento casuale a probabilità 50/50:
   - Bonus tempo (+10 secondi)
   - Penalità tempo (−5 secondi)

4. **Fase finale – Taglio del cavo**  
   Il cavo corretto dipende dalla **somma dei risultati dei primi due enigmi**:
   - Pari → Rosso  
   - Dispari → Blu  
   - Uguale a 0 o 5 → Verde

Se il tempo scade prima del disinnesco → 💥 **BOOM**

---

## ⏱️ Gestione del tempo

- Countdown in formato **SS.CC** (secondi e centesimi)
- Visualizzazione su **display 7-segmenti a 4 cifre**
- Effetto **turbo countdown** negli ultimi secondi
- Timer modificabile via codice

---

## 🧠 Architettura del software

Il codice è strutturato come **macchina a stati**, con modalità principali:

- `IDLE` – bomba non armata
- `PUZZLE_1`
- `PUZZLE_2`
- `MISTERY`
- `WIRE_CUT`
- `DISARMED`
- `EXPLODED`

Ogni stato gestisce:
- input
- output su LCD
- aggiornamento del timer
- transizioni verso lo stato successivo

---

## 🔧 Hardware utilizzato

- Arduino UNO R3
- Display LCD 16x2
- Display 7-segmenti 4 digit (common cathode)
- Shift register **74HC595**
- Ricevitore IR + telecomando
- Buzzer attivo
- LED di stato / errore
- Pulsanti fisici
- Resistenze, breadboard, cablaggi

---

## 📁 Struttura del repository

📦 bomba-logica
┣ 📜 README.md
┣ 📜 BombaLogica.ino
┣ 📂 docs
┃ ┣ 📄 Manuale_Utente.pdf
┃ ┣ 📄 Manuale_Tecnico.pdf
┃ ┣ 📄 Flowchart.png
┃ ┗ 📄 Schema_Elettrico.png
┗ 📂 assets


---

## 📘 Documentazione

Il progetto include:

- 📙 **Manuale Utente**
  - istruzioni di gioco
  - interfaccia
  - messaggi a schermo
  - troubleshooting base

- 📕 **Manuale Tecnico**
  - schema elettrico
  - descrizione hardware
  - struttura del codice
  - flow chart completo
  - manutenzione e sicurezza

---

## ⚠️ Avvertenze

Questo progetto è **puramente didattico e ludico**.  
Non ha alcuna relazione con dispositivi reali o pericolosi.

---

## 👤 Autore

Progetto sviluppato da **Matteo Frigoli**  
per finalità didattiche / universitarie.

---

## 📜 Licenza

Distribuito a scopo educativo.  
Uso libero per studio e sperimentazione.
