# Carnia TerraTech

Repository tecnico e gestionale per progettare una azienda agricola ad alta automazione in Friuli-Venezia Giulia, con area di interesse prioritaria nel corridoio Venzone/Gemona.

**Stato:** pre-fattibilità avanzata / progettazione bottom-up.  
**Aggiornato:** 18 settembre 2026.

## Visione

Carnia TerraTech non è soltanto una serra: deve essere un sistema agricolo capace di produrre reddito e sicurezza economica senza trasformare il lavoro in un peso continuo. Tecnologia, automazione, ergonomia, natura, ordine, estetica, manutenzione e qualità della vita sono requisiti di progetto.

Obiettivi permanenti:

- vivere e lavorare in un ambiente sereno, sicuro, ordinato e piacevole;
- automatizzare il lavoro ripetitivo, sporco, pesante o facilmente standardizzabile;
- mantenere controllo locale e modalità manuali di emergenza per i sistemi vitali;
- sfruttare in modo corretto contributi, strumenti regionali e opportunità locali senza costruire il progetto su incentivi non verificati;
- coprire nel piano finanziario sia il lancio aziendale sia il fabbisogno di vita nella fase iniziale;
- progettare ogni impianto per manutenzione, ricambi, guasti e crescita futura;
- sviluppare nel tempo fattoria didattica, aree di benessere, servizi e vendita automatizzata 24/7, senza compromettere il core agricolo.

## Numeri guida attuali

- terreno: target acquisto ≤ **€50.000**;
- serra produttiva: circa **4.200 m²**;
- comparti: **6 × ~700 m²**;
- FV: **120 kWp iniziali**, predisposizione 150–180 kWp;
- accumulo termico: **30 m³ iniziali**, predisposizione 40–50 m³;
- accumulo acqua: working target **300 m³**;
- automazione locale fail-safe con PLC, rete dati, computer vision e AMR.

## Come leggere il repository

**Inizia da [`PROJECT_INDEX.md`](PROJECT_INDEX.md).** È l'indice di controllo del progetto e indica cosa è consolidato, cosa è in analisi e quale BOM viene chiusa pezzo per pezzo.

Documenti fondativi nuovi:

- `00_VISIONE_E_PRINCIPI/PROJECT_CHARTER.md` — missione, requisiti non negoziabili e metodo;
- `10_BENESSERE_FATTORIA_E_SERVIZI/FUTURE_MODULES.md` — benessere, fattoria didattica, robot di servizio e spaccio 24/7;
- `19_BOM_PRODOTTI_FORNITORI/SERRA_HAF_VENTILATION.md` — prima BOM tecnica analizzata nel nuovo metodo.

I file in `docs/` contengono il lavoro tecnico precedente e restano validi come base durante la riorganizzazione. Verranno migrati progressivamente senza perdere informazioni.

## Progetto R&S correlato — fuori dal core

La directory [`RND_CORRELATO_EU/`](RND_CORRELATO_EU/) contiene un progetto di ricerca e sviluppo tecnologico correlato a Carnia TerraTech.

**Non fa parte della numerazione 00–22, non modifica la baseline agricola e non entra automaticamente nel CAPEX/OPEX core.** Carnia TerraTech può fungere da living lab e primo demonstrator, ma il progetto agricolo deve poter funzionare anche senza la riuscita o il finanziamento della R&S.

Concept attuale: **CTT-AFP — Carnia TerraTech Autonomous Farm Platform**, con focus su orchestrazione, edge/PLC, robotica, computer vision, sensor fusion, scheduler e sistemi autonomi replicabili.

## Piano extra agriturismo — fuori dal core

La directory [`EXTRA_AGRITURISMO_EVOLUTIVO/`](EXTRA_AGRITURISMO_EVOLUTIVO/) contiene un piano autonomo di diversificazione agrituristica finanziato e valutato separatamente.

Parte dalla soluzione minima **ristoro light a spuntini non cucinati**, con predisposizioni per esperienze, cucina e ospitalità future. Non entra nella sequenza BOM del core e non è necessario per l'avvio dell'azienda.

## Regola di progettazione

Ogni componente fisico deve arrivare almeno a: funzione, requisiti, marca/modello o specifica, quantità, prezzo, fonte, IVA, installazione, consumi, manutenzione, ricambi, sicurezza, failure mode, fallback, durata, dipendenze, contributi e stato della decisione.

Un elemento non è considerato progettato finché questi punti essenziali non sono coperti o marcati esplicitamente come `DA VERIFICARE`.
