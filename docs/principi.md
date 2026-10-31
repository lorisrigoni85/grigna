# Principi

Sei idee guidano Grigna. Quando una regola più specifica non copre un caso, si decide partendo da qui.

## 1. Il sistema è il contesto

Un design system ben strutturato è il miglior contesto che un agente possa avere. Per questo ogni scelta è scritta, ha un nome ed è verificabile da uno script, non solo da un occhio esperto. Se una regola non si può controllare, va riscritta finché si può.

## 2. Pulito e luminoso

Superfici chiare, molto spazio, un solo colore d'accento. L'interfaccia si fa da parte e lascia la scena ai contenuti: foto, mappe, dati. Ispirazione dichiarata: AllTrails e Komoot, per i principi e non per le forme. Da loro non si copiano colori, logo, icone o componenti.

## 3. Il colore ha sempre un significato

Ogni colore ha un compito preciso: l'Abete indica l'azione, i colori di feedback lo stato. Un livello brand può dare a un colore un significato suo, e da quel momento quel colore serve solo a quello. Un colore non si usa per decorare né per distinguere categorie, perché finirebbe per avere due significati.

E il colore non è mai da solo: va sempre insieme a un testo, un'icona o una forma. Così l'informazione arriva anche a chi non distingue i colori, su uno schermo al sole o in bianco e nero.

## 4. Accessibile per costruzione

- Contrasto minimo 4,5:1 per il testo e 3:1 per gli elementi grafici e i bordi dei controlli. Lo controlla la build: se un abbinamento non passa, si ferma.
- Area di tocco minima di 44px per ogni elemento interattivo.
- Testo corrente mai sotto i 16px.
- Focus sempre visibile da tastiera.
- Tema chiaro e scuro con gli stessi nomi di token.

## 5. Meno scelte, più coerenza

Pochi token con nomi chiari valgono più di una scala infinita. Si sceglie `--grigna-space-md`, non "16px" o "15px che sta meglio". Se manca qualcosa si aggiunge al sistema, non si aggira con un valore scritto a mano.

## 6. Niente contenuti inventati

Esempi, testi di prova e anteprime usano segnaposto chiari: un testo come "Titolo di esempio", o il [segnaposto](componenti/segnaposto.md) per numeri e date. I dati veri arrivano solo da fonti vere. Vale per le persone e soprattutto per gli agenti.

E in un'interfaccia con dati veri, **un dato che manca non si mostra**: niente trattini, "n.d." o stime. Si toglie l'elemento.

---

## Per gli agenti

- Prima di creare un'interfaccia, leggi [`AGENTS.md`](../AGENTS.md) e la pagina del componente che stai per usare.
- Se un caso non è coperto da nessuna regola, applica questi principi e **segnala** il caso nella risposta, invece di inventare una soluzione nuova in silenzio.
