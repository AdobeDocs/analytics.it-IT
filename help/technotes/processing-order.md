---
title: Ordine di elaborazione dei dati in Adobe Analytics
description: Scopri l’ordine dei componenti e dei servizi che elaborano i dati in Adobe Analytics.
source-git-commit: 64693627459b85031edbe61865077c44f93f72bf
workflow-type: tm+mt
source-wordcount: '587'
ht-degree: 0%

---

# Ordine di elaborazione dei dati in Adobe Analytics

Adobe offre diversi modi per modificare o manipolare i dati prima che vengano visualizzati nel reporting. Questa pagina mostra l’ordine in cui diverse funzioni di Adobe Analytics elaborano i dati. È possibile utilizzare questo elenco per risolvere eventuali incongruenze nei dati o per determinare la funzione migliore da utilizzare quando sono necessarie regolazioni dei dati.

![Ordine di elaborazione](assets/processing-order.png)

## Dati prima dell’invio all’Adobe

Prima dell&#39;invio dei dati ad Adobe, in genere viene compilato lato client utilizzando uno dei seguenti metodi:

* **AppMeasurement**: Un file JavaScript ospitato sul tuo sito e a cui si fa riferimento in ogni pagina. I dati vengono inviati direttamente ad Adobe Analytics.
* **Adobe Experience Platform Web SDK**: Un file JavaScript ospitato sul tuo sito e a cui si fa riferimento in ogni pagina. I dati vengono inviati ad Adobe Experience Edge.
* **Tag nella raccolta dati di Adobe Experience Cloud**: Un file JavaScript a cui si fa riferimento in ogni pagina, contenente regole create all’interno dell’interfaccia utente Raccolta dati. L&#39;estensione Adobe Analytics offre e un modo più semplice per implementare AppMeasurement. L&#39;estensione SDK per web offre un modo più semplice per implementare l&#39;SDK per web.

Se invii dati ad Adobe Experience Edge, puoi configurarli per l’inoltro di dati ad Adobe Analytics (nonché a molte altre soluzioni Adobe Experience Cloud). Indipendentemente dal metodo di implementazione, alla fine una richiesta di immagine con le variabili desiderate viene inviata ai server di raccolta dati di Adobe.

## Dati in arrivo sui server di raccolta dati di Adobe Analytics

Una volta arrivati i dati ad Adobe Analytics, le seguenti funzioni regolano i dati in base alle esigenze:

1. **Tabelle di ricerca**: Dimension che si basano su tabelle di ricerca interne di Adobe (ad esempio, il [Browser](/help/components/dimensions/browser.md) (dimension) viene confrontato al valore corrispondente.
2. [**Variabili dinamiche**](/help/implement/vars/page-vars/dynamic-variables.md): Se una variabile dinamica viene visualizzata in una qualsiasi parte di una richiesta di immagine, il valore viene copiato e trattato come un valore indipendente che si sposta in avanti.
3. [**Regole bot**](/help/admin/admin/bot-removal/bot-rules.md): Applica un filtro bot standard o personalizzato per escludere tali dati dal reporting.
4. [**Regole di elaborazione**](/help/admin/admin/c-processing-rules/processing-rules.md): Regole personalizzate applicate ai dati dalla tua organizzazione. Include la mappatura di [Variabili di dati di contesto](/help/implement/vars/page-vars/contextdata.md) alla relativa variabile.
5. **Regole VISTA**: Regole flessibili personalizzate applicate ai dati da un consulente di Adobe. Le regole VISTA possono essere potenzialmente eseguite prima o dopo le regole di elaborazione, a seconda delle esigenze della tua organizzazione. La maggior parte delle regole VISTA viene generalmente eseguita dopo le regole di elaborazione, ma ogni organizzazione viene impostata in modo diverso. Contatta il tuo Adobe Account Manager per ulteriori informazioni sulle regole VISTA esistenti.
6. [**Regole di elaborazione per il canale di marketing**](/help/components/c-marketing-channels/c-rules.md): È possibile utilizzare [Regole di elaborazione](/help/admin/admin/c-processing-rules/processing-rules.md) preparare i dati da utilizzare nelle regole di elaborazione del canale di marketing.
7. **Dati di geolocalizzazione**: Dimension che si basano sulla ricerca degli indirizzi IP (ad esempio, il [Paesi](/help/components/dimensions/countries.md) (dimension) sono compilati.
8. [**Offuscamento IP**](/help/admin/admin/general-acct-settings-admin.md): Se l’organizzazione ha scelto di offuscare gli indirizzi IP nei dati non elaborati, questo viene fatto al termine di tutte le altre funzioni di elaborazione.

A questo punto, il singolo hit viene registrato nelle tabelle di dati della suite di rapporti. Dopo lo standard [latenza](latency.md) intervallo, è disponibile nel reporting.

## Modifica dei dati dopo l’elaborazione

I dati in Adobe Analytics sono per lo più permanenti; tuttavia, esistono alcune funzioni che possono consentire la regolazione o la rimozione selettiva dei dati:

* [**API di ripristino dati**](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/data-repair/): Modificare determinate colonne o eliminare le righe di dati desiderate.
* [**Governance dei dati**](/help/admin/c-data-governance/an-gdpr-workflow.md): Soddisfare le richieste di privacy per eliminare definitivamente i dati.
* [**Classificazioni**](/help/components/classifications/c-classifications.md): Crea dimensioni basate su regole o dati caricati che ti consentono di organizzare i dati in modo diverso. I dati sottostanti della suite di rapporti non vengono modificati, pertanto puoi modificare o sovrascrivere liberamente i dati di classificazione.
* [**Suite di rapporti virtuali**](/help/components/vrs/vrs-about.md): Creare una visualizzazione alternativa della suite di rapporti che può modificare il timeout della visita o consentire [Analisi multidispositivo](/help/components/cda/overview.md).
