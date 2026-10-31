# Bottone

```html anteprima
<button class="grigna-button grigna-button--primary"><i data-lucide="plus" aria-hidden="true"></i>Nuova uscita</button>
<button class="grigna-button">Salva bozza</button>
<button class="grigna-button grigna-button--ghost">Annulla</button>
<button class="grigna-button grigna-button--sm">Piccolo</button>
<button class="grigna-button" disabled>Disattivato</button>
```

## Cos'è
Un elemento che avvia un'azione: salvare, inviare, aprire, annullare.

## Quando usarlo
- Per un'azione che cambia qualcosa o apre un passaggio successivo.

## Quando non usarlo
- Per andare a un'altra pagina: usa un link (`<a>`). Se deve *sembrare* un bottone, il link può avere le classi del bottone.
- Per attivare o disattivare un filtro: usa il [filtro](filtro.md).

## Codice

```html
<button class="grigna-button grigna-button--primary">Pubblica uscita</button>
<button class="grigna-button">Salva bozza</button>
<button class="grigna-button grigna-button--ghost">Annulla</button>
```

Con icona (Lucide, prima del testo):

```html
<button class="grigna-button grigna-button--primary">
  <i data-lucide="plus" aria-hidden="true"></i>Nuova uscita
</button>
```

Solo icona:

```html
<button class="grigna-button grigna-button--ghost" aria-label="Chiudi">
  <i data-lucide="x" aria-hidden="true"></i>
</button>
```

## Varianti e stati

| Classe | Uso |
| --- | --- |
| `grigna-button--primary` | L'azione principale della vista. **Al massimo una per vista** |
| *(nessuna)* | Secondario: la scelta di default per tutte le altre azioni |
| `grigna-button--ghost` | Azioni minori o di rinuncia: annulla, chiudi |
| `grigna-button--sm` | Più basso (36px). Solo in aree dense su desktop, mai come azione principale su mobile |

Stati: hover, focus da tastiera (anello Abete) e disattivato (`disabled` o `aria-disabled="true"`).

**Sul disattivato:** è meglio evitarlo. Un bottone grigio non spiega perché non funziona. Spesso è meglio lasciarlo attivo e mostrare un errore chiaro quando si clicca.

## Testi
- Verbo all'inizio, una-tre parole: "Salva bozza", "Pubblica uscita".
- Niente "OK", "Invia" generico o "Clicca qui".

## Token
`--grigna-button-height`, `-height-sm`, `-padding-x`, `-padding-x-sm`, `-gap`, `-radius`, `-font`, `-font-sm`, `-primary-bg`, `-primary-bg-hover`, `-primary-text`, `-secondary-bg`, `-secondary-bg-hover`, `-secondary-border`, `-secondary-text`, `-ghost-bg-hover`, `-ghost-text` (tutti con prefisso `--grigna-button`).

## Accessibilità
- Altezza minima 44px (36px solo per `--sm`).
- Usa sempre `<button>` per le azioni e `<a>` per la navigazione, mai un `<div>` cliccabile.
- Un bottone con sola icona ha sempre `aria-label`.

---

## Per gli agenti

**Sempre**
- `<button class="grigna-button">` più al massimo un modificatore di variante e uno di misura.
- Una sola `grigna-button--primary` per vista.
- Testo che comincia con un verbo.

**Mai**
- Mai stili personalizzati sul bottone (colori, bordi, ombre, padding).
- Mai due bottoni primari affiancati: il secondo diventa secondario.
- Mai `grigna-button--sm` per l'azione principale.
