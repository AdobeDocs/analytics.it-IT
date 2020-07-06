---
description: Questo documento descrive cosa fare in Adobe Analytics per supportare i diritti di accesso e cancellazione delle persone interessate in base al CCPA.
title: Adobe Analytics e CCPA
uuid: 16fd5af8-9148-4e09-ad54-9e3cdd2b3c6d
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '641'
ht-degree: 100%

---


# Adobe Analytics e CCPA

Questo documento descrive cosa fare in Adobe Analytics per supportare i diritti di accesso e cancellazione delle persone interessate in base al CCPA.

## Panoramica di Adobe

>[!IMPORTANT]
>
>Il contenuto di questo documento non rappresenta e non intende sostituirsi a una consulenza legale. Fai riferimento all’ufficio legale della tua azienda per una consulenza relativa al CCPA.

Il 1° gennaio 2020 entrerà in vigore l’Atto sulla tutela della privacy dei consumatori della California (California Consumer Privacy Act, CCPA). Per altre informazioni sulla risposta di Adobe e sulle conseguenze per i clienti di Adobe, consulta il [Centro per la privacy di Adobe.](https://www.adobe.com/it/privacy.html)

Quando Adobe fornisce software e servizi a un’impresa, agisce in qualità di responsabile del trattamento di tutti i dati personali che riceve e conserva per conto dei clienti, in quanto previsto dalla fornitura dei servizi. In qualità di responsabile del trattamento dei dati, Adobe elabora i dati personali secondo le autorizzazioni e le istruzioni fornite dalla tua azienda (ad esempio, quelli definiti nell’accordo con Adobe).

In qualità di Titolare del trattamento dei dati, l’utente determina i dati personali che Adobe tratta e memorizza per suo conto. Se usi le soluzioni Experience Cloud, Adobe potrebbe conservare i dati personali per l’utente in base alle soluzioni che usi e alle informazioni che scegli di inviare al tuo account di Adobe Experience Cloud. Per un elenco di esempi, consulta [Privacy di Adobe Experience Cloud.](https://www.adobe.com/it/privacy/experience-cloud.html#collect)

## In che modo Adobe gestisce i dati in base al CCPA

Adobe Cloud Platform (ACP) fornisce una soluzione integrata che collega l&#39;infrastruttura per la governance dei dati del tuo marchio agli strumenti di Adobe usati per creare e gestire l&#39;esperienza del consumatore. Le funzioni di governance dei dati di Adobe Cloud Platform consentono un collegamento diretto tra i criteri di governance dei dati e l&#39;utilizzo dei dati.

Acquisisci familiarità con [il modo in cui Adobe Analytics gestisce il RGPD](https://www.adobe.com/data-analytics-cloud/analytics/general-data-protection-regulation.html): l’articolo illustra la procedura per prepararsi alla privacy e le modalità di integrazione con l’API del servizio di Privacy di Adobe Experience Cloud.

## Prepararsi per il CCPA e gestire i dati di Adobe Analytics

Poiché Adobe riconosce che l’utente ha più familiarità con i dati personalizzati nelle suite di rapporti, consente all’utente stesso di definire le impostazioni e le preferenze di governance dei dati.
A tal fine, Adobe Analytics fornisce un’interfaccia utente per la governance dei dati che ti consente, in qualità di titolare del trattamento dei dati, di impostare le [etichette sulla privacy](/help/admin/c-data-governance/gdpr-labels.md#data-governance-labels), oltre a tutte le dimensioni e le metriche, nelle suite di rapporti di Analytics. Puoi identificare le colonne nel set di dati che contengono i dati direttamente o indirettamente identificabili in modo da poter inviare le richieste di accesso e cancellazione per il trattamento di tali dati. Per ogni richiesta, le etichette definite nell&#39;interfaccia utente per la governance dei dati di Analytics verranno rispettate per l&#39;identificatore specifico che corrisponde a tale richiesta.

Consulta [Etichettare i dati della suite di rapporti](/help//admin/c-data-governance/gdpr-setup-reportsuite.md) per altre informazioni su come impostare le etichette.

## Prerequisiti

* Acquisisci familiarità con la [terminologia RGPD.](/help/admin/c-data-governance/gdpr-terminology.md)
* Se non lo hai già fatto, collega la tua società di accesso a un’organizzazione Experience Cloud. Contatta l’Assistenza clienti di Adobe e fai riferimento a [Organizzazioni e collegamento di account.](https://docs.adobe.com/content/help/it-IT/core-services/interface/manage-users-and-products/organizations.html)
* Mappa tutte le suite di rapporti di Adobe Analytics che vuoi configurare per la governance dei dati nella tua [organizzazione Experience Cloud.](https://docs.adobe.com/content/help/it-IT/core-services/interface/about-core-services/report-suite-mapping.html)
* Imposta i criteri di conservazione dei dati per ciascuna suite di rapporti in modo da poter rispettare le richieste di accesso e cancellazione del CCPA.

   In Adobe Analytics non è possibile ricevere assistenza per elaborare le richieste per l’API dei servizi di Privacy, ovvero per elaborare le richieste di accesso o cancellazione ricevute dagli utenti finali, se non è stato impostato il periodo di conservazione dei dati. Contatta il tuo Customer Success Manager per impostare il periodo di conservazione dei dati.

* Controlla le tue autorizzazioni: per usare l&#39;interfaccia di gestione della governance dei dati in Adobe Analytics, devi essere un amministratore di Adobe Analytics.
* Prendi in considerazione l’implementazione delle [variabili di gestione del consenso](/help/admin/c-data-governance/consent-variables.md) per monitorare lo stato del consenso a livello di hit.
