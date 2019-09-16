---
description: Attiva le autorizzazioni degli utenti per gli elementi generali (fatturazione, registri ecc.), gestione società, strumenti, accesso ai servizi Web, Report Builder e integrazione dei Data Connectors.
keywords: gruppi;autorizzazioni
seo-description: Attiva le autorizzazioni degli utenti per gli elementi generali (fatturazione, registri ecc.), gestione società, strumenti, accesso ai servizi Web, Report Builder e integrazione dei Data Connectors.
seo-title: Personalizzare le autorizzazioni degli strumenti di Analytics
solution: Analytics
subtopic: Utenti e gruppi
title: Personalizzare le autorizzazioni degli strumenti di Analytics
topic: Strumenti di amministrazione
uuid: 8e86bc17-46d3-4c5e-ac25-9f3bfc29b8fa
translation-type: tm+mt
source-git-commit: 31222a67cae860e5e914eea1c0c2fd82296d3704

---


# Personalizzare le autorizzazioni degli strumenti di Analytics

>[!IMPORTANT]
>
>La gestione di utenti e prodotti è stata spostata in [Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html). Adobe ti informerà quando è il momento di eseguire la migrazione degli utenti. Dopo la migrazione di tutti i clienti, i contenuti della guida per **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL User Management]** verranno ritirati.

Attiva le autorizzazioni degli utenti per gli elementi generali (fatturazione, registri ecc.), gestione società, strumenti, accesso ai servizi Web, Report Builder e integrazione dei Data Connectors.

**[!UICONTROL User Management]** &gt; **[!UICONTROL Groups]** &gt; **[!UICONTROL All Report Access]** &gt; **[!UICONTROL Analytics Tools]** &gt; **[!UICONTROL Customize]**

>[!NOTE]
>
>La versione Autunno 2016 (20 ottobre) ha apportato modifiche alla gestione dei gruppi. Per un riepilogo delle modifiche, consultate Modifiche [amministrative - Autunno 2016](../../../admin/user-management2/c-user-management/permissions-changes.md#concept_86581595B86B47D5B8F90282FC3E31EF) .

## Accesso ai report - Strumenti di Analytics

![](assets/report-access-analytics-tools.png)

Fate clic **[!UICONTROL Customize]** per selezionare gli elementi a cui il gruppo avrà accesso.

## Descrizioni dei campi

Le impostazioni di questa pagina si riferiscono alle suite di rapporti selezionate sulla [!UICONTROL Define User Groups] pagina.

| Elemento | Descrizione |
|--- |--- |
| **Generale** |  |
| [Gestore codici](../../../admin/admin/code-manager-admin.md) | Consente di scaricare il codice di raccolta dati per le piattaforme Web e mobili. |
| Code Manager - Servizi Web | Consente a un utente non amministrativo di accedere a Code Manager tramite i servizi Web. |
| [Registri](../../../admin/admin/logs.md) | Abilita l'autorizzazione per registrare i file, utile per visualizzare quando gli utenti accedono, il loro utilizzo, accesso, suite di rapporti e modifiche dell'amministratore. |
| Registri - Servizi Web | Consente a un utente non amministrativo di accedere ai registri di Strumenti di amministrazione tramite i Servizi Web. |
| [Gestione traffico](../../../admin/c-traffic-management/traffic-management.md) | La pagina Gestione traffico consente di specificare le modifiche previste per il volume di traffico. |
| Gestione autorizzazioni | Consente agli utenti non amministratori di accedere alle pagine Gestione utente in Strumenti di amministrazione. Questi utenti dispongono di autorizzazioni di lettura ma non dispongono di autorizzazioni di scrittura. |
| Autorizzazioni (scrittura) - Servizi Web | Concede agli utenti non amministrativi le impostazioni di autorizzazione di lettura e scrittura in Gestione utente in Servizi Web.<br>Questa impostazione si riferisce in modo specifico alle azioni di autorizzazione indicate nell'API Admin. |
| Autorizzazioni (lettura) - Servizi Web | Consente a un utente non amministrativo di visualizzare le impostazioni delle autorizzazioni in Gestione utente in Servizi Web.<br>Questa impostazione si riferisce in modo specifico alle azioni di autorizzazione indicate nell'API Admin. |
| **Gestione società** |  |
| [Sicurezza](../../../admin/company/security-manager.md) | Consente di controllare l'accesso ai dati di reporting alla pagina Gestione sicurezza. Le opzioni disponibili includono password complesse, scadenza password, restrizioni di accesso IP e limitazioni del dominio e-mail. |
| Informazioni di supporto | Concede l'autorizzazione alle informazioni di supporto nelle impostazioni aziendali. |
| [Servizi web](../../../admin/company/web-services-admin.md) | Consente l'accesso alla pagina Servizi Web nell'interfaccia Strumenti di amministrazione ([!UICONTROL Company Settings] &gt; [!UICONTROL Web Services]).<br>L'API Web Services fornisce l'accesso programmatico ai servizi Adobe Analytics che consente di duplicare e ampliare le funzionalità disponibili tramite l'interfaccia utente. |
| Single Sign-On (Legacy) | Consente di accedere alla pagina di accesso singolo in Strumenti di amministrazione.<br>**** Nota: Il single sign-on in Adobe Experience Cloud è implementato utilizzando il collegamento [dell'](https://marketing.adobe.com/resources/help/en_US/mcloud/organizations.html) account tra Experience Cloud e le soluzioni. |
| [Azioni in sospeso](../../../admin/company/pending-actions-admin.md) | Concede l'autorizzazione per gestire le azioni in sospeso in [!UICONTROL Company Settings]. |
| [Co-branding](../../../admin/company/co-branding-admin.md) | Concede l'autorizzazione per la co-brand Analytics. |
| [Preferenze](../../../admin/admin/preferences-manager.md) | Concede l'autorizzazione all' [!UICONTROL Preference Manager]. |
| [Nascondi suite di rapporti](../../../admin/company/c-hide-report-suites.md) | Concede l'autorizzazione per nascondere le suite di rapporti nell'interfaccia utente di Adobe Analytics. |
| **Strumenti** | Queste impostazioni consentono l'accesso agli strumenti di Analytics (interfacce e applicazioni) e alle funzionalità avanzate come segmentazione e metriche calcolate. |
| [Dati correnti](https://marketing.adobe.com/resources/help/en_US/reference/data_latency.html) | Concede l'autorizzazione per utilizzare la funzione Dati correnti nel reporting. |
| [Utenti della licenza di Analisi](https://marketing.adobe.com/resources/help/en_US/dsc/) ad hoc | Concede l'autorizzazione di accesso [!UICONTROL Ad Hoc Analysis]. |
| Accesso al servizio Web | Abilita l'accesso ai servizi Web per i non amministratori. Genera le credenziali del servizio Web. |
| [Report Builder](https://marketing.adobe.com/resources/help/en_US/arb/setup.html) | Consente ai membri di questo gruppo di accedere alle [!UICONTROL Report Builder] licenze. |
| [Accesso in Analysis Workspace](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/) | Consente agli utenti di accedere ad Analysis Workspace, l’interfaccia di reporting consigliata per [!DNL Adobe Analytics]. |
| [Reports &amp; Analytics](https://marketing.adobe.com/resources/help/en_US/sc/user/) | Consente agli utenti di accedere a Reporting e analisi. |
| [Creazione della metrica calcolata](https://marketing.adobe.com/resources/help/en_US/analytics/calcmetrics/) | Consente agli utenti di creare metriche calcolate. |
| [Creazione di segmenti](https://marketing.adobe.com/resources/help/en_US/analytics/segment/) | Consente agli utenti di creare segmenti. |
| **Data Connectors** |  |
| Integrazioni (Crea, Aggiorna o Elimina) | Concede l'autorizzazione per creare, aggiornare ed eliminare integrazioni del connettore dati. |
