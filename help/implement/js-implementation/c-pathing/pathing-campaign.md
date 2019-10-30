---
description: Consente di rispondere alla domanda "Dopo che un utente fa clic sul mio sito da una campagna, dove si trova sul sito?"
keywords: Implementazione di Analytics
seo-description: Consente di rispondere alla domanda "Dopo che un utente fa clic sul mio sito da una campagna, dove si trova sul sito?"
seo-title: Percorsi per campagna o codice di tracciamento
solution: Analytics
title: Percorsi per campagna o codice di tracciamento
topic: Sviluppatore e implementazione
uuid: eb6e3484-1b40-4ec6-8017-ac1003cdf636
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Percorsi per campagna o codice di tracciamento

Consente di rispondere alla domanda "Dopo che un utente fa clic sul mio sito da una campagna, dove si trova sul sito?"

Per rispondere a questa domanda, è necessario mettere da parte un [!UICONTROL sprop] da utilizzare per questo rapporto. È quindi necessario strutturare i dati per popolare il prop in modo che abbia senso quando il percorso è abilitato.

Per questo esempio, utilizzerete [!UICONTROL prop1] come proprietà di percorso della campagna. Ora si desidera compilare questo [!UICONTROL sprop] con lo stesso valore immesso nella [!UICONTROL page name] variabile. Vedere di seguito:

```js
s.prop1=s.pageName;
```

A meno che la persona non abbia fatto clic su una campagna, è necessario eseguire questa operazione su tutte le pagine. Se l’utente ha fatto clic su una campagna e si trova sulla pagina di destinazione della campagna, il prop viene compilato con una concatenazione della campagna e del [!UICONTROL pagename]. Vedere di seguito:

```js
 s.prop1=s.campaign + ' : ' + s.pageName;
```

Se la campagna su cui hanno fatto clic era denominata "banner1234" e la pagina su cui è atterrata era denominata "Home Page", il valore in quella proprietà sarebbe "banner1234: Home Page." In ogni pagina successiva viene inserito il [!UICONTROL pagename] prop come mostrato sopra.

Quando un utente fa clic su questa campagna e visualizza quattro pagine totali della visita, vengono visualizzati i seguenti valori nell’elenco a discesa nell’ordine seguente:

```js
"banner1234 : Home Page" > "Page 2" > "Page 3" > "Page 4"
```

Con i nostri dati acquisiti in [!UICONTROL prop1] questo modo, con percorsi abilitati su questa proprietà, ora puoi guardare uno dei vari report di percorsi per capire come si muovono nel sito dopo aver fatto clic da una campagna.

È possibile specificare la pagina iniziale dalla quale avviare il rapporto sul percorso. In questo caso, avete selezionato "banner1234: Home Page", perché si desidera sapere dove sono finiti gli utenti dopo aver fatto clic sulla campagna "banner 1234". Questo rapporto è solo un esempio di uno dei molti rapporti sui percorsi.
