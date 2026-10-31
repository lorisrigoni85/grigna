# Campo

```html anteprima
<div class="demo-grid">
<div class="grigna-field">
  <label class="grigna-field__label" for="demo-titolo">Titolo dell'uscita</label>
  <input class="grigna-field__input" id="demo-titolo" placeholder="Via normale dal rifugio" aria-describedby="demo-titolo-aiuto">
  <p class="grigna-field__help" id="demo-titolo-aiuto">Lo vedranno tutti nella scheda.</p>
</div>
<div class="grigna-field">
  <label class="grigna-field__label" for="demo-dislivello">Dislivello (m)</label>
  <input class="grigna-field__input" id="demo-dislivello" value="abc" aria-invalid="true" aria-describedby="demo-dislivello-errore">
  <p class="grigna-field__error" id="demo-dislivello-errore">Inserisci un numero, per esempio 850.</p>
</div>
<div class="grigna-field">
  <label class="grigna-field__label" for="demo-tipo">Tipo di attività</label>
  <select class="grigna-field__input" id="demo-tipo"><option>Escursione</option><option>Salita</option><option>Traversata</option></select>
</div>
<div class="grigna-field">
  <label class="grigna-field__label" for="demo-off">Campo disattivato</label>
  <input class="grigna-field__input" id="demo-off" value="Non modificabile" disabled>
</div>
</div>
```

## Cos'è
Un'etichetta con il suo controllo di inserimento (testo, menu a tendina o testo lungo), più un aiuto o un errore facoltativi.

## Quando usarlo
- Ogni volta che la persona deve scrivere o scegliere un valore in un modulo.

## Quando non usarlo
- Per scegliere tra 2-5 opzioni sempre visibili: meglio un gruppo di [filtri](filtro.md) o, in futuro, i radio.
- Per cercare: servirà un componente di ricerca dedicato.

## Codice

```html
<div class="grigna-field">
  <label class="grigna-field__label" for="titolo">Titolo dell'uscita</label>
  <input class="grigna-field__input" id="titolo" aria-describedby="titolo-aiuto">
  <p class="grigna-field__help" id="titolo-aiuto">Lo vedranno tutti nella scheda.</p>
</div>
```

Con errore:

```html
<div class="grigna-field">
  <label class="grigna-field__label" for="dislivello">Dislivello (m)</label>
  <input class="grigna-field__input" id="dislivello" aria-invalid="true" aria-describedby="dislivello-errore">
  <p class="grigna-field__error" id="dislivello-errore">Inserisci un numero, per esempio 850.</p>
</div>
```

Funziona allo stesso modo con `<select class="grigna-field__input">` e `<textarea class="grigna-field__input">`.

## Varianti e stati

| Stato | Come si ottiene |
| --- | --- |
| Normale | — |
| Focus | Automatico da tastiera e mouse: bordo e anello Abete |
| Errore | `aria-invalid="true"` sul controllo, più `grigna-field__error` collegato con `aria-describedby` |
| Disattivato | `disabled` sul controllo |

La select ha la sua freccia, con lo stesso margine interno del testo.

## Testi
- **Etichetta:** breve e sempre visibile. Il segnaposto non la sostituisce, perché sparisce mentre si scrive.
- **Segnaposto:** un esempio realistico ("Via normale dal rifugio"), facoltativo.
- **Errore:** cosa è successo e come rimediare, in una frase. "Inserisci un numero, per esempio 850", non "Valore non valido".

## Token
`--grigna-field-height`, `-padding-x`, `-radius`, `-gap`, `-font`, `-label-font`, `-help-font`, `-bg`, `-border`, `-border-focus`, `-border-error`, `-text`, `-placeholder`, `-help-text`, `-error-text` (tutti con prefisso `--grigna-field`).

## Accessibilità
- `for` dell'etichetta uguale all'`id` del controllo.
- Aiuto ed errore collegati con `aria-describedby`.
- L'errore non si segnala solo con il bordo rosso: c'è sempre il testo.

---

## Per gli agenti

**Sempre**
- Struttura completa: `grigna-field` > `grigna-field__label` + `grigna-field__input` (+ `__help` o `__error`).
- `<label>` collegata, anche se lo spazio è poco.
- Errore con `aria-invalid="true"` e messaggio che dice come rimediare.

**Mai**
- Mai un campo senza etichetta visibile, mai il segnaposto al posto dell'etichetta.
- Mai segnalare l'errore solo con il colore.
- Mai inventare stati non previsti (successo verde, avviso giallo sul campo): se servono, si aggiungono al sistema.
