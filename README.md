# Appunti di Algoritmi e Complessità

## Compilazione

Dalla cartella del progetto:

```powershell
latexmk -pdf main.tex
```

Per eliminare soltanto i file generati dalla compilazione:

```powershell
latexmk -c
```

## Struttura

```text
main.tex
config/
  pacchetti.tex
  comandi.tex
  listings.tex
  metadati.tex
capitoli/
  01-introduzione.tex
  02-analisi-di-algoritmi.tex
  analisi-di-algoritmi/
    load-balancing.tex
```

- `main.tex` stabilisce l'ordine dei capitoli.
- `config/pacchetti.tex` contiene esclusivamente i pacchetti e le librerie.
- `config/comandi.tex` raccoglie comandi e ambienti riutilizzabili.
- `config/listings.tex` definisce l'aspetto del codice e dello pseudocodice.
- `config/metadati.tex` contiene titolo, autore e anno accademico.
- `capitoli/` contiene la struttura del corso e i singoli argomenti.

## Aggiungere un capitolo

1. Creare, per esempio, `capitoli/03-complessita.tex`.
2. Inserire il contenuto iniziando con `\section{Complessità}`.
3. Aggiungere in `main.tex`:

   ```latex
   \input{capitoli/03-complessita}
   ```

Se un capitolo diventa lungo, creare una sottocartella e lasciare nel file del
capitolo soltanto la sezione e gli `\input` dei singoli argomenti, come già
fatto per `Analisi di algoritmi`.

## Convenzioni

- Nomi dei file in minuscolo, con parole separate da trattini.
- Numerare i file dei capitoli per mantenere evidente il loro ordine.
- Mettere nel preambolo soltanto definizioni usate in più punti.
- Usare gli ambienti `teorema`, `dimostrazione` e `paragrafo` per la struttura
  principale.
- Dentro le dimostrazioni usare `\osservazione`, `giustificazione`, `rientro`,
  `\corollario`, `nota` e `\fonte`, evitando `\hspace` e `\vspace` nei capitoli.
- Per gli incisi autonomi usare `digressione`, così titolo e rientro restano
  coerenti in tutto il documento.
- Usare etichette descrittive senza spazi, per esempio `alg:offline-greedy`.
