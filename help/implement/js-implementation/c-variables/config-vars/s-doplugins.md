---
description: Le variabili dinamiche consentono di copiare i valori da una variabile all’altra senza digitare più volte i valori completi nelle richieste di immagini sul sito.
keywords: Implementazione di Analytics
seo-description: Le variabili dinamiche consentono di copiare i valori da una variabile all’altra senza digitare più volte i valori completi nelle richieste di immagini sul sito.
solution: null
title: Variabili dinamiche
translation-type: tm+mt
source-git-commit: 60dd1b300035e5149f53870239de85fb3174a77a

---



# s.doPlugins

La variabile è un riferimento alla funzione e consente di richiamare la funzione nella posizione appropriata all'interno del file JavaScript.

La *`s_doPlugins`* funzione viene chiamata ogni volta che si verifica una delle seguenti situazioni:

* La *`t()`* funzione viene chiamata
* La *`tl()`* funzione viene chiamata
* Fate clic su un collegamento di uscita o di download
* Viene fatto clic su qualsiasi elemento di pagina tracciato dalla mappa clic del visitatore

La *`doPlugins`* funzione viene utilizzata per eseguire routine personalizzate per raccogliere o modificare i dati. Se utilizzate un nome di oggetto diverso da "s", accertatevi che l'oggetto *`s_doPlugins`* sia rinominato in modo appropriato. Ad esempio, se il nome dell'oggetto è s_mc, la *`s_doPlugins`* funzione deve essere denominata s_mc_doPlugins.

## Sintassi e valori possibili

La *`s_doPlugins`* funzione non deve essere racchiusa tra virgolette e *`doPlugins`* deve essere sempre assegnata al nome esatto della *`s_doPlugins`* funzione (se la funzione viene rinominata).

```js
s.doPlugins=s_doPlugins;
```

## Esempi

```js
s.doPlugins=s_doPlugins;
```

```js
s_mc.doPlugins=s_mc_doPlugins;
```

## Impostazioni di configurazione

Nessuno

## Insidie, domande e suggerimenti

* L'unico motivo per cambiare il nome dell'oggetto (ad esempio da s a s_mc) è se condividete contenuto con altri clienti o estraete contenuto da essi. Se si rinomina la *`s_doPlugins`* funzione per [!UICONTROL s_mc_doPlugins] assicurare che il file JavaScript di un altro client non sovrascriva la *`doPlugins`* funzione,

* Se iniziate inaspettatamente a richiamare contenuti da un altro cliente Adobe e la vostra *`s_doPlugins`* funzione viene sovrascritta, è possibile rinominare semplicemente la *`s_doPlugins`* funzione senza modificare il nome dell'oggetto. La soluzione migliore è utilizzare un nome oggetto diverso rispetto ad altri file JavaScript sulla stessa pagina, ma non è necessario farlo.