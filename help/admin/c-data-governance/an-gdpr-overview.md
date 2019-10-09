---
description: Questo documento descrive cosa fare in Adobe Analytics per supportare i diritti di accesso e cancellazione delle persone interessate in base al RGPD.
seo-description: Questo documento descrive cosa fare in Adobe Analytics per supportare i diritti di accesso e cancellazione delle persone interessate in base al RGPD.
seo-title: Adobe Analytics e RGPD
title: Adobe Analytics e RGPD
uuid: 16fd5af8-9148-4e09-ad54-9e3cdd2b3c6d
translation-type: tm+mt
source-git-commit: 21fe6a0ee434e430d77a24d060acd2ffce08e219

---


# Adobe Analytics e RGPD

Questo documento descrive cosa fare in Adobe Analytics per supportare i diritti di accesso e cancellazione delle persone interessate in base al RGPD.

## Panoramica di Adobe {#section_E582A1D77583410EBB790BB646854A2C}

>[!IMPORTANT]
>
>Il contenuto di questo documento non rappresenta e non intende sostituirsi a una consulenza legale. Fai riferimento all'ufficio legale della tua azienda per una consulenza relativa al RGPD.

Il 25 maggio 2018 è entrato in vigore il Regolamento generale sulla protezione dei dati (General Data Protection Regulation, GDPR) dell'Unione Europea. Per altre informazioni sulla risposta di Adobe e sulle conseguenze per i clienti di Adobe, consulta [Il RGPD e la tua azienda.](https://www.adobe.com/privacy/general-data-protection-regulation.html)

Quando Adobe fornisce software e servizi a un'impresa, agisce in qualità di responsabile del trattamento di tutti i dati personali che riceve e conserva per conto dei clienti, in quanto previsto dalla fornitura dei servizi. In qualità di responsabile del trattamento, Adobe elabora i dati personali secondo le istruzioni e le autorizzazioni dell'azienda (ad esempio, in base a quanto previsto dal contratto con Adobe).

In qualità di titolare del trattamento, l'utente determina i dati personali che Adobe elabora e memorizza per suo conto. Se usi le soluzioni Experience Cloud, Adobe potrebbe conservare i dati personali per l'utente in base alle soluzioni che usi e alle informazioni che scegli di inviare al tuo account di Adobe Experience Cloud. Per un elenco di esempi, consulta [Privacy di Adobe Experience Cloud.](https://www.adobe.com/privacy/marketing-cloud.html#collect)

![](assets/privacy_ready.png)

## In che modo Adobe gestisce i dati in base al RGPD {#section_A20BCC08A80B410D97601BFB1CAF83F1}

Adobe Cloud Platform (ACP) fornisce una soluzione integrata che collega l'infrastruttura per la governance dei dati del tuo marchio agli strumenti di Adobe usati per creare e gestire l'esperienza del consumatore. Le funzioni di governance dei dati di Adobe Cloud Platform consentono un collegamento diretto tra i criteri di governance dei dati e l'utilizzo dei dati.

Acquisisci familiarità con [il modo in cui Adobe Analytics gestisce il RGPD](https://www.adobe.com/data-analytics-cloud/analytics/general-data-protection-regulation.html): l'articolo illustra la procedura per prepararsi al RGPD e le modalità di integrazione con l'API del RGPD di Adobe Experience Cloud.

## Prepararsi per il RGPD e gestire i dati di Adobe Analytics {#section_9A47CDCD614C42238F6E05CFF0180195}

Poiché Adobe riconosce che l'utente ha più familiarità con i dati personalizzati nelle suite di rapporti, consente all'utente stesso di definire le impostazioni e le preferenze di governance dei dati.

A tal fine, Adobe Analytics fornisce un'interfaccia utente per la governance dei dati che ti consente, in qualità di titolare del trattamento dei dati, di impostare le [etichette sulla privacy](../../admin/c-data-governance/gdpr-labels.md#concept_F4061E29353446B5B0A7CF248D54E6F2), oltre a tutte le dimensioni e le metriche, nelle suite di rapporti di Analytics. Puoi identificare le colonne nel set di dati che contengono i dati direttamente o indirettamente identificabili in modo da poter inviare le richieste di accesso e cancellazione per il trattamento di tali dati. Per ogni richiesta, le etichette definite nell'interfaccia utente per la governance dei dati di Analytics verranno rispettate per l'identificatore specifico che corrisponde a tale richiesta.

Consulta [Etichettare i dati della suite di rapporti](../../admin/c-data-governance/gdpr-setup-reportsuite.md#concept_FAA948AD8CEA4BC38CB482EAF3648731) per altre informazioni su come impostare le etichette.

## Prerequisiti {#section_3C766371CE0641C0821FE8E750E5AE0C}

* Acquisisci familiarità con la [terminologia RGPD.](/help/admin/c-data-governance/gdpr-terminology.md#concept_83C744A9D077476BAD8F8492DF68EBD7)
* Se non lo hai già fatto, collega la tua società di accesso a un'organizzazione Experience Cloud. Contatta l'Assistenza clienti di Adobe e fai riferimento a [Organizzazioni e collegamento di account.](https://marketing.adobe.com/resources/help/en_US/mcloud/organizations.html)
* Mappa tutte le suite di rapporti di Adobe Analytics che vuoi configurare per la governance dei dati nella tua [organizzazione Experience Cloud.](https://marketing.adobe.com/resources/help/en_US/mcloud/report-suite-mapping.html)
* Imposta i criteri di conservazione dei dati per ciascuna suite di rapporti in modo da poter rispettare le richieste di accesso e cancellazione del RGPD.

   >[!NOTE]
   >
   >Adobe Analytics non è in grado di fornire assistenza nell'elaborazione delle richieste all'API GDPR, ovvero l'elaborazione delle richieste di accesso o di eliminazione ricevute dagli utenti finali, se il periodo di conservazione dei dati non è stato impostato in Adobe Analytics. Contatta il tuo Customer Success Manager per impostare il periodo di conservazione dei dati.

* Controlla le tue autorizzazioni: per usare l'interfaccia di gestione della governance dei dati in Adobe Analytics, devi essere un amministratore di Adobe Analytics.

