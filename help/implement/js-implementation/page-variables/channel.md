---
description: Le variabili di pagina popolano direttamente un report, ad esempio pageName, List Props, List Variables e così via.
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: Variabili di pagina
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: ea6109f2f9aa421001fde6d7bec65b82beda883c

---


# channel

La variabile viene utilizzata più spesso per identificare una sezione del sito.

<!-- 

channel.xml

 -->

Ad esempio, un esercente può avere sezioni quali Elettronica, Giocattoli o Abbigliamento. Un sito multimediale può contenere sezioni quali News, Sport o Business.

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| 100 byte | CH | Contenuto del sito &gt; Sezioni del sito | "" |

Adobe consiglia di compilare la variabile del canale su ogni pagina. È inoltre possibile attivare una correlazione tra le *`channel`* variabili e le [!UICONTROL page name] variabili.

Se le sezioni hanno uno o più livelli di sottosezioni, è possibile mostrare tali sezioni nella *`channel`* variabile o utilizzare variabili separate per identificare i livelli.

**Sintassi e valori possibili**

```js
s.channel="value"
```

La *`channel`* variabile non presenta ulteriori limitazioni ai suoi valori.

**Esempi** {#section_2527B2BB1CFD46CB952178ABF7A9028A}

```js
s.channel="Electronics"
```

```js
s.channel="Media"
```

**Insidie, domande e suggerimenti**{#section_61941D5E4E644B59A267A4F44FD5DE8C}

Se il sito contiene più livelli, potete utilizzare la *`hierarchy`* o un'altra variabile per definirli. Il *`channel`* valore non persiste, ma gli eventi di successo attivati sulla stessa pagina sono attribuiti al *`channel`* valore.
