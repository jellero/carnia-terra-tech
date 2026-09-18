# Carnia TerraTech — KPI & Guardrails

**Aggiornato:** 18 settembre 2026  
**Scopo:** tradurre la visione del progetto in indicatori osservabili. Dove la soglia non è ancora stata deliberata, il KPI resta obbligatorio ma la soglia è `DA DEFINIRE` nel blocco competente.

## 1. Qualità della vita e lavoro

| KPI | Stato soglia | Nota |
|---|---|---|
| Ore medie/settimana per socio a regime | **~20 h/settimana** working target | da validare con piano operativo reale |
| Ore manuali ripetitive per settimana | DA DEFINIRE | devono ridursi progressivamente con automazione |
| Ore di lavoro sporco/pesante per settimana | DA DEFINIRE | da minimizzare e misurare |
| Numero di interventi d'emergenza fuori orario | DA DEFINIRE | deve essere tracciato |
| Ore di lavoro nei picchi stagionali | DA DEFINIRE | da coprire con piano personale/automazione |
| Giorni/anno in cui l'azienda richiede presenza di entrambi i soci | DA DEFINIRE | indicatore di dipendenza organizzativa |
| Capacità di assentarsi di un socio senza perdita di continuità | OBBLIGATORIA | da dimostrare con ruoli, procedure e automazione |

## 2. Sicurezza economica personale e aziendale

| KPI | Soglia |
|---|---|
| Fabbisogno personale mensile minimo | DA DEFINIRE nel blocco 17 |
| Runway personale durante il lancio | DA DEFINIRE |
| Cassa aziendale minima operativa | DA DEFINIRE |
| Capitale circolante necessario | DA CALCOLARE |
| IVA ponte massima attesa | DA CALCOLARE |
| Ritardo contributi/SAL sostenibile | DA CALCOLARE |
| Debito massimo sostenibile | DA CALCOLARE |
| DSCR minimo accettabile | DA DEFINIRE nel modello finanziario |
| Scenario con contributo/finanziamento approvato ma erogazione ritardata | OBBLIGATORIO | il progetto non parte senza concessione; deve però sopportare ritardi di cassa |

Regola: nessun investimento irreversibile importante deve essere approvato senza conoscere l'effetto sulla cassa personale e aziendale.

## 2A. Mitigazione del rischio di sito

KPI obbligatori prima dell'acquisto:
- % superficie utile coperta da campionamento;
- numero punti/griglia;
- zone anomale non risolte;
- prove infiltrazione/drenaggio eseguite;
- rilievo quote completato;
- parametri geotecnici necessari disponibili;
- costo mitigazioni sito;
- aree non utilizzabili;
- criticità ambientali aperte.

Guardrail:
- **0 UNKNOWN bloccanti** prima dell'acquisto;
- **0 fondazioni/drenaggi progettati su assunzioni non verificate**.

## 3. Continuità operativa

Per ogni sistema vitale devono essere misurati o definiti:

- autonomia senza Internet;
- autonomia senza cloud;
- comportamento in caso di blackout;
- disponibilità acqua utile;
- tempo massimo di ripristino accettabile;
- ricambio critico disponibile in azienda;
- modalità manuale o ridondante;
- allarme locale e remoto;
- persona/procedura responsabile del ripristino.

KPI principali:

| KPI | Soglia |
|---|---|
| Funzioni vitali dipendenti solo dal cloud | **0** |
| Single point of failure non mitigati su funzioni vitali | **0** a progetto esecutivo |
| Asset critici senza procedura di guasto | **0** a commissioning |
| Asset critici senza ricambio/fallback definito | **0** a commissioning |
| Tempo medio di ripristino per classe di asset | DA DEFINIRE per classe |

## 4. Manutenzione

Ogni asset deve alimentare un futuro asset register.

KPI da tracciare:

- ore manutenzione preventiva/mese;
- ore manutenzione correttiva/mese;
- costo ricambi/anno;
- numero fermi imprevisti;
- tempo medio tra guasti;
- tempo medio di ripristino;
- disponibilità ricambi in Italia/UE;
- percentuale interventi eseguibili internamente;
- asset dipendenti da assistenza proprietaria esclusiva.

Guardrail: se una macchina riduce 2 ore di lavoro ma ne crea 3 di manutenzione o dipendenza esterna, non è automaticamente un miglioramento.

## 5. Ergonomia e benessere fisico

Da misurare durante layout e operazione:

- distanza media percorsa per kg/prodotto o turno;
- numero di movimentazioni manuali per cassetta;
- peso massimo movimentato manualmente nelle procedure ordinarie;
- attività sopraelevate;
- attività in postura scomoda;
- esposizione a caldo/freddo/pioggia durante i flussi ordinari;
- esposizione a rumore, polvere, odori e deiezioni;
- presenza di percorsi asciutti e sicuri;
- disponibilità di servizi, ristoro, ombra e zona pausa.

Le soglie specifiche saranno definite durante il layout operativo e la valutazione sicurezza.

## 6. Agronomia e risorse

KPI minimi da rendere disponibili per coltura/comparto quando il sistema sarà operativo:

- kg/m²;
- kg/ora uomo;
- ore uomo/kg;
- L acqua/kg;
- fertilizzante/kg;
- kWh elettrici/kg;
- kWh termici/kg;
- percentuale scarto;
- percentuale drenaggio;
- ricavo/m²;
- margine di contribuzione per comparto.

Questi KPI devono impedire che una coltura venga mantenuta solo perché agronomicamente interessante ma economicamente o operativamente penalizzante.

## 7. Energia

KPI minimi:

- produzione FV;
- autoconsumo FV;
- import/export rete;
- kWh per sistema principale;
- COP reale PDC;
- energia termica accumulata e utile;
- picco elettrico;
- energia per kg prodotto.

Le soglie di progetto saranno definite dopo profilo carichi e dati sito.

## 8. Acqua

KPI minimi:

- volume stoccato;
- consumo giornaliero;
- consumo per comparto;
- autonomia idrica stimata;
- recupero pioggia;
- perdite;
- pressione/portata;
- qualità acqua;
- drenato recuperabile/non recuperabile.

## 9. Crescita e modularità

Per ogni infrastruttura principale va indicato:

- capacità installata;
- capacità predisposta;
- punto di saturazione;
- costo marginale del primo ampliamento;
- opere da rifare in caso di espansione.

Guardrail: un'espansione già prevedibile non deve richiedere demolizioni sostanziali evitabili dell'infrastruttura iniziale.

## 10. Natura, estetica e qualità del luogo

Da controllare nel masterplan:

- presenza di verde produttivo e non solo ornamentale;
- ombreggiamento utile delle aree di sosta;
- separazione visiva ordinata fra aree tecniche e aree aperte a visitatori;
- integrazione di pergolati, vite e alberature senza ombreggiare la produzione;
- gestione fango/polvere/acqua superficiale;
- illuminazione notturna senza abbagliamento inutile;
- collocazione delle sorgenti rumorose;
- percezione ordinata di cavi, tubi, rifiuti, materiali e ricambi.

La valutazione estetica non avrà un punteggio unico: verrà verificata attraverso requisiti di masterplan e manutenzione.

## 8A. Cicli di materia

KPI:
- % residui organici aziendali valorizzati;
- kg humus/vermicompost prodotto;
- kg input esterni con provenienza tracciata;
- €/kg prodotto interno;
- ore uomo/t;
- ore mezzo/t;
- ammendante acquistato evitato;
- non conformità/biosecurity.

## 11. Automazione

Per ogni automazione devono essere registrati:

- ore manuali eliminate;
- errori/rischi ridotti;
- energia aggiuntiva;
- manutenzione aggiuntiva;
- CAPEX;
- OPEX;
- dipendenza software/cloud;
- fallback;
- vita utile prevista.

Una automazione viene mantenuta se il beneficio complessivo resta positivo nel ciclo di vita.

Guardrail aggiuntivo: un robot dedicato a una funzione marginale non ha priorità su mezzi di movimentazione, accesso sicuro in quota, manutenzione, acqua, energia o continuità.

## 12. Dashboard futura di progetto

Quando BOM, CAPEX e modello operativo saranno maturi, questi KPI confluiranno in una dashboard unica con almeno cinque viste:

1. qualità della vita/lavoro;
2. economico-finanziaria;
3. produzione/agronomia;
4. energia/acqua;
5. affidabilità/manutenzione.

Il progetto non sarà considerato ottimizzato se migliora una sola vista peggiorando in modo non accettabile le altre.
