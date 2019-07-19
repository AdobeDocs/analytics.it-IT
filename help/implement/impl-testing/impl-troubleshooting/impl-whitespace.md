---
description: In HTML sono disponibili diversi caratteri per creare spazi bianchi.
keywords: Implementazione di Analytics
seo-description: In HTML sono disponibili diversi caratteri per creare spazi bianchi.
seo-title: Utilizzo dello spazio vuoto nei valori delle variabili
solution: Analytics
subtopic: 'Risoluzione dei problemi   '
title: Utilizzo dello spazio vuoto nei valori delle variabili
topic: Sviluppatore e implementazione
uuid: 1 edd 7934-9 b 3 e -43 e 2-9 f 24-65 f 42 cb 306 e 2
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Utilizzo dello spazio vuoto nei valori delle variabili

In HTML sono disponibili diversi caratteri per creare spazi bianchi.

Includono uno spazio, una scheda e un ritorno a capo (o linefeed). Prendi in considerazione l'esempio seguente:

```js
<head> 
 <title> 
   Home Page 
 </title> 
</head> 
<body> 
<script language="javascript"> 
 s.pageName=document.title 
</script> 
```

In this case, document.title populates [!UICONTROL s.pageName], which should receive a value of "Home Page." Osservate lo spazio prima di «Home Page». Non tutti i browser interpretano lo spazio bianco allo stesso modo. Il risultato può essere costituito da due esempi:

```js
s.pageName="Home Page"
```

```js
s.pageName="        Home Page"
```

Il primo valore viene visualizzato correttamente, ma il secondo mostra lo spazio bianco prima del testo. [!DNL Analytics] considera questi valori distinti per la [!UICONTROL s.pageName] variabile. [!DNL Analytics] L'interfaccia rimuove lo spazio bianco iniziale dal secondo valore. Il risultato è un rapporto visualizzato come mostrato di seguito.

![](assets/white_space.jpg)

Questo errore di implementazione causa la frammentazione dei valori delle variabili su più elementi. [!DNL SAINT] non consente lo spazio vuoto iniziale in un valore chiave. Ciò significa che non può essere utilizzato per raggruppare più elementi di righe come soluzione alternativa se questo problema riguarda il sito. L'unico modo per risolvere il problema consiste nell'eseguire il pre-elaborazione del valore della variabile desiderato (in questo caso, la proprietà document. title) per rimuovere qualsiasi spazio vuoto iniziale (o finale).

The example above uses the [!UICONTROL s.pageName] variable with the document.title property. Adobe does not recommend using document.title as the page name, nor does this issue only affect the [!UICONTROL s.pageName] variable. Qualsiasi variabile con spazi vuoti iniziali/finali nel relativo valore può essere modificata.
