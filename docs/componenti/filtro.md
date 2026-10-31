# Filtro

```html anteprima
<div class="demo-stack" role="group" aria-label="Tipo di attività, esempio">
<span class="demo-label">Prova a cliccare: il filtro attivo mostra la spunta.</span>
<div style="display:flex;flex-wrap:wrap;gap:var(--grigna-space-xs)">
<button class="grigna-chip" aria-pressed="true">Escursione</button>
<button class="grigna-chip" aria-pressed="false">Salita</button>
<button class="grigna-chip" aria-pressed="false">Traversata</button>
</div>
</div>
```

## Cos'è
Un'opzione a forma di pillola che si attiva e si disattiva, per restringere una lista.

## Quando usarlo
- Per filtrare risultati: disciplina, difficoltà, periodo.
- In gruppi, quando le opzioni sono poche e conviene vederle tutte.

## Quando non usarlo
- Per un'etichetta fissa: usa il [badge](badge.md).
- Per un'azione: usa il [bottone](bottone.md).
- Con molte opzioni (più di 8 circa): serve un altro componente, per esempio una select.

## Codice

```html
<div role="group" aria-label="Disciplina">
  <button class="grigna-chip" aria-pressed="true">Escursionismo</button>
  <button class="grigna-chip" aria-pressed="false">Alpinismo</button>
</div>
```

E per farlo cambiare stato al clic:

```js
chip.addEventListener("click", () =>
  chip.setAttribute("aria-pressed", chip.getAttribute("aria-pressed") !== "true"));
```

## Varianti e stati

| Stato | Come si ottiene |
| --- | --- |
| Non attivo | `aria-pressed="false"` |
| Attivo | `aria-pressed="true"`: sfondo Abete tenue, bordo Abete e **spunta** disegnata dal CSS |
| Focus | Automatico da tastiera |

Lo stato sta in `aria-pressed`, non in una classe. Così l'aspetto e quello che sente lo screen reader non possono andare in disaccordo.

## Token
`--grigna-chip-height`, `-padding-x`, `-gap`, `-radius`, `-font`, `-bg`, `-bg-hover`, `-border`, `-text`, `-selected-bg`, `-selected-border`, `-selected-text` (tutti con prefisso `--grigna-chip`).

## Accessibilità
- Altezza minima 44px.
- Il gruppo ha `role="group"` e un `aria-label` che dice cosa si filtra.
- Lo stato attivo si vede anche senza colore, grazie alla spunta.

---

## Per gli agenti

**Sempre**
- `<button class="grigna-chip" aria-pressed="…">` dentro un `role="group"` con `aria-label`.
- Cambia stato modificando `aria-pressed`.

**Mai**
- Mai una classe tipo `--selected` o `--active`: lo stato è solo `aria-pressed`.
- Mai aggiungere una spunta a mano, la disegna il CSS.
- Mai colori diversi per filtri diversi (per esempio un colore per disciplina).
