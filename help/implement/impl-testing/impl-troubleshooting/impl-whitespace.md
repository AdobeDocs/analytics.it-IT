---
description: In HTML ci sono diversi caratteri che creano spazi bianchi.
keywords: Implementazione di Analytics
seo-description: In HTML ci sono diversi caratteri che creano spazi bianchi.
seo-title: Utilizzo dello spazio vuoto nei valori delle variabili
solution: Analytics
subtopic: Risoluzione dei problemi
title: Utilizzo dello spazio vuoto nei valori delle variabili
topic: Sviluppatore e implementazione
uuid: 1edd7934-9b3e-43e2-9f24-65f42cb306e2
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Utilizzo dello spazio vuoto nei valori delle variabili

In HTML ci sono diversi caratteri che creano spazi bianchi.

Questi includono uno spazio, una scheda e un ritorno a capo (o avanzamento linea). Prendi in considerazione l'esempio seguente:

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

In questo caso document.title viene compilato [!UICONTROL s.pageName], che deve ricevere il valore "Home Page". Osservate lo spazio prima di "Home Page". Non tutti i browser interpretano questo spazio vuoto allo stesso modo. Il risultato può essere uno dei due esempi seguenti:

```js
s.pageName="Home Page"
```

```js
s.pageName="        Home Page"
```

Il primo valore viene visualizzato correttamente, mentre il secondo visualizza lo spazio vuoto prima del testo. [!DNL Analytics] li gestisce come valori distinti per la [!UICONTROL s.pageName] variabile. L' [!DNL Analytics] interfaccia elimina lo spazio vuoto iniziale dal secondo valore. Il risultato è un report che viene visualizzato come mostrato di seguito.

![](assets/white_space.jpg)

Questo errore di implementazione causa la frammentazione dei valori variabili tra più elementi riga. [!DNL SAINT] non consente lo spazio vuoto iniziale in un valore chiave. Questo significa che non può essere utilizzato per raggruppare più elementi di riga come soluzione alternativa se questo problema interessa il sito. L'unico modo per risolvere il problema è preelaborare il valore della variabile desiderata (in questo caso, la proprietà document.title) per rimuovere qualsiasi spazio vuoto iniziale (o finale).

Nell'esempio precedente viene utilizzata la [!UICONTROL s.pageName] variabile con la proprietà document.title. Adobe non consiglia di utilizzare document.title come nome della pagina, né questo problema interessa solo la [!UICONTROL s.pageName] variabile. È possibile modificare qualsiasi variabile con spazio vuoto iniziale/finale nel relativo valore.
