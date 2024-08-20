---
product: analytics
audience: admin
user-guide-title: Guida dell’amministratore di Analytics
breadcrumb-title: Guida dell’amministratore
user-guide-description: Scopri le attività di amministrazione di Analytics, come gestire utenti e prodotti nell’Admin Console di Experience Cloud, configurare suite di rapporti e altro ancora.
source-git-commit: 38478fbccf7680e5b404b306136594e627d09a08
workflow-type: ht
source-wordcount: '626'
ht-degree: 100%

---


# Guida dell’amministratore di Adobe Analytics {#admin}

+ [Guida dell’amministratore di Analytics](home.md)
+ [Note sulla versione di Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=it)
+ Adobe Admin Console {#admin-console}
   + [Panoramica](admin-console/home.md)
   + [Prima guida dell’amministratore di Adobe Analytics](admin-console/first-admin-guide.md)
   + [Ruoli di amministratore in Adobe Analytics](admin-console/admin-roles-in-analytics.md)
   + Riepilogo delle autorizzazioni degli strumenti Analytics {#permissions}
      + [Profili di prodotto per Adobe Analytics](admin-console/permissions/product-profile.md)
      + [Autorizzazioni del profilo di prodotto per gli strumenti Report Suite](admin-console/permissions/report-suite-tools.md)
      + [Autorizzazioni del profilo di prodotto per gli strumenti Analytics](admin-console/permissions/analytics-tools.md)
+ Strumenti di amministrazione di Analytics {#admin-tools}
   + [Panoramica sugli strumenti di amministrazione](admin/c-admin-tools.md)
   + [Gestione codici](admin/code-manager-admin.md)
   + [Origini dati](admin/data-sources.md)
   + [Escludi per indirizzo IP](admin/exclude-ip.md)
   + [Registri](admin/logs.md)
   + Reporting Activity Manager {#reporting-activity-manager}
      + [Panoramica](admin/reporting-activity-manager/reporting-activity-overview.md)
      + [Visualizzare l’attività di reporting](admin//reporting-activity-manager/reporting-activity.md)
      + [Annullare le richieste di reporting](admin/reporting-activity-manager/reporting-activity-cancel-requests.md)
   + Migrazione componente {#component-migration}
      + [Prepararsi alla migrazione](admin/component-migration/prepare-component-migration.md)
      + [Flusso di lavoro della migrazione](admin/component-migration/component-migration.md)
   + Report Suite Manager {#manage-report-suites}
      + Modificare le impostazioni di una suite di rapporti {#edit-report-suite}
         + Generale {#report-suite-general}
            + [Impostazioni account generali](admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md)
            + [Filtri URL interni](admin/c-manage-report-suites/c-edit-report-suites/general/internal-url-filter-admin.md)
            + [Personalizza calendario](admin/c-manage-report-suites/c-edit-report-suites/general/custom-calendar.md)
            + Rilevamento di ricerca a pagamento {#paid-search-detection}
               + [Panoramica sul rilevamento di ricerca a pagamento](admin/c-manage-report-suites/c-edit-report-suites/general/paid-search-detection/paid-search-detection.md)
               + [Configurare il rilevamento di ricerche a pagamento](admin/c-manage-report-suites/c-edit-report-suites/general/paid-search-detection/t-paid-search-detection.md)
            + Regole di elaborazione {#c-processing-rules}
               + [Panoramica sulle regole di elaborazione](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules.md)
               + Regole di elaborazione {#c-processing-rules-configuration}
                  + [Funzionamento delle regole di elaborazione](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/c-processing-rules-configuration/processing-rules-about.md)
                  + [Creare regole di elaborazione](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/c-processing-rules-configuration/t-processing-rules.md)
                  + [Visualizzare le regole di elaborazione attive](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/c-processing-rules-configuration/t-processing-rules-view.md)
                  + [Visualizzare la cronologia delle regole di elaborazione](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/c-processing-rules-configuration/t-processing-rule-view-history.md)
                  + [Ripristinare le regole di elaborazione](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/c-processing-rules-configuration/t-processing-rules-restore.md)
                  + [Copiare le regole di elaborazione in un&#39;altra suite di rapporti](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/c-processing-rules-configuration/t-processing-rules-copy-to-rs.md)
                  + [Dimensioni disponibili per le regole di elaborazione](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rule-dimensions.md)
               + Regole di elaborazione, esempi {#processing-rules-examples}
                  + [Esempi di regole di elaborazione](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-examples.md)
                  + [Compilare un ID campagna da un parametro di stringa di query](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-populate-campaign-id.md)
                  + [Impostare l&#39;evento di visualizzazione prodotto dalla pagina di panoramica prodotto](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/setting-the-product-view-event.md)
                  + [Aggiungere una sottocategoria concatenando la categoria e il nome della pagina](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/subcategory-concatenating.md)
                  + [Determinare un percorso copiando un valore eVar in un prop](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-determining-path.md)
                  + [Pulire i valori in un rapporto](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/clean-up-values-in-a-report.md)
                  + [Compilare termini di ricerca interni utilizzando un parametro di stringa di query](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-populating-internal-search.md)
                  + [Copiare una variabile di dati di contesto in una eVar](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data.md)
                  + [Impostare un evento utilizzando una variabile di dati di contesto](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data-event.md)
                  + [Rimuovere un evento da un hit](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-remove-event.md)
               + [Suggerimenti e trucchi per le regole di elaborazione](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-tips.md)
            + Regole bot {#bot-removal}
               + [Rimozione bot](admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-removal.md)
               + [Comprendere e configurare le regole bot](admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md)
               + [Firme bot comuni](admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-signatures.md)
               + [Metodi di esclusione bot](admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-exclusion-methods.md)
            + [Impostazioni privacy](admin/c-manage-report-suites/c-edit-report-suites/general/privacy-settings.md)
            + [Configurazione delle marche temporali](admin/c-manage-report-suites/c-edit-report-suites/general/timestamp-optional.md)
            + Inoltro lato server {#server-side-forwarding}
               + [Panoramica sull&#39;inoltro lato server](admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf.md)
               + [Conformità a RGPD/ePrivacy e inoltro lato server](admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf-gdpr.md)
               + [Requisiti per l&#39;inoltro lato server](admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf-requirements.md)
               + [Dati inoltro lato server e codice](admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf-reference.md)
               + [Verificare l’implementazione dell’inoltro lato server](admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf-verify.md)
               + [Domande frequenti sull&#39;inoltro lato server](admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf-faq.md)
         + Traffico {#traffic-variables}
            + [Variabili di traffico](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/traffic-var.md)
            + [Classificazioni traffico](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/traffic-classifications.md)
            + [Descrizioni report personalizzati](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/custom-desc-admin.md)
         + Conversione {#conversion-variables}
            + [Variabili di conversione](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/conversion-var-admin.md)
            + [Metodi di ricerca](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/finding-methods.md)
            + [Classificazioni di conversione](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/conversion-classifications.md)
            + Variabile visitatore univoco {#unique-visitor-variable}
               + [Specificare la variabile Visitatore univoco](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/unique-visitor-variable-admin/t-unique-visitor-variable.md)
               + [Caso di utilizzo: estrazione degli ID visitatore](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/unique-visitor-variable-admin/extract-visitorids-usecase.md)
            + [Eventi di successo](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/success-event.md)
            + [Gerarchie di classificazione](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/classification-hierarchies.md)
            + [Variabili elenco](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/list-var-admin.md)
            + [eVar di merchandising](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/merchandising-evars.md)
         + Canali marketing {#marketing-channels}
            + [Gestore del canale di marketing](admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-channels.md)
            + [Regole di elaborazione per il canale di marketing](admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-rules.md)
            + [Classificazioni del canale di marketing](admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/classifications-mchannel.md)
            + [Scadenza del canale di marketing](admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/visitor-engagement.md)
         + Gestione traffico {#traffic-management}
            + [Panoramica](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-management/traffic-management.md)
            + [Pianificare un picco](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-management/t-traffic-schedule-spike.md)
            + [Traffico permanente](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-management/t-traffic-permanent.md)
         + [Metriche predefinite](admin/c-manage-report-suites/c-edit-report-suites/default-metrics.md)
         + Gestione delle app {#app-management}
            + [Rapporti sulle app](admin/c-manage-report-suites/c-edit-report-suites/app-reporting.md)
            + [Classificazioni delle app](admin/c-manage-report-suites/c-edit-report-suites/app-classifications.md)
         + [Gestione dei file multimediali](admin/c-manage-report-suites/c-edit-report-suites/media-management.md)
         + [Activity Map](admin/c-manage-report-suites/c-edit-report-suites/activity-map.md)
         + [AEM](admin/c-manage-report-suites/c-edit-report-suites/adobe-experience-manager.md)
         + [Adobe Campaign](admin/c-manage-report-suites/c-edit-report-suites/adobe-campaign.md)
         + [Rapporti sula privacy](admin/c-manage-report-suites/c-edit-report-suites/privacy-reporting.md)
         + Gestione di Document Cloud {#doc-cloud-mgt}
            + [Configurare Document Cloud con Adobe Analytics](admin/c-manage-report-suites/c-edit-report-suites/document-cloud-mgt.md)
            + [Configurare il reporting di Document Cloud](admin/c-manage-report-suites/c-edit-report-suites/document-cloud-config.md)
         + [Configurazione di Advertising Analytics](admin/c-manage-report-suites/c-edit-report-suites/advertising-analytics-config.md)
         + Tempo reale {#real-time-reports}
            + [Panoramica rapporti in tempo reale](admin/c-manage-report-suites/c-edit-report-suites/realtime/realtime.md)
            + [Configurazione rapporti in tempo reale](admin/c-manage-report-suites/c-edit-report-suites/realtime/t-realtime-admin.md)
            + [Metriche e dimensioni in tempo reale supportate](admin/c-manage-report-suites/c-edit-report-suites/realtime/realtime-metrics.md)
      + [Gestione suite di rapporti](admin/c-manage-report-suites/report-suites-admin.md)
      + [Suite di rapporti globali](admin/c-manage-report-suites/rollup-report-suite.md)
      + [Salvare una ricerca suite di rapporti](admin/c-manage-report-suites/t-report-suite-saved-search.md)
      + [Scaricare le impostazioni delle suite di rapporti](admin/c-manage-report-suites/t-download-rs-settings.md)
      + New Report Suite (Nuova suite di rapporti) {#c-new-report-suite}
         + [Creare una suite di rapporti](admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md)
         + [Creare un gruppo suite di rapporti](admin/c-manage-report-suites/c-new-report-suite/t-create-rs-group.md)
         + [Nuova suite di rapporti: impostazioni](admin/c-manage-report-suites/c-new-report-suite/new-report-suite.md)
         + [Impostazioni non copiate da una suite di rapporti di origine](admin/c-manage-report-suites/c-new-report-suite/settings-not-copied-from-rs.md)
      + Modelli suite di rapporti {#report-suite-templates}
         + [Panoramica dei modelli delle suite di rapporti](admin/c-manage-report-suites/c-report-suite-templates/report-suite-templates.md)
         + [Portale Aggregator](admin/c-manage-report-suites/c-report-suite-templates/aggregator-portal.md)
         + [Commerce](admin/c-manage-report-suites/c-report-suite-templates/commerce-admin.md)
         + [Contenuto e media](admin/c-manage-report-suites/c-report-suite-templates/content-media.md)
         + [Modello predefinito](admin/c-manage-report-suites/c-report-suite-templates/default-rs-template.md)
         + [Servizi finanziari](admin/c-manage-report-suites/c-report-suite-templates/financial-services.md)
         + [Portale dei processi](admin/c-manage-report-suites/c-report-suite-templates/job-portal.md)
         + [Generazione di lead](admin/c-manage-report-suites/c-report-suite-templates/lead-generation.md)
         + [Supporto media](admin/c-manage-report-suites/c-report-suite-templates/support-media.md)
   + Impostazioni aziendali {#company-settings}
      + [Panoramica delle impostazioni aziendali](admin/company/c-company-settings.md)
      + [Security Manager](admin/company/security-manager.md)
      + [Servizi web](admin/company/web-services-admin.md)
      + [Rapporti di Report Builder](admin/company/report-builder-reports-admin.md)
      + [Single Sign-On](admin/company/single-signon-admin.md)
      + [Nascondi le suite di rapporti](admin/company/c-hide-report-suites.md)
      + [Preferenze manager](admin/company/preferences-manager.md)
      + [Azioni in sospeso](admin/company/pending-actions-admin.md)
      + [Livelli di accesso alle funzionalità](admin/company/feature-access-levels.md)
   + Etichette di privacy e governance dei dati {#data-governance}
      + [Flusso di lavoro sulla privacy dei dati di Adobe Analytics](admin/c-data-governance/an-gdpr-workflow.md)
      + [Domande frequenti](admin/c-data-governance/gdpr-faq.md)
      + Etichettatura dei dati {#data-labels}
         + [Etichette Privacy dei dati per i componenti di Analytics](admin/c-data-governance/data-labeling/gdpr-labels.md)
         + [Etichettare i dati della suite di rapporti](admin/c-data-governance/data-labeling/gdpr-setup-reportsuite.md)
         + [Visualizzare/gestire le etichette sulla privacy della suite di rapporti](admin/c-data-governance/data-labeling/gdpr-view-settings.md)
         + [Tecniche di etichettatura consigliate](admin/c-data-governance/data-labeling/gdpr-analytics-ids.md)
         + [Esempi di etichettatura](admin/c-data-governance/data-labeling/gdpr-labeling-example.md)
         + [Namespace](admin/c-data-governance/data-labeling/gdpr-namespaces.md)
      + [Espansione dell’ID](admin/c-data-governance/gdpr-id-expansion.md)
      + [Esenzione dal consenso CNIL](admin/c-data-governance/cnil-consent-exemption.md)
   + Utilizzo delle chiamate server {#server-call-usage}
      + [Guida per il primo amministratore di Adobe Analytics](admin/c-server-call-usage/overage-overview.md)
      + [Visualizzazione dell&#39;utilizzo della chiamata server corrente](admin/c-server-call-usage/server-call-usage-dashboard.md)
      + [Visualizzazione dell&#39;utilizzo della suite di rapporti](admin/c-server-call-usage/report-suite-usage.md)
      + [Avvisi di utilizzo delle chiamate al server](admin/c-server-call-usage/scu-alerts.md)
      + [Domande frequenti sull&#39;utilizzo delle chiamate server](admin/c-server-call-usage/overage-faq.md)
   + Gestione di utenti e prodotti (Legacy) {#user-product-management}
      + [Gestione di utenti e prodotti (Legacy)](admin/user-management2/user-management.md)
      + [Gestire account utente, risorse e scadenze legacy](admin/user-management2/users-assets.md)
      + Migrazione utenti ad Adobe Admin Console {#migrate-users}
         + [Migrazione degli utenti di Analytics all’Admin Console](admin/user-management2/user-migration/c-migration-tool.md)
         + [Eseguire la migrazione degli account utente di Analytics per Adobe ID](admin/user-management2/user-migration/t-migrate-users.md)
         + [Eseguire la migrazione degli account utente di Analytics per Enterprise ID e Federated ID](admin/user-management2/user-migration/migrate-enterprise.md)
         + [Disattivazione degli accessi legacy](admin/user-management2/user-migration/t-disable-legacy-login.md)
         + [API interessate dalla migrazione](admin/user-management2/user-migration/developer.md)
+ [Amministratore API](c-admin-api/c-admin-api.md)
+ [Domande frequenti sulla fine del ciclo di vita dell’API Adobe Analytics 1.4](c-admin-api/c-admin-14-api-eol.md)

