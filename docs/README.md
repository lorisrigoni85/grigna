# Linee guida di Grigna

Queste pagine spiegano come usare Grigna. Sono scritte per due lettori:

- **Persone** (designer, sviluppatori): trovate il perché delle scelte, quando usare un elemento e quando no, esempi giusti e sbagliati.
- **Agenti AI**: ogni pagina chiude con una sezione **Per gli agenti**, con regole brevi e verificabili, nomi esatti di classi e token e cosa non inventare mai.

Le regole generali per gli agenti stanno in [`AGENTS.md`](../AGENTS.md), nella radice del progetto.

## Indice

**Principi**
- [Principi](principi.md): le idee da cui discende tutto il resto

**Fondamenti**
- [Colore](fondamenta/colore.md)
- [Tipografia](fondamenta/tipografia.md)
- [Spazi, raggi ed elevazione](fondamenta/spazi-e-forme.md)
- [Icone](fondamenta/icone.md)

**Componenti generici**
- [Bottone](componenti/bottone.md)
- [Campo](componenti/campo.md)
- [Scheda](componenti/scheda.md)
- [Badge](componenti/badge.md)
- [Filtro](componenti/filtro.md)
- [Accordion](componenti/accordion.md)
- [Segnaposto](componenti/segnaposto.md)

**Livelli brand**

Un progetto che usa Grigna può aggiungere un proprio livello: token, componenti e linee guida suoi, con un prefisso suo. Il livello si aggiunge a Grigna e non lo cambia. Le sue docs stanno in `docs/<nome del livello>/`.

## Come sono fatte le pagine dei componenti

Tutte hanno le stesse sezioni, nello stesso ordine, così si trovano le cose senza cercarle:

1. **Esempio dal vivo**: il componente com'è davvero, subito sotto il titolo. Nel Markdown è un blocco `html anteprima`.
2. **Cos'è**: una frase.
3. **Quando usarlo / Quando non usarlo**
4. **Codice**: HTML da copiare.
5. **Varianti e stati**
6. **Token**: i token del componente.
7. **Accessibilità**
8. **Per gli agenti**: regole *Sempre* e *Mai*.

## Dove vedere tutto

```bash
node scripts/serve.mjs
```

Poi apri `http://127.0.0.1:4173/preview/` (token) e `http://127.0.0.1:4173/preview/components.html` (componenti).
