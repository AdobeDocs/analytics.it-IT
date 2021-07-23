---
title: Lingua
description: L’impostazione della lingua preferita nel browser.
exl-id: 590406a4-d336-42c7-8048-e7cd8e611d43
source-git-commit: e6f3beadfba340cea07f5fd2694105ad31de9751
workflow-type: tm+mt
source-wordcount: '158'
ht-degree: 1%

---

# Lingua

La dimensione &quot;Lingua&quot; mostra le lingue principali in cui i visitatori preferiscono visualizzare il contenuto. Questa dimensione è utile quando desideri comprendere le lingue preferite più frequenti dei visitatori per facilitarne le attività di localizzazione.

>[!NOTE]
>
>Questa dimensione non raccoglie la lingua del sito. Se desideri raccogliere la lingua del sito in una dimensione, Adobe consiglia di utilizzare una variabile personalizzata, ad esempio un [eVar](evar.md).

## Popolare questa dimensione con i dati

Questa dimensione fa riferimento a una tabella di ricerca interna all’Adobe. Il valore di ricerca si basa sull’intestazione HTTP `Accept-Language` nelle richieste di immagini. Se utilizzi una libreria AppMeasurement (ad esempio tramite tag in Adobe Experience Platform), questa dimensione funziona automaticamente.

## Elementi Dimension

Gli elementi di Dimension includono nomi descrittivi delle lingue preferite dei visitatori. Gli esempi includono `"English (United States)"`, `"English (United Kingom)"`, `"Chinese (China)"` e `"Spanish (Spain)"`. Se una richiesta di immagine non contiene una lingua valida nell’intestazione HTTP, l’elemento dimensione è `"None"`.
