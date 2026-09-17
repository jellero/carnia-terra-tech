# Serbatoi fertilizzanti e contenimento — architettura e criteri

**Aggiornato:** 17 settembre 2026  
**Stato:** `ARCHITETTURA DEFINITA / VOLUMI E MATERIALI FINALI DA RICETTE, SDS E RFQ`.

## 1. Obiettivo

Stoccare e alimentare i concentrati **A**, **B** e **acido** in modo sicuro, misurabile, pulibile e manutenibile, senza introdurre contatti accidentali tra chimici incompatibili.

Baseline:

`serbatoio dedicato -> livello continuo + low-low indipendente -> aspirazione dedicata -> pompa dosatrice BOM-016 -> iniezione`.

Ogni contenitore deve essere fisicamente identificato, contenuto secondariamente e accessibile per riempimento, campionamento, pulizia e manutenzione.

## 2. Canali e segregazione

Canali iniziali:

- **A** — concentrato fertilizzante A;
- **B** — concentrato fertilizzante B;
- **ACID** — acido/correttore pH;
- predisposizione futura per un quarto chimico/additivo.

Regole:

- A, B e acido hanno serbatoi, tubazioni e punti di aspirazione separati;
- raccordi/etichette devono ridurre il rischio di scambio umano;
- non condividere un unico bacino di contenimento fra sostanze incompatibili senza una verifica documentata;
- per l'acido la baseline è **contenimento dedicato**;
- nessun drenaggio del bacino va direttamente in fognatura, suolo o rete acque meteoriche.

## 3. Dimensionamento dei volumi

Il volume non si sceglie per abitudine.

Per ogni chimico:

`V_operativo = consumo_giornaliero_massimo × giorni_autonomia`

`V_nominale >= V_operativo / frazione_riempimento_utilizzabile`

La frazione utilizzabile deve considerare:

- volume libero anti-trabocco;
- fondo non pescabile;
- volume minimo per agitazione/aspirazione;
- dilatazione;
- procedura di riempimento;
- eventuale volume di lotto minimo del fornitore.

### Scenario di confronto, non selezione

Per costruire RFQ e ingombri preliminari si confronta:

- A: **500 L**;
- B: **500 L**;
- acido: **200 L**.

È solo uno scenario di classe dimensionale. I volumi d'ordine dipenderanno dalle ricette C1–C6, dalla concentrazione degli stock e dall'autonomia desiderata.

## 4. Materiali e compatibilità

Baseline economica: **PE/HDPE/LLDPE** per serbatoi atmosferici, ma solo con compatibilità confermata sul prodotto reale.

Prima dell'ordine il fornitore deve confermare per iscritto:

- prodotto chimico esatto;
- concentrazione;
- densità;
- temperatura minima/massima;
- compatibilità del corpo serbatoio;
- compatibilità di guarnizioni, valvole, raccordi, tubi, sonde e agitatori;
- eventuali limiti UV/esterno;
- durata/garanzia nelle condizioni dichiarate.

Non basta la dicitura generica `serbatoio per chimici`.

## 5. Serbatoi candidati

### PE chimici 500 L — benchmark

Pack Services PFF-CH0500:

- 500 L;
- PE stabilizzato UV;
- monolitico;
- circa Ø1000 × 705 mm;
- campo dichiarato -30…+50 °C;
- coperchio filettato con sfiato;
- prezzo pubblico: **€188,73 + IVA**;
- stato: `PREZZO TROVATO / COMPATIBILITÀ SPECIFICA DA CONFERMARE`.

### PE chimici 200 L — benchmark

Pack Services PFF-CH0200:

- 200 L;
- PE stabilizzato UV;
- monolitico;
- circa Ø770 × 565 mm;
- prezzo pubblico: **€131,94 + IVA**;
- stato: `PREZZO TROVATO / CANDIDATO DI CLASSE PER ACIDO SOLO DOPO COMPATIBILITÀ`.

### Elbi CHL-500 — alternativa

- 500 L PE;
- prezzo retail osservato **€219 IVA inclusa**;
- il venditore rimanda esplicitamente alla tabella di resistenza chimica ELBI;
- stato: `PREZZO TROVATO / ALTERNATIVA`.

## 6. Contenimento secondario

Il contenimento deve:

- resistere al chimico stoccato;
- trattenere una perdita significativa senza tracimare;
- rimanere ispezionabile;
- avere drenaggio **controllato**, normalmente chiuso;
- non essere riempito da pioggia o lavaggi;
- consentire recupero/neutralizzazione secondo SDS e procedura.

### Target ingegneristico iniziale

Per singolo serbatoio: capacità del contenimento **almeno pari al volume nominale del serbatoio** come baseline prudente di progetto.

Per più serbatoi nello stesso bacino: dimensionamento finale `DA VERIFICARE` con incompatibilità, classificazione chimica, norme applicabili, prescrizioni locali e assicuratore.

**Nota normativa:** in Italia esistono criteri 30%/1/3 del totale e comunque almeno il serbatoio maggiore (in alcuni casi +10%) in norme dedicate allo stoccaggio di rifiuti liquidi pericolosi. Questi criteri sono utili come benchmark conservativo ma **non vengono assunti automaticamente come norma applicabile ai fertilizzanti**.

### Benchmark vasche

DENIOS classic-line PE 600 L:

- capacità raccolta 600 L;
- dichiarata idonea per acidi, soluzioni alcaline e chimici non infiammabili compatibili;
- **€560 + IVA**;
- stato: `PREZZO TROVATO`.

Gaesco vasca PE 500 L con griglia:

- 500 L;
- **€641,72 IVA inclusa**;
- stato: `PREZZO TROVATO / ALTERNATIVA`.

## 7. Livello e anti-trabocco

Per A/B/acido prevedere almeno:

1. misura continua di livello;
2. allarme low;
3. **low-low indipendente** che blocca il relativo dosaggio;
4. high/high-high per evitare sovrariempimento durante travaso;
5. indicazione locale visibile o metodo manuale di verifica.

Preferenza per sensore non a contatto quando evita problemi di compatibilità.

Candidati/benchmark:

- Novus TL400 laser 4–20 mA: da **€130** pubblicati, IVA da confermare;
- WIKA ILT-C01 radar 4–20 mA: **€390,09 + IVA** benchmark Automation24;
- Elesa HFLT-E/HFL-E livello limite in tecnopolimero: da **€39,18 / €60,41 + IVA**, materiali speciali disponibili su richiesta.

La tecnologia finale dipende da schiuma, vapori, geometria e compatibilità.

## 8. Agitazione e ricircolo

A/B possono richiedere omogeneizzazione; l'acido **non riceve automaticamente un agitatore**.

Confrontare per A/B:

- agitatore lento top-entry;
- ricircolo con piccola pompa dedicata;
- preparazione batch con agitazione temporizzata;
- nessuna agitazione se la soluzione è stabile e validata.

Requisiti:

- evitare vortice/aria eccessiva;
- materiali compatibili;
- albero/elica dimensionati per densità e viscosità;
- coperchio e supporto serbatoio verificati per carico dinamico;
- interlock: agitatore non avviabile a livello troppo basso.

Benchmark professionale: agitatore AISI 316 da 0,37 kW per serbatoi fino a 500 L, **€1.835 + IVA**. È un benchmark alto e non implica che Carnia TerraTech necessiti di questa classe.

## 9. Riempimento e travaso

Evitare come procedura normale il travaso manuale con secchi/imbuti.

Prevedere:

- punto di riempimento dedicato e identificato;
- attacco incompatibile/chiave diversa fra A/B/acido dove possibile;
- pompa di travaso o sistema chiuso se i contenitori di fornitura lo richiedono;
- valvola di intercettazione accessibile;
- tubo compatibile e facilmente sostituibile;
- anti-sifone/non ritorno;
- high-level stop;
- vaschetta locale antigoccia al punto di disconnessione;
- procedura di risciacquo solo dove chimicamente ammessa.

## 10. Sfiati

Ogni serbatoio atmosferico necessita sfiato adeguato a riempimento e svuotamento.

Per l'acido verificare da SDS:

- volatilità;
- necessità di sfiato convogliato;
- eventuale scrubber/neutralizzazione;
- distanza da operatori, elettronica e metalli sensibili.

Non installare un semplice sfiato libero interno al locale senza verifica.

## 11. Pavimento, drenaggi e locale chimici

Requisiti di layout:

- superficie continua, impermeabile e resistente ai chimici reali;
- nessun pozzetto aperto nel bacino;
- pendenza controllata verso punto recuperabile solo se prevista;
- lavaggio senza trascinare chimici nel drenaggio ordinario;
- accesso transpallet/carrello per contenitori di fornitura se previsto;
- spazio per estrarre sonde, pompe e agitatori;
- illuminazione e ventilazione;
- segregazione da alimenti, imballaggi, server/elettrico e vie visitatori.

## 12. Ergonomia e sicurezza operatore

Da coordinare con punto 12 Sicurezza:

- SDS immediatamente disponibile;
- etichettatura permanente e CLP dove applicabile;
- DPI definiti da valutazione rischio;
- lavaocchi/doccia di emergenza in posizione appropriata se richiesta dal rischio;
- spill kit compatibile;
- attrezzi dedicati;
- procedura riempimento/travaso con doppio controllo per acido;
- nessuna manutenzione su pompa/tubo senza isolamento e depressurizzazione.

## 13. Failure modes

- serbatoio fessurato;
- raccordo passaparete perde;
- bacino pieno/non disponibile;
- livello continuo guasto;
- low-low guasto;
- high-high non interviene;
- riempimento nel serbatoio sbagliato;
- A/B/acido contaminati fra loro;
- agitatore fermo;
- precipitazione cristalli;
- sfiato ostruito;
- pompa di travaso guasta;
- valvola fondo perde;
- acido corrode materiale non compatibile;
- allagamento del locale.

Fallback:

- stop automatico del canale;
- isolamento manuale;
- uso del secondo stock solo se esiste procedura approvata;
- recupero sversamento dal contenimento;
- preparazione manuale temporanea solo con procedura sicura e misura indipendente.

## 14. Manutenzione

Registrare:

- volume caricato/consumato;
- pulizie;
- ispezione crepe/deformazioni;
- stato passaparete/guarnizioni;
- prova low-low/high-high;
- calibrazione livello;
- ore agitatore;
- tenuta valvole;
- stato vasca di contenimento;
- sversamenti e cause;
- sostituzioni tubi/guarnizioni.

## 15. Gate

BOM-017 diventa ordinabile con:

1. ricette C1–C6;
2. consumo massimo A/B/acido;
3. autonomia target;
4. concentrazioni stock;
5. acido esatto e concentrazione;
6. SDS complete;
7. densità/temperatura;
8. compatibilità serbatoi, valvole, guarnizioni, sonde e agitatori;
9. layout locale chimici;
10. dimensionamento contenimento;
11. strategia riempimento/travaso;
12. ventilazione/sfiati;
13. agitazione/ricircolo A/B;
14. RFQ comparabili;
15. commissioning e prova sversamento/interlock.
