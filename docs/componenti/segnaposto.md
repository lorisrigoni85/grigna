# Segnaposto

```html anteprima
<article class="grigna-card" style="max-width: var(--grigna-size-card-min)">
  <div class="grigna-card__body">
    <strong>Titolo di esempio</strong>
    <span><span class="grigna-placeholder" style="--w:5ch" role="img" aria-label="Dato di esempio"></span> · <span class="grigna-placeholder" style="--w:8ch" role="img" aria-label="Dato di esempio"></span></span>
  </div>
</article>
```

## Cos'è
Una barra neutra che prende il posto di un dato che non c'è ancora, in un prototipo o in un esempio.

## Quando usarlo
- Nei prototipi e negli esempi senza dati veri, per numeri, date e misure.

## Quando non usarlo
- **Con dati veri.** Un dato che manca non si mostra (vedi [Principi](../principi.md#6-niente-contenuti-inventati)).
- Per nomi e testi brevi: lì va bene un testo segnaposto leggibile, come "Titolo di esempio".
- Come indicatore di caricamento: è un'altra cosa, non ancora prevista da Grigna.

## Codice

```html
<dd><span class="grigna-placeholder" style="--w: 5ch" role="img" aria-label="Dato di esempio"></span></dd>
```

La larghezza si regola con `--w`, in `ch`, più o meno quanti caratteri avrebbe il dato vero.

## Segnaposto e graffe

Negli esempi di codice delle docs i dati sono scritti tra graffe, per esempio `{distanza} km`: significa "qui va il dato". **Le graffe non si mostrano mai a schermo.** In una pagina vera si mette il dato. In un prototipo si mette un segnaposto.

## Token
`--grigna-placeholder-bg`, `--grigna-placeholder-radius`.

## Accessibilità
- `role="img"` e `aria-label="Dato di esempio"`: chi usa uno screen reader sa che lì non c'è un dato vero.

---

## Per gli agenti

**Sempre**
- In un prototipo senza dati veri usa `grigna-placeholder` per numeri, date e misure.
- Con `role="img"` e `aria-label="Dato di esempio"`.

**Mai**
- Mai mostrare a schermo le graffe degli esempi (`{distanza}`). `check-page.mjs` lo segnala come errore.
- Mai segnaposto in un'interfaccia con dati veri: lì un dato mancante non si mostra.
- Mai numeri inventati "di esempio" al posto del segnaposto.
