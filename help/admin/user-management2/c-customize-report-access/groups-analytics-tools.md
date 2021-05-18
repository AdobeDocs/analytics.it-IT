---
description: Attiva le autorizzazioni degli utenti per gli elementi generali (fatturazione, registri ecc.), gestione società, strumenti, accesso ai servizi Web, Report Builder e integrazione dei Data Connectors.
keywords: gruppi;autorizzazioni
subtopic: Users and groups
title: Personalizzare le autorizzazioni degli strumenti di Analytics
feature: Strumenti di amministrazione
uuid: 8e86bc17-46d3-4c5e-ac25-9f3bfc29b8fa
exl-id: fe3a9f65-f121-438f-91d0-45cfaea94416
source-git-commit: d198e8ef0ec8415a4a555d3c385823baad6104fe
workflow-type: tm+mt
source-wordcount: '629'
ht-degree: 19%

---

# Personalizzare le autorizzazioni degli strumenti di Analytics

>[!IMPORTANT]
>
>La gestione di utenti e prodotti è stata spostata nell&#39; [Admin Console](https://helpx.adobe.com/it/enterprise/using/admin-console.html). Adobe ti avviserà quando è il tuo momento di eseguire la migrazione degli utenti. Dopo la migrazione di tutti i clienti, i contenuti della guida per **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL All admin]** > **[!UICONTROL User management]** verranno ritirati.

Attiva le autorizzazioni degli utenti per gli elementi generali (fatturazione, registri ecc.), gestione società, strumenti, accesso ai servizi Web, Report Builder e integrazione dei Data Connectors.

**[!UICONTROL User Management]** >  **[!UICONTROL Groups]** >  **[!UICONTROL All Report Access]** >  **[!UICONTROL Analytics Tools]** >  **[!UICONTROL Customize]**

>[!NOTE]
>
>La versione Autunno 2016 (20 ottobre) ha apportato modifiche alla gestione dei gruppi. Per un riepilogo delle modifiche, consulta [Modifiche amministrative - Autunno 2016](/help/admin/user-management2/c-user-management/permissions-changes.md) .

## Accesso ai rapporti - Strumenti di Analytics

![](assets/report-access-analytics-tools.png)

Fai clic su **[!UICONTROL Customize]** per selezionare gli elementi a cui il gruppo avrà accesso.

## Descrizioni campo

Le impostazioni di questa pagina si riferiscono alle suite di rapporti selezionate nella pagina [!UICONTROL Define User Groups] .

| Elemento | Descrizione |
|--- |--- |
| **Generale** |  |
| [Gestore codici](/help/admin/admin/code-manager-admin.md) | Abilita l’autorizzazione a scaricare il codice di raccolta dati per piattaforme web e mobili. |
| Gestione codici - Servizi Web | Consente a un utente non amministrativo di accedere a Code Manager tramite Web Services. |
| [Registri](/help/admin/admin/logs.md) | Abilita l’autorizzazione a registrare i file, che ti aiuta a vedere quando gli utenti accedono, il loro utilizzo, accesso, suite di rapporti e modifiche dell’amministratore. |
| Registri - Servizi Web | Consente a un utente non amministrativo di accedere ai registri degli Strumenti di amministrazione tramite i servizi Web. |
| [Gestione traffico](/help/admin/c-traffic-management/traffic-management.md) | La pagina Gestione traffico consente di specificare le modifiche previste al volume di traffico. |
| Gestione autorizzazioni | Consente agli utenti non amministratori di accedere alle pagine Gestione utente in Strumenti di amministrazione. Questi utenti dispongono di autorizzazioni di lettura ma non dispongono di autorizzazioni di scrittura. |
| Autorizzazioni (scrittura) - Servizi Web | Consente agli utenti non amministrativi di leggere e scrivere le impostazioni delle autorizzazioni in Gestione utente in Servizi Web.<br>Questa impostazione si riferisce in modo specifico alle azioni di autorizzazione indicate nell&#39;API amministratore. |
| Autorizzazioni (lettura) - Servizi Web | Consente a un utente non amministrativo di visualizzare le impostazioni delle autorizzazioni in Gestione utente in Servizi Web.<br>Questa impostazione si riferisce in modo specifico alle azioni di autorizzazione indicate nell&#39;API amministratore. |
| **Gestione aziendale** |  |
| [Sicurezza](/help/admin/company/security-manager.md) | Consente di controllare l&#39;accesso ai dati di reporting tramite la pagina Gestione sicurezza. Le opzioni includono password complesse, scadenza password, restrizioni di accesso IP e restrizioni del dominio e-mail. |
| Informazioni di supporto | Consente di accedere alle informazioni di supporto nelle impostazioni aziendali. |
| [Servizi web](/help/admin/company/web-services-admin.md) | Consente di accedere alla pagina Web Services nell’interfaccia Strumenti di amministrazione ([!UICONTROL Company Settings] > [!UICONTROL Web Services]).<br>L’API dei servizi Web fornisce accesso programmatico ai servizi Adobe Analytics che consentono di duplicare e potenziare le funzionalità disponibili tramite l’interfaccia utente. |
| Single Sign-On (legacy) | Consente di accedere alla pagina di accesso singolo in Strumenti di amministrazione.<br>**Nota:** il single sign-on in Adobe Experience Cloud viene implementato utilizzando il  [collegamento dell&#39;account ](https://docs.adobe.com/content/help/it-IT/core-services/interface/manage-users-and-products/organizations.html) tra l&#39;Experience Cloud e le soluzioni. |
| [Azioni in sospeso](/help/admin/company/pending-actions-admin.md) | Consente di gestire le azioni in sospeso in [!UICONTROL Company Settings]. |
| [Co-branding](/help/admin/company/co-branding-admin.md) | Concede l’autorizzazione ad utilizzare Analytics con il co-brand. |
| [Preferenze](/help/admin/admin/preferences-manager.md) | Concede l&#39;autorizzazione a [!UICONTROL Preference Manager]. |
| [Nascondi suite di rapporti](/help/admin/company/c-hide-report-suites.md) | Consente di nascondere le suite di rapporti nell’interfaccia utente di Adobe Analytics. |
| **Strumenti** | Queste impostazioni consentono l’accesso agli strumenti di Analytics (interfacce e applicazioni) e alle funzionalità avanzate come la segmentazione e le metriche calcolate. |
| [Dati correnti](https://docs.adobe.com/content/help/en/analytics/analyze/reports-analytics/current-data.html) | Consente di utilizzare la funzione Dati correnti nel reporting. |
| Accesso al servizio Web | Abilita l&#39;accesso ai servizi Web per i non amministratori. Genera le credenziali del servizio Web. |
| [Report Builder](https://docs.adobe.com/content/help/en/analytics/analyze/report-builder/report-builder-setup/t-install-arb.html) | Consente ai membri di questo gruppo di accedere alle licenze [!UICONTROL Report Builder]. |
| [Accesso in Analysis Workspace](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/home.html) | Consente agli utenti di accedere ad Analysis Workspace, l’interfaccia di reporting consigliata per [!DNL Adobe Analytics]. |
| [Reports &amp; Analytics](https://docs.adobe.com/content/help/en/analytics/landing/an-key-concepts.html) | Consente agli utenti di accedere a Reporting e analisi. |
| [Creazione di metriche calcolate](https://docs.adobe.com/content/help/it-IT/analytics/components/calculated-metrics/cm-overview.html) | Consente agli utenti di creare metriche calcolate. |
| [Creazione di segmenti](https://docs.adobe.com/content/help/it-IT/analytics/components/segmentation/seg-home.html) | Consente agli utenti di creare segmenti. |
| **Data Connectors** |  |
| Integrazioni (creare, aggiornare o eliminare) | Consente di creare, aggiornare ed eliminare integrazioni tramite Data Connector. |
