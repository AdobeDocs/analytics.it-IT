---
description: Abilitate le autorizzazioni utente per Accesso API, Gestione suite di rapporti, Strumenti e rapporti ed Elementi dashboard.
keywords: groups;permissions
subtopic: Users and groups
title: Personalizzare le autorizzazioni degli strumenti delle suite di rapporti
topic: Admin tools
uuid: 3c95d296-ffd0-4971-9c5f-110ddbe042ce
translation-type: tm+mt
source-git-commit: 89a5524ac0e96d63acd54c2ef3e22c17314f332d
workflow-type: tm+mt
source-wordcount: '1141'
ht-degree: 15%

---


# Personalizzare le autorizzazioni degli strumenti delle suite di rapporti

>[!IMPORTANT]
>
>La gestione di utenti e prodotti sta passando al [Admin Console](https://helpx.adobe.com/it/enterprise/using/admin-console.html).  Adobe ti avviserà quando è il momento di eseguire la migrazione degli utenti. Dopo la migrazione di tutti i clienti, i contenuti della guida per **[!UICONTROL Analytics]** > **[!UICONTROL Admin Tools]** > **[!UICONTROL User Management]** verranno ritirati.

Abilitate le autorizzazioni utente per Accesso API, Gestione suite di rapporti, Strumenti e rapporti ed Elementi dashboard.

**[!UICONTROL User Management]** > **[!UICONTROL Groups]** > **[!UICONTROL Report Access]** > **[!UICONTROL Report Suite Tools]** > **[!UICONTROL Customize]**

La [!UICONTROL Customize Report Suite Tools] pagina consente ai membri di un gruppo di accedere ai seguenti elementi.

![](assets/report-suite-tools.png)

## Descrizioni dei campi

Le impostazioni di questa pagina si riferiscono alle suite di rapporti selezionate sulla [!UICONTROL Define User Groups] pagina.

| Elemento | Descrizione |
|--- |--- |
| **Servizi web** |  |
| Queste impostazioni consentono agli utenti di effettuare chiamate al metodo di Data Warehouse e di richiamare le impostazioni della suite di rapporti. |  |
| Data Warehouse | Consente a un utente non amministratore di effettuare chiamate utilizzando i metodi di Data Warehouse tramite l&#39;API dei servizi Web. Vedere [Data Warehouse - Documentazione per sviluppatori](/help/export/data-warehouse/data-warehouse.md) |
| Suite di rapporti (lettura) | Consente a un utente non amministratore di utilizzare i metodi della suite di rapporti nell&#39;API. |
| Suite di rapporti (scrittura) | Consente a un utente non amministratore di utilizzare i metodi della suite di rapporti nell&#39;API. |
| **Gestione delle suite di rapporti** |  |
| Queste impostazioni concedono l&#39;accesso alle voci di menu in Amministratore > Suite di rapporti > Modifica impostazioni ([Report Suite Manager](/help/admin/c-manage-report-suites/report-suites-admin.md)). |  |
| [Gestione traffico](/help/admin/c-traffic-management/traffic-management.md) | Concede l&#39;autorizzazione alla gestione del traffico. |
| [Gestione delle suite di rapporti](/help/admin/c-manage-report-suites/report-suites-admin.md) | Concede l&#39;autorizzazione per gestire le suite di rapporti. |
| [Riepilogo account](/help/admin/admin/general-acct-settings-admin.md) | Consente di modificare le impostazioni dell&#39;account per una suite di rapporti. |
| [Filtri URL](/help/admin/admin/internal-url-filter-admin.md) | Concede l&#39;autorizzazione ai filtri URL interni nelle suite per report. I filtri URL interni vengono utilizzati per determinare quali riferimenti, o pagine di riferimento, sono interni al sito. |
| [Calendario personalizzato](/help/admin/admin/custom-calendar.md) | Consente di modificare il calendario personalizzato. |
| [Ricerca pagata](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/paid-search-detection/paid-search-detection.html) | La funzione Rilevamento ricerca a pagamento si distingue dalle ricerche naturali nei report Motori di ricerca e Parole chiave di ricerca. |
| [Personalizzazione menu](/help/admin/admin/customize-menus.md) | Personalizzare i menu dei rapporti visualizzati da un utente in Reporting e analisi. |
| [Configurazione report in tempo reale](/help/admin/admin/realtime/t-realtime-admin.md) | Autorizzazioni per l&#39;impostazione di report in tempo reale Analytics. |
| [Impostazioni video](/help/admin/admin/video-management.md) | Autorizzazioni per specificare un set di variabili di conversione personalizzate (eVar) ed eventi personalizzati da utilizzare nel tracciamento e nella generazione di rapporti sui video. |
| [Classificazioni video](https://docs.adobe.com/content/help/it-IT/media-analytics/using/media-overview.html) | Autorizzazione per specificare un set di variabili di conversione personalizzate (eVar) ed eventi personalizzati da utilizzare nel monitoraggio e nel reporting sui video. |
| [Variabili di traffico](/help/admin/admin/c-traffic-variables/traffic-var.md) | Autorizzazione per correlare dati personalizzati con eventi specifici relativi al traffico. |
| [Classificazioni traffico](/help/admin/admin/c-traffic-variables/traffic-classifications.md) | Consolidato in Classificazioni (in Strumenti e Rapporti). |
| [Canali](/help/components/c-marketing-channels/analyze-mc.md) | Consente di accedere alle impostazioni Marketing Channel in Report Suite Manager > Edit Settings > Marketing Channels (Modifica impostazioni > Canali di marketing). |
| [Costi](https://docs.adobe.com/content/help/en/analytics/components/marketing-channels/analyze-mc.html) | Consente l&#39;autorizzazione a Marketing Channels (Canali di marketing) > Marketing Channel Cost (Costi canale di marketing) in Report Suite Manager (Gestore suite di rapporti). |
| [Variabili di conversione](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) | La variabile di conversione Custom Insight (o eVar ) viene inserita nel codice di  Adobe in pagine Web selezionate del sito. Il suo scopo principale è segmentare le metriche di successo della conversione nei report di marketing personalizzati. |
| [Metodi di ricerca](/help/admin/admin/finding-methods.md) | Consente di identificare il modo in cui i vari rapporti sui metodi di ricerca ricevono credito per gli eventi di successo di conversione sul sito. |
| [Classificazioni conversione](/help/admin/admin/conversion-var-admin/conversion-classifications.md) | Consolidato in Classificazioni (in Strumenti e Rapporti). |
| [Visitatore unico](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/unique-visitor-variable/t-unique-visitor-variable.html) | Concede l&#39;autorizzazione per specificare la variabile Visitatore univoco. |
| [Eventi di successo](https://docs.adobe.com/content/help/it-IT/analytics/admin/admin-tools/success-events/success-event.html) | Azioni che possono essere tracciate, come la visualizzazione del prodotto, il checkout e l&#39;acquisto. |
| [Gerarchie classificazione](/help/admin/admin/conversion-var-admin/classification-hierarchies.md) | Consolidato in Classificazioni (in Strumenti e Rapporti). |
| [Variabili elenco](https://docs.adobe.com/content/help/it-IT/analytics/implementation/vars/page-vars/page-variables.html) | Noto anche come Var elenco. Analogamente alla funzione Elenco proprietà, le Var elenco consentono più valori all’interno della stessa richiesta di immagine. |
| [Metriche predefinite](/help/admin/admin/default-metrics.md) | Reporting e analisi visualizza un set predefinito di metriche in tutti i report di conversione, a meno che un utente non selezioni un set personalizzato di metriche. Le metriche selezionate vengono visualizzate per tutti gli utenti della suite di rapporti associata. |
| [Regole di elaborazione](https://docs.adobe.com/content/help/it-IT/analytics/admin/admin-tools/processing-rules/processing-rules.html) | Consente l&#39;accesso alle regole di elaborazione, che semplificano la raccolta dei dati e gestiscono il contenuto durante l&#39;invio ai report. |
| **Strumenti e rapporti** |  |
| [Rilevamento delle anomalie](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/virtual-analyst/anomaly-detection/anomaly-detection.html) | Concede l&#39;autorizzazione al rilevamento delle anomalie, che fornisce un metodo statistico per determinare in che modo una determinata metrica è cambiata rispetto ai dati precedenti. |
| [Report canale](/help/components/c-marketing-channels/analyze-mc.md) | Concede l&#39;autorizzazione per i rapporti sul canale di marketing, disponibile in Rapporti > Rapporti sul canale di marketing. |
| [Report in tempo reale](/help/admin/admin/realtime/t-realtime-admin.md) | Consente l&#39;accesso al report in tempo reale. |
| [Pagine bot](/help/admin/admin/bot-removal/bot-rules.md) | **Nota: Le pagine dei bot sono per report Reporting e analisi specifici, non per la gestione delle regole bot. Al momento, non è disponibile l&#39;autorizzazione per consentire la modifica delle regole bot.** Le regole bot consentono di rimuovere il traffico generato da spider e bot noti dalla suite di rapporti. La rimozione del traffico bot può fornire una misurazione più precisa dell’attività degli utenti sul sito Web. |
| [Bot](/help/admin/admin/bot-removal/bot-rules.md) | **Nota: I bot sono per report Reporting e analisi specifici, non per la gestione delle regole bot. Al momento, non è disponibile l&#39;autorizzazione per consentire la modifica delle regole bot.** I bot consentono di rimuovere il traffico generato da ragni e bot noti dalla suite di rapporti. La rimozione del traffico bot può fornire una misurazione più precisa dell’attività degli utenti sul sito Web. |
| [Report Data Warehouse personalizzata](/help/export/data-warehouse/data-warehouse.md) | Data warehouse si basa su copie di dati grezzi e non ancora elaborati per l&#39;archiviazione e la creazione di report personalizzati, che puoi eseguire filtrando i dati. Puoi chiedere ai report di visualizzare relazioni avanzate tra i dati, partendo da dati grezzi basati su tue precise domande. |
| Visite giornaliere di ritorno | (Legacy) Report che visualizza il numero di visitatori del sito Web più di una volta in un dato giorno. Un giorno è definito come l’ultimo periodo di 24 ore. |
| [Origini dati Manager](/help/admin/admin/data-sources.md) | La funzione Origini dati consente di importare dati in Analytics da origini offline. |
| [Escludi per indirizzo IP](/help/admin/admin/exclude-ip.md) | Puoi escludere dai rapporti i dati da indirizzi IP specifici, ad esempio attività interne sul sito Web, test del sito e utilizzo dei dipendenti. |
| ClickMap precedenti | Consente l&#39;accesso al menu per lo strumento sovrapposizione ClickMap legacy. |
| Installazione di Clickmap legacy | Concede i diritti di installazione allo strumento ClickMap legacy. |
| Visite di ritorno | Un rapporto che mostra il numero di visite in cui il numero di visite è maggiore di 1. Il rapporto Return Visits (Visite di ritorno) include i visitatori non inclusi nel cookie. |
| [Importatore](https://docs.adobe.com/content/help/it-IT/analytics/components/classifications/classifications-importer/c-working-with-saint.html) classificazioni / Esportatore e Generatore di [regole](https://docs.adobe.com/content/help/it-IT/analytics/components/classifications/classifications-rulebuilder/classification-rule-builder.html) | Consolidato in Classificazioni (vedi sotto). |
| Gestione feed dati | Concede i diritti al feed di dati di Analytics. |
| Classificazioni | Combina le seguenti autorizzazioni: &quot;Classificazioni traffico&quot;, &quot;Classificazioni video&quot;, &quot;Classificazioni conversione&quot;, &quot;Gerarchie classificazione&quot;, &quot;Gestione classificazioni&quot; e &quot;Importazione/Esportatore classificazioni e Generatore regole&quot;.  Nota:  Con questa autorizzazione, gli utenti possono modificare le classificazioni per tutte le suite di rapporti, non solo per quelle selezionate. |
| [Analisi contributi](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/virtual-analyst/contribution-analysis/ca-tokens.html) | Concede i diritti per l’utilizzo di Contribution Analysis in  Analysis Workspace. |
| **Elementi dashboard** |  |
| Le impostazioni in Elementi dashboard consentono l&#39;accesso ai [minirapporti](https://docs.adobe.com/content/help/en/analytics/admin/server-call-usage/server-call-usage-dashboard.html) in Reporting e analisi:, Report consigliati, Report riepilogo società, Immagine, Report KPI/Gage, Totali suite di rapporti, Testo, Report, Report di riepilogo dell&#39;uso e Risorse Web |  |
| **Altre** |  |
| Social | Controlla l&#39;accesso al menu Gestione social network in Report Suite Manager. |
