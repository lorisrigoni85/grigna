# Accordion

```html anteprima
<div class="grigna-accordion" style="width: 100%">
  <details class="grigna-accordion__item" name="demo-grigna" open>
    <summary class="grigna-accordion__summary">Cos'è Grigna?</summary>
    <div class="grigna-accordion__content"><p>Un design system pensato per persone e agenti AI: token, componenti e linee guida scritte per due lettori.</p></div>
  </details>
  <details class="grigna-accordion__item" name="demo-grigna">
    <summary class="grigna-accordion__summary">Quali icone usa?</summary>
    <div class="grigna-accordion__content"><p>Lucide 1.57.0, una sola libreria per tutto il sistema.</p></div>
  </details>
  <details class="grigna-accordion__item" name="demo-grigna">
    <summary class="grigna-accordion__summary">Si può usare in altri progetti?</summary>
    <div class="grigna-accordion__content"><p>Per ora no: è un progetto personale e un caso studio.</p></div>
  </details>
</div>
```

## Cos'è
Una lista di sezioni con un titolo sempre visibile e un contenuto che si apre e si chiude cliccando sul titolo.

## Quando usarlo
- Domande frequenti, dettagli tecnici, informazioni secondarie che non devono occupare spazio.
- Quando chi legge cerca una sola risposta tra tante, e le altre possono restare chiuse.

## Quando non usarlo
- Per informazioni importanti che tutti devono leggere: nasconderle non le rende più semplici, le rende invisibili.
- Per passi in sequenza, come una procedura: lì serve una struttura che mostri l'ordine.
- Un accordion dentro un altro accordion: mai.
- Con una sola sezione: basta il testo, o un link "mostra di più".

## Codice

```html
<div class="grigna-accordion">
  <details class="grigna-accordion__item">
    <summary class="grigna-accordion__summary">Titolo della sezione</summary>
    <div class="grigna-accordion__content">
      <p>Contenuto della sezione.</p>
    </div>
  </details>
  <details class="grigna-accordion__item">
    <summary class="grigna-accordion__summary">Altra sezione</summary>
    <div class="grigna-accordion__content">
      <p>Altro contenuto.</p>
    </div>
  </details>
</div>
```

Non serve JavaScript: apertura e chiusura le gestisce il browser.

## Varianti e stati

| Come | Risultato |
| --- | --- |
| *(nessun attributo)* | Si possono aprire più sezioni insieme. È il comportamento di default |
| Stesso `name="…"` su tutti i `<details>` del gruppo | Una sola sezione aperta alla volta: aprendone una, le altre si chiudono |
| `open` su un `<details>` | Quella sezione è aperta quando la pagina si carica |
| Hover, focus | Superficie tenue al passaggio del mouse, anello Abete da tastiera |

La freccia a destra la disegna il CSS: punta in giù da chiuso e in su da aperto.

## Testi
- **Titolo**: dice cosa c'è dentro, in poche parole. Una domanda funziona bene per le FAQ ("Quali icone usa?").
- **Contenuto**: breve. Se un contenuto è lungo, forse merita una pagina sua.

## Token
`--grigna-accordion-bg`, `-bg-hover`, `-border`, `-icon`, `-text`, `-radius`, `-min-height`, `-padding-x`, `-padding-y`, `-gap`, `-summary-font`, `-content-font` (tutti con prefisso `--grigna-accordion`).

## Accessibilità
- `<details>` e `<summary>` sono nativi: tastiera (Invio e Spazio), stato "aperto/chiuso" letto dallo screen reader e ricerca nella pagina anche dentro le sezioni chiuse funzionano senza codice in più.
- Area cliccabile del titolo alta almeno 44px.
- Il titolo è testo semplice: niente link o bottoni dentro `<summary>`.

---

## Per gli agenti

**Sempre**
- Struttura completa: `grigna-accordion` > `details.grigna-accordion__item` > `summary.grigna-accordion__summary` + `div.grigna-accordion__content`.
- Per "una sola aperta alla volta" usa l'attributo `name`, uguale su tutto il gruppo.

**Mai**
- Mai ricostruire l'accordion con `<div>` e JavaScript: usa `<details>` e `<summary>`.
- Mai link, bottoni o altri controlli dentro `<summary>`.
- Mai accordion annidati, mai un accordion con una sola sezione.
- Mai nascondere in un accordion informazioni che tutti devono leggere.
