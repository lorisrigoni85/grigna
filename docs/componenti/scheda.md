# Scheda

```html anteprima
<div class="demo-grid">
<article class="grigna-card">
  <div class="grigna-card__body">
    <strong>Scheda semplice</strong>
    <span class="demo-label">Testo di prova dentro una scheda.</span>
  </div>
</article>
<article class="grigna-card grigna-card--interactive">
  <div class="grigna-card__media"></div>
  <div class="grigna-card__body">
    <a class="grigna-card__link" href="#"><strong>Scheda cliccabile</strong></a>
    <span class="demo-label">Passa sopra col mouse.</span>
  </div>
</article>
</div>
```

## Cos'è
Un contenitore elevato che raggruppa le informazioni su un solo oggetto: una gita, un rifugio, un articolo.

## Quando usarla
- Per elementi di una lista o di una griglia, tutti dello stesso tipo, che si possono aprire.
- Per isolare un blocco di contenuto dalla pagina.

## Quando non usarla
- Per liste dense di righe (impostazioni, risultati testuali): bastano righe separate da un bordo.
- Una scheda dentro un'altra scheda: mai.

## Codice

```html
<article class="grigna-card">
  <div class="grigna-card__media"><img src="…" alt="Descrizione della foto"></div>
  <div class="grigna-card__body">…</div>
</article>
```

Scheda cliccabile su tutta la superficie:

```html
<article class="grigna-card grigna-card--interactive">
  <div class="grigna-card__media"><img src="…" alt="…"></div>
  <div class="grigna-card__body">
    <h3><a class="grigna-card__link" href="/gite/…">Titolo</a></h3>
    …
  </div>
</article>
```

C'è **un solo link**, sul titolo. La classe `grigna-card__link` lo estende a tutta la scheda, così chi usa uno screen reader sente un link con un nome chiaro e non "link, link, link".

## Varianti e stati

| Classe | Uso |
| --- | --- |
| `grigna-card` | Scheda semplice |
| `grigna-card--interactive` | Cliccabile: l'ombra cresce al passaggio del mouse, focus su tutta la scheda |
| `grigna-card__media` | Area immagine 16:9 in alto. Senza immagine mostra la superficie tenue |
| `grigna-card__body` | Contenuto, con margine interno e spazio tra le righe |

## Token
`--grigna-card-bg`, `-border`, `-radius`, `-padding`, `-gap`, `-shadow`, `-shadow-hover` (tutti con prefisso `--grigna-card`).

## Accessibilità
- Ogni immagine ha un `alt` che descrive la foto. Se è solo decorativa, `alt=""`.
- Nella scheda cliccabile non vanno altri link o bottoni, perché sarebbero coperti dal link principale.

---

## Per gli agenti

**Sempre**
- `<article class="grigna-card">` per un oggetto, con `__media` e `__body`.
- Se è cliccabile: `--interactive` e **un solo** `grigna-card__link` sul titolo.

**Mai**
- Mai schede annidate.
- Mai più link o bottoni dentro una scheda `--interactive`.
- Mai cambiare ombra, raggio o bordo della scheda: se serve una variante, si aggiunge al sistema.
