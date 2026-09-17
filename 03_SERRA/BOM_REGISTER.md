# Carnia TerraTech — Greenhouse BOM Register

**Aggiornato:** 17 settembre 2026  
**Regola:** una riga resta aperta finché quantità, specifica, prezzo, posa, manutenzione e ricambio non sono chiusi.

## 1. Registro principale

| Codice | Voce | Quantità working | Stato | Prezzo / nota |
|---|---|---:|---|---|
| GH-STR-001 | Struttura portante 4.200 m² | 1 sistema | `PACKAGE COSTI DEFINITO / DA RFQ` | peso acciaio obbligatorio dal fornitore |
| GH-STR-002 | Colonne/pali principali | DA SHOP DRAWING | `DA PREVENTIVARE` | kg/pz/sezione obbligatori |
| GH-STR-003 | Archi/travi/reticolari | DA SHOP DRAWING | `DA PREVENTIVARE` | kg/pz/sezione obbligatori |
| GH-STR-004 | Gronde strutturali | DA SHOP DRAWING | `DA PREVENTIVARE` | separare funzione strutturale/raccolta acqua |
| GH-STR-005 | Controventi/tiranti | DA SHOP DRAWING | `DA PREVENTIVARE` | carichi e quantità espliciti |
| GH-STR-006 | Piastre/staffe/giunti | DA DISTINTA | `DA PREVENTIVARE` | non assorbire in forfait |
| GH-STR-007 | Bulloneria/cavallotti/morsetti | DA DISTINTA | `DA PREVENTIVARE` | classi/trattamenti + scorta |
| GH-STR-008 | Zincatura/protezione | kg interessati | `DA PREVENTIVARE` | benchmark FVG 2026 +€1,50/kg hot-dip generico |
| GH-STR-009 | Engineering/shop drawing/as-built | 1 lotto | `DA PREVENTIVARE` | calcoli e documenti separati |
| GH-STR-010 | Trasporto/scarico/montaggio/mezzi | 1 lotto | `DA PREVENTIVARE` | distinguere le quattro voci |
| GH-FND-001 | Fondazioni/ancoraggi | DA CALCOLARE | `BLOCCATO DAL LOTTO` | confrontare F1/F2/F3/F4 |
| GH-FND-002 | Scavi fondazioni | m³ da calcolo | `BLOCCATO DAL LOTTO` | terreno e geometria reali |
| GH-FND-003 | Calcestruzzo | m³ da calcolo | `BLOCCATO DAL LOTTO` | FVG 2026 C25/30 materiale ~€111,84–113,17/m³ benchmark |
| GH-FND-004 | Armatura B450C | kg da calcolo | `BLOCCATO DAL PROGETTO` | prezzo da prezzario/fornitore corrente |
| GH-FND-005 | Tirafondi/piastre/grout | da calcolo | `BLOCCATO DAL SISTEMA` | distinta dedicata |
| GH-FND-006 | Prove geotecniche/estrazione | da progetto | `REQUISITO` | necessarie per soluzione reale |
| GH-FND-007 | Rinterro/smaltimento/drenaggio | da sito | `DA PREVENTIVARE` | non dimenticare opere accessorie |
| GH-COV-001 | Film/copertura principale 200 µm | m² sviluppati | `CANDIDATI REALI / DA GEOMETRIA` | Polyane €1,27/m² + IVA; Deltagri da €1,24/m² + IVA; Lucchini da preventivo |
| GH-COV-002 | Profili + wiggle wire/fissaggi | m da shop drawing | `CANDIDATO / DA PREVENTIVARE` | retail benchmark ~€2,17–2,46/m; validare sistema professionale |
| GH-COV-003 | Kit riparazione UV | stock da piano ricambi | `CANDIDATO` | tape 8 cm × 15 m benchmark €18,05 IVA incl. |
| GH-COV-004 | Protezioni anti-abrasione compatibili | m da geometria | `DA VALIDARE COL FILM` | no materiali generici senza approvazione produttore |
| GH-COV-005 | Guarnizioni/sigillanti/profili terminali | da distinta | `DA PREVENTIVARE` | compatibilità chimica obbligatoria |
| GH-COV-006 | Sfrido/scorta film | da piano taglio | `DA CALCOLARE` | non usare % arbitraria |
| GH-COV-007 | Posa/tensionamento copertura | 1 lotto | `DA PREVENTIVARE` | separare ore/piattaforme/garanzia |
| GH-COV-008 | Sostituzione/fine vita | TCO futuro | `REQUISITO` | rimozione, fermo, riciclo/smaltimento |
| GH-END-001 | Testate | 6 comparti / layout | `DA PREVENTIVARE` | separare film/pannelli da struttura |
| GH-DR-001 | Porte persone | DA LAYOUT | `DA PREVENTIVARE` | sicurezza + biosicurezza |
| GH-DR-002 | Porte logistiche/AMR | DA LAYOUT | `DA PREVENTIVARE` | quota dopo scelta mezzi |
| GH-GUT-001 | Gronde | DA GEOMETRIA | `DA PREVENTIVARE` | integrate con recupero pioggia |
| GH-GUT-002 | Pluviali/collettori primari | DA GEOMETRIA | `DA PREVENTIVARE` | collegamento punto 04 |
| GH-CMP-001 | Divisori comparti | 5 separazioni + dettagli | `DA PREVENTIVARE` | materiale da definire |
| GH-VENT-001 | Aperture laterali | 6–12 gruppi working | `CANDIDATI REALI / DA CALCOLO` | vedi BOM-003 |
| GH-VENT-002 | Aperture zenitali | DA GEOMETRIA | `CANDIDATO / DA VALUTARE` | legate a rete e ventilazione |
| GH-VENT-003 | Motori laterali professionali | 6–12 working | `CANDIDATO` | Ridder RW45-L €675,49 + IVA benchmark |
| GH-VENT-004 | Trasmissioni laterali | da layout | `DA PREVENTIVARE` | tubi, giunti, catene/rack, supporti |
| GH-VENT-005 | Quadro/cablaggio aperture | per gruppo | `DA PREVENTIVARE` | protezioni, sezionatori, I/O |
| GH-NET-001 | Rete anti-insetto 50 Air Plus | scenario N1 | `CANDIDATO` | 47% air passage / ~30% vent reduction |
| GH-NET-002 | Rete anti-insetto 60 Air Plus | scenario N2 | `CANDIDATO` | 40% air passage / ~31% vent reduction |
| GH-NET-003 | Rete anti-insetto 80 Air Plus | scenario N3 | `CANDIDATO` | 26% air passage / ~42% vent reduction; tripidi |
| GH-NET-004 | Profili/sigillature rete | da layout | `DA PREVENTIVARE` | bordi senza bypass |
| GH-NET-005 | Scorta rete/clip/profili | lotto | `REQUISITO` | quantità da definire |
| GH-SCR-001 | Schermi C1/C2/C6 | ~2.100 m² nominali + geometria | `CANDIDATI REALI / DA PREVENTIVARE` | vedi BOM-002 |
| GH-SCR-002 | Predisposizione schermi C3-C5 | 3 comparti | `REQUISITO` | integrare nella struttura |
| GH-SCR-003 | Energy screen FR | scenario S1 | `CANDIDATO` | RES 10+ FR / LUXOUS 1147 FR |
| GH-SCR-004 | Shade/diffusion screen FR | scenario S2 | `CANDIDATO` | RLD 45 FR O / HARMONY 5220 O FR |
| GH-SCR-005 | Doppio schermo | scenario S3 | `DA PREVENTIVARE` | doppia meccanica/carichi |
| GH-SCR-006 | Motoriduttori schermo | ~1/comparto/livello | `CANDIDATO` | famiglia Ridder RW45 |
| GH-SCR-007 | Finecorsa/feedback | 1 set/motore | `CANDIDATO` | compatibilità da verificare |
| GH-SCR-008 | Meccanica screen | da shop drawing | `DA PREVENTIVARE` | fili, profili, alberi, push-pull |
| GH-SCR-009 | Quadro/cablaggio screen | per motore/zona | `DA PREVENTIVARE` | protezioni, cavi, I/O |
| GH-SCR-010 | Posa/commissioning/ricambi | 1 lotto | `DA PREVENTIVARE` | separare taratura e stock |
| GH-HAF-001 | Ventilatori HAF | 24 working + scorta | `CANDIDATO` | vedi BOM-001 |
| GH-FOG-001 | Fogging C1/C2/C6 | 3 zone | `BOM-005 SVILUPPATA / DA CALCOLO` | vedi SERRA_FOGGING.md |
| GH-FOG-002 | Pompa/e HP | scenario F1/F2/F3 | `CANDIDATI REALI` | LUBING 5,5 L/min €2.830,43; 20 L/min €3.747,49; FERMO 8/21 L/min benchmark |
| GH-FOG-003 | Filtrazione fine | da portata | `CANDIDATI REALI / DA DIMENSIONARE` | cartuccia 1 µm 20" €13,45; set 5+1+0,005 µm €259,23 benchmark |
| GH-FOG-004 | RO/softening | se analisi acqua lo richiede | `CONDIZIONALE` | prezzo da preventivo dopo analisi |
| GH-FOG-005 | Tubazione HP | m da layout | `CANDIDATI REALI / DA GEOMETRIA` | inox 12 mm ~€3,59/m; PA12 3/8 ~€4,59/m benchmark |
| GH-FOG-006 | Raccordi/supporti | da distinta | `PREZZI TROVATI / DA GEOMETRIA` | diritti/gomiti/tee/staffe separati |
| GH-FOG-007 | Elettrovalvole HP zone | 3 + scorta da definire | `CANDIDATO` | Tecnocooling 3/8 24VAC €217,07/cad |
| GH-FOG-008 | Ugelli HP | da calcolo | `CANDIDATI REALI` | LUBING inox 0,2 €8,98; Tecnocooling inox anti-drip 0,2 €15,70 |
| GH-FOG-009 | Valvole isolamento/drenaggio/relief | da P&ID | `REQUISITO / DA PREVENTIVARE` | non assorbire in pompa |
| GH-FOG-010 | Pressione/portata/dry-run | da architettura | `REQUISITO` | sensori e protezioni separate |
| GH-FOG-011 | Quadro/cablaggio/PLC | 1 package | `DA PREVENTIVARE` | integrazione nel controllo locale |
| GH-FOG-012 | Ricambi/consumabili | 1 lotto | `REQUISITO` | ugelli, filtri, tenute, coil, kit pompa |
| GH-FOG-013 | Posa/commissioning | 1 lotto | `DA PREVENTIVARE` | uniformità, anti-wetting, failure test |
| GH-CROP-001 | Filo/cavo high-wire C1/C2 | m da shop drawing | `DA CALCOLO/RFQ` | diametro, carico, zincatura, tenditori e terminali da progetto |
| GH-CROP-002 | Hook/ReelHook | = steli attivi + scorta | `CANDIDATI REALI` | ReelHook 30 m €7,01 + IVA; hook semplice benchmark €1,45 IVA incl. |
| GH-CROP-003 | Spago coltura | m = hook × lunghezza | `CANDIDATI REALI` | ECOTWINE 400 N ~3.350 m: €54,70–62,70 + IVA/bobina |
| GH-CROP-004 | Clip pianta PP | da steli/ciclo | `PREZZO TROVATO` | Bato 22 mm €77,50 + IVA/10.000 pz |
| GH-CROP-005 | Clip biodegradabili | alternativa | `CANDIDATO` | 22 mm €30,95 + IVA/1.000 pz; disponibilità da verificare |
| GH-CROP-006 | Ancoraggi/tenditori/morsetti | da shop drawing | `DA RFQ` | carico strutturale esplicito |
| GH-DRAIN-001 | Canalina/gutter C1/C2 | m di fila reali | `CANDIDATI / DA RFQ` | metallica continua preferenza iniziale; plastica da confronto |
| GH-DRAIN-002 | Staffe/supporti gutter | da passo | `DA RFQ` | carico slab saturo + manutenzione |
| GH-DRAIN-003 | Giunti/terminali/scarichi | da architettura | `DA RFQ` | righe separate |
| GH-DRAIN-004 | Collettore drenaggi | m/diametri da P&ID | `COLLEGAMENTO PUNTO 04` | per comparto / misura da definire |
| GH-DRAIN-005 | Punti lavaggio/ispezione | da linee | `REQUISITO` | evitare ristagni/biofilm |
| GH-DRAIN-006 | Sensori drenaggio | da architettura | `COLLEGAMENTO PUNTO 04` | volume/EC/pH/T |
| GH-DRAIN-007 | Posa/test pendenza/perdite | 1 lotto | `DA PREVENTIVARE` | commissioning obbligatorio |
| GH-ELEC-001 | Passerelle/canaline elettriche | DA LAYOUT | `REQUISITO` | collegamento punti 06/07 |
| GH-SAFE-001 | Accessi/manutenzione/anticaduta | DA PROGETTO | `REQUISITO` | procedure/normativa |
| GH-SP-001 | Bulloneria/minuteria scorta | DA DISTINTA | `REQUISITO` | non assorbire in forfait |
| GH-LAB-001 | Montaggio struttura | ~960 h-persona benchmark storico | `DA PREVENTIVARE` | da sostituire con piano reale |
| GH-TOOLS-001 | Attrezzatura cantiere | 1 lotto | `DA BOM` | budget storico €18–30k da ricostruire |

## 2. Package/BOM sviluppati

- **BOM-001 HAF** — `19_BOM_PRODOTTI_FORNITORI/SERRA_HAF_VENTILATION.md`;
- **BOM-002 schermi** — `19_BOM_PRODOTTI_FORNITORI/SERRA_SCHERMI_TERMICI_OMBREGGIANTI.md`;
- **BOM-003 aperture/reti** — `19_BOM_PRODOTTI_FORNITORI/SERRA_APERTURE_RETI_ANTIINSETTO.md`;
- **BOM-004 copertura** — `19_BOM_PRODOTTI_FORNITORI/SERRA_COPERTURA_FILM_FISSAGGI.md`;
- **package struttura/fondazioni** — `19_BOM_PRODOTTI_FORNITORI/SERRA_STRUTTURA_FONDAZIONI.md`;
- **BOM-005 fogging** — `19_BOM_PRODOTTI_FORNITORI/SERRA_FOGGING.md`;
- **BOM-006 supporti coltura + drenaggio** — `19_BOM_PRODOTTI_FORNITORI/SERRA_SUPPORTI_COLTURA_DRENAGGIO.md`.

RFQ BOM-006: `03_SERRA/RFQ_CROP_SUPPORT_DRAINAGE.md`.

## 3. Regola costo completo

Per ogni macrovoce:

`materiale + accessori + minuteria + trasporto + scarico + posa + mezzi + progettazione + commissioning + ricambi iniziali`.

Separare costo reale, IVA, costo eleggibile, contributo potenziale, finanziamento e cassa/equity.

## 4. Prossima sequenza economica serra

1. **porte + compartimentazioni interne + gronde/pluviali**;
2. **attrezzatura e consumabili di montaggio**;
3. chiusura del punto 03 con matrice di dipendenze e costi aperti.

BOM-006 torna in lavorazione appena crop card C1/C2 e layout reale sbloccano steli, file, lunghezze, gutter e pendenze.
