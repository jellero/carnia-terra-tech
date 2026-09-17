# BOM-010 — Accumulo termico, primario PDC e scambiatore

**Aggiornato:** 17 settembre 2026  
**Ambito:** 3×22 kW PDC working, predisposizione quarta unità, accumulo 30 m³ con espansione 40–50 m³.  
**Stato:** `SCENARI E COMPONENTI CANDIDATI / TAGLIE FINALI DA CALCOLO E RFQ`.

## 1. Distinta principale

| Codice | Voce | Quantità working | Stato | Benchmark / nota |
|---|---|---:|---|---|
| TH-STO-001 | Accumulo termico iniziale | 30 m³ | DA RFQ | confrontare 6×5 m³ / 3×10 m³ / 1×30 m³ |
| TH-STO-002 | Predisposizione espansione | +10–20 m³ | REQUISITO | arrivare 40–50 m³ senza rifare impianto |
| TH-STO-003 | Puffer 5 m³ professionale | 6 working scenario T1 | CANDIDATO | Cordivari PUFFER COMPACT 5000, 5.042 l, 3 bar, 99 °C, prezzo da preventivo |
| TH-STO-004 | Puffer/custom 10 m³ | 3 working scenario T2 | DA RFQ | specifica pressione/temperatura/isolamento |
| TH-STO-005 | Tank custom 30 m³ | 1 scenario T3 | DA RFQ | single point of failure, accesso/installazione critici |
| TH-STO-006 | Isolamento accumulo | per volume/scenario | DA RFQ | richiedere perdita termica dichiarata |
| TH-STO-007 | Valvole isolamento tank | ogni modulo/attacco | REQUISITO | manutenzione modulare |
| TH-STO-008 | Scarichi e sfiati tank | ogni modulo/collettore | REQUISITO | accessibili |
| TH-STO-009 | Sonde stratificazione | da 4–6 livelli + top/bottom moduli | REQUISITO | architettura finale da definire |
| TH-STO-010 | Misura energia termica accumulo | 1+ punti | REQUISITO | portata + ΔT |
| TH-HX-001 | Scambiatore a piastre | 1–2 | CANDIDATI REALI | 100 kW saldobrasato benchmark €1.252; inox a piastre €3.013 listino 2025/2 |
| TH-HX-002 | Secondo HX / ridondanza | 0–1 | DA TCO | elimina SPOF se dimensionato per capacità richiesta |
| TH-HX-003 | Valvole isolamento HX | per lato/unità | REQUISITO | permettere lavaggio/sostituzione |
| TH-HX-004 | Bypass / raccordi lavaggio | da P&ID | REQUISITO | manutenzione chimica/meccanica |
| TH-HX-005 | Sensori T ingresso/uscita HX | 4 per HX o schema equivalente | REQUISITO | approach e fouling |
| TH-PRI-001 | Collettore primario PDC | 1 set | DA CALCOLO | 3 unità + predisposizione quarta |
| TH-PRI-002 | Valvole isolamento PDC | 2/unità + accessori | REQUISITO | rimozione singola unità |
| TH-PRI-003 | Non ritorno PDC | per ramo se richiesto | DA P&ID | evitare ricircoli parassiti |
| TH-PRI-004 | Filtro/defangatore | centrale o per ramo | DA PROGETTARE | perdita di carico/manutenzione |
| TH-PRI-005 | Sfiato/separatore aria | da P&ID | REQUISITO | punto alto/centrale |
| TH-PRI-006 | Pompa primaria esterna | 0–2 | CONDIZIONALE | pompa SHIMGE integrata confermata; serve curva Q/H e prevalenza residua reale |
| TH-PRI-007 | Classe pompa benchmark | — | BENCHMARK | MAGNA3 32-80 da ~€1.149, ~10 m³/h, 8 m; non selezionata |
| TH-PRI-008 | Tubazioni primario esterno | m/DN da layout | DA CALCOLO | coibentazione e protezione gelo |
| TH-PRI-009 | Coibentazione primario | m da layout | REQUISITO | esterno/meteo/UV |
| TH-GLY-001 | Glicole propilenico inibito | kg da volume/concentrazione | CANDIDATI REALI | 25 kg ~€122–185 benchmark correnti |
| TH-GLY-002 | Refrattometro/controllo concentrazione | 1 | REQUISITO | manutenzione fluido |
| TH-GLY-003 | Serbatoio riempimento/miscela | da procedura | CANDIDATO | gestione ordinata del primario |
| TH-EXP-001 | Vaso espansione accumulo/secondario | da calcolo | DA CALCOLO | 500 l non automaticamente sufficiente |
| TH-EXP-002 | Vaso espansione primario glicolato | da calcolo | DA CALCOLO | separato se HX separa i circuiti |
| TH-EXP-003 | Caleffi 556500 500 l | benchmark | CANDIDATO DI CLASSE | ~€1.165,20, 6 bar, max 50% glicole, EN 13831 |
| TH-SAF-001 | Valvole sicurezza | da P&ID | OBBLIGATORIO | taratura coerente Pmax componenti |
| TH-SAF-002 | Manometri/trasduttori pressione | da P&ID | REQUISITO | locale + PLC |
| TH-SAF-003 | Protezione bassa pressione/flussostato | da architettura | REQUISITO | protezione PDC/pompe |
| TH-FIL-001 | Trattamento acqua tecnica | 1 procedura/package | DA DEFINIRE | qualità acqua e prescrizioni produttori |
| TH-FIL-002 | Riempimento/lavaggio iniziale | 1 lotto | OBBLIGATORIO | flushing prima commissioning |
| TH-ELC-001 | Quadro/cablaggio primario | 1 package | DA RFQ | pompe, valvole, sensori, sicurezza |
| TH-CTL-001 | PLC/EMS logica accumulo | 1 package | REQUISITO | locale, no cloud dependency |
| TH-COM-001 | Prova pressione/tenuta | 1 lotto | OBBLIGATORIO | verbale commissioning |
| TH-COM-002 | Bilanciamento primario/HX | 1 lotto | OBBLIGATORIO | portate, ΔT, perdite |
| TH-COM-003 | Mappa stratificazione | 1 test | OBBLIGATORIO | carica/scarica a diversi regimi |
| TH-COM-004 | Test failover | 1 lotto | OBBLIGATORIO | PDC/HX/pompa/sensori |
| TH-DOC-001 | P&ID/as-built/manuali | 1 lotto | OBBLIGATORIO | base manutenzione |

## 2. Capacità energetica

`E[kWh] ≈ 1,163 × V[m³] × ΔT[K]`.

- 30 m³: ~349 kWh/10 K; ~698 kWh/20 K; ~1.047 kWh/30 K;
- 40 m³: ~465 / 930 / 1.395 kWh;
- 50 m³: ~581 / 1.163 / 1.744 kWh.

Non usare questi valori come energia interamente estraibile: dipende da Tmin utile, stratificazione, portate e temperature richieste dai comparti.

## 3. Tank professionali vs tank acqua

### Cordivari PUFFER COMPACT 5000

Scheda tecnica pubblica:

- volume 5.042 l;
- Pmax 3 bar;
- Tmax 99 °C;
- attacchi principali 2";
- prodotto per acqua di riscaldamento.

Prezzo: `DA PREVENTIVO`.

### Serbatoi PE acqua — solo benchmark economico

ALTA AcquaTec promozione settembre 2026, IVA esclusa:

- 10.000 l verticale: €1.840;
- 15.000 l: €2.940;
- 20.000 l: €4.740.

La serie da esterno dichiara resistenza termica circa -40…+60 °C. Non viene classificata come puffer pressurizzato/isolato. **Non è alternativa equivalente**.

## 4. Scambiatore

Benchmark Sunerg 2025/2:

- 60 kW saldobrasato €932;
- 100 kW saldobrasato €1.252;
- 100 kW a piastre inox €3.013.

RFQ obbligatorio su tre scenari:

- HX1 1×100 kW;
- HX2 2×100 kW, uno isolabile mantenendo piena potenza nominale 88 kW se verificato alle temperature reali;
- HX3 2×50–60 kW, ridondanza parziale.

La potenza nominale del catalogo non basta: dichiarare temperature, portate, glicole, perdite di carico e approach.

## 5. Primario e pompe

Working PDC Kensol KHP-R290-22-3:

- 22 kW max A7/W35;
- 18,8 kW max A2/W35;
- 3 unità = 66 kW A7/W35 ma 56,4 kW A2/W35;
- predisposizione quarta = 88 kW A7/W35 ma 75,2 kW A2/W35;
- prezzo osservato €3.616,74 + IVA/unità.

La pompa integrata è ora confermata dal datasheet corrente:

- marca SHIMGE;
- portata nominale 2,9 m³/h;
- prevalenza pompa alla portata nominale 100 kPa;
- perdita interna massima 65 kPa.

Il manuale KHP-R290 codice 6/26 riporta invece 45 kPa di perdita interna e 6,9 m di prevalenza. La revisione effettivamente acquistata deve essere chiarita da OEM/fornitore.

La differenza 100−65 = 35 kPa non viene assunta come prevalenza residua garantita senza curva Q/H e definizione OEM del metodo di misura.

Portata nominale aggregata:

- 3 unità: 8,7 m³/h;
- 4 unità: 11,6 m³/h.

Pompe esterne solo se il calcolo completo di HX, glicole, filtri, valvole e tubazioni dimostra che la prevalenza integrata non basta.

MAGNA3 32-80 (~10 m³/h, 8 m, da ~€1.149) resta solo benchmark di classe.

## 6. Glicole

Benchmark:

- Polsinelli propilenico 25 kg: €122,13 + trasporto;
- Antigel atossico 25 kg: €185,11 IVA inclusa.

La percentuale deve derivare dalla Tmin esterna di progetto e dallo scenario blackout. Il costo viene calcolato sul **solo volume primario protetto**, non sull'accumulo completo.

## 7. Espansione

Caleffi 556500:

- 500 l;
- Pmax 6 bar;
- fluido acqua/soluzioni glicolate max 50%;
- -10…120 °C lato sistema;
- EN 13831;
- prezzo benchmark €1.165,20.

Il vaso reale va dimensionato. Con 30–50 m³, temperatura e pressioni hanno un impatto tale che possono servire più vasi o una diversa architettura; nessuna quantità viene congelata da questo benchmark.

## 8. Sensori e controllo

Minimo funzionale:

- T esterna;
- T PDC mandata/ritorno;
- T lato primario HX in/out;
- T lato accumulo HX in/out;
- stratificazione verticale;
- pressione primario;
- pressione secondario/accumulo;
- portata primaria e/o energia termica;
- stato pompe;
- allarmi antigelo/pressione/portata.

EMS/PLC deve conoscere i kWh termici disponibili nell'accumulo per decidere carica, priorità comparti e modalità sopravvivenza.

## 9. Manutenzione / ricambi

Prevedere:

- sonde temperatura di scorta;
- guarnizioni/raccordi HX;
- kit/fluido pulizia HX secondo costruttore;
- valvole/attuatori critici;
- materiale per reintegro glicole;
- controllo annuale concentrazione/pH fluido secondo specifica;
- controllo precarica vasi;
- verifica valvole sicurezza;
- registro pressione/ΔT/portata e dispersioni.

## 10. Open points

1. carico termico reale;
2. temperatura minima sito;
3. mandata/ritorno PDC;
4. prestazioni Kensol a -7/-10/-15 °C e defrost;
5. volume accumulo ottimo;
6. tank architecture T1/T2/T3;
7. capacità/numero HX;
8. curva pompa integrata e prevalenza residua confermata;
9. DN e perdite primario;
10. volume/concentrazione glicole;
11. espansione e sicurezza;
12. isolamento/dispersioni;
13. layout Tech Barn e accessi sostituzione;
14. RFQ professionali.

Vedi anche BOM-011 `TERMICO_PDC_MODULARI.md` e `05_TERMICO_E_CLIMA/HEAT_PUMP_CASCADE.md`.
