# Carnia TerraTech

Repository tecnico e gestionale per progettare una azienda agricola ad alta automazione in Friuli-Venezia Giulia, con area di interesse prioritaria nel corridoio Venzone/Gemona.

**Stato:** pre-fattibilità avanzata / progettazione bottom-up.  
**Aggiornato:** 18 settembre 2026.

## Visione

**Principio guida: mitigazione del rischio prima dell'ottimizzazione.**

Il progetto parte dalla riduzione delle incertezze che possono compromettere sito, cassa, sicurezza, manutenzione e continuità. Solo dopo si ottimizzano resa e automazione.

Carnia TerraTech non è soltanto una serra: deve essere un sistema agricolo capace di produrre reddito e sicurezza economica senza trasformare il lavoro in un peso continuo. Tecnologia, automazione, ergonomia, natura, ordine, estetica, manutenzione e qualità della vita sono requisiti di progetto.

Obiettivi permanenti:

- vivere e lavorare in un ambiente sereno, sicuro, ordinato e piacevole;
- automatizzare il lavoro ripetitivo, sporco, pesante o facilmente standardizzabile;
- mantenere controllo locale e modalità manuali di emergenza per i sistemi vitali;
- sfruttare in modo corretto contributi, strumenti regionali e opportunità locali senza costruire il progetto su incentivi non verificati;
- coprire nel piano finanziario sia il lancio aziendale sia il fabbisogno di vita nella fase iniziale;
- progettare ogni impianto per manutenzione, ricambi, guasti e crescita futura;
- sviluppare nel tempo fattoria didattica, aree di benessere, servizi e vendita automatizzata 24/7, senza compromettere il progetto principale agricolo.

## Numeri guida attuali

- terreno: target acquisto ≤ **€50.000**;
- superficie lotto preferita: **10.000–12.000 m² realmente utilizzabili**; 9.000–10.000 m² solo se molto efficienti;
- serra produttiva: circa **4.200 m²**;
- comparti: **6 × ~700 m²**;
- FV: **120 kWp iniziali**, predisposizione 150–180 kWp;
- accumulo termico: **30 m³ iniziali**, predisposizione 40–50 m³;
- accumulo acqua: obiettivo di lavoro **300 m³**;
- automazione locale a sicurezza intrinseca con PLC e rete dati; AMR solo dopo pilot;
- mezzo multifunzione core per materiali, humus, cantiere e manutenzione;
- capacità certificata di accesso umano in quota con piattaforma OEM/PLE ragno/noleggio;
- robot ragno R&S prioritario per ispezione/manutenzione delle parti alte, sempre con recovery umano;
- humus/vermicompost prodotto internamente quando sicuro, legale ed economicamente sensato.

## Come leggere il repository

**Inizia da [`PROJECT_INDEX.md`](PROJECT_INDEX.md).** È l'indice di controllo del progetto e indica cosa è consolidato, cosa è in analisi e quale BOM viene chiusa pezzo per pezzo.

Documenti fondativi nuovi:

- `00_VISIONE_E_PRINCIPI/PROJECT_CHARTER.md` — missione, requisiti non negoziabili e metodo;
- `10_BENESSERE_FATTORIA_E_SERVIZI/FUTURE_MODULES.md` — benessere, fattoria didattica e spaccio; rover galline rimosso dal core;
- `19_BOM_PRODOTTI_FORNITORI/SERRA_HAF_VENTILATION.md` — prima BOM tecnica analizzata nel nuovo metodo.

I file in `docs/` contengono il lavoro tecnico precedente e restano validi come base durante la riorganizzazione. Verranno migrati progressivamente senza perdere informazioni.

## Progetto R&S correlato — fuori dal progetto principale

La directory [`RND_CORRELATO_EU/`](RND_CORRELATO_EU/) contiene un progetto di ricerca e sviluppo tecnologico correlato a Carnia TerraTech.

**Non fa parte della numerazione 00–22, non modifica la configurazione base agricola e non entra automaticamente nel CAPEX/OPEX progetto principale.** Carnia TerraTech può fungere da laboratorio operativo reale e primo dimostratore, ma il progetto agricolo deve poter funzionare anche senza la riuscita o il finanziamento della R&S.

Concetto attuale: **CTT-PAA — Piattaforma di Automazione Agricola Carnia TerraTech**, con focus su orchestrazione, edge/PLC, robotica, visione artificiale, fusione sensoriale, pianificatore e sistemi autonomi replicabili.

## Piano extra agriturismo — fuori dal progetto principale

La directory [`EXTRA_AGRITURISMO_EVOLUTIVO/`](EXTRA_AGRITURISMO_EVOLUTIVO/) contiene un piano autonomo di diversificazione agrituristica finanziato e valutato separatamente.

Parte dalla soluzione minima **ristoro light a spuntini non cucinati**, con predisposizioni per esperienze, cucina e ospitalità future. Non entra nella sequenza BOM del progetto principale e non è necessario per l'avvio dell'azienda.

## Terreno: prima misurare, poi progettare

Quando viene individuato un lotto serio:
- griglia di campionamento su tutta la superficie utile;
- prove di infiltrazione/drenaggio;
- rilievo quote e ristagni;
- anomalie e riporti;
- geotecnica professionale per le opere;
- masterplan di prova prima del rogito.

Riferimento: [`01_MASTERPLAN_E_TERRENO/PIANO_CAMPIONAMENTO_TERRENO_E_DRENAGGIO.md`](01_MASTERPLAN_E_TERRENO/PIANO_CAMPIONAMENTO_TERRENO_E_DRENAGGIO.md).

## Business plan e struttura societaria

La directory [`16_SOCIETA_FINANZA_E_CONTRIBUTI/`](16_SOCIETA_FINANZA_E_CONTRIBUTI/) contiene il pacchetto societario-finanziario di lavoro:

- business plan master;
- Piano Aziendale per bandi;
- scelta forma societaria;
- statuto tipo S.r.l. società agricola da validare col notaio;
- patti tra soci;
- governance e deleghe;
- checklist costituzione e data room;
- contributi e cassa iniziale.

Il principio è mantenere **un'unica base numerica** fra progetto tecnico, banca, soci e bandi.

## Piano operativo di avvio

Il riferimento per l'esecuzione della Fase P1 è [`20_CANTIERE_E_CRONOPROGRAMMA/PIANO_OPERATIVO_AVVIO/`](20_CANTIERE_E_CRONOPROGRAMMA/PIANO_OPERATIVO_AVVIO/).

Numeri di governo:
- CAPEX netto di lavoro: **€950.000**;
- riserva operativa protetta: **€120.000**;
- linea IVA/ponte: **€140.000–170.000**;
- serra finale: ~4.200 m² / 6 comparti;
- prima messa a reddito: **3 comparti / ~2.100 m²**;
- target commerciale P1 da validare: ~**€280.000/anno**;
- espansione agli altri 3 comparti solo dopo dati reali tecnici, commerciali e di cassa.

## Regola di progettazione

Ogni componente fisico deve arrivare almeno a: funzione, requisiti, marca/modello o specifica, quantità, prezzo, fonte, IVA, installazione, consumi, manutenzione, ricambi, sicurezza, modalità di guasto, ripiego, durata, dipendenze, contributi e stato della decisione.

Un elemento non è considerato progettato finché questi punti essenziali non sono coperti o marcati esplicitamente come `DA VERIFICARE`.
