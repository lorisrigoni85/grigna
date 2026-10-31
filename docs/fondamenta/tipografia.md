# Tipografia

```html anteprima
<div class="demo-stack">
<div><p style="margin: 0; font: var(--grigna-type-display); letter-spacing: var(--grigna-type-display-letter-spacing);">Titolo di esempio</p><code class="demo-label">display</code></div>
<div><p style="margin: 0; font: var(--grigna-type-heading-lg); letter-spacing: var(--grigna-type-heading-lg-letter-spacing);">Titolo di esempio</p><code class="demo-label">heading-lg</code></div>
<div><p style="margin: 0; font: var(--grigna-type-heading-md); letter-spacing: var(--grigna-type-heading-md-letter-spacing);">Titolo di esempio</p><code class="demo-label">heading-md</code></div>
<div><p style="margin: 0; font: var(--grigna-type-heading-sm); letter-spacing: var(--grigna-type-heading-sm-letter-spacing);">Titolo di esempio</p><code class="demo-label">heading-sm</code></div>
<div><p style="margin: 0; font: var(--grigna-type-body); letter-spacing: var(--grigna-type-body-letter-spacing);">Titolo di esempio</p><code class="demo-label">body</code></div>
<div><p style="margin: 0; font: var(--grigna-type-body-strong); letter-spacing: var(--grigna-type-body-strong-letter-spacing);">Titolo di esempio</p><code class="demo-label">body-strong</code></div>
<div><p style="margin: 0; font: var(--grigna-type-label); letter-spacing: var(--grigna-type-label-letter-spacing);">Titolo di esempio</p><code class="demo-label">label</code></div>
<div><p style="margin: 0; font: var(--grigna-type-caption); letter-spacing: var(--grigna-type-caption-letter-spacing);">Titolo di esempio</p><code class="demo-label">caption</code></div>
<div><p style="margin: 0; font: var(--grigna-type-data); letter-spacing: var(--grigna-type-data-letter-spacing); font-variant-numeric: tabular-nums;">1.240 m · 12,4 km · 5 h 30</p><code class="demo-label">data</code></div>
</div>
```

Un solo carattere, **Inter**, in quattro pesi: 400, 500, 600 e 700. Nove stili con un nome, ognuno pronto da usare con una sola riga di CSS.

## Stili

| Stile | Dimensione / interlinea | Peso | Uso |
| --- | --- | --- | --- |
| `display` | 36 / 1,2 | 700 | Titolo principale della pagina, uno per schermata |
| `heading-lg` | 24 / 1,2 | 700 | Titoli di sezione |
| `heading-md` | 20 / 1,35 | 600 | Sottosezioni, titoli di pannelli |
| `heading-sm` | 18 / 1,35 | 600 | Titoli di schede |
| `body` | 16 / 1,5 | 400 | Testo corrente |
| `body-strong` | 16 / 1,5 | 600 | Enfasi nel testo, etichette dei campi, bottoni |
| `label` | 14 / 1,35 | 500 | Etichette brevi: badge, filtri, bottoni piccoli |
| `caption` | 14 / 1,5 | 400 | Metadati brevi: date, fonti, testi di aiuto |
| `data` | 16 / 1,35 | 600 | Numeri e misure, sempre con cifre tabulari |

## Come si usa

Ogni stile è una variabile `font` completa, più una per la spaziatura tra le lettere:

```css
.titolo {
  font: var(--grigna-type-heading-lg);
  letter-spacing: var(--grigna-type-heading-lg-letter-spacing);
}

.dislivello {
  font: var(--grigna-type-data);
  font-variant-numeric: tabular-nums;
}
```

Il carattere va caricato nella pagina, per esempio da Google Fonts:

```html
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap">
```

Se Inter non si carica, il testo usa il carattere di sistema, quindi la pagina resta leggibile.

## Regole

- **Il testo corrente non scende sotto i 16px.** I 14px (`label`, `caption`) sono solo per testi brevi, mai per paragrafi.
- **I numeri si allineano.** Dove ci sono misure (distanze, dislivelli, tempi) si usa `data` con `tabular-nums`, così le cifre restano in colonna.
- **La gerarchia viene dalla dimensione e dal peso, non dal colore.** Il colore del testo è `text-default` o `text-muted`.
- **Si scrive in minuscolo normale**, con la maiuscola solo a inizio frase. Niente parole tutte in maiuscolo.

---

## Per gli agenti

**Sempre**
- Usa `font: var(--grigna-type-{stile})` scegliendo uno dei nove stili della tabella.
- Per numeri e misure usa `--grigna-type-data` con `font-variant-numeric: tabular-nums`.

**Mai**
- Mai scrivere `font-size`, `font-weight` o `line-height` a mano.
- Mai caratteri diversi da Inter, mai serif.
- Mai testo di paragrafo con `label` o `caption`.
- Mai titoli tutti in maiuscolo.
