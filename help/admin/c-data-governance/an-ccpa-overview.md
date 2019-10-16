---
description: Questo documento descrive le operazioni da effettuare in Adobe Analytics per supportare l'accesso e l'eliminazione dei diritti CCPA degli interessati.
seo-description: Questo documento descrive le operazioni da effettuare in Adobe Analytics per supportare l'accesso e l'eliminazione dei diritti CCPA degli interessati.
seo-title: Adobe Analytics e CCPA
title: Adobe Analytics e CCPA
uuid: 16fd5af8-9148-4e09-ad54-9e3cdd2b3c6d
translation-type: tm+mt
source-git-commit: 3be4e96df12d5e53bf77b1960afc229a1ac6c046

---


# Adobe Analytics e CCPA

Questo documento descrive le operazioni da effettuare in Adobe Analytics per supportare l'accesso e l'eliminazione dei diritti CCPA degli interessati.

## Panoramica di Adobe

>[!IMPORTANT] Il contenuto di questo documento non rappresenta e non intende sostituirsi a una consulenza legale. Consulta l'ufficio legale della tua azienda per ricevere consigli su CCPA.

Il 1° gennaio 2020 entrerà in vigore l'Atto sulla tutela della privacy dei consumatori (California Consumer Privacy Act, CCPA). For more information about Adobe's response and what this means for you as an Adobe customer, see [Adobe's Privacy Center.](https://www.adobe.com/privacy.html)

Quando Adobe fornisce software e servizi a un'impresa, agisce in qualità di responsabile del trattamento di tutti i dati personali che riceve e conserva per conto dei clienti, in quanto previsto dalla fornitura dei servizi. In qualità di elaboratore di dati, Adobe elabora i dati personali in conformità con le autorizzazioni e le istruzioni della tua azienda (ad esempio, come indicato nel tuo contratto con Adobe).

In qualità di Titolare del trattamento dei dati, l’utente determina i dati personali che Adobe tratta e memorizza per suo conto. Se usi le soluzioni Experience Cloud, Adobe potrebbe conservare i dati personali per l’utente in base alle soluzioni che usi e alle informazioni che scegli di inviare al tuo account di Adobe Experience Cloud. Per un elenco di esempi, consulta [Privacy di Adobe Experience Cloud.](https://www.adobe.com/privacy/marketing-cloud.html#collect)

## Gestione dei dati CCPA da parte di Adobe

Adobe Cloud Platform (ACP) fornisce una soluzione integrata che collega l'infrastruttura per la governance dei dati del tuo marchio agli strumenti di Adobe usati per creare e gestire l'esperienza del consumatore. Le funzioni di governance dei dati di Adobe Cloud Platform consentono un collegamento diretto tra i criteri di governance dei dati e l'utilizzo dei dati.

Familiarize yourself with [how Adobe Analytics handles GDPR](https://www.adobe.com/data-analytics-cloud/analytics/general-data-protection-regulation.html) which discusses steps for privacy readiness and how to integrate with the Adobe Experience Cloud Privacy Service API.

## Preparazione CCPA e dati Adobe Analytics

Poiché Adobe riconosce che l'utente ha più familiarità con i dati personalizzati nelle suite di rapporti, consente all'utente stesso di definire le impostazioni e le preferenze di governance dei dati.
To that end, Adobe Analytics provides a Data Governance user interface that lets you, as the data controller, set [privacy labels](/help/admin/c-data-governance/gdpr-labels.md#data-governance-labels) on your Analytics report suites and all the dimensions and metrics in those report suites. Puoi identificare le colonne nel set di dati che contengono i dati direttamente o indirettamente identificabili in modo da poter inviare le richieste di accesso e cancellazione per il trattamento di tali dati. Per ogni richiesta, le etichette definite nell'interfaccia utente per la governance dei dati di Analytics verranno rispettate per l'identificatore specifico che corrisponde a tale richiesta.

Consulta [Etichettare i dati della suite di rapporti](/help//admin/c-data-governance/gdpr-setup-reportsuite.md) per altre informazioni su come impostare le etichette.

## Prerequisiti

* Acquisisci familiarità con la [terminologia RGPD.](/help/admin/c-data-governance/gdpr-terminology.md)
* Se non lo hai già fatto, collega la tua società di accesso a un'organizzazione Experience Cloud. Contatta l'Assistenza clienti di Adobe e fai riferimento a [Organizzazioni e collegamento di account.](https://marketing.adobe.com/resources/help/en_US/mcloud/organizations.html)
* Mappa tutte le suite di rapporti di Adobe Analytics che vuoi configurare per la governance dei dati nella tua [organizzazione Experience Cloud.](https://marketing.adobe.com/resources/help/en_US/mcloud/report-suite-mapping.html)
* Imposta un criterio di conservazione dei dati per ciascuna suite di rapporti in modo che le richieste di eliminazione e accesso CCPA possano essere rispettate.

   Adobe Analytics non è in grado di fornire assistenza nell'elaborazione delle richieste all'API dei servizi per la privacy, ovvero l'elaborazione delle richieste di accesso o eliminazione ricevute dagli utenti finali, se il periodo di conservazione dei dati non è stato impostato in Adobe Analytics. Contatta il tuo Customer Success Manager per impostare il periodo di conservazione dei dati.

* Controlla le tue autorizzazioni: per usare l'interfaccia di gestione della governance dei dati in Adobe Analytics, devi essere un amministratore di Adobe Analytics.
* Prendete in considerazione l'implementazione delle variabili [di gestione del](/help/admin/c-data-governance/consent-variables.md) consenso per monitorare lo stato del consenso a livello di hit.
