---
title: Lingua
description: Impostazione della lingua preferita nel browser.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
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

## Valori dimensione

I valori delle dimensioni includono nomi descrittivi delle lingue preferite dai visitatori. Alcuni esempi includono `"English (United States)"`, `"English (United Kingom)"`, `"Chinese (China)"`e `"Spanish (Spain)"`. Se una richiesta di immagine non contiene una lingua valida nell’intestazione HTTP, il valore della dimensione è `"None"`.
