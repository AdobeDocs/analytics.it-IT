---
description: Disponibile in Analysis Workspace e nel Generatore di segmenti.
seo-description: Disponibile in Analysis Workspace e nel Generatore di segmenti.
seo-title: Visitatori con Experience Cloud ID
title: Visitatori con Experience Cloud ID
uuid: 47 ebd 3 d 6-a 921-4 e 51-ac 7 a-b 8 d 5 fb 9565 e 0
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# Visitatori con Experience Cloud ID

Disponibile in Analysis Workspace e nel Generatore di segmenti.

Mostra il numero di visitatori che hanno un Experience Cloud ID. Puoi capire a quali pagine è stato distribuito il servizio Identità e quanti visitatori possono essere condivisi con altre soluzioni Experience Cloud. Puoi anche utilizzare questa metrica nei segmenti condivisi in Experience Cloud.

>[!IMPORTANT]
>
>For this metric to appear, you have to have the [Identity Service](https://marketing.adobe.com/resources/help/en_US/mcvid/) running for the report suite.

## Debug your Experience Cloud ID Setup {#section_679E62142A3E46548FF8FBDA46568005}

The [!UICONTROL Visitors with Experience Cloud ID] metric is a useful metric in Adobe Analytics intended to help you find and debug your [!UICONTROL Identity Service]setup. La metrica è un numero del numero di visitatori in una suite di rapporti a cui è stato assegnato un Experience Cloud ID dal servizio identità. Questa metrica può essere utile per diagnosticare perché alcune integrazioni Experience Cloud possono non condividere il numero di visitatori previsto, oppure identificare le aree del sito che potrebbero non avere ancora distribuito MCID.

To use the Visitors with Experience Cloud ID metric, simply drag it in to any report as a metric, such as this [!UICONTROL Pages] report:

![](assets/metric-mcvid1.png)

In questo esempio, notare che ogni pagina ha lo stesso numero di Visitatori unici di Visitatori con un Experience Cloud ID. Tuttavia, il numero totale di Visitatori unici è maggiore del numero totale di visitatori con Experience Cloud ID. To find the pages that are not setting the MCID for all visitors, [create a calculated metric](https://marketing.adobe.com/resources/help/en_US/analytics/calcmetrics/cm_build_metrics.html) with this definition:

![](assets/metric-mcvid2.png)

Aggiungendo la metrica calcolata al rapporto, puoi ordinare il rapporto Pagine in modo che le pagine con il numero più elevato di visitatori senza MCID vengano ignorate:

![](assets/metric-mcvid3.png)

Ora puoi vedere rapidamente che le pagine «Visualizzazioni rapide prodotto» non sono correttamente implementate con il servizio Identità e devono essere aggiornate al più presto. Un rapporto simile può essere costruito su qualsiasi tipo di dimensione, ad esempio tipo di browser, sezione del sito o tipo di contenuto.

Dopo aver identificato le pagine che hanno visitatori senza MCID, dovreste essere in grado di reindirizzarla al team di implementazione in modo che possano correggerle.

In alcuni casi, è possibile che un numero limitato di MCID non venga impostato per alcuni visitatori, anche se il servizio MCID è stato implementato sulla pagina. In questi casi, ciò è probabilmente dovuto a una configurazione errata della configurazione javascript o DTM di Analytics in cui la funzione appmeasurement viene chiamata prima di fornire una suite di rapporti. To avoid this, make sure you [insert core AppMeasurement code](https://marketing.adobe.com/resources/help/en_US/sc/implement/dtm/t_appmeasurement-code.html) properly.

Tieni presente che qualsiasi segmento basato sulla pagina «Visualizzazioni rapide prodotto» (come mostrato sopra) condiviso con Experience Cloud avrà probabilmente una frequenza di corrispondenza molto bassa con altre soluzioni Experience Cloud. Per controllare la copertura MCID di qualsiasi segmento, puoi creare un rapporto come questo:

![](assets/metric-mcvid4.png)

Da questa tabella, che confronta il numero di Visitatori unici ai visitatori con un Experience Cloud ID, è facile vedere che «Segmento 1» non ha copertura MCID 100%, mentre «Segmento 2». Ciò significa che se condividessi Segmento 1 con Experience Cloud, solo il 2,186 dei 3,859 visitatori totali sarebbero idonei per la condivisione.
