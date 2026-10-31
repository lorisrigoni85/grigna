# Colore

```html anteprima
<div class="demo-stack">
<span class="demo-label">Superfici · valori del tema attivo</span>
<div class="demo-grid">
<div class="swatch"><span class="swatch-chip" style="background: var(--grigna-color-surface-default)"></span><code>surface-default</code><span class="demo-label" data-token="--grigna-color-surface-default"></span></div>
<div class="swatch"><span class="swatch-chip" style="background: var(--grigna-color-surface-subtle)"></span><code>surface-subtle</code><span class="demo-label" data-token="--grigna-color-surface-subtle"></span></div>
<div class="swatch"><span class="swatch-chip" style="background: var(--grigna-color-surface-raised)"></span><code>surface-raised</code><span class="demo-label" data-token="--grigna-color-surface-raised"></span></div>
<div class="swatch"><span class="swatch-chip" style="background: var(--grigna-color-surface-inverse)"></span><code>surface-inverse</code><span class="demo-label" data-token="--grigna-color-surface-inverse"></span></div>
</div>
<span class="demo-label">Bordi · valori del tema attivo</span>
<div class="demo-grid">
<div class="swatch"><span class="swatch-chip" style="background: var(--grigna-color-border-default)"></span><code>border-default</code><span class="demo-label" data-token="--grigna-color-border-default"></span></div>
<div class="swatch"><span class="swatch-chip" style="background: var(--grigna-color-border-strong)"></span><code>border-strong</code><span class="demo-label" data-token="--grigna-color-border-strong"></span></div>
</div>
<span class="demo-label">Testo · valori del tema attivo</span>
<div class="demo-grid">
<div class="swatch"><span class="swatch-chip" style="background: var(--grigna-color-text-default)"></span><code>text-default</code><span class="demo-label" data-token="--grigna-color-text-default"></span></div>
<div class="swatch"><span class="swatch-chip" style="background: var(--grigna-color-text-muted)"></span><code>text-muted</code><span class="demo-label" data-token="--grigna-color-text-muted"></span></div>
<div class="swatch"><span class="swatch-chip" style="background: var(--grigna-color-text-disabled)"></span><code>text-disabled</code><span class="demo-label" data-token="--grigna-color-text-disabled"></span></div>
<div class="swatch"><span class="swatch-chip" style="background: var(--grigna-color-text-inverse)"></span><code>text-inverse</code><span class="demo-label" data-token="--grigna-color-text-inverse"></span></div>
<div class="swatch"><span class="swatch-chip" style="background: var(--grigna-color-text-on-accent)"></span><code>text-on-accent</code><span class="demo-label" data-token="--grigna-color-text-on-accent"></span></div>
</div>
<span class="demo-label">Accento · valori del tema attivo</span>
<div class="demo-grid">
<div class="swatch"><span class="swatch-chip" style="background: var(--grigna-color-accent-default)"></span><code>accent-default</code><span class="demo-label" data-token="--grigna-color-accent-default"></span></div>
<div class="swatch"><span class="swatch-chip" style="background: var(--grigna-color-accent-hover)"></span><code>accent-hover</code><span class="demo-label" data-token="--grigna-color-accent-hover"></span></div>
<div class="swatch"><span class="swatch-chip" style="background: var(--grigna-color-accent-subtle)"></span><code>accent-subtle</code><span class="demo-label" data-token="--grigna-color-accent-subtle"></span></div>
<div class="swatch"><span class="swatch-chip" style="background: var(--grigna-color-accent-text)"></span><code>accent-text</code><span class="demo-label" data-token="--grigna-color-accent-text"></span></div>
<div class="swatch"><span class="swatch-chip" style="background: var(--grigna-color-focus-ring)"></span><code>focus-ring</code><span class="demo-label" data-token="--grigna-color-focus-ring"></span></div>
</div>
<span class="demo-label">Feedback · valori del tema attivo</span>
<div class="demo-grid">
<div class="swatch"><span class="swatch-chip" style="background: var(--grigna-color-feedback-success-fill)"></span><code>feedback-success-fill</code><span class="demo-label" data-token="--grigna-color-feedback-success-fill"></span></div>
<div class="swatch"><span class="swatch-chip" style="background: var(--grigna-color-feedback-warning-fill)"></span><code>feedback-warning-fill</code><span class="demo-label" data-token="--grigna-color-feedback-warning-fill"></span></div>
<div class="swatch"><span class="swatch-chip" style="background: var(--grigna-color-feedback-danger-fill)"></span><code>feedback-danger-fill</code><span class="demo-label" data-token="--grigna-color-feedback-danger-fill"></span></div>
<div class="swatch"><span class="swatch-chip" style="background: var(--grigna-color-feedback-info-fill)"></span><code>feedback-info-fill</code><span class="demo-label" data-token="--grigna-color-feedback-info-fill"></span></div>
</div>
</div>
```

Grigna ha un solo colore d'accento, l'**Abete**, una base di grigi neutri e quattro colori di feedback. Ogni colore ha un compito, e lo stesso nome vale nel tema chiaro e in quello scuro.

L'esempio qui sopra mostra i valori del tema attivo: cambia tema in alto per vedere l'altro. Tutti i valori, chiaro e scuro, stanno in [`dist/tokens.json`](../../dist/tokens.json). Qui sotto ci sono i nomi e il loro uso: i nomi non cambiano, i valori sì.

## Come sono organizzati

| Livello | Esempio | Si usa? |
| --- | --- | --- |
| Primitivi | `primitive.color.abete.500` | **No.** Sono la tavolozza grezza, non hanno significato |
| Semantici | `--grigna-color-accent-default` | **Sì.** Per comporre interfacce nuove |
| Componenti | `--grigna-button-primary-bg` | **Sì**, ma solo dentro quel componente |

I primitivi non esistono come variabili CSS, proprio perché nessuno li usi per sbaglio.

## Token semantici

### Superfici
| Token | Uso |
| --- | --- |
| `--grigna-color-surface-default` | Sfondo della pagina |
| `--grigna-color-surface-subtle` | Sezioni e zone di raggruppamento, segnaposto delle immagini |
| `--grigna-color-surface-raised` | Schede e pannelli, sempre insieme a un'elevazione |
| `--grigna-color-surface-inverse` | Superfici in contrasto con il tema: tooltip, toast |

### Bordi
| Token | Uso |
| --- | --- |
| `--grigna-color-border-default` | Divisori e bordi decorativi |
| `--grigna-color-border-strong` | Bordi che definiscono un controllo (campi, filtri, bottone secondario). Contrasto almeno 3:1 |

### Testo
| Token | Uso |
| --- | --- |
| `--grigna-color-text-default` | Testo principale |
| `--grigna-color-text-muted` | Testo secondario, metadati, segnaposto nei campi |
| `--grigna-color-text-disabled` | Solo per elementi disattivati |
| `--grigna-color-text-inverse` | Testo su `surface-inverse` |
| `--grigna-color-text-on-accent` | Testo su `accent-default` |

### Accento (Abete)
| Token | Uso |
| --- | --- |
| `--grigna-color-accent-default` | Azione principale. Al massimo un bottone primario per vista |
| `--grigna-color-accent-hover` | Stato hover dell'accento |
| `--grigna-color-accent-subtle` | Sfondo tenue per elementi selezionati |
| `--grigna-color-accent-text` | Link e testo d'accento |
| `--grigna-color-focus-ring` | Anello del focus da tastiera |

### Feedback
Quattro famiglie: `success`, `warning`, `danger`, `info`. Ognuna ha tre token:

| Token | Uso |
| --- | --- |
| `--grigna-color-feedback-{stato}-fill` | Icone e indicatori pieni. Contrasto 3:1 sulla pagina |
| `--grigna-color-feedback-{stato}-bg` | Sfondo tenue di badge e messaggi |
| `--grigna-color-feedback-{stato}-text` | Testo sopra il `bg` della stessa famiglia |

Il verde del successo è volutamente più giallo e brillante dell'Abete, così un messaggio "fatto" non si confonde con un bottone.

## Regole

- **Un solo accento per vista.** L'Abete attira l'occhio: se ce ne sono tre, non ne attira nessuno.
- **Il colore non è mai da solo.** Uno stato si legge sempre anche dal testo, da un'icona o da una forma.
- **Testo colorato solo sul suo sfondo.** `feedback-danger-text` va su `feedback-danger-bg` o su una superficie, mai su un altro colore.
- **I colori non distinguono categorie.** Categorie come tipi di attività o di contenuto si distinguono con icona ed etichetta in neutro.

## Tema scuro

Il tema scuro usa gli stessi nomi. Si attiva in due modi:
- da solo, se il sistema operativo è in modalità scura;
- forzandolo con `data-theme="dark"` su `<html>`. `data-theme="light"` forza invece il chiaro.

Nel tema scuro l'elevazione si legge soprattutto dal colore della superficie: `surface-raised` è più chiara della pagina.

## Controlli automatici

`node scripts/build-tokens.mjs` verifica 47 abbinamenti per tema: testo su superfici, testo sull'accento, testo di feedback sul suo sfondo, bordi dei controlli, focus e colori dei livelli brand. Se uno è sotto la soglia WCAG, la build si ferma e dice quale.

---

## Per gli agenti

**Sempre**
- Usa solo variabili `--grigna-color-*` (o i token del componente che stai usando).
- Testo su `accent-default`: `--grigna-color-text-on-accent`.
- Accompagna ogni colore di stato con un testo o un'icona.

**Mai**
- Mai scrivere colori a mano (`#…`, `rgb()`, `hsl()`, nomi come `green`). La build lo rifiuta nei componenti.
- Mai usare i primitivi (`abete.500`, `neutral.200`…): non sono variabili CSS.
- Mai usare l'accento o un colore di feedback per decorare o per distinguere categorie.
- Mai più di un elemento con `accent-default` pieno nella stessa vista.
- Mai `opacity` sul testo per renderlo più tenue: usa `--grigna-color-text-muted`.
