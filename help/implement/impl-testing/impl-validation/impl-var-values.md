---
description: Accertarsi che le variabili compilate dagli script o dal codice del server non restituiscano virgolette che interferiscano con i valori.
keywords: Implementazione di Analytics
seo-description: Accertarsi che le variabili compilate dagli script o dal codice del server non restituiscano virgolette che interferiscano con i valori.
seo-title: Variabili e valori
solution: Analytics
title: Variabili e valori
topic: Sviluppatore e implementazione
uuid: 2ff4857a-9451-4794-9146-f417abd1d1ba
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Variabili e valori

Accertarsi che le variabili compilate dagli script o dal codice del server non restituiscano virgolette che interferiscano con i valori.

Ad esempio:

```js
s.pageName="Article: "Article Name"" 
s.pageName='Company's Information' 
```

Assicurarsi che i valori delle variabili non superino i limiti massimi specificati in questo documento. I caratteri aggiuntivi vengono ritagliati sui server di raccolta dati. Possono interferire con la lunghezza totale, aumentare la larghezza di banda inutilmente e possono causare altri problemi.

Non utilizzare $, ™, ®, © o virgole (,) nella variabile products. In genere, non sono utili per nessuna [!DNL Analytics] variabile e possono interferire con la capacità di interpretare o esportare i campi. È consigliabile limitare i caratteri ai primi 127 caratteri ASCII.

Assicurarsi che la variabile eventi sia compilata con un valore appropriato ( [!UICONTROL prodView], [!UICONTROL purchase], [!UICONTROL scAdd], [!UICONTROL scRemove], o event1-event5) ogni volta che [!UICONTROL scOpen]*`products`* viene compilata. Assicurarsi che il caso di tutte [!DNL Analytics] le variabili e funzioni sia mantenuto, come illustrato di seguito.

```js
s.pageName 
s.server 
s.channel 
s.pageType 
s.prop1 - s.prop20 
s.campaign 
s.state 
s.zip 
s.events 
s.products 
s.purchaseID 
s.eVar1 - s.eVar20 
var s_code=s.t();if(s_code)document.write(s_code)//--> 
```

I nomi delle pagine sono con distinzione tra maiuscole e minuscole e le differenze creano record di pagina aggiuntivi. "Home" e "home" sono due diverse pagine all'interno [!DNL Analytics].

> [!NOTE] Non è possibile combinare più record di pagina all'interno dei report.

Convalidare che i collegamenti siano segnalati nel [!UICONTROL Custom Links] rapporto. Assicurarsi che i parametri corretti siano passati alla [!UICONTROL tl] funzione. Per ulteriori informazioni su [!UICONTROL custom links], consulta [Tracciamento](../../../implement/js-implementation/function-tl.md#concept_EA13689CB8EE4F308FC89A1293046D5E)collegamenti.
