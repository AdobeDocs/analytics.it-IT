---
description: Assicurarsi che le variabili compilate da script o codice sul server non possano restituire virgolette che interferiscano con i valori.
keywords: Implementazione di Analytics
seo-description: Assicurarsi che le variabili compilate da script o codice sul server non possano restituire virgolette che interferiscano con i valori.
seo-title: Variabili e valori
solution: Analytics
title: Variabili e valori
topic: Sviluppatore e implementazione
uuid: 2 ff 4857 a -9451-4794-9146-f 417 abd 1 d 1 ba
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Variabili e valori

Assicurarsi che le variabili compilate da script o codice sul server non possano restituire virgolette che interferiscano con i valori.

Ad esempio:

```js
s.pageName="Article: "Article Name"" 
s.pageName='Company's Information' 
```

Assicurarsi che i valori delle variabili non superino i limiti massimi specificati in questo documento. Sui server di raccolta dati vengono ritagliati altri caratteri. Possono interferire con la lunghezza totale, aumentare inutilmente la larghezza di banda e causare altri problemi.

Non utilizzare $, ™, ®, © o virgole (,) nella variabile products. Generally, these are not useful in any [!DNL Analytics] variables and may interfere with the ability to interpret or export fields. La procedura ottimale prevede di limitare i caratteri ai primi 127 caratteri ASCII.

Ensure that the events variable is populated with an appropriate value ( [!UICONTROL prodView], [!UICONTROL purchase], [!UICONTROL scAdd], [!UICONTROL scRemove], [!UICONTROL scOpen], or event1-event5) whenever *`products`* is populated. Ensure that the case of all [!DNL Analytics] variables and functions are maintained, as shown below.

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

I nomi delle pagine sono con distinzione tra maiuscole e minuscole e le differenze creano record di pagina aggiuntivi. "Home" and "home" are two different pages within [!DNL Analytics].

>[!NOTE]
>
>I record di pagina multipli non possono essere combinati all'interno dei rapporti.

Validate that links are reported in the [!UICONTROL Custom Links] report. Ensure that the correct parameters are passed to the [!UICONTROL tl] function. For more information on [!UICONTROL custom links], see [Link Tracking](../../../implement/js-implementation/function-tl.md#concept_EA13689CB8EE4F308FC89A1293046D5E).
