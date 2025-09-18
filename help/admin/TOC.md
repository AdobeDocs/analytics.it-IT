---
product: analytics
audience: admin
user-guide-title: Guida dell’amministratore di Analytics
breadcrumb-title: Guida dell’amministratore
user-guide-description: Scopri le attività di amministrazione di Analytics, come gestire utenti e prodotti nell’Admin Console di Experience Cloud, configurare suite di rapporti e altro ancora.
source-git-commit: 35675c2e65456a175d1516dd421b80d2af809286
workflow-type: tm+mt
source-wordcount: '496'
ht-degree: 88%

---


# Guida dell’amministratore di Adobe Analytics {#admin}

+ [Guida per l’amministratore di Analytics](home.md)
+ [Note sulla versione di Analytics](https://experienceleague.adobe.com/it/docs/analytics/release-notes/latest)
+ Admin Console di Adobe {#admin-console}
   + [Panoramica](admin-console/home.md)
   + [Prima guida dell’amministratore di Adobe Analytics](admin-console/first-admin-guide.md)
   + [Ruoli di amministratore in Adobe Analytics](admin-console/admin-roles-in-analytics.md)
   + Riepilogo autorizzazioni strumenti di Analytics {#permissions}
      + [Profili di prodotto per Adobe Analytics](admin-console/permissions/product-profile.md)
      + [Autorizzazioni del profilo di prodotto per gli strumenti Report Suite](admin-console/permissions/report-suite-tools.md)
      + [Autorizzazioni del profilo di prodotto per gli strumenti Analytics](admin-console/permissions/analytics-tools.md)
+ Strumenti di amministrazione di Analytics {#admin-tools}
   + [Panoramica sugli strumenti di amministrazione](tools/c-admin-tools.md)
   + [Gestione codici](tools/code-manager-admin.md)
   + [Inventario analitico](tools/analytics-inventory.md)
   + [Origini dati](tools/data-sources.md)
   + [Escludi per indirizzo IP](tools/exclude-ip.md)
   + [Registri](tools/logs.md)
   + Reporting Activity Manager {#reporting-activity-manager}
      + [Panoramica](tools/reporting-activity-manager/reporting-activity-overview.md)
      + [Visualizzare l’attività di reporting](tools//reporting-activity-manager/reporting-activity.md)
      + [Annullare le richieste di reporting](tools/reporting-activity-manager/reporting-activity-cancel-requests.md)
   + Migrazione dei componenti {#component-migration}
      + [Prepararsi alla migrazione](tools/component-migration/prepare-component-migration.md)
      + [Flusso di lavoro della migrazione](tools/component-migration/component-migration.md)
   + Report Suite Manager {#manage-report-suites}
      + Modificare le impostazioni di una suite di rapporti {#edit-report-suite}
         + Generale {#report-suite-general}
            + [Impostazioni account generali](tools/manage-rs/edit-settings/general/general-acct-settings-admin.md)
            + [Filtri URL interni](tools/manage-rs/edit-settings/general/internal-url-filter-admin.md)
            + [Personalizza calendario](tools/manage-rs/edit-settings/general/custom-calendar.md)
            + Rilevamento di ricerca a pagamento {#paid-search-detection}
               + [Panoramica sul rilevamento di ricerca a pagamento](tools/manage-rs/edit-settings/general/paid-search-detection/paid-search-detection.md)
               + [Configurare il rilevamento di ricerche a pagamento](tools/manage-rs/edit-settings/general/paid-search-detection/t-paid-search-detection.md)
            + Regole di elaborazione {#processing-rules}
               + [Panoramica](tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md)
               + [Interfaccia](tools/manage-rs/edit-settings/general/processing-rules/pr-interface.md)
               + [Visualizza cronologia](tools/manage-rs/edit-settings/general/processing-rules/pr-view-history.md)
               + [Copia regole](tools/manage-rs/edit-settings/general/processing-rules/pr-copy.md)
               + [Dimensioni e metriche disponibili](tools/manage-rs/edit-settings/general/processing-rules/pr-variables.md)
               + [Casi d’uso](tools/manage-rs/edit-settings/general/processing-rules/pr-use-cases.md)
            + Regole bot {#bot-removal}
               + [Rimozione bot](tools/manage-rs/edit-settings/general/bot-removal/bot-removal.md)
               + [Comprendere e configurare le regole bot](tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md)
               + [Firme bot comuni](tools/manage-rs/edit-settings/general/bot-removal/bot-signatures.md)
               + [Metodi di esclusione bot](tools/manage-rs/edit-settings/general/bot-removal/bot-exclusion-methods.md)
            + [Impostazioni privacy](tools/manage-rs/edit-settings/general/privacy-settings.md)
            + [Configurazione timestamp](tools/manage-rs/edit-settings/general/timestamp-configuration.md)
            + Inoltro lato server {#server-side-forwarding}
               + [Panoramica sull&#39;inoltro lato server](tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf.md)
               + [Conformità a GDPR/ePrivacy e inoltro lato server](tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf-gdpr.md)
               + [Requisiti per l&#39;inoltro lato server](tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf-requirements.md)
               + [Dati inoltro lato server e codice](tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf-reference.md)
               + [Verificare l’implementazione dell’inoltro lato server](tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf-verify.md)
               + [Domande frequenti sull&#39;inoltro lato server](tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf-faq.md)
         + Traffic (Traffico) {#traffic-variables}
            + [Variabili di traffico](tools/manage-rs/edit-settings/c-traffic-variables/traffic-var.md)
            + [Classificazioni traffico](tools/manage-rs/edit-settings/c-traffic-variables/traffic-classifications.md)
            + [Descrizioni report personalizzati](tools/manage-rs/edit-settings/c-traffic-variables/custom-desc-admin.md)
         + Conversione {#conversion-variables}
            + [Variabili di conversione](tools/manage-rs/edit-settings/conversion-var-admin/conversion-var-admin.md)
            + [Metodi di ricerca](tools/manage-rs/edit-settings/conversion-var-admin/finding-methods.md)
            + [Classificazioni di conversione](tools/manage-rs/edit-settings/conversion-var-admin/conversion-classifications.md)
            + Variabile visitatore univoco {#unique-visitor-variable}
               + [Specificare la variabile Visitatore univoco](tools/manage-rs/edit-settings/conversion-var-admin/unique-visitor-variable-admin/t-unique-visitor-variable.md)
               + [Caso di utilizzo: estrazione degli ID visitatore](tools/manage-rs/edit-settings/conversion-var-admin/unique-visitor-variable-admin/extract-visitorids-usecase.md)
            + [Eventi di successo](tools/manage-rs/edit-settings/conversion-var-admin/c-success-events/success-event.md)
            + [Gerarchie di classificazione](tools/manage-rs/edit-settings/conversion-var-admin/classification-hierarchies.md)
            + [Variabili elenco](tools/manage-rs/edit-settings/conversion-var-admin/list-var-admin.md)
            + [eVar di merchandising](tools/manage-rs/edit-settings/conversion-var-admin/merchandising-evars.md)
         + Canali marketing {#marketing-channels}
            + [Gestore del canale di marketing](tools/manage-rs/edit-settings/marketing-channels/c-channels.md)
            + [Regole di elaborazione per il canale di marketing](tools/manage-rs/edit-settings/marketing-channels/c-rules.md)
            + [Classificazioni del canale di marketing](tools/manage-rs/edit-settings/marketing-channels/classifications-mchannel.md)
            + [Scadenza del canale di marketing](tools/manage-rs/edit-settings/marketing-channels/visitor-engagement.md)
         + Gestione traffico {#traffic-management}
            + [Panoramica](tools/manage-rs/edit-settings/c-traffic-management/traffic-management.md)
            + [Pianificare un picco](tools/manage-rs/edit-settings/c-traffic-management/t-traffic-schedule-spike.md)
            + [Traffico permanente](tools/manage-rs/edit-settings/c-traffic-management/t-traffic-permanent.md)
         + [Metriche predefinite](tools/manage-rs/edit-settings/default-metrics.md)
         + Gestione delle app {#app-management}
            + [Rapporti sulle app](tools/manage-rs/edit-settings/app-reporting.md)
            + [Classificazioni delle app](tools/manage-rs/edit-settings/app-classifications.md)
         + [Gestione dei file multimediali](tools/manage-rs/edit-settings/media-management.md)
         + [Activity Map](tools/manage-rs/edit-settings/activity-map.md)
         + [AEM](tools/manage-rs/edit-settings/adobe-experience-manager.md)
         + [Adobe Campaign](tools/manage-rs/edit-settings/adobe-campaign.md)
         + [Rapporti sula privacy](tools/manage-rs/edit-settings/privacy-reporting.md)
         + Gestione Document Cloud {#doc-cloud-mgt}
            + [Configurare Document Cloud con Adobe Analytics](tools/manage-rs/edit-settings/document-cloud-mgt.md)
            + [Configurare il reporting di Document Cloud](tools/manage-rs/edit-settings/document-cloud-config.md)
         + [Configurazione di Advertising Analytics](tools/manage-rs/edit-settings/advertising-analytics-config.md)
         + Tempo reale {#real-time-reports}
            + [Panoramica rapporti in tempo reale](tools/manage-rs/edit-settings/realtime/realtime.md)
            + [Configurazione rapporti in tempo reale](tools/manage-rs/edit-settings/realtime/t-realtime-admin.md)
            + [Metriche e dimensioni in tempo reale supportate](tools/manage-rs/edit-settings/realtime/realtime-metrics.md)
      + [Gestione suite di rapporti](tools/manage-rs/report-suites-admin.md)
      + [Suite di rapporti globali](tools/manage-rs/rollup-report-suite.md)
      + [Salvare una ricerca suite di rapporti](tools/manage-rs/t-report-suite-saved-search.md)
      + [Scaricare le impostazioni delle suite di rapporti](tools/manage-rs/t-download-rs-settings.md)
      + Nuova suite di rapporti {#c-new-report-suite}
         + [Creare una suite di rapporti](tools/manage-rs/new-rs/t-create-a-report-suite.md)
         + [Creare un gruppo suite di rapporti](tools/manage-rs/new-rs/t-create-rs-group.md)
         + [Nuova suite di rapporti: impostazioni](tools/manage-rs/new-rs/new-report-suite.md)
         + [Impostazioni non copiate da una suite di rapporti di origine](tools/manage-rs/new-rs/settings-not-copied-from-rs.md)
      + Modelli suite di rapporti {#report-suite-templates}
         + [Panoramica dei modelli delle suite di rapporti](tools/manage-rs/rs-templates/report-suite-templates.md)
         + [Portale Aggregator](tools/manage-rs/rs-templates/aggregator-portal.md)
         + [Commerce](tools/manage-rs/rs-templates/commerce-admin.md)
         + [Contenuto e media](tools/manage-rs/rs-templates/content-media.md)
         + [Modello predefinito](tools/manage-rs/rs-templates/default-rs-template.md)
         + [Servizi finanziari](tools/manage-rs/rs-templates/financial-services.md)
         + [Portale dei processi](tools/manage-rs/rs-templates/job-portal.md)
         + [Generazione di lead](tools/manage-rs/rs-templates/lead-generation.md)
         + [Supporto media](tools/manage-rs/rs-templates/support-media.md)
   + Impostazioni società {#company-settings}
      + [Panoramica delle impostazioni aziendali](tools/company/c-company-settings.md)
      + [Security Manager](tools/company/security-manager.md)
      + [Servizi web](tools/company/web-services-admin.md)
      + [Rapporti di Report Builder](tools/company/report-builder-reports-admin.md)
      + [Single Sign-On](tools/company/single-signon-admin.md)
      + [Nascondi le suite di rapporti](tools/company/c-hide-report-suites.md)
      + [Preferenze manager](tools/company/preferences-manager.md)
      + [Azioni in sospeso](tools/company/pending-actions-admin.md)
      + [Livelli di accesso alle funzionalità](tools/company/feature-access-levels.md)
   + Etichettatura privacy {#privacy-labeling}
      + [Panoramica](tools/privacy-labeling/labeling-overview.md)
      + [Etichette Privacy dei dati per i componenti di Analytics](tools/privacy-labeling/labels.md)
      + [Visualizzare/gestire le etichette sulla privacy della suite di rapporti](tools/privacy-labeling/view-settings.md)
      + [Tecniche di etichettatura consigliate](tools/privacy-labeling/best-practices.md)
      + [Esempi di etichettatura](tools/privacy-labeling/examples.md)
      + [Namespace](tools/privacy-labeling/namespaces.md)
   + Utilizzo chiamate al server {#server-call-usage}
      + [Guida per il primo amministratore di Adobe Analytics](tools/server-call-usage/overage-overview.md)
      + [Visualizzazione dell&#39;utilizzo della chiamata server corrente](tools/server-call-usage/server-call-usage-dashboard.md)
      + [Visualizzazione dell&#39;utilizzo della suite di rapporti](tools/server-call-usage/report-suite-usage.md)
      + [Avvisi di utilizzo delle chiamate al server](tools/server-call-usage/scu-alerts.md)
      + [Domande frequenti sull&#39;utilizzo delle chiamate server](tools/server-call-usage/overage-faq.md)
   + Gestione di utenti e prodotti (Legacy) {#user-product-management}
      + [Gestione di utenti e prodotti (Legacy)](tools/user-management/user-management.md)
      + [Gestire account utente, risorse e scadenze legacy](tools/user-management/users-assets.md)
      + Migrazione utenti a Adobe Admin Console {#migrate-users}
         + [Migrazione degli utenti di Analytics all’Admin Console](tools/user-management/user-migration/c-migration-tool.md)
         + [Eseguire la migrazione degli account utente di Analytics per Adobe ID](tools/user-management/user-migration/t-migrate-users.md)
         + [Eseguire la migrazione degli account utente di Analytics per Enterprise ID e Federated ID](tools/user-management/user-migration/migrate-enterprise.md)
         + [Disattivazione degli accessi legacy](tools/user-management/user-migration/t-disable-legacy-login.md)
         + [API interessate dalla migrazione](tools/user-management/user-migration/developer.md)
+ [Amministratore API](c-admin-api/c-admin-api.md)
+ [Domande frequenti sulla fine del ciclo di vita dell’API Adobe Analytics 1.4](c-admin-api/c-admin-14-api-eol.md)

