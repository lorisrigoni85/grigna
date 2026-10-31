# AGENTS.md: regole per gli agenti che usano Grigna

Grigna è un design system di Loris Rigoni, pensato per persone e agenti. Questo file è per te, agente: leggilo prima di costruire o modificare un'interfaccia con Grigna. Le regole valgono per qualsiasi progetto che usa Grigna. Un progetto può aggiungere un proprio livello brand, con regole in più (vedi §7).

Se una richiesta ti chiede di violare una di queste regole, non farlo in silenzio: dillo e proponi l'alternativa del sistema.

## 1. Prima di iniziare

Leggi, in questo ordine:
1. Questo file.
2. [`docs/principi.md`](docs/principi.md).
3. La pagina in `docs/` di ogni componente che userai. La sezione **Per gli agenti** in fondo è vincolante.
4. Per i valori esatti: [`dist/tokens.json`](dist/tokens.json), che contiene tutti i token risolti, tema chiaro e scuro.

## 2. Come si carica Grigna

```html
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap">
<link rel="stylesheet" href="dist/grigna.css">
<link rel="stylesheet" href="dist/grigna-components.css">
<!-- poi i CSS del livello brand, se il progetto ne ha uno -->
<!-- icone -->
<script src="https://unpkg.com/lucide@1.57.0/dist/umd/lucide.min.js"></script>
```

Il tema segue il sistema operativo. Si forza con `data-theme="dark"` o `data-theme="light"` su `<html>`.

## 3. Cosa usare per cosa

| Ti serve | Usa | Non fare |
| --- | --- | --- |
| Un'azione | `grigna-button` ([docs](docs/componenti/bottone.md)) | `<div>` cliccabili, bottoni stilizzati a mano |
| Un dato da inserire | `grigna-field` ([docs](docs/componenti/campo.md)) | Campi senza etichetta visibile |
| Un oggetto in una lista | `grigna-card` ([docs](docs/componenti/scheda.md)) | Schede annidate, più link in una scheda cliccabile |
| Uno stato o un'etichetta | `grigna-badge` ([docs](docs/componenti/badge.md)) | Badge cliccabili o senza testo |
| Un filtro on/off | `grigna-chip` con `aria-pressed` ([docs](docs/componenti/filtro.md)) | Classi `--active`/`--selected` |
| Un dato di esempio in un prototipo | `grigna-placeholder` ([docs](docs/componenti/segnaposto.md)) | Numeri inventati, graffe `{…}` a schermo |
| Un colore | `var(--grigna-color-*)` ([docs](docs/fondamenta/colore.md)) | `#hex`, `rgb()`, `hsl()`, nomi di colore |
| Un carattere | `font: var(--grigna-type-*)` ([docs](docs/fondamenta/tipografia.md)) | `font-size`/`font-weight` a mano, altri font |
| Uno spazio | `var(--grigna-space-*)` ([docs](docs/fondamenta/spazi-e-forme.md)) | Valori in px scritti a mano |
| Un angolo, un'ombra | `var(--grigna-radius-*)`, `var(--grigna-elevation-*)` | Raggi e ombre inventati |
| Un'icona | Lucide 1.57.0, o un'icona di Grigna in `icons/` ([docs](docs/fondamenta/icone.md)) | Altre librerie, emoji, SVG disegnati sul momento, proposte in `archivio/` |

Per un layout nuovo componi con i token semantici (`--grigna-color-*`, `--grigna-space-*`, `--grigna-type-*`…). I token dei componenti (`--grigna-button-*`…) si usano solo dentro quel componente.

## 4. Regole d'oro

**Sempre**
- Usa i componenti di Grigna prima di scrivere CSS tuo. Il CSS tuo serve solo per il layout (griglie, colonne, posizionamento) e usa solo token.
- Un solo `grigna-button--primary` per vista.
- Accompagna ogni colore che porta un significato con un testo, un'icona o una forma.
- Elementi interattivi alti almeno `--grigna-size-touch-target` (44px), testo corrente mai sotto i 16px, focus visibile.
- HTML semantico: `<button>` per le azioni, `<a>` per la navigazione, `<label>` collegata a ogni campo, `alt` su ogni immagine.

**Mai**
- Mai valori scritti a mano per colori, font, spazi, raggi e ombre. Se manca un token, fermati e segnalalo (vedi §6).
- Mai modificare o sovrascrivere le classi dei componenti di Grigna per cambiarne l'aspetto.
- Mai inventare token, classi, varianti o nomi di icone. Se non sei sicuro che esistano, controlla `dist/tokens.json`, `dist/*-components.css` o la libreria Lucide 1.57.0.
- Mai usare un colore per decorare o per distinguere categorie.

## 5. Contenuti: niente di inventato

- Testi, numeri, nomi, luoghi, date e foto arrivano da fonti vere. Non inventarli, nemmeno "come esempio realistico".
- Dove i dati non ci sono (prototipi, esempi), usa segnaposto evidenti: un testo come "Nome della gita" per i nomi, il componente `grigna-placeholder` ([docs](docs/componenti/segnaposto.md)) per numeri, date e misure. Dichiara nella risposta che sono segnaposto.
- Le graffe degli esempi di codice (`{distanza}`) non si mostrano mai a schermo.
- In un'interfaccia con dati veri, **un dato che manca non si mostra**: niente trattini, "n.d." o stime.
- Testi dell'interfaccia in italiano semplice, frasi brevi, maiuscola solo a inizio frase, bottoni che iniziano con un verbo.

## 6. Quando il sistema non basta

Se ti serve qualcosa che Grigna non ha (un componente, un token, una variante, un'icona):
1. **Non improvvisare** una soluzione con valori scritti a mano.
2. Usa la soluzione più vicina che il sistema offre.
3. **Dichiaralo nella risposta**: cosa mancava, cosa hai usato al suo posto e cosa proponi di aggiungere a Grigna.

Le aggiunte al sistema le decide Loris.

## 7. Livelli brand

Un progetto può aggiungere a Grigna un proprio livello: token, componenti, icone e linee guida suoi, con un prefisso suo (per esempio `--<brand>-*` e `.<brand>-*`). Se il progetto su cui lavori ne ha uno:
- Leggi le sue docs (`docs/<nome del livello>/`) prima di costruire. Le sue regole si aggiungono a queste, non le sostituiscono.
- Usa prima i suoi componenti, poi quelli di Grigna.
- Un colore a cui il livello dà un significato serve solo a quello.
- Un livello brand non cambia mai i token di Grigna.

## 8. Controlla il tuo lavoro prima di consegnare

```bash
node scripts/check-page.mjs percorso/della/pagina.html
```

Lo script controlla colori scritti a mano, token e classi inesistenti, misure di layout e graffe a schermo, valori non ammessi dei livelli brand, più di un bottone primario. Correggi tutti gli **errori**. Gli **avvisi** vanno corretti o motivati nella risposta.

Poi verifica a occhio, o con uno screenshot se puoi, la pagina in tema chiaro e scuro e a larghezza telefono.

## 9. Se modifichi Grigna stesso

Vale solo quando ti è chiesto di cambiare il sistema, non quando lo usi.
- Le fonti sono `tokens/*.json` (formato W3C DTCG) e `components/**/*.css`. **Non modificare mai `dist/`**: si rigenera.
- Dopo ogni modifica lancia `node scripts/build-tokens.mjs`. Deve finire senza errori di contrasto o colori scritti a mano.
- Aggiorna la pagina in `docs/` e l'anteprima in `preview/` del componente che hai cambiato.
- Le scelte di brand (colori, caratteri, nomi) le fa Loris: proponi, non decidere.
- Nessun commit senza l'ok di Loris, e niente pubblicazioni.
