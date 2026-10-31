# Icone

```html anteprima
<div class="demo-grid">
<div class="swatch"><i data-lucide="search" aria-hidden="true" style="width: var(--grigna-size-icon-lg); height: var(--grigna-size-icon-lg)"></i><code class="demo-label">search</code></div>
<div class="swatch"><i data-lucide="check" aria-hidden="true" style="width: var(--grigna-size-icon-lg); height: var(--grigna-size-icon-lg)"></i><code class="demo-label">check</code></div>
<div class="swatch"><i data-lucide="x" aria-hidden="true" style="width: var(--grigna-size-icon-lg); height: var(--grigna-size-icon-lg)"></i><code class="demo-label">x</code></div>
<div class="swatch"><i data-lucide="plus" aria-hidden="true" style="width: var(--grigna-size-icon-lg); height: var(--grigna-size-icon-lg)"></i><code class="demo-label">plus</code></div>
<div class="swatch"><i data-lucide="info" aria-hidden="true" style="width: var(--grigna-size-icon-lg); height: var(--grigna-size-icon-lg)"></i><code class="demo-label">info</code></div>
<div class="swatch"><i data-lucide="map-pin" aria-hidden="true" style="width: var(--grigna-size-icon-lg); height: var(--grigna-size-icon-lg)"></i><code class="demo-label">map-pin</code></div>
<div class="swatch"><i data-lucide="route" aria-hidden="true" style="width: var(--grigna-size-icon-lg); height: var(--grigna-size-icon-lg)"></i><code class="demo-label">route</code></div>
<div class="swatch"><i data-lucide="mountain" aria-hidden="true" style="width: var(--grigna-size-icon-lg); height: var(--grigna-size-icon-lg)"></i><code class="demo-label">mountain</code></div>
</div>
```

Grigna usa una sola libreria: **[Lucide](https://lucide.dev)**, versione **1.57.0** (licenza ISC). Il tratto è sottile e arrotondato, coerente con il tono pulito e amichevole del sistema.

## Perché una sola libreria

Icone di librerie diverse hanno spessori, angoli e proporzioni diversi: messe vicine, si vede subito. Se a Lucide manca un'icona, la si disegna nello stesso stile (griglia 24×24, tratto 2px, estremità arrotondate) e la si aggiunge a Grigna. Non si prende da un'altra libreria.

## Come si usa

Con il pacchetto UMD:

```html
<script src="https://unpkg.com/lucide@1.57.0/dist/umd/lucide.min.js"></script>
<i data-lucide="mountain"></i>
<script>lucide.createIcons();</script>
```

Oppure si copia il file SVG da `lucide-static@1.57.0/icons/{nome}.svg`. In entrambi i casi l'icona prende il colore del testo (`currentColor`).

Misure: `--grigna-size-icon-sm` (16px) dentro badge e filtri, `--grigna-size-icon-md` (20px) nei bottoni e accanto al testo, `--grigna-size-icon-lg` (24px) da sola. I componenti di Grigna dimensionano già le icone che contengono.

## Regole

- **Icona più testo, quasi sempre.** Un'icona da sola si capisce solo se è universale (cerca, chiudi, menu). In quel caso il bottone ha un `aria-label`.
- **Le icone decorative si nascondono** agli screen reader con `aria-hidden="true"`.
- **Il colore dell'icona è quello del testo vicino.** Non si colora un'icona per farla notare.
- **Stesso concetto, stessa icona** in tutto il prodotto.

## Icone disegnate per Grigna

Quando Lucide non ha un'icona, la si disegna nello stesso stile e la si salva in `icons/`, nella cartella del livello a cui appartiene: `icons/<nome del livello>/`. Le icone di un livello brand sono elencate nelle sue docs.

Si usano copiando il contenuto del file SVG così com'è dentro la pagina, con `aria-hidden="true"` sull'elemento `<svg>`. Prendono il colore del testo e i componenti di Grigna le dimensionano come le icone Lucide.

```html
<span>
  <svg aria-hidden="true" …contenuto del file SVG…></svg>Etichetta
</span>
```

Le regole di disegno: griglia 24×24, tratto 2px, estremità e angoli arrotondati, nessun riempimento, colore `currentColor`.

---

## Per gli agenti

**Sempre**
- Solo icone Lucide 1.57.0, con il nome esatto della libreria, oppure le icone disegnate in `icons/`.
- Per i concetti di un livello brand usa la tabella delle icone nelle docs di quel livello.
- Un'icona di Grigna si copia così com'è dal suo file, senza modificarne i tracciati.
- `aria-hidden="true"` sulle icone accanto a un testo, `aria-label` sui bottoni con sola icona.

**Mai**
- Mai icone da altre librerie (Material, Font Awesome, Heroicons…), mai emoji al posto delle icone.
- Mai disegnare SVG a mano dentro una pagina: un'icona nuova si propone e si aggiunge a Grigna.
- Mai usare le proposte in `archivio/`: sono solo la storia del processo.
- Mai inventare nomi di icone: se non sei sicuro che un nome esista in Lucide 1.57.0, dillo.
