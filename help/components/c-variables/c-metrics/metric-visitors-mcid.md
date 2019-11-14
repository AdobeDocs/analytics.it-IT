---
description: Disponibile in Analysis Workspace e nel Generatore di segmenti.
title: Visitatori con Experience Cloud ID
uuid: 47ebd3d6-a921-4e51-ac7a-b8d5fb9565e0
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Visitatori con Experience Cloud ID

Disponibile in Analysis Workspace e nel Generatore di segmenti.

Mostra il numero di visitatori con un Experience Cloud ID. Puoi capire su quali pagine è stato implementato il servizio identità e quanti visitatori possono essere condivisi con altre soluzioni Experience Cloud. Puoi anche usare questa metrica nei segmenti condivisi con Experience Cloud.

>[!IMPORTANT]
>
>Affinché questa metrica venga visualizzata, è necessario che il servizio [](https://marketing.adobe.com/resources/help/en_US/mcvid/) identità sia in esecuzione per la suite di rapporti.

## Debug della configurazione di Experience Cloud ID {#section_679E62142A3E46548FF8FBDA46568005}

La [!UICONTROL Visitors with Experience Cloud ID] metrica è una metrica utile in Adobe Analytics per aiutarti a trovare ed eseguire il debug della tua [!UICONTROL Identity Service]configurazione. La metrica è un conteggio del numero di visitatori in una suite di rapporti a cui è stato assegnato un Experience Cloud ID dal servizio identità. Questa metrica può essere molto utile per diagnosticare il motivo per cui alcune integrazioni Experience Cloud potrebbero non condividere il numero di visitatori previsto, o per identificare le aree del sito che potrebbero non avere ancora implementato MCID.

Per usare la metrica Visitatori con Experience Cloud ID, trascinala in qualsiasi rapporto come metrica, come ad esempio questo [!UICONTROL Pages] rapporto:

![](assets/metric-mcvid1.png)

In questo esempio, nota che ogni pagina ha lo stesso numero di Visitatori unici dei Visitatori con un Experience Cloud ID. Tuttavia, il numero totale di Visitatori unici è maggiore del numero totale di Visitatori con Experience Cloud ID. Per trovare le pagine che non impostano il MCID per tutti i visitatori, [create una metrica](https://marketing.adobe.com/resources/help/en_US/analytics/calcmetrics/cm_build_metrics.html) calcolata con la seguente definizione:

![](assets/metric-mcvid2.png)

Aggiungendo la metrica calcolata al rapporto, puoi ordinare il rapporto Pagine in modo che vengano visualizzate le pagine con il numero più elevato di visitatori senza un MCID:

![](assets/metric-mcvid3.png)

Ora puoi vedere rapidamente che le pagine "Visualizzazioni rapide del prodotto" non sono correttamente implementate con il servizio identità e dovrebbero essere aggiornate il prima possibile. Un rapporto simile può essere costruito intorno a qualsiasi tipo di dimensione, ad esempio tipo di browser, sezione del sito o tipo di contenuto.

Una volta identificate le pagine che contengono visitatori senza MCID, dovreste essere in grado di riportarle al team di implementazione in modo che possano correggere tali pagine.

In alcuni casi, è possibile che un numero limitato di MCID non sia impostato per alcuni visitatori anche se il servizio MCID è stato implementato sulla pagina. In questi casi, ciò è più probabile a causa di una configurazione errata comune di Analytics JavaScript o DTM in cui viene chiamata la funzione AppMeasurement prima di fornire una suite di rapporti. Per evitare questo problema, accertati di [inserire correttamente il codice](https://marketing.adobe.com/resources/help/en_US/sc/implement/dtm/t_appmeasurement-code.html) AppMeasurement principale.

I segmenti basati sulla pagina "Product Quick Views" (Visualizzazioni rapide del prodotto) condivisi con Experience Cloud avranno probabilmente un tasso di corrispondenza molto basso con altre soluzioni Experience Cloud. Per verificare la copertura MCID per qualsiasi segmento, puoi creare un rapporto come quello seguente:

![](assets/metric-mcvid4.png)

Da questa tabella, che confronta il numero di Visitatori unici con quello dei Visitatori con un Experience Cloud ID, è facile vedere che "Segmento 1" non ha una copertura MCID al 100%, mentre "Segmento 2" no. Ciò significa che se dovessi condividere il segmento 1 con Experience Cloud, solo 2.186 dei 3.859 visitatori totali potrebbero essere ammessi alla condivisione.
