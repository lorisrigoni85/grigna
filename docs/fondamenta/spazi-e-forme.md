# Spazi, raggi ed elevazione

```html anteprima
<div class="demo-stack">
<span class="demo-label">Spazi</span>
<div><div class="demo-bar" style="width: var(--grigna-space-2xs)"></div><code class="demo-label">space-2xs · <span data-token="--grigna-space-2xs"></span></code></div>
<div><div class="demo-bar" style="width: var(--grigna-space-xs)"></div><code class="demo-label">space-xs · <span data-token="--grigna-space-xs"></span></code></div>
<div><div class="demo-bar" style="width: var(--grigna-space-sm)"></div><code class="demo-label">space-sm · <span data-token="--grigna-space-sm"></span></code></div>
<div><div class="demo-bar" style="width: var(--grigna-space-md)"></div><code class="demo-label">space-md · <span data-token="--grigna-space-md"></span></code></div>
<div><div class="demo-bar" style="width: var(--grigna-space-lg)"></div><code class="demo-label">space-lg · <span data-token="--grigna-space-lg"></span></code></div>
<div><div class="demo-bar" style="width: var(--grigna-space-xl)"></div><code class="demo-label">space-xl · <span data-token="--grigna-space-xl"></span></code></div>
<div><div class="demo-bar" style="width: var(--grigna-space-2xl)"></div><code class="demo-label">space-2xl · <span data-token="--grigna-space-2xl"></span></code></div>
<div><div class="demo-bar" style="width: var(--grigna-space-3xl)"></div><code class="demo-label">space-3xl · <span data-token="--grigna-space-3xl"></span></code></div>
<span class="demo-label">Raggi</span>
<div class="demo-grid">
<div><div class="demo-box" style="border-radius: var(--grigna-radius-control)"></div><code class="demo-label">radius-control</code></div>
<div><div class="demo-box" style="border-radius: var(--grigna-radius-card)"></div><code class="demo-label">radius-card</code></div>
<div><div class="demo-box" style="border-radius: var(--grigna-radius-overlay)"></div><code class="demo-label">radius-overlay</code></div>
<div><div class="demo-box" style="border-radius: var(--grigna-radius-pill)"></div><code class="demo-label">radius-pill</code></div>
</div>
<span class="demo-label">Elevazione</span>
<div class="demo-grid">
<div class="demo-surface" style="box-shadow: var(--grigna-elevation-flat)"><code class="demo-label">elevation-flat</code></div>
<div class="demo-surface" style="box-shadow: var(--grigna-elevation-raised)"><code class="demo-label">elevation-raised</code></div>
<div class="demo-surface" style="box-shadow: var(--grigna-elevation-overlay)"><code class="demo-label">elevation-overlay</code></div>
</div>
</div>
```

## Spazi

Una scala su base 4px, con otto nomi. Tra un elemento e l'altro si usa sempre uno di questi.

| Token | Valore | Uso tipico |
| --- | --- | --- |
| `--grigna-space-2xs` | 4px | Tra icona e testo piccolo |
| `--grigna-space-xs` | 8px | Tra elementi dello stesso gruppo |
| `--grigna-space-sm` | 12px | Margine interno dei campi, tra righe di dati |
| `--grigna-space-md` | 16px | Margine interno delle schede, margine laterale su mobile |
| `--grigna-space-lg` | 24px | Tra gruppi diversi |
| `--grigna-space-xl` | 32px | Tra sezioni |
| `--grigna-space-2xl` | 48px | Sopra i titoli di sezione |
| `--grigna-space-3xl` | 64px | Respiro di pagina |

**Regola pratica:** più due cose sono legate, più stanno vicine. Gli spazi crescono passando da "dentro un elemento" a "tra elementi" a "tra sezioni".

## Raggi

| Token | Valore | Uso |
| --- | --- | --- |
| `--grigna-radius-control` | 8px | Bottoni, campi |
| `--grigna-radius-card` | 12px | Schede, pannelli |
| `--grigna-radius-overlay` | 16px | Finestre di dialogo, fogli dal basso |
| `--grigna-radius-pill` | tondo | Badge, filtri, etichette di stato |

Gli angoli sono generosi, per un tono amichevole. Un bordo su un solo lato non si arrotonda.

## Elevazione

Tre livelli. Più un elemento è "sopra" la pagina, più ombra ha.

| Token | Uso |
| --- | --- |
| `--grigna-elevation-flat` | Elementi nel flusso della pagina: nessuna ombra |
| `--grigna-elevation-raised` | Schede |
| `--grigna-elevation-overlay` | Menu, finestre di dialogo, fogli dal basso, hover delle schede cliccabili |

Nel tema scuro le ombre si vedono poco: l'elevazione si legge soprattutto da `surface-raised`, che è più chiara della pagina. Per questo un elemento elevato usa sempre **entrambi**: superficie e ombra.

## Misure

| Token | Valore | Uso |
| --- | --- | --- |
| `--grigna-size-touch-target` | 44px | Area minima di tocco di ogni elemento interattivo |
| `--grigna-size-text-min` | 16px | Dimensione minima del testo corrente |
| `--grigna-size-icon-sm` / `-md` / `-lg` | 16 / 20 / 24px | Icone |
| `--grigna-size-focus-ring` | 2px | Spessore dell'anello del focus |

## Layout

| Token | Valore | Uso |
| --- | --- | --- |
| `--grigna-size-page-max` | 1200px | Larghezza massima del contenuto della pagina, centrato |
| `--grigna-size-card-min` | 280px | Larghezza minima di una scheda in una griglia |

Una griglia di schede che si adatta da sola a telefono e computer:

```css
.pagina { max-width: var(--grigna-size-page-max); margin-inline: auto; padding-inline: var(--grigna-space-md); }
.schede { display: grid; gap: var(--grigna-space-lg);
          grid-template-columns: repeat(auto-fill, minmax(min(100%, var(--grigna-size-card-min)), 1fr)); }
```

**Punto di rottura: 768px.** Sotto è telefono, sopra è tablet e computer. Nelle media query il CSS non accetta variabili, quindi è l'unico valore che si scrive a mano: `@media (min-width: 768px)`. Prima di usarlo, chiediti se una griglia che si adatta da sola non basta già.

(Valori scelti il 30/10/2026.)

---

## Per gli agenti

**Sempre**
- `margin`, `padding` e `gap` con `--grigna-space-*`.
- `border-radius` con `--grigna-radius-*`.
- `box-shadow` con `--grigna-elevation-*`, insieme a `--grigna-color-surface-raised`.
- Elementi interattivi alti almeno `--grigna-size-touch-target`.
- Larghezza della pagina con `--grigna-size-page-max`, griglie di schede con `--grigna-size-card-min`.
- Nelle media query solo il punto di rottura `768px`.

**Mai**
- Mai valori in px scritti a mano per spazi, raggi e ombre (fanno eccezione i bordi da 1px).
- Mai valori "a metà" (10px, 14px, 20px di spazio): se servono davvero, si aggiungono al sistema e non si improvvisano.
- Mai ombre colorate o sfumate fatte a mano.
