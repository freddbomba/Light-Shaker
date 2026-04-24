# Fotoarmonio — Piano dell'installazione
## Genova Design Week 2026
### Sestiere del Molo, ex camiceria — cantina

---

## Concept dell'allestimento

L'installazione occupa la cantina dell'edificio, invisibile al
piano superiore. Il pubblico può accedere o percepire i riflessi
di luce che salgono dalla scala. L'acqua in vibrazione proietta
caustiche di luce sul soffitto della volta.

---

## Architettura tecnica

### Generazione audio (cervello)
- Orange Pi 4 con Sonic Pi
- Algoritmo Hénon+tarocchi: 7 comportamenti × 3 arcani = 21 valori
- Output: jack audio stereo → amplificatore

### Trasduzione e luce (muscolo)
- Amplificatore (recuperato dal 2016)
- Transducer accoppiato alla vasca
- LED centrale con dimmer PWM
- Il segnale audio modula sia la vibrazione dell'acqua che
  l'intensità della luce

### Ingresso audio
- Jack in esterno (ingresso opzionale per strumento/performer)
- Microfono con switch on/off

### Switch modalità
OFF (standalone)   — solo Orange Pi + algoritmo Hénon
ON  (performativa) — microfono aperto, suono ambiente entra nel loop
JACK               — strumento/performer esterno via jack in

---

## Il contenitore dell'acqua — varianti da testare

### Variante A — vasca da bowl ikea (storica)
- Vasca bassa in materiale opaco o acciaio
- Caustiche diffuse, proiettate su ampia superficie del soffitto
- Vicina all'originale del 2016

### Variante B — semisfera di vetro con mylar specchiato
- Oggetto di vetro semisferico con foglio mylar interno
- Caustiche circolari, concentrate, più intense
- Forma più scultorea, leggibile come oggetto di design
- problemi a far passare i fili (sotto il mylar, ombre)

**Da decidere dopo test:** una delle due varianti, o entrambe
in dialogo.

---

## Lista materiali

### Da recuperare
- [ ] Transducer grande + amplificatore (2016, da localizzare)

### Già disponibile
- [x] Transducer piccoli (nuovi)
- [x] Orange Pi 4

### Da procurare
- [ ] Vasca (variante A) e/o semisfera di vetro (variante B)
- [ ] Foglio mylar specchiato
- [ ] LED alta potenza + dimmer PWM
- [ ] Switch (microfono on/off)
- [ ] Jack in 6.35mm
- [ ] Cavi, supporti, alimentazione

---

## Piano di test (prima dell'installazione)

| Data limite | Test |
|-------------|------|
| 10 maggio   | Sonic Pi su Orange Pi 4: algoritmo Hénon genera audio stabile |
| 17 maggio   | Transducer + vasca: calibrazione frequenza portante (~38Hz) |
| 17 maggio   | Variante A vs B: confronto caustiche |
| 24 maggio   | Sistema completo standalone: 24h continuative senza crash |
| 24 maggio   | Switch modalità: test mic / jack in / standalone |
| 31 maggio   | Trasporto e allestimento in cantina |
| 1 giugno    | Install day — apertura 3 giugno |

---

## Requisiti del luogo (da verificare con Raffaella)

- [ ] Accesso alla cantina durante i giorni della mostra
- [ ] Alimentazione elettrica 220V in cantina
- [ ] Soffitto sufficientemente chiaro per le caustiche
- [ ] Oscurità controllabile (finestre, porte)
- [ ] Connessione WiFi in cantina (per accesso remoto a Orange Pi)

---

## Varianti aperte

- Titolo dell'installazione per la mostra: *Fotoarmonio* o
  sottotitolo specifico per GDW?
- Testo a parete / didascalia al piano superiore?
- Accesso del pubblico: libero in cantina o solo visione
  dalla scala?
