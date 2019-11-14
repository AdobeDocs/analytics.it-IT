---
description: Quando si inseriscono valori in una variabile, è possibile seguire alcune best practice.
keywords: Analytics Implementation
solution: Analytics
subtopic: Troubleshooting
title: Utilizzo delle virgolette
topic: Developer and implementation
uuid: 9f09c48b-7ae5-441e-8635-fd6bdc2e94c7
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Utilizzo delle virgolette

Quando si inseriscono valori in una variabile, è possibile seguire alcune best practice.

Potete usare virgolette singole o doppie, assicurarvi di essere coerenti. Se utilizzate virgolette singole, utilizzate sempre virgolette singole. Se utilizzate virgolette doppie, utilizzate sempre le virgolette doppie. Entrambi gli esempi riportati di seguito sono corretti.

```js
s.prop2='test' (single quotes)
```

```js
s.prop2="test" (double quotes)
```

Accertatevi che le virgolette intelligenti siano disattivate. Se usate virgolette singole e disponete di un apostrofo nel valore della variabile, JavaScript interpreta l’apostrofo come virgolette singole. Ciò significa che è la fine della stringa. Prendi in considerazione l'esempio seguente:

```js
s.pageName='John's Home Page'
```

In questo caso, JavaScript interpreterebbe l'apostrofo (che è anche una citazione singola) in "John's" come la fine della stringa. Poiché la Home Page di ''s non ha alcun significato in JavaScript, causa un errore che impedisce il verificarsi della richiesta di immagine. Uno dei seguenti esempi funzionerebbe:

```js
s.pageName='John\'s Home Page'
```

```js
s.pageName="John's Home Page"
```

Nel primo esempio, potete evitare l'apostrofo inserendo una barra rovesciata (\) immediatamente prima. Questo indica a JavaScript che l'apostrofo non sta terminando la stringa, ma piuttosto ne fa parte. La stringa termina come previsto, alla chiusura della quotazione singola. Nel secondo esempio vengono utilizzate virgolette doppie intorno all'intera stringa. In questo caso, una citazione singola non può indicare la fine della stringa. Lo stesso vale se una doppia citazione fa parte della stringa. Un valore di s.pageName="Team dice "We Win!" non è corretto a causa dell'uso di virgolette doppie all'interno della stringa, oltre che per il suo contorno. Questo sarebbe corretto se fosse immesso come s.pageName="Team dice \"Abbiamo vinto!\"".
