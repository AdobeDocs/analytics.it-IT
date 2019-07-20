---
description: Scopri come le visite al sito Web diventano un rapporto in Adobe Analytics.
keywords: Implementazione di Analytics; raccolta dati
seo-description: Scopri come le visite al sito Web diventano un rapporto in Adobe Analytics.
seo-title: Raccolta dati
solution: Analytics
title: Raccolta dati
topic: Sviluppatore e implementazione
uuid: d 0 d 6098 d -113 e -4 cf 5-bb 89-e 435 f 7 b 6 b 1 af
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Raccolta dati

Scopri come le visite al sito Web diventano un rapporto in Adobe Analytics.

La raccolta dei dati di Analytics viene realizzata mediante una richiesta speciale di immagini ai server di raccolta dati Adobe. Nella maggior parte delle implementazioni, il codice javascript viene inserito nelle pagine Web tracciate. Quando viene caricata una pagina Web con tag nel browser di un visitatore, il browser esegue il codice javascript, eseguendo logica per acquisire informazioni sui visitatori e compilare correttamente i tag. L'ultimo passaggio dell'elaborazione javascript è una richiesta di immagine a un server di raccolta dati Analytics che raccoglie i dati in corso di invio e restituisce una piccola immagine trasparente al browser del visitatore.

Dato che l'elaborazione dei colli di bottiglia tipica nell'elaborazione del browser rappresenta il tempo necessario per scaricare elementi di pagina (immagini, et cetera) dai server Web, il tempo necessario al browser per eseguire il codice javascript è trascurabile. Tuttavia, l'ultimo passaggio in cui il browser del visitatore richiede un'immagine dal server di raccolta dati Adobe aggiunge al tempo totale di download della pagina. L'impatto generale sul tempo di download della pagina dipende dalle prossimità del visitatore (in genere nel flusso Internet, non dalla distanza geografica) ai server di raccolta dati Adobe.

Adobe ha creato diversi modi per inviare dati in Analytics. Questi metodi includono le informazioni di tracciamento in tempo reale da:

* Applicazioni che possono accedere a Internet
* Campagne
* Applicazioni client-server
* E-mail
* Dispositivi mobili
* Chiosks basati sul Web
* Siti Web

<!-- 

<p>Need to reconcile with Data Collection topics in the user guide, in this guide, and in reference. </p>

 -->

1. Quando un visitatore accede al sito, viene richiesta una richiesta al server Web.

   ![](assets/how-data-is-collected-1.png)

1. Il server Web del sito invia le informazioni sul codice della pagina e la pagina viene visualizzata nel browser.

   ![](assets/how-data-is-collected-2.png)

1. La pagina viene caricata e il codice javascript di Analytics viene eseguito.

   ![](assets/how-data-is-collected-3.png)

   Il codice javascript invia una richiesta di immagine al server Adobe, passando le variabili, le metriche e i dati della pagina definiti nella tua implementazione.

   **Esempio di codice javascript:** Il codice javascript è posizionato all'interno dei tag body di una pagina Web:

   ![](assets/code-example-geometrixx.png)

   **Esempio di richiesta immagine:** Snippet di una richiesta di immagine con il nome della pagina delineato:

   ![](assets/image-request-snippet.png)

   >[!NOTE]
   >
   >Ogni richiesta di immagine contiene una stringa numero casuale per impedire la memorizzazione nella cache del browser e verificare che le richieste di immagini successive vengano eseguite dal browser.

1. Adobe restituisce un'immagine pixel trasparente.

   ![](assets/how-data-is-collected-4.png)

   Il codice raccoglie automaticamente ulteriori dettagli (ad esempio sistema operativo, tipo di browser, altezza e larghezza del browser, indirizzo IP e lingua del browser).

1. Adobe servers store web analysis data in *`report suites`* (your data repository).

   ![](assets/how-data-is-collected-5.png)

   Una [suite di rapporti](https://marketing.adobe.com/resources/help/en_US/reference/?f=report_suites_admin) definisce il reporting indipendente e completo su un sito Web scelto, su un insieme di siti Web o su un sottoinsieme di pagine Web.

1. I dati della suite di rapporti compilano i rapporti a cui puoi accedere in un browser Web.

   ![](assets/how-data-is-collected-6.png)

   **Esempio di rapporto:**

   ![](assets/two-months-summary-project.png)

   L'esecuzione del codice javascript si verifica rapidamente e non influisce in modo evidente sui tempi di caricamento delle pagine. This approach allows you to count pages that were displayed when a visitor clicked **[!UICONTROL Reload]** or **[!UICONTROL Back]** to reach a page, because the JavaScript runs even when the page is retrieved from cache.

Per ulteriori dettagli consulta:

* [Raccolta dati](../../implement/js-implementation/data-collection/query-parameters.md)
* [Creare un elemento dati](../../implement/c-implement-with-dtm/t-data-element.md#task_962EF08CE2AE49B3B739295F6E4792C2)
* [Data Warehouse](https://marketing.adobe.com/resources/help/en_US/reference/data_warehouse.html)
* [Ad Hoc Analysis](https://marketing.adobe.com/resources/help/en_US/dsc/c_getting_started.html)
* [Origini dati](https://marketing.adobe.com/resources/help/en_US/whitepapers/ftp/ftp_datasources.html)
* [Data Connectors](https://marketing.adobe.com/resources/help/en_US/whitepapers/ftp/ftp_genesis.html)
* [Feed dati di Analytics](/help/export/analytics-data-feed/c-getstarted/data-feed-overview.md)

>[!MORE_ LIKE_ THIS]
>       
>* [Debugger di Experience Cloud](/help/implement/impl-testing/debugger.md)

