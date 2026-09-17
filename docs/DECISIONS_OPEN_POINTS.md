# Carnia TerraTech — Decisions & Open Points

**Aggiornato:** 17 settembre 2026

Questa pagina separa ciò che è già deciso, ciò che è una working hypothesis e ciò che è ancora da verificare.

---

## A. Decisioni consolidate

### Terreno

- Target acquisto: **≤ €50.000**.
- Area prioritaria: corridoio Venzone/Gemona.
- Nessun acquisto senza due diligence tecnica e urbanistica.

### Serra

- **4.200 m² produttivi**.
- **6 comparti da circa 700 m²**.
- Struttura modulare e indipendenza impiantistica per comparto.
- Montaggio seguito direttamente dal promotore con 4 lavoratori esperti retribuiti.

### Persone

- 2 soci: promotore + amico under 40.
- Socio B: **Project Manager + commerciale**.
- Socio A: tecnico, automazione, energia, progettazione interna e cantiere.
- Collaboratore/trice: supporto operativo, non socio/a.
- Ripartizione lavoro soci: **50/50**.

### Automazione

- PLC locale fail-safe.
- Nessuna dipendenza dal cloud per funzioni vitali.
- Architettura desired → command → ack → observed.
- Sensoristica distribuita e ridondanza sui punti critici.

### Robotica

- AMR incluso nel progetto.
- Mezzo multifunzione nuovo con forche e attrezzature intercambiabili da ricercare.
- Piattaforma per persone solo certificata/OEM; niente retrofit artigianali.

### Energia

- Fotovoltaico su superfici tecniche, non sopra la serra produttiva opaca.
- Working target **120 kWp iniziali**, predisposizione 150–180 kWp.
- Pannelli+fissaggi: input di procurement ~€200/kWp.
- Pompe di calore modulari.
- Batteria termica grande da decine di m³.

### Acqua

- Recupero pioggia dalle serre.
- Accumulo working target **300 m³**.
- Pompe principali ridondate 1+1.

### Vermicompost

- Reparto incluso.
- Partenza con residui aziendali sani.
- Evitare rifiuti di terzi nella fase iniziale.

### Siepi

- Siepi produttive/frangivento multifunzione.
- More su filo solo in tratti gestibili.
- Fascia tecnica libera attorno alla serra.

### Luppolo

- Eventuale prova outdoor, non dentro la serra principale.
- Solo dopo verifica domanda/prezzo con birrifici.

---

## B. Working hypotheses forti

### Società

- Società Agricola S.r.l. ordinaria.
- Quote ancora da definire in base ai requisiti del bando e alla posizione del socio giovane.

### PDC

- Kensol KHP-R290-22-3.
- 3 unità iniziali, predisposizione quarta.
- Da confermare solo dopo curva prestazioni a freddo e dati idraulici ufficiali.

### Batteria termica

- 30.000 L iniziali.
- predisposizione 40–50.000 L.
- preferenza per architettura modulare.

### Colture

- C1 pomodoro premium;
- C2 peperone;
- C3/C4 lattuga/leaf;
- C5 baby leaf/rucola/spinacio;
- C6 basilico/vivaio/jolly.

### Tech Barn

- ~450 m².
- due celle frigo separate.

### Automazione BOM

- WAGO PFC200 + Advantech ADAM come working stack.
- UniFi per videosorveglianza.
- server edge dedicato.

---

## C. Questioni tecniche ancora aperte

1. Lotto reale e topografia.
2. Geometria finale serra e orientamento.
3. Preventivo vero multicampata.
4. Carichi neve/vento.
5. Fondazioni/ancoraggi.
6. Schermo termico: tutti i comparti o solo 3 iniziali.
7. Modelli HAF e portate.
8. Fogging: tecnologia e comparti.
9. Calcolo termico reale per coltura/setpoint.
10. Materiale e diametro tubi termici.
11. Aerotermi di boost: quantità e taglia.
12. Architettura esatta accumulo 30 m³.
13. Scambiatore a piastre sì/no e dimensionamento.
14. Portate PDC reali.
15. Modelli circolatori.
16. Fonte acqua reale.
17. Analisi acqua.
18. Serbatoi 300 m³: tipo/costo/fondazioni.
19. Filtrazione.
20. Pompe irrigazione reali.
21. Dosatrici reali.
22. Recupero drenato e trattamento.
23. Moduli FV reali.
24. Inverter reali.
25. Potenza disponibile rete.
26. Eventuale cabina/trasformatore.
27. UPS/generatore.
28. Edge server definitivo.
29. Robot AMR reale.
30. Mezzo multifunzione reale.
31. Celle frigo reali.
32. Macchina raccolta baby leaf compatibile con letti.
33. Layout packaging.
34. Piano HACCP/processo post-raccolta.
35. Sistemi antincendio e sicurezza.

---

## D. Questioni economiche aperte

1. CAPEX serra.
2. CAPEX Tech Barn.
3. CAPEX acqua.
4. CAPEX termico.
5. CAPEX FV completo.
6. CAPEX automazione definitivo.
7. CAPEX macchine/robot.
8. OPEX energetico.
9. OPEX lavoro.
10. OPEX sementi/piantine/substrati/fertilizzanti.
11. Prezzi medi di vendita reali.
12. Rese conservative per coltura.
13. Scarti e non conformità.
14. Ore uomo reali.
15. Cassa minima.
16. IVA ponte.
17. Interessi/pre-ammortamento.
18. Contributi realmente applicabili.
19. Debito massimo sostenibile.
20. Break-even e DSCR.

---

## E. Questioni amministrative aperte

1. PRGC del lotto.
2. CDU.
3. PAI.
4. vincoli paesaggistici/Natura.
5. titoli edilizi.
6. SUAP.
7. scarichi/drenaggi.
8. pozzo/prelievo se necessario.
9. connessione elettrica.
10. prevenzione incendi se applicabile.
11. sicurezza macchine.
12. gestione fertilizzanti e prodotti fitosanitari.
13. eventuale vendita humus.
14. eventuale vendita diretta/spaccio.
15. eventuale ospitalità/area sociale.

---

## F. Regole da non dimenticare

- Non inventare prezzi.
- Cercare prodotti reali e linkarli.
- Distinguere prezzo trovato / preventivo / stima.
- Non trattare un bando chiuso come fonte finanziaria disponibile.
- Non considerare la manodopera propria “gratis”.
- Non inserire usato nel budget contributivo salvo ammissibilità esplicita.
- Non dimensionare una PDC da dato nominale a +7 °C se serve lavorare a -7 °C.
- Non comprare in massa sensori low-cost senza test.
- Non mettere un singolo punto di guasto sui sistemi vitali.
- Non togliere luce alla serra con FV opaco.
- Non trasformare subito il progetto in IV gamma/ospitalità: prima chiudere core agricolo.
