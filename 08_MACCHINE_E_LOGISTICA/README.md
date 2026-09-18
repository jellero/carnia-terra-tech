# Carnia TerraTech — Punto 08: Macchine e logistica

**Aggiornato:** 18 settembre 2026  
**Stato:** `BOM-020 AMR + BOM-021 SOLLEVAMENTO + BOM-022 TAGLIAERBA SVILUPPATE / PILOT, MASTERPLAN E RFQ BLOCCANTI`.

## 1. Obiettivo

Ridurre rischio, fatica e dipendenze operative con mezzi realmente utili. La priorità è movimentare materiali e persone in sicurezza; l'autonomia robotica viene dopo. Ogni macchina deve avere un ruolo distinto, fallback manuale e integrazione coerente con corridoi, persone, acqua, animali e aree visitatori.

## 2. Architettura macchine

- **AMR BOM-020:** trasporto/scouting/inventario/docking in serra e Tech Barn;
- **L1 BOM-021:** telescopico elettrico compatto CORE per pallet, materiali, humus/compost, piazzale, corridoio tecnico e cantiere;
- **L2 BOM-021:** stoccatore elettrico stretto per pallet ordinari nel Tech Barn;
- **H1:** accesso in quota certificato tramite piattaforma OEM o PLE cingolata "ragno"; funzione core, asset da TCO;
- **BOM-022:** robot tagliaerba per prato/verde non produttivo;
- nessuna macchina deve essere usata fuori dal proprio envelope di sicurezza solo per ridurre il numero di mezzi.

## 2A. Ordine di priorità

1. telescopico + forche + benna;
2. accesso sicuro in quota;
3. stoccatore Tech Barn;
4. AMR solo dopo pilot e dati lavoro;
5. tagliaerba solo se l'area lo giustifica.

Robot dedicati a funzioni marginali non precedono manutenzione e movimentazione.

## 3. BOM-020 — AMR serra

Missioni: trasporto, traino, ritorno vuoti, scouting/imaging, inventario e docking.

Working site: robot <=0,75 m preferito, corsie >=1,20 m, turning ~2–2,5 m, ambiente umido/condensa reale.

Candidati:

- **Burro Verde** prioritario da pilot: 68,5 cm, payload 227 kg, towing 908 kg, IP65, prezzo UE/Italia da preventivo;
- **MiR250** benchmark industriale ma non baseline serra finché resta indoor-only/IP21/non-condensing;
- **AgileX Bunker** per R&D/scouting, non AMR collaborativo baseline;
- scouting vendor-independent OAK-D + Jetson opzionale.

Gate: demo realistica, CE/DoC, IP/condensa, offline/API, dock, canoni/TCO, ricambi Italia e acceptance >=100 missioni.

Documenti: `AMR_ARCHITECTURE.md`, `RFQ_AMR.md`, BOM-020 e fonti dedicate.

## 4. BOM-021 — sollevatore / mezzo multifunzione

Architettura a due livelli.

### L1 telescopico elettrico

Candidato prioritario **Merlo EW25.5-90**:

- 2.500 kg;
- ~4,8–5 m;
- ~1,54 m larghezza, ~1,98 m altezza;
- 4WD versione 90;
- piattaforma persone OEM disponibile;
- benchmark demo/usato: ~€69.000 + IVA con forche, ~€75.000 + IVA con forche+navicella/radiocomando;
- nuovo 2026 `DA PREVENTIVO`.

Alternative: Manitou MLT 625 e e JCB 525-60E.

Nessun telescopico entra nelle corsie coltura ~1,20 m: uso su corridoio tecnico ~4 m, Tech Barn se compatibile e piazzale.

### L2 stoccatore

EP EST122 benchmark: 1.200 kg, 792 mm, ~3 m, raggio ~1,46 m, da ~€2.900. Serve a evitare di usare il telescopico per ogni pallet ordinario.

Safety: piattaforma persone solo OEM e abbinamento autorizzato; niente retrofit DIY.

Documenti: `LIFTING_MULTIFUNCTION_ARCHITECTURE.md`, `RFQ_LIFTING_MULTIFUNCTION.md`, BOM-021 e fonti dedicate.

## 4A. Accesso in quota H1

Documenti:
- `ACCESSO_IN_QUOTA_RAGNO_ARCHITETTURA.md`;
- `RFQ_ACCESSO_IN_QUOTA_RAGNO.md`.

Ogni punto alto che richiede manutenzione deve essere raggiungibile in sicurezza.

## 5. BOM-022 — robot tagliaerba

La macchina si dimensiona sulla **superficie netta di prato robotizzabile**, non sul lotto né sull'area agricola outdoor.

Classi working:

- <=1.500 m²: Kress KR171E, €1.699 IVA incl.;
- 1.500–5.000 m² regolare: **Kress KR174E**, €2.999 IVA incl., candidato economico working;
- <=5.000 m² difficile/pendente: Mammotion LUBA 2 AWD 5000X, €2.499 promo / €2.999 listino, oppure Kress 4×4 KR285E €4.499;
- >5.000 fino a ~12.000 m²/professionale: Husqvarna 560 EPOS €6.994 + RS5 €1.019 = €8.013 IVA incl. hardware base.

Guardrail:

- niente taglio notturno;
- area didattica/relax occupata = stop/no-go;
- pollaio/free-range = no-go;
- buffer da vasche, fossi, strade e drop-off;
- obstacle detection non sostituisce segregazione;
- perdita cloud/RTK deve produrre stop/park sicuro.

Documenti: `LAWN_MOWER_ARCHITECTURE.md`, `RFQ_LAWN_MOWER.md`, BOM-022 e fonti dedicate.

## 6. Principio di integrazione

AMR e processi vitali richiedono controllo locale robusto. Il robot tagliaerba è non vitale: API/cloud sono utili ma non giustificano integrazioni complesse se il comportamento offline è sicuro.

Le porte, le aree di transito e le finestre operative devono essere progettate nel masterplan, non compensate a posteriori con software.

## 7. Failure/fallback trasversale

- AMR guasto -> carrelli/manuale;
- telescopico guasto -> noleggio/servizio esterno + stoccatore per logistica leggera;
- stoccatore guasto -> transpallet/manuale;
- tagliaerba guasto -> rasaerba/decespugliatore di backup;
- nessuna macchina singola deve fermare raccolta, irrigazione o sicurezza della serra.

## 8. Gate punto 08

1. masterplan definitivo e larghezze/passaggi;
2. carichi reali e flussi logistici;
3. pavimenti/pendenze/acqua;
4. pilot AMR;
5. demo telescopico con carichi/accessori;
6. superficie prato e pilot mower;
7. CE/DoC e safety delle configurazioni;
8. assistenza/ricambi FVG/Italia;
9. TCO 5–8 anni;
10. commissioning e formazione.