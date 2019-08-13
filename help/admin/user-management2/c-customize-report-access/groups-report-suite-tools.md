---
description: Abilitare le autorizzazioni utente per Accesso API, Gestione suite di rapporti, Strumenti e rapporti e Elementi Dashboard.
keywords: gruppi; permissions
seo-description: Abilitare le autorizzazioni utente per Accesso API, Gestione suite di rapporti, Strumenti e rapporti e Elementi Dashboard.
seo-title: Personalizzare le autorizzazioni degli strumenti delle suite di rapporti
solution: Analytics
subtopic: Utenti e gruppi
title: Personalizzare le autorizzazioni degli strumenti delle suite di rapporti
topic: Strumenti di amministrazione
uuid: 3 c 95 d 296-ffd 0-4971-9 c 5 f -110 ddbe 042 ce
translation-type: tm+mt
source-git-commit: 01ac0011f2e47e6798a520df8ffe5d8393ac0c3c

---


# Personalizzare le autorizzazioni degli strumenti delle suite di rapporti

>[!IMPORTANT]
>
>La gestione di utenti e prodotti passa ad [Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html). Adobe ti informerà quando sarà il momento di eseguire la migrazione degli utenti. Dopo che tutti i clienti avranno trasferito, il contenuto della guida per **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin Tools]** &gt; **[!UICONTROL User Management]** verrà ritirato.

Abilitare le autorizzazioni utente per Accesso API, Gestione suite di rapporti, Strumenti e rapporti e Elementi Dashboard.

**[!UICONTROL User Management]** &gt; **[!UICONTROL Groups]** &gt; **[!UICONTROL Report Access]** &gt; **[!UICONTROL Report Suite Tools]** &gt; **[!UICONTROL Customize]**

[!UICONTROL Customize Report Suite Tools] La pagina concede ai membri di un gruppo l'accesso ai seguenti elementi.

![](assets/report-suite-tools.png)

## Descrizioni campo

Le impostazioni di questa pagina interessano le suite di rapporti selezionate sulla [!UICONTROL Define User Groups] pagina.

| Elemento | Descrizione |
|--- |--- |
| **Servizi web** |  |
| Queste impostazioni consentono agli utenti di effettuare chiamate al metodo Data Warehouse ed eseguire il pull delle impostazioni della suite di rapporti. |  |
| Data Warehouse | Consente a un utente non amministratore di effettuare chiamate utilizzando i metodi Data Warehouse tramite l'API dei servizi Web. Consulta [Data Warehouse - Documentazione per sviluppatori](/help/export/data-warehouse/data-warehouse.md) |
| Suite di rapporti (Leggi) | Consente a un utente non amministratore di utilizzare i metodi delle suite di rapporti nell'API. |
| Suite di rapporti (scrittura) | Consente a un utente non amministratore di utilizzare i metodi delle suite di rapporti nell'API. |
| **Gestione delle suite di rapporti** |  |
| Queste impostazioni consentono di accedere alle voci di menu in Admin (Amministratore) &gt; Report Suites (Suite di rapporti) &gt; Edit Settings (Modifica impostazioni) ([Report Suite Manager,](../../../admin/c-manage-report-suites/report-suites-admin.md)Modifica suite di rapporti). |  |
| [Gestione traffico](../../../admin/c-traffic-management/traffic-management.md) | Concede l'autorizzazione alla gestione traffico. |
| [Gestione delle suite di rapporti](../../../admin/c-manage-report-suites/report-suites-admin.md) | Concede l'autorizzazione per gestire le suite di rapporti. |
| [Riepilogo account](../../../admin/admin/general-acct-settings-admin.md) | Concede l'autorizzazione per modificare le impostazioni dell'account per una suite di rapporti. |
| [Filtri URL](../../../admin/admin/internal-url-filter-admin.md) | Concede l'autorizzazione a Filtri URL interni nelle suite di rapporti. I filtri URL interni sono utilizzati per determinare quali riferimenti o pagine di riferimento sono interni al sito. |
| [Calendario personalizzato](../../../admin/admin/custom-calendar.md) | Concede l'autorizzazione per modificare il calendario personalizzato. |
| [Ricerca pagata](https://marketing.adobe.com/resources/help/en_US/reference/paid_search_detection.html) | Il rilevamento della ricerca a pagamento viene differenziato dalle ricerche naturali nei report Motore di ricerca e Cerca parole chiave. |
| [Personalizzazione del menu](../../../admin/admin/customize-menus.md) | Personalizzate i menu dei report che un utente vede in Reporting e analisi. |
| [Configurazione dei report in tempo reale](../../../admin/admin/realtime/t-realtime-admin.md) | Autorizzazioni per configurare report in tempo reale Analytics. |
| [Impostazioni video](../../../admin/admin/video-management.md) | Autorizzazioni per designare un set di variabili conversione personalizzate (evar) e eventi personalizzati da utilizzare per il tracciamento e la creazione di rapporti sui video. |
| [Classificazioni video](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/video/video_config.html) | Autorizzazione per designare un set di variabili di conversione personalizzate (evar) e eventi personalizzati da utilizzare per il tracciamento e la creazione di rapporti sui video. |
| [Variabili di traffico](../../../admin/admin/c-traffic-variables/traffic-var.md) | Autorizzazione per correlare dati personalizzati con eventi correlati al traffico. |
| [Classificazioni traffico](/help/admin/admin/c-traffic-variables/traffic-classifications.md) | Consolidato in Classificazioni (in Strumenti e Rapporti). |
| [Canali](https://marketing.adobe.com/resources/help/en_US/mchannel/index.html) | Concede l'autorizzazione alle impostazioni Canale marketing in Gestore suite di rapporti &gt; Modifica impostazioni &gt; Canali marketing. |
| [Costi](https://marketing.adobe.com/resources/help/en_US/mchannel/c_overview_budget.html) | Abilita l'autorizzazione per Marketing Channels (Canali di marketing) &gt; Marketing Channel Costs (Costi canale di marketing) in Report Suite Manager (Gestore suite di rapporti). |
| [Variabili di conversione](../../../admin/admin/conversion-var-admin/conversion-var-admin.md) | La variabile di conversione personalizzata (o evar) viene inserita nel codice Adobe sulle pagine Web selezionate del sito. Il suo scopo primario è quello di segmentare le metriche di successo conversione nei report di marketing personalizzati. |
| [Metodi di ricerca](../../../admin/admin/finding-methods.md) | Consente di identificare il modo in cui i rapporti di ricerca ricevono credito per gli eventi di successo di conversione sul sito. |
| [Classificazioni conversione](../../../admin/admin/conversion-var-admin/conversion-classifications.md) | Consolidato in Classificazioni (in Strumenti e Rapporti). |
| [Visitatore univoco](https://marketing.adobe.com/resources/help/en_US/reference/t_unique_visitor_variable.html) | Concede l'autorizzazione per specificare la variabile Visitatore univoco. |
| [Eventi di successo](https://marketing.adobe.com/resources/help/en_US/reference/success_event.html) | Azioni che possono essere monitorate, ad esempio visualizzazione prodotto, ritiro e acquisto. |
| [Gerarchie di classificazione](../../../components/c-classifications2/classification-hierarchies.md) | Consolidato in Classificazioni (in Strumenti e Rapporti). |
| [Variabili elenco](https://marketing.adobe.com/resources/help/en_US/sc/implement/listN.html) | Noto anche come Var elenco. Analogamente alla funzione Elenco proprietà, le variabili elenco consentono più valori all'interno della stessa richiesta di immagine. |
| [Metriche predefinite](../../../admin/admin/default-metrics.md) | Reporting e analisi visualizza un set predefinito di metriche in tutti i rapporti sulla conversione, a meno che un utente non selezioni un set personalizzato di metriche. Le metriche selezionate vengono visualizzate per tutti gli utenti della suite di rapporti associata. |
| [Regole di elaborazione](https://marketing.adobe.com/resources/help/en_US/sc/implement/ref-processing-rules.html) | Concede l'accesso alle regole di elaborazione, semplificando la raccolta di dati e gestendo i contenuti durante l'invio ai rapporti. |
| **Strumenti e rapporti** |  |
| [Rilevamento delle anomalie](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/anomaly_detection.html) | Concede l'autorizzazione a Rilevamento anomalie, che fornisce un metodo statistico per determinare in che modo una particolare metrica è cambiata rispetto ai dati precedenti. |
| [Report canale](https://marketing.adobe.com/resources/help/en_US/mchannel/index.html) | Concede l'autorizzazione ai rapporti Canale di marketing, disponibili in Rapporti &gt; Rapporti canale marketing. |
| [Report in tempo reale](../../../admin/admin/realtime/t-realtime-admin.md) | Consente l'accesso al report in tempo reale. |
| [Pagine bot](../../../admin/admin/bot-removal/bot-rules.md#concept_A306689C65EB4D0F9AE65E3FD48ED5F7) | Regole bot consente di rimuovere il traffico generato da spider noti e bot dalla suite di rapporti. La rimozione del traffico bot permette di misurare meglio l'attività degli utenti sul sito Web. |
| [Bot](../../../admin/admin/bot-removal/bot-rules.md) | Regole bot consente di rimuovere il traffico generato da spider noti e bot dalla suite di rapporti. La rimozione del traffico bot permette di misurare meglio l'attività degli utenti sul sito Web. |
| [Report personalizzato Data Warehouse](../../..//export/data-warehouse/data-warehouse.md) | Data warehouse si basa su copie di dati grezzi e non ancora elaborati per l'archiviazione e la creazione di report personalizzati, che puoi eseguire filtrando i dati. Puoi chiedere ai report di visualizzare relazioni avanzate tra i dati, partendo da dati grezzi basati su tue precise domande. |
| [Visite giornaliere di ritorno](../../../components/c-variables/dimensionslist/reports-daily-return-visits.md) | (Legacy) Report che mostra il numero di visitatori sul sito Web più di una volta in un dato giorno. Un giorno è definito come ultimo periodo di 24 ore. |
| [Origini dati Manager](../../../admin/admin/data-sources.md) | La funzione Origini dati consente di importare dati in Analytics da fonti offline. |
| [Escludi per indirizzo IP](../../../admin/admin/exclude-ip.md) | Dai rapporti potete escludere dati da indirizzi IP specifici, ad esempio attività interne al sito Web, test di siti e uso dei dipendenti. |
| Clickmap legacy | Consente di accedere al menu per lo strumento di sovrapposizione clickmap legacy. |
| Installazione clickmap precedente | Concede diritti di installazione allo strumento clickmap precedente. |
| [Visite di ritorno](../../../components/c-variables/dimensionslist/reports-return-visits.md) | Un rapporto che mostra il numero di visite in cui il numero di visite è maggiore di 1. Il report Return Visits (Visite di ritorno) include i visitatori non cooker. |
| [Importazione](https://marketing.adobe.com/resources/help/en_US/reference/c_working_with_saint.html) /esportazione di classificazioni e [Generatore di regole](https://marketing.adobe.com/resources/help/en_US/reference/classification_rule_builder.html) | Consolidato in Classificazioni (vedi di seguito). |
| Feed Feed Manager | Concede diritti al feed dati di Analytics. |
| Classificazioni | Combina le seguenti autorizzazioni: «Classificazioni traffico», «Classificazioni video», «Classificazioni conversione», «Gerarchie classificazione», «Gestione classificazioni» e «Importazione/esportazione classificazioni e Strumento di creazione regola». Nota: Con questa autorizzazione, gli utenti modificano le classificazioni per tutte le suite di rapporti, non solo per quelle selezionate. |
| [Analisi contributi](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/contribution-analysis.html) | Concede i diritti per l'utilizzo di Analisi contributi in Analysis Workspace. |
| **Elementi dashboard** |  |
| Le impostazioni in Elementi dashboard consentono di accedere ai [minirapporti](https://marketing.adobe.com/resources/help/en_US/sc/user/dashboard.html) in Reporting e analisi: , My Recommended Reports, Company Summary Reportlet, Image, KPI/Amount Reportlet, Report Suite Totals, Text, Reportlet, Usage Summary Reportlet e Web Resources |  |
| **Altro** |  |
| Social | Controlla l'accesso al menu Gestione social network nel Report Suite Manager (Gestione suite di rapporti). |
