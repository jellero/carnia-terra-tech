# Carnia TerraTech — Crop Card Template

**Uso:** duplicare una scheda per ogni coltura/cultivar prima della validazione commerciale.

## Identità

- Coltura:
- Cultivar / portinnesto:
- Fornitore seme/piantina:
- Stato: `IDEA / REQUISITO / CANDIDATO / VALIDATO`:
- Comparto previsto:
- Sistema: suolo / substrato / letto / altro:
- Prodotto venduto:
- Cliente/canale target:

## Ciclo

- Semina:
- Trapianto:
- Inizio raccolta:
- Fine raccolta:
- Durata ciclo:
- Cicli/anno:
- Finestra commerciale target:

Ogni data deve essere associata a fonte o dati aziendali; non usare calendari generici come dato definitivo.

## Layout e densità

- Superficie netta:
- Numero file/letti:
- Lunghezza file/letti:
- Distanze:
- Piante/m² oppure steli/m²:
- Numero piante:
- Tutoraggio/supporti:
- Spazio di manovra/raccolta:

## Clima

Definire con fonte tecnica specifica per cultivar/sistema:

- temperatura giorno/notte;
- temperatura minima di sicurezza;
- temperatura radicale;
- UR/VPD target;
- PAR/DLI, quando rilevante;
- CO₂, se previsto;
- ventilazione;
- schermatura;
- fogging;
- esigenze di impollinazione.

## Acqua e nutrizione

- qualità acqua richiesta;
- sistema irriguo;
- portata per settore;
- frequenza/strategia;
- drenaggio target, se applicabile;
- pH;
- EC;
- ricetta nutrienti per fase;
- consumo acqua previsto per ciclo;
- fertilizzante previsto per ciclo;
- modalità di verifica con sensori/analisi.

I valori diventano operativi solo dopo validazione agronomica e analisi acqua.

## Materiali e consumabili

- seme/piantine;
- substrato;
- vasi/slab/cubetti;
- fili/clip/supporti;
- gocciolatori/tubi specifici;
- insetti utili/mezzi biologici;
- packaging;
- altri consumabili.

Per ciascuna voce: quantità, costo, fornitore, lead time e ricambio/alternativa.

## Operazioni e lavoro

Elencare tutte le attività con frequenza e tempo:

- preparazione;
- semina/trapianto;
- legatura/potatura/scacchiatura;
- controllo fitosanitario;
- pulizia;
- raccolta;
- movimentazione;
- cernita;
- confezionamento;
- fine ciclo e sanificazione.

Calcolare:

- ore/ciclo;
- ore/settimana medie;
- picco ore/settimana;
- ore/kg vendibile.

## Automazione

Per ogni attività indicare:

- manuale oggi;
- automatizzabile;
- automazione già prevista;
- prerequisiti layout;
- rischio/beneficio;
- investimento necessario.

## Fitosanità e biosicurezza

- principali patogeni/parassiti rilevanti;
- vettori;
- monitoraggio;
- trappole;
- soglie/criteri di intervento;
- prevenzione;
- igiene;
- biocontrollo/mezzi non chimici;
- prodotti fitosanitari solo se autorizzati e verificati al momento dell'uso;
- procedura isolamento focolaio;
- fine ciclo/sanificazione.

## Raccolta e post-raccolta

- maturità commerciale;
- frequenza raccolta;
- metodo;
- cassette/contenitori;
- tempo massimo campo-cella;
- temperatura/UR conservazione;
- shelf life obiettivo;
- packaging;
- tracciabilità;
- scarto e destinazione.

## Resa

Registrare separatamente:

- resa biologica totale;
- resa vendibile;
- scarto %;
- resa prudente;
- resa base;
- resa alta.

Ogni scenario deve riportare fonte, condizioni e motivo della sua applicabilità al progetto.

## Economia

- prezzo medio per canale;
- ricavo/m²;
- costo piantine/seme;
- substrato;
- fertilizzanti;
- acqua;
- energia;
- fitosanità;
- packaging;
- lavoro;
- logistica;
- quota manutenzione/consumabili;
- margine di contribuzione/m²;
- margine di contribuzione/ora uomo;
- break-even prezzo;
- break-even resa vendibile.

## Rischi

- agronomici;
- climatici;
- fitosanitari;
- tecnici;
- lavoro;
- mercato;
- post-raccolta;
- dipendenza da fornitore;
- dipendenza da singolo cliente.

Per ogni rischio: probabilità qualitativa, impatto, prevenzione, fallback.

## Gate finale

Una coltura non passa a `VALIDATA` finché non sono chiusi almeno:

- sistema di coltivazione;
- cultivar/materiale vegetale;
- calendario;
- input principali;
- raccolta/post-raccolta;
- resa vendibile prudente con fonte;
- ore uomo;
- mercato/prezzo;
- margine;
- principali rischi e fallback.