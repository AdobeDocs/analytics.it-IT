---
title: Ordine di elaborazione per dati in Adobe Analytics
description: Scopri l’ordine dei componenti e dei servizi che elaborano i dati in Adobe Analytics.
exl-id: a8dc9c12-07d3-4dc8-b2df-136f7a7a1e77
source-git-commit: 35e7c8bccb8524fa5e87cae223f0854956c7528a
workflow-type: tm+mt
source-wordcount: '588'
ht-degree: 100%

---

# Ordine di elaborazione per dati in Adobe Analytics

Adobe offre diversi modi per modificare o intervenire sui dati prima che vengano visualizzati nel reporting. Questa pagina mostra l’ordine in cui diverse funzioni di Adobe Analytics elaborano i dati. È possibile utilizzare questo elenco per risolvere eventuali incongruenze nei dati o per determinare la funzione migliore da utilizzare quando sono necessarie modifiche dei dati.

![Ordine di elaborazione](assets/processing-order.png)

## Dati prima dell’invio ad Adobe

Prima dell’invio dei dati ad Adobe, in genere avviene una compilazione lato client utilizzando uno dei seguenti metodi:

* **AppMeasurement**: un file JavaScript ospitato sul tuo sito e a cui si fa riferimento in ogni pagina. I dati vengono inviati direttamente ad Adobe Analytics.
* **Adobe Experience Platform Web SDK**: un file JavaScript ospitato sul tuo sito e a cui si fa riferimento in ogni pagina. I dati vengono inviati ad Adobe Experience Edge.
* **Tag nella raccolta dati di Adobe Experience Cloud**: un file JavaScript a cui si fa riferimento in ogni pagina, contenente regole create all’interno dell’interfaccia di Raccolta dati. L’estensione Adobe Analytics offre un modo più semplice per implementare AppMeasurement. L’estensione Web SDK offre un modo più semplice per implementare Web SDK.

Se invii dati ad Adobe Experience Edge, puoi configurarlo per l’inoltro dei dati ad Adobe Analytics (nonché a molte altre soluzioni Adobe Experience Cloud). Indipendentemente dal metodo di implementazione, il risultato è l’invio di una richiesta di immagine con le variabili desiderate ai server di raccolta dati di Adobe.

## Dati in arrivo sui server di raccolta dati di Adobe Analytics

Una volta arrivati i dati ad Adobe Analytics, le seguenti funzioni modificano i dati secondo necessità:

1. **Tabelle di ricerca**: dimensioni che si basano su tabelle di ricerca interne di Adobe (ad esempio, la dimensione [Browser](/help/components/dimensions/browser.md)) vengono associate al valore corrispondente.
2. [**Variabili dinamiche**](/help/implement/vars/page-vars/dynamic-variables.md): se una variabile dinamica viene visualizzata in una qualsiasi parte di una richiesta di immagine, il valore viene copiato e trattato come un valore indipendente da qui in avanti.
3. [**Regole bot**](/help/admin/admin/bot-removal/bot-rules.md): applica un filtro bot standard o personalizzato per escludere tali dati dal reporting.
4. [**Regole di elaborazione**](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules.md): regole personalizzate applicate ai dati dalla tua organizzazione. Include la mappatura delle [Variabili di dati di contesto](/help/implement/vars/page-vars/contextdata.md) alla rispettiva variabile.
5. **Regole VISTA**: regole flessibili personalizzate applicate ai tuoi dati da un consulente di Adobe. Potenzialmente, le regole VISTA possono essere eseguite prima o dopo le regole di elaborazione, a seconda delle esigenze della tua organizzazione. La maggior parte delle regole VISTA viene generalmente eseguita dopo le regole di elaborazione, ma ogni organizzazione viene impostata in modo diverso. Contatta il tuo Adobe Account Manager per ulteriori informazioni sulle regole VISTA esistenti.
6. [**Regole di elaborazione per il canale di marketing**](/help/components/c-marketing-channels/c-rules.md): è possibile utilizzare le [Regole di elaborazione](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules.md) per preparare i dati da utilizzare nelle regole di elaborazione del canale di marketing.
7. **Dati di geolocalizzazione**: vengono compilate dimensioni che si basano sulla ricerca degli indirizzi IP (ad esempio, la dimensione [Paesi](/help/components/dimensions/countries.md)).
8. [**Offuscamento IP**](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md): se l’organizzazione ha scelto di offuscare gli indirizzi IP nei dati non elaborati, ciò viene effettuato al termine di tutte le altre funzioni di elaborazione.

A questo punto, il singolo hit viene registrato nelle tabelle di dati della suite di rapporti. Dopo l’intervallo di [latenza](latency.md) standard, questo diviene disponibile nel reporting.

## Modifica dei dati dopo l’elaborazione

I dati in Adobe Analytics sono per lo più permanenti. Tuttavia, esistono alcune funzioni che possono consentire la modifica o la rimozione selettiva dei dati:

* [**API Data Repair**](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/data-repair/): modifica determinate colonne o elimina le righe di dati desiderate.
* [**Governance dei dati**](/help/admin/c-data-governance/an-gdpr-workflow.md): soddisfa le richieste di privacy per eliminare definitivamente i dati.
* [**Classificazioni**](/help/components/classifications/c-classifications.md): crea dimensioni basate su regole o dati caricati che ti consentono di organizzare i dati in modo diverso. I dati sottostanti della suite di rapporti non vengono modificati, pertanto puoi modificare o sovrascrivere liberamente i dati di classificazione.
* [**Suite di rapporti virtuale**](/help/components/vrs/vrs-about.md): crea una visualizzazione alternativa della suite di rapporti che può modificare il timeout della visita o consentire [Cross-Device Analytics](/help/components/cda/overview.md).
