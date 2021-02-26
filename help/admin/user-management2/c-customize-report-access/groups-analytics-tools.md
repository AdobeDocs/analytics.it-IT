---
description: Attiva le autorizzazioni degli utenti per gli elementi generali (fatturazione, registri ecc.), gestione società, strumenti, accesso ai servizi Web, Report Builder e integrazione dei Data Connectors.
keywords: gruppi;autorizzazioni
subtopic: Users and groups
title: Personalizzare le autorizzazioni degli strumenti di Analytics
topic: Strumenti di amministrazione
uuid: 8e86bc17-46d3-4c5e-ac25-9f3bfc29b8fa
translation-type: tm+mt
source-git-commit: d0fe97b9368cbc4c9e79f9e56adf9786b58dce1a
workflow-type: tm+mt
source-wordcount: '629'
ht-degree: 19%

---


# Personalizzare le autorizzazioni degli strumenti di Analytics

>[!IMPORTANT]
>
>La gestione di utenti e prodotti è stata spostata nel Admin Console [](https://helpx.adobe.com/it/enterprise/using/admin-console.html).  Adobe ti avviserà quando è il momento di eseguire la migrazione degli utenti. Dopo la migrazione di tutti i clienti, il contenuto della guida per **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL User Management]** verrà ritirato.

Attiva le autorizzazioni degli utenti per gli elementi generali (fatturazione, registri ecc.), gestione società, strumenti, accesso ai servizi Web, Report Builder e integrazione dei Data Connectors.

**[!UICONTROL User Management]** >  **[!UICONTROL Groups]** >  **[!UICONTROL All Report Access]** >  **[!UICONTROL Analytics Tools]** >  **[!UICONTROL Customize]**

>[!NOTE]
>
>La versione Autunno 2016 (20 ottobre) ha apportato modifiche alla gestione dei gruppi. Per un riepilogo delle modifiche, vedere [Modifiche amministrative - Autunno 2016](/help/admin/user-management2/c-user-management/permissions-changes.md).

## Accesso ai report - Strumenti di Analytics

![](assets/report-access-analytics-tools.png)

Fate clic su **[!UICONTROL Customize]** per selezionare gli elementi a cui il gruppo avrà accesso.

## Descrizioni dei campi

Le impostazioni di questa pagina si riferiscono alle suite di rapporti selezionate nella pagina [!UICONTROL Define User Groups].

| Elemento | Descrizione |
|--- |--- |
| **Generale** |  |
| [Gestore codici](/help/admin/admin/code-manager-admin.md) | Consente di scaricare il codice di raccolta dati per le piattaforme Web e mobili. |
| Code Manager - Servizi Web | Consente a un utente non amministrativo di accedere a Code Manager tramite i servizi Web. |
| [Registri](/help/admin/admin/logs.md) | Abilita l&#39;autorizzazione per registrare i file, utile per visualizzare quando gli utenti accedono, il loro utilizzo, accesso, suite di rapporti e modifiche dell&#39;amministratore. |
| Registri - Servizi Web | Consente a un utente non amministrativo di accedere ai registri di Strumenti di amministrazione tramite i Servizi Web. |
| [Gestione traffico](/help/admin/c-traffic-management/traffic-management.md) | La pagina Gestione traffico consente di specificare le modifiche previste per il volume di traffico. |
| Gestione autorizzazioni | Consente agli utenti non amministratori di accedere alle pagine Gestione utente in Strumenti di amministrazione. Questi utenti dispongono di autorizzazioni di lettura ma non dispongono di autorizzazioni di scrittura. |
| Autorizzazioni (scrittura) - Servizi Web | Concede agli utenti non amministrativi le impostazioni di autorizzazione di lettura e scrittura in Gestione utente in Servizi Web.<br>Questa impostazione si riferisce in modo specifico alle azioni di autorizzazione indicate nell&#39;API Admin. |
| Autorizzazioni (lettura) - Servizi Web | Consente a un utente non amministrativo di visualizzare le impostazioni delle autorizzazioni in Gestione utente in Servizi Web.<br>Questa impostazione si riferisce in modo specifico alle azioni di autorizzazione indicate nell&#39;API Admin. |
| **Gestione società** |  |
| [Sicurezza](/help/admin/company/security-manager.md) | Consente di controllare l&#39;accesso ai dati di reporting alla pagina Gestione sicurezza. Le opzioni disponibili includono password complesse, scadenza password, restrizioni di accesso IP e limitazioni del dominio e-mail. |
| Informazioni di supporto | Concede l&#39;autorizzazione alle informazioni di supporto nelle impostazioni aziendali. |
| [Servizi web](/help/admin/company/web-services-admin.md) | Consente l&#39;accesso alla pagina Servizi Web nell&#39;interfaccia Strumenti di amministrazione ([!UICONTROL Company Settings] > [!UICONTROL Web Services]).<br>L&#39;API Web Services fornisce l&#39;accesso programmatico a  servizi Adobe Analytics che consente di duplicare e ampliare le funzionalità disponibili tramite l&#39;interfaccia utente. |
| Single Sign-On (Legacy) | Consente di accedere alla pagina di accesso singolo in Strumenti di amministrazione.<br>**Nota: il** Single Sign-On nell&#39;Adobe Experience Cloud è implementato utilizzando il  [collegamento ](https://docs.adobe.com/content/help/it-IT/core-services/interface/manage-users-and-products/organizations.html) dell&#39;account tra il Experience Cloud  e le soluzioni. |
| [Azioni in sospeso](/help/admin/company/pending-actions-admin.md) | Concede l&#39;autorizzazione per gestire le azioni in sospeso in [!UICONTROL Company Settings]. |
| [Co-branding](/help/admin/company/co-branding-admin.md) | Concede l&#39;autorizzazione per la co-brand Analytics. |
| [Preferenze](/help/admin/admin/preferences-manager.md) | Concede l&#39;autorizzazione per [!UICONTROL Preference Manager]. |
| [Nascondi suite di rapporti](/help/admin/company/c-hide-report-suites.md) | Concede l&#39;autorizzazione per nascondere le suite di rapporti nell&#39;interfaccia utente  di Adobe Analytics. |
| **Strumenti** | Queste impostazioni concedono l&#39;accesso agli strumenti di Analytics (interfacce e applicazioni) e alle funzionalità avanzate come segmentazione e metriche calcolate. |
| [Dati correnti](https://docs.adobe.com/content/help/en/analytics/analyze/reports-analytics/current-data.html) | Concede l&#39;autorizzazione per utilizzare la funzione Dati correnti nel reporting. |
| Accesso al servizio Web | Abilita l&#39;accesso ai servizi Web per i non amministratori. Genera le credenziali del servizio Web. |
| [Report Builder](https://docs.adobe.com/content/help/en/analytics/analyze/report-builder/report-builder-setup/t-install-arb.html) | Concede ai membri di questo gruppo l&#39;accesso alle licenze [!UICONTROL Report Builder]. |
| [Accesso in Analysis Workspace](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/home.html) | Consente agli utenti di accedere a  Analysis Workspace, l&#39;interfaccia di reporting consigliata per [!DNL Adobe Analytics]. |
| [Reports &amp; Analytics](https://docs.adobe.com/content/help/en/analytics/landing/an-key-concepts.html) | Consente agli utenti di accedere a Reporting e analisi. |
| [Creazione della metrica calcolata](https://docs.adobe.com/content/help/it-IT/analytics/components/calculated-metrics/cm-overview.html) | Consente agli utenti di creare metriche calcolate. |
| [Creazione di segmenti](https://docs.adobe.com/content/help/it-IT/analytics/components/segmentation/seg-home.html) | Consente agli utenti di creare segmenti. |
| **Data Connectors** |  |
| Integrazioni (Crea, Aggiorna o Elimina) | Concede l&#39;autorizzazione per creare, aggiornare ed eliminare integrazioni del connettore dati. |
