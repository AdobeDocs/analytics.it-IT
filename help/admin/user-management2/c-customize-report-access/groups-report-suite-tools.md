---
description: Attiva le autorizzazioni degli utenti per Accesso API, Gestione suite di rapporti, Strumenti e rapporti ed elementi del dashboard.
keywords: gruppi;autorizzazioni
subtopic: Users and groups
title: Personalizzare le autorizzazioni degli strumenti delle suite di rapporti
feature: Strumenti di amministrazione
uuid: 3c95d296-ffd0-4971-9c5f-110ddbe042ce
exl-id: 8b776055-66a5-4ada-8d92-391c50a1d4f1
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '1145'
ht-degree: 15%

---

# Personalizzare le autorizzazioni degli strumenti delle suite di rapporti

>[!IMPORTANT]
>
>La gestione di utenti e prodotti sta passando all&#39; [Admin Console](https://helpx.adobe.com/it/enterprise/using/admin-console.html). Adobe ti avviserà quando è il tuo momento di eseguire la migrazione degli utenti. Dopo la migrazione di tutti i clienti, i contenuti della guida per **[!UICONTROL Analytics]** > **[!UICONTROL Admin Tools]** > **[!UICONTROL User Management]** verranno ritirati.

Attiva le autorizzazioni degli utenti per Accesso API, Gestione suite di rapporti, Strumenti e rapporti ed elementi del dashboard.

**[!UICONTROL User Management]** >  **[!UICONTROL Groups]** >  **[!UICONTROL Report Access]** >  **[!UICONTROL Report Suite Tools]** >  **[!UICONTROL Customize]**

La pagina [!UICONTROL Customize Report Suite Tools] consente ai membri di un gruppo di accedere ai seguenti elementi.

![](assets/report-suite-tools.png)

## Descrizioni campo

Le impostazioni di questa pagina si riferiscono alle suite di rapporti selezionate nella pagina [!UICONTROL Define User Groups] .

| Elemento | Descrizione |
|--- |--- |
| **Servizi web** |  |
| Queste impostazioni consentono agli utenti di effettuare chiamate al metodo Data Warehouse e di richiamare le impostazioni della suite di rapporti. |  |
| Data Warehouse | Consente a un utente non amministratore di effettuare chiamate utilizzando i metodi Data Warehouse tramite l’API dei servizi Web. Consulta [Data Warehouse - Documentazione per sviluppatori](/help/export/data-warehouse/data-warehouse.md) |
| Suite di rapporti (lettura) | Consente a un utente non amministratore di utilizzare i metodi della suite di rapporti nell’API. |
| Suite di rapporti (scrittura) | Consente a un utente non amministratore di utilizzare i metodi della suite di rapporti nell’API. |
| **Gestione delle suite di rapporti** |  |
| Queste impostazioni consentono l&#39;accesso alle voci di menu in Amministratore > Suite di rapporti > Modifica impostazioni ([Report Suite Manager](/help/admin/c-manage-report-suites/report-suites-admin.md)). |  |
| [Gestione traffico](/help/admin/c-traffic-management/traffic-management.md) | Concede l&#39;autorizzazione alla gestione del traffico. |
| [Gestione delle suite di rapporti](/help/admin/c-manage-report-suites/report-suites-admin.md) | Consente di gestire le suite di rapporti. |
| [Riepilogo account](/help/admin/admin/general-acct-settings-admin.md) | Consente di modificare le impostazioni account per una suite di rapporti. |
| [Filtri URL](/help/admin/admin/internal-url-filter-admin.md) | Concede l’autorizzazione a Filtri URL interni nelle suite di rapporti. I filtri URL interni vengono utilizzati per determinare quali riferimenti, o pagine di riferimento, sono interni al sito. |
| [Calendario personalizzato](/help/admin/admin/custom-calendar.md) | Consente di modificare il calendario personalizzato. |
| [Ricerca a pagamento](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/paid-search-detection/paid-search-detection.html) | La funzione Rilevamento ricerca a pagamento differenzia le ricerche naturali nei report Motori di ricerca e Parole chiave di ricerca. |
| [Personalizzazione del menu](/help/admin/admin/customize-menus.md) | Personalizzare i menu dei rapporti visualizzati da un utente in Reports &amp; Analytics. |
| [Configurazione rapporti in tempo reale](/help/admin/admin/realtime/t-realtime-admin.md) | Autorizzazioni per configurare report in tempo reale Analytics. |
| [Impostazioni video](/help/admin/admin/video-management.md) | Autorizzazioni per designare un set di variabili di conversione personalizzate (eVar) ed eventi personalizzati da utilizzare nel tracciamento e nel reporting sui video. |
| [Classificazioni video](https://docs.adobe.com/content/help/it-IT/media-analytics/using/media-overview.html) | Autorizzazione a designare un set di Variabili di conversione personalizzate (eVar) ed Eventi personalizzati da utilizzare nel tracciamento e nel reporting sui video. |
| [Variabili di traffico](/help/admin/admin/c-traffic-variables/traffic-var.md) | Autorizzazione per correlare dati personalizzati con eventi specifici relativi al traffico. |
| [Classificazioni traffico](/help/admin/admin/c-traffic-variables/traffic-classifications.md) | Consolidato in Classificazioni (in Strumenti e Rapporti). |
| [Canali](/help/components/c-marketing-channels/analyze-mc.md) | Consente l&#39;autorizzazione alle impostazioni del canale di marketing in Report Suite Manager > Edit Settings (Modifica impostazioni) > Marketing Channels (Canali di marketing). |
| [Costi](https://docs.adobe.com/content/help/en/analytics/components/marketing-channels/analyze-mc.html) | Consente l&#39;autorizzazione a Marketing Channels (Canali di marketing) > Marketing Channel Cost (Costi canale di marketing) nel Report Suite Manager (Gestore suite di rapporti). |
| [Variabili di conversione](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) | La variabile di conversione Custom Insight (o eVar) viene inserita nel codice di Adobe nelle pagine Web selezionate del sito. Il suo scopo principale è segmentare le metriche di successo della conversione nei rapporti di marketing personalizzati. |
| [Metodi di ricerca](/help/admin/admin/finding-methods.md) | Consente di identificare in che modo i rapporti sui vari metodi di ricerca ricevono credito per gli eventi di successo della conversione sul sito. |
| [Classificazioni di conversione](/help/admin/admin/conversion-var-admin/conversion-classifications.md) | Consolidato in Classificazioni (in Strumenti e Rapporti). |
| [Visitatore univoco](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/unique-visitor-variable/t-unique-visitor-variable.html) | Consente di specificare la variabile Visitatore univoco. |
| [Eventi di successo](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/success-events/success-event.html) | Azioni che possono essere tracciate, ad esempio visualizzazione del prodotto, pagamento e acquisto. |
| [Gerarchie di classificazione](/help/admin/admin/conversion-var-admin/classification-hierarchies.md) | Consolidato in Classificazioni (in Strumenti e Rapporti). |
| [Variabili elenco](https://docs.adobe.com/content/help/it-IT/analytics/implementation/vars/page-vars/page-variables.html) | Noto anche come Var elenco . Analogamente alla funzione Proprietà elenco, le Var elenco consentono più valori all’interno della stessa richiesta di immagine. |
| [Metriche predefinite](/help/admin/admin/default-metrics.md) | Reports &amp; Analytics visualizza un set predefinito di metriche in tutti i rapporti di conversione, a meno che un utente non selezioni un set personalizzato di metriche. Le metriche selezionate vengono visualizzate per tutti gli utenti della suite di rapporti associata. |
| [Regole di elaborazione](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/processing-rules/processing-rules.html) | Consente l’accesso alle Regole di elaborazione, che semplificano la raccolta dei dati e gestiscono il contenuto mentre viene inviato ai rapporti. |
| **Strumenti e rapporti** |  |
| [Rilevamento delle anomalie](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/virtual-analyst/anomaly-detection/anomaly-detection.html) | Concede l’autorizzazione a Rilevamento anomalie, che fornisce un metodo statistico per determinare la variazione di una data metrica rispetto ai dati precedenti. |
| [Rapporto canale](/help/components/c-marketing-channels/analyze-mc.md) | Concede l&#39;autorizzazione ai rapporti sul canale di marketing, disponibili in Report > Rapporti sul canale di marketing. |
| [Rapporto in tempo reale](/help/admin/admin/realtime/t-realtime-admin.md) | Consente l&#39;accesso al report in tempo reale. |
| [Pagine bot](/help/admin/admin/bot-removal/bot-rules.md) | **Nota: Le pagine dei bot sono per report specifici di Reports &amp; Analytics e non per la gestione delle regole dei bot. Al momento, non è disponibile alcuna autorizzazione per consentire la modifica delle regole bot.** Le regole bot consentono di rimuovere dalla suite di rapporti il traffico generato da spider e bot noti. La rimozione del traffico da bot può fornire una misurazione più precisa dell’attività degli utenti sul sito web. |
| [Bot](/help/admin/admin/bot-removal/bot-rules.md) | **Nota: I bot sono per report specifici di Reports &amp; Analytics, non per la gestione delle regole bot. Al momento, non è disponibile alcuna autorizzazione per consentire la modifica delle regole bot.** I bot ti consentono di rimuovere il traffico generato da spider e bot noti dalla suite di rapporti. La rimozione del traffico da bot può fornire una misurazione più precisa dell’attività degli utenti sul sito web. |
| [Rapporto Data Warehouse personalizzato](/help/export/data-warehouse/data-warehouse.md) | Data warehouse si basa su copie di dati grezzi e non ancora elaborati per l&#39;archiviazione e la creazione di report personalizzati, che puoi eseguire filtrando i dati. Puoi chiedere ai rapporti di visualizzare relazioni avanzate tra i dati, partendo da dati grezzi basati su tue domande specifiche. |
| Visite giornaliere di ritorno | (Legacy) Report che visualizza il numero di visitatori del sito web più di una volta al giorno specificato. Un giorno è definito come l’ultimo periodo di 24 ore. |
| [Origini dati Manager](/help/admin/admin/data-sources.md) | La funzione Origini dati ti consente di importare dati in Analytics da origini offline. |
| [Escludi per indirizzo IP](/help/admin/admin/exclude-ip.md) | Puoi escludere dai rapporti i dati da indirizzi IP specifici, ad esempio attività interne del sito web, test del sito e utilizzo dei dipendenti. |
| ClickMap legacy | Consente di accedere al menu per lo strumento di sovrapposizione ClickMap legacy. |
| Installazione legacy di ClickMap | Concede i diritti di installazione allo strumento ClickMap legacy. |
| Visite di ritorno | Un rapporto che mostra il numero di visite in cui il numero di visite è maggiore di 1. Il rapporto Visite di ritorno include i visitatori non cookie. |
| [Importazione](https://docs.adobe.com/content/help/it-IT/analytics/components/classifications/classifications-importer/c-working-with-saint.html) /esportazione classificazioni e Generatore di  [regole](https://docs.adobe.com/content/help/it-IT/analytics/components/classifications/classifications-rulebuilder/classification-rule-builder.html) | Consolidato in classificazioni (vedi di seguito). |
| Gestione feed dati | Concede i diritti al feed di dati di Analytics. |
| Classificazioni | Combina le seguenti autorizzazioni: &quot;Classificazioni traffico&quot;, &quot;Classificazioni video&quot;, &quot;Classificazioni conversione&quot;, &quot;Gerarchie di classificazione&quot;, &quot;Gestione classificazioni&quot; e &quot;Importazione/esportazione classificazioni e generatore di regole&quot;.  Nota:  Con questa autorizzazione, gli utenti modificano le classificazioni per tutte le suite di rapporti, non solo per quelle selezionate. |
| [Analisi contributi](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/virtual-analyst/contribution-analysis/ca-tokens.html) | Concede i diritti per l’utilizzo di Analisi contributi in Analysis Workspace. |
| **Elementi del dashboard** |  |
| Le impostazioni in Elementi dashboard consentono l&#39;accesso ai [minirapporti](https://docs.adobe.com/content/help/en/analytics/admin/server-call-usage/server-call-usage-dashboard.html) in Reports &amp; Analytics:, I miei report consigliati, Report di riepilogo della società, Immagine, KPI/Reportlet di analisi, Totali delle suite di rapporti, Testo, Reportlet, Report di riepilogo dell&#39;utilizzo e risorse Web |  |
| **Altre** |  |
| Social | Controlla l&#39;accesso al menu Gestione social in Report Suite Manager. |
