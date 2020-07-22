---
title: Lingua
description: Impostazione della lingua preferita nel browser.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 1%

---


# Lingua

La dimensione &quot;Lingua&quot; mostra le lingue principali in cui i visitatori preferiscono visualizzare il contenuto. Questa dimensione è preziosa per comprendere le lingue preferite più frequenti dai visitatori per facilitare gli sforzi di localizzazione.

>[!NOTE]
>
>Questa dimensione non raccoglie la lingua del sito. Se desiderate raccogliere la lingua del sito in una dimensione, Adobe consiglia di utilizzare una variabile personalizzata, ad esempio una [eVar](evar.md).

## Compilare questa dimensione con i dati

Questa dimensione fa riferimento a una tabella di ricerca interna ad Adobe. Il valore di ricerca è basato sull’intestazione `Accept-Language` HTTP nelle richieste di immagini. Se utilizzi una libreria AppMeasurement (ad esempio tramite  lancio del Adobe Experience Platform), questa dimensione non è disponibile.

## Elementi dimensione

Gli elementi dimensione includono nomi descrittivi delle lingue preferite dei visitatori. Alcuni esempi includono `"English (United States)"`, `"English (United Kingom)"`, `"Chinese (China)"`e `"Spanish (Spain)"`. Se una richiesta di immagine non contiene una lingua valida nell’intestazione HTTP, l’elemento dimensione è `"None"`.
