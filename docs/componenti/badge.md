# Badge

```html anteprima
<span class="grigna-badge">Neutro</span>
<span class="grigna-badge grigna-badge--accent">Accento</span>
<span class="grigna-badge grigna-badge--success"><i data-lucide="check" aria-hidden="true"></i>Pubblicata</span>
<span class="grigna-badge grigna-badge--warning"><i data-lucide="alert-triangle" aria-hidden="true"></i>Da verificare</span>
<span class="grigna-badge grigna-badge--danger"><i data-lucide="x" aria-hidden="true"></i>Rifiutata</span>
<span class="grigna-badge grigna-badge--info"><i data-lucide="info" aria-hidden="true"></i>Novità</span>
```

## Cos'è
Un'etichetta piccola, che non si clicca, per indicare uno stato o una caratteristica.

## Quando usarlo
- Per uno stato: "Pubblicata", "Da verificare", "Novità".
- Per una caratteristica breve accanto a un titolo.

## Quando non usarlo
- Se si deve cliccare: usa il [filtro](filtro.md) o un [bottone](bottone.md).
- Per uno stato che un livello brand ha già definito con un suo componente: usa quello.
- Per frasi: un badge sta in una-tre parole.

## Codice

```html
<span class="grigna-badge">Bozza</span>
<span class="grigna-badge grigna-badge--success">
  <i data-lucide="check" aria-hidden="true"></i>Pubblicata
</span>
```

## Varianti

| Classe | Uso |
| --- | --- |
| *(nessuna)* | Neutro: caratteristiche senza giudizio |
| `grigna-badge--accent` | Evidenza legata al brand, con parsimonia |
| `grigna-badge--success` | Esito positivo, completato |
| `grigna-badge--warning` | Richiede attenzione |
| `grigna-badge--danger` | Errore, rifiutato, bloccato |
| `grigna-badge--info` | Informazione, novità |

## Token
`--grigna-badge-height`, `-padding-x`, `-gap`, `-radius`, `-font`, più `-{variante}-bg` e `-{variante}-text` per ogni variante, e `-neutral-border` (tutti con prefisso `--grigna-badge`).

## Accessibilità
- Il testo dice lo stato: il colore lo rinforza ma non lo sostituisce.
- Le icone nel badge sono decorative (`aria-hidden="true"`).

---

## Per gli agenti

**Sempre**
- `<span class="grigna-badge">` con al massimo un modificatore di variante.
- Testo di una-tre parole che dice lo stato.

**Mai**
- Mai un badge cliccabile.
- Mai un badge solo colorato, senza testo.
- Mai usare i badge di feedback al posto dei componenti di stato di un livello brand.
