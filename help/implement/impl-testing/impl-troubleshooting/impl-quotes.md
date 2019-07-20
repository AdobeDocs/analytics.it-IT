---
description: Quando inserite valori in una variabile, vi sono alcune best practice da seguire.
keywords: Implementazione di Analytics
seo-description: Quando inserite valori in una variabile, vi sono alcune best practice da seguire.
seo-title: Uso delle virgolette
solution: Analytics
subtopic: 'Risoluzione dei problemi   '
title: Uso delle virgolette
topic: Sviluppatore e implementazione
uuid: 9 f 09 c 48 b -7 ae 5-441 e -8635-fd 6 bdc 2 e 94 c 7
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Uso delle virgolette

Quando inserite valori in una variabile, vi sono alcune best practice da seguire.

È possibile utilizzare virgolette singole o doppie. Se si utilizzano virgolette singole, utilizzare sempre le virgolette singole. Se utilizzate doppie virgolette, usate sempre doppie virgolette. Entrambi gli esempi di seguito sono corretti.

```js
s.prop2='test' (single quotes)
```

```js
s.prop2="test" (double quotes)
```

Accertatevi che le virgolette intelligenti siano disattivate. Se si utilizzano virgolette singole e si dispone di un apostrofo nel valore della variabile, javascript interpreta l'apostrofo come una singola virgoletta. Ciò significa che è la fine della stringa. Prendi in considerazione l'esempio seguente:

```js
s.pageName='John's Home Page'
```

In questo caso, javascript interpreta l'apostrofo (anch'esso una virgoletta singola) in "John" come fine della stringa. Poiché «S Home Page» non ha alcun significato in javascript, causa un errore che impedisce l'esecuzione della richiesta. Uno dei seguenti esempi funziona:

```js
s.pageName='John\'s Home Page'
```

```js
s.pageName="John's Home Page"
```

Nel primo esempio, potete uscire dall'apostrofo inserendo una barra rovesciata (\) immediatamente prima di essa. Questo indica a javascript che l'apostrofo non terminerà la stringa, ma fa parte di esso. La stringa termina quindi come previsto, alla singola virgoletta. Il secondo esempio utilizza due virgolette attorno all'intera stringa. In questo caso, una singola virgoletta non può indicare la fine della stringa. Lo stesso vale se una virgoletta fa parte della stringa. Un valore di s. pagename = "Team dice" We Win! " " sarebbe errato a causa dell'utilizzo di doppie virgolette all'interno della stringa e circostante. Questo sarebbe corretto se viene inserito come s. pagename = "Team dice\" We Win!\"".
