# Dashboard Fatturato medi Italia — PWA

## Link app
**https://nicolosantoro190595-design.github.io/Fatturato**

Installata come app su iPhone: icona sulla schermata home, funziona offline.

---

## Cosa contiene la dashboard

- **KPI mensili e YTD** — fatturato, crescita %, delta vs 2025 e budget
- **Grafico andamento mensile** — 2026 vs 2025 con filtri (entrambi / solo 2026 / delta €)
- **Tabella agenti per mese** — selezionabile indipendentemente
- **Ranking agenti** — delta % YTD e delta € YTD affiancati
- **Direzione** — KPI mese + YTD e grafico annuale
- **Spese Trasporto** — KPI mese + YTD e grafico annuale
- **Dettaglio agente × anno** — grafico mensile 2026 vs 2025 e 3 mini KPI

---

## Come aggiornare ogni mese (procedura completa)

### Passo 1 — Manda il file Excel a Claude
Apri questa chat (o un nuovo Progetto Claude "Dashboard medi Italia") e manda il file `FATTURATO_MESE_2026.xlsx`. Claude genera un nuovo `index.html` con tutti i dati aggiornati hardcoded.

### Passo 2 — Carica su GitHub
1. Vai su `github.com/nicolosantoro190595-design/Fatturato`
2. Clicca **Add file → Upload files**
3. Trascina il nuovo `index.html`
4. Clicca **Commit changes**
5. Aspetta 1-2 minuti

### Passo 3 — Aggiorna l'app sul telefono
Chiudi e riapri l'icona dalla schermata home — si aggiorna automaticamente.

---

## Alternativa rapida (senza GitHub)

1. Apri la dashboard nel browser
2. Trascina il file Excel nella zona tratteggiata in cima
3. I dati si aggiornano subito in quella sessione
4. ⚠️ Non viene salvato alla chiusura — serve il Passo 2 per renderlo permanente

---

## File nel repository

| File | Descrizione |
|------|-------------|
| `index.html` | Dashboard completa (tutto in un file — dati + grafici + logica) |
| `manifest.json` | Configurazione PWA per installazione su iPhone |
| `sw.js` | Service worker per funzionamento offline |
| `icon.png` | Icona app sulla schermata home |
| `README.md` | Questo file |

---

## Dati hardcoded (aggiornati a Maggio 2026)

- Totali mensili: **gen-mag 2026** reali + f25 tutti i 12 mesi
- Agenti: **22 agenti** con f26/f25/budget per gen-mag, f25 per giu-dic
- Direzione e Trasporto: completi per tutti i 12 mesi
- Ranking YTD: basato su foglio GENERALE dell'Excel

---

## Note tecniche

- Chart.js e SheetJS sono **inline nel file** — funziona senza internet
- Il parser Excel legge `TOTALE VENDITE` per i totali mensili
- I mesi futuri (f26=0 o null) vengono ignorati automaticamente
- Il mese attivo si imposta sull'ultimo con dati reali
- 22 agenti incluso FIORA-PIGHETTI (PV-LO) che è una zona separata

---

*Ultima versione: Maggio 2026*
