---
description: In questo documento viene descritto ciò che è necessario fare in Adobe Analytics per supportare l'accesso GDPR e i diritti di eliminazione degli interessati.
title: Adobe Analytics e RGPD
uuid: 16fd5af8-9148-4e09-ad54-9e3cdd2b3c6d
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Adobe Analytics e RGPD

In questo documento viene descritto ciò che è necessario fare in Adobe Analytics per supportare l&#39;accesso GDPR e i diritti di eliminazione degli interessati.

## Panoramica di Adobe  {#section_E582A1D77583410EBB790BB646854A2C}

>[!IMPORTANT] Il contenuto di questo documento non rappresenta e non intende sostituirsi a una consulenza legale. Fai riferimento all’ufficio legale della tua azienda per una consulenza relativa al RGPD.

Il 25 maggio 2018 è entrato in vigore il RGPD (General Data Protection Regulation, regolamento generale sulla protezione dei dati) dell’Unione Europea. Per altre informazioni sulla risposta di Adobe e sulle conseguenze per i clienti di Adobe, consulta [Il RGPD e la tua azienda.](https://www.adobe.com/it/privacy/general-data-protection-regulation.html)

Quando Adobe fornisce software e servizi a un’impresa, agisce in qualità di responsabile del trattamento di tutti i dati personali che riceve e conserva per conto dei clienti, in quanto previsto dalla fornitura dei servizi. In qualità di responsabile del trattamento dei dati, Adobe elabora i dati personali secondo le autorizzazioni e le istruzioni fornite dalla tua azienda (ad esempio, quelli definiti nell’accordo con Adobe).

In qualità di Titolare del trattamento dei dati, l’utente determina i dati personali che Adobe tratta e memorizza per suo conto. Se usi le soluzioni Experience Cloud, Adobe potrebbe conservare i dati personali per l’utente in base alle soluzioni che usi e alle informazioni che scegli di inviare al tuo account di Adobe Experience Cloud. Per un elenco di esempi, consulta [Privacy di Adobe Experience Cloud.](https://www.adobe.com/it/privacy/experience-cloud.html#collect)

![](assets/privacy_ready.png)

## In che modo Adobe gestisce i dati in base al RGPD {#section_A20BCC08A80B410D97601BFB1CAF83F1}

La piattaforma Adobe Cloud (ACP) offre una soluzione integrata che collega l&#39;infrastruttura di gestione dei dati del tuo marchio con gli strumenti Adobe utilizzati per creare e gestire esperienze dei consumatori. Le funzioni di governance dei dati della piattaforma Adobe Cloud consentono di collegare direttamente i criteri di governance dei dati all&#39;utilizzo dei dati.

Acquisisci familiarità con [il modo in cui Adobe Analytics gestisce il RGPD](https://www.adobe.com/it/data-analytics-cloud/analytics/general-data-protection-regulation.html): l’articolo illustra la procedura per prepararsi al RGPD e le modalità di integrazione con l’API del RGPD di Adobe Experience Cloud.

## Prepararsi per il RGPD e gestire i dati di Adobe Analytics {#section_9A47CDCD614C42238F6E05CFF0180195}

Poiché Adobe riconosce che l’utente ha più familiarità con i dati personalizzati nelle suite di rapporti, consente all’utente stesso di definire le impostazioni e le preferenze di governance dei dati.

A tal fine, Adobe Analytics fornisce un’interfaccia utente per la governance dei dati che ti consente, in qualità di titolare del trattamento dei dati, di impostare le [etichette sulla privacy](/help/admin/c-data-governance/gdpr-labels.md#data-governance-labels), oltre a tutte le dimensioni e le metriche, nelle suite di rapporti di Analytics. È possibile identificare le colonne del set di dati che contengono dati direttamente identificabili o dati indirettamente identificabili, in modo da poter inviare le richieste di accesso ed eliminare i dati richiesti. Per ogni richiesta, le etichette definite nell&#39;interfaccia utente di Analytics Data Governance saranno rispettate per l&#39;identificatore specifico che corrisponde a tale richiesta.

See [Label Report Suite Data](/help/admin/c-data-governance/gdpr-setup-reportsuite.md) for more information on how to set the labels.

## Prerequisiti {#section_3C766371CE0641C0821FE8E750E5AE0C}

* Acquisisci familiarità con la [terminologia RGPD.](/help/admin/c-data-governance/gdpr-terminology.md)
* Se non lo hai già fatto, collega la tua società di accesso a un’organizzazione Experience Cloud. Contatta l’Assistenza clienti di Adobe e fai riferimento a [Organizzazioni e collegamento di account.](https://marketing.adobe.com/resources/help/it_IT/mcloud/organizations.html)
* Mappa tutte le suite di rapporti di Adobe Analytics che vuoi configurare per la governance dei dati nella tua [organizzazione Experience Cloud.](https://marketing.adobe.com/resources/help/it_IT/mcloud/report-suite-mapping.html)
* Imposta i criteri di conservazione dei dati per ciascuna suite di rapporti in modo da poter rispettare le richieste di accesso e cancellazione per conformità RGPD.

   > [!NOTE] Adobe Analytics non offre assistenza per elaborare le richieste per l’API RGPD, ovvero per elaborare le richieste di accesso o cancellazione ricevute dagli utenti finali, se non è stato impostato il periodo di conservazione dei dati. Contatta il tuo Customer Success Manager per impostare il periodo di conservazione dei dati.

* Controlla le autorizzazioni: per utilizzare l&#39;interfaccia di gestione della governance dei dati in Adobe Analytics, devi essere un amministratore di Adobe Analytics.
