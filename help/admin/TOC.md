---
product: analytics
audience: admin
user-guide-title: Guida dell’amministratore di Analytics
breadcrumb-title: Guida dell’amministratore
user-guide-description: Scopri le attività di amministrazione di Analytics, come gestire utenti e prodotti nell’Admin Console di Experience Cloud, configurare suite di rapporti e altro ancora.
source-git-commit: 4bbed2efde0574bc9f5f6a78a022a22490e75549
workflow-type: tm+mt
source-wordcount: '639'
ht-degree: 96%

---


# Guida dell’amministratore di Adobe Analytics {#admin}

+ [Guida dell’amministratore di Analytics](home.md)
+ [Note sulla versione di Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=it)
+ Admin Console di Adobe {#admin-console}
   + [Analytics in Adobe Admin Console](admin-console/home.md)
   + [Prima guida dell’amministratore di Adobe Analytics](admin-console/first-admin-guide.md)
   + [Ruoli di amministratore in Adobe Analytics](admin-console/admin-roles-in-analytics.md)
   + Autorizzazioni {#permissions}
      + [Autorizzazioni di Analytics in Admin Console](admin-console/permissions/summary-tables.md)
      + [Profili di prodotto per Adobe Analytics](admin-console/permissions/product-profile.md)
      + [Autorizzazioni del profilo di prodotto per gli strumenti Report Suite](admin-console/permissions/report-suite-tools.md)
      + [Autorizzazioni del profilo di prodotto per gli strumenti Analytics](admin-console/permissions/analytics-tools.md)
   + Gestione di utenti e prodotti (Legacy) {#user-product-management}
      + [Gestione di utenti e prodotti (Legacy)](admin-console/user-management2/user-management.md)
      + Migrazione utenti ad Adobe Admin Console {#migrate-users}
         + [Migrazione degli utenti di Analytics all’Admin Console](admin-console/user-management2/user-migration/c-migration-tool.md)
         + [Eseguire la migrazione degli account utente di Analytics per Adobe ID](admin-console/user-management2/user-migration/t-migrate-users.md)
         + [Eseguire la migrazione degli account utente di Analytics per Enterprise ID e Federated ID](admin-console/user-management2/user-migration/migrate-enterprise.md)
         + [Disattivazione degli accessi legacy](admin-console/user-management2/user-migration/t-disable-legacy-login.md)
         + [API interessate dalla migrazione](admin-console/user-management2/user-migration/developer.md)
+ Strumenti di amministrazione di Analytics {#admin-tools}
   + [Panoramica degli strumenti di amministrazione](admin/c-admin-tools.md)
   + [Fatturazione](admin/billing-admin.md)
   + [Gestione codici](admin/code-manager-admin.md)
   + [Codici valuta](admin/currency.md)
   + [Origini dati](admin/data-sources.md)
   + [Metriche predefinite](admin/default-metrics.md)
   + [Escludi per indirizzo IP](admin/exclude-ip.md)
   + [Registri](admin/logs.md)
   + [Visibilità delle metriche](admin/metric-visibility.md)
   + [Preferenze manager](admin/preferences-manager.md)
   + [Rapporti sulla privacy](admin/privacy-reporting.md)
   + [Reporting Activity Manager](admin/reporting-activity.md)
   + [Coda dei report pianificati](admin/scheduled-reports-admin.md)
   + Report Suite Manager {#manage-report-suites}
      + [Gestione suite di rapporti](admin/c-manage-report-suites/report-suites-admin.md)
      + [Suite di rapporti di aggregazione dati e globali](admin/c-manage-report-suites/rollup-report-suite.md)
      + [Salvare una ricerca suite di rapporti](admin/c-manage-report-suites/t-report-suite-saved-search.md)
      + [Scaricare le impostazioni delle suite di rapporti](admin/c-manage-report-suites/t-download-rs-settings.md)
      + New Report Suite (Nuova suite di rapporti) {#c-new-report-suite}
         + [Creare una suite di rapporti](admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md)
         + [Creare una suite di rapporti di aggregazione dati](admin/c-manage-report-suites/c-new-report-suite/t-rollups.md)
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
      + Modificare le impostazioni di una suite di rapporti {#edit-report-suite}
         + Generale {#report-suite-general}
            + [Impostazioni account generali](admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md)
            + [Filtri URL interni](admin/c-manage-report-suites/c-edit-report-suites/general/internal-url-filter-admin.md)
            + Rilevamento di ricerca a pagamento {#paid-search-detection}
               + [Panoramica sul rilevamento di ricerca a pagamento](admin/c-manage-report-suites/c-edit-report-suites/general/paid-search-detection/paid-search-detection.md)
               + [Configurare il rilevamento di ricerche a pagamento](admin/c-manage-report-suites/c-edit-report-suites/general/paid-search-detection/t-paid-search-detection.md)
            + [Personalizzare i menu](admin/c-manage-report-suites/c-edit-report-suites/general/customize-menus.md)
            + [Personalizza calendario](admin/c-manage-report-suites/c-edit-report-suites/general/custom-calendar.md)
            + Regole di elaborazione {#c-processing-rules}
               + [Panoramica sulle regole di elaborazione](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules.md)
               + Configurazione delle regole di elaborazione {#c-processing-rules-configuration}
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
            + Rimozione bot {#bot-removal}
               + [Rimozione bot](admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-removal.md)
               + [Panoramica delle regole bot](admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md)
               + [Firme bot comuni](admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-signatures.md)
               + [Metodi di esclusione bot](admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-exclusion-methods.md)
            + [Impostazioni privacy](admin/c-manage-report-suites/c-edit-report-suites/general/privacy-settings.md)
            + [Marca temporale opzionale](admin/c-manage-report-suites/c-edit-report-suites/general/timestamp-optional.md)
            + Inoltro lato server {#server-side-forwarding}
               + [Panoramica sull&#39;inoltro lato server](admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf.md)
               + [Conformità a RGPD/ePrivacy e inoltro lato server](admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf-gdpr.md)
               + [Requisiti per l&#39;inoltro lato server](admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf-requirements.md)
               + [Dati inoltro lato server e codice](admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf-reference.md)
               + [Verificare l’implementazione dell’inoltro lato server](admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf-verify.md)
               + [Domande frequenti sull&#39;inoltro lato server](admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf-faq.md)
         + Variabili traffico {#traffic-variables}
            + [Panoramica della variabile traffico (prop)](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/traffic-var.md)
            + [Abilitare i rapporti sulle variabili traffico](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/t-traffic-variable.md)
            + [Classificazioni traffico](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/traffic-classifications.md)
            + [Descrizioni report personalizzati](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/custom-desc-admin.md)
         + Variabili di conversione {#conversion-variables}
            + [Variabili di conversione (eVar)](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/conversion-var-admin.md)
            + [Modificare le variabili di conversione](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/t-conversion-variables-admin.md)
            + [Classificazioni di conversione](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/conversion-classifications.md)
            + [Gerarchie di classificazione](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/classification-hierarchies.md)
            + [Variabili elenco](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/list-var-admin.md)
            + [eVar di Merchandising](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/merchandising-evars.md)
            + [Metodi di ricerca](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/finding-methods.md)
            + Variabile Visitatore univoco {#unique-visitor-variable}
               + [Specificare la variabile Visitatore univoco](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/unique-visitor-variable-admin/t-unique-visitor-variable.md)
               + [Caso di utilizzo: estrazione degli ID visitatore](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/unique-visitor-variable-admin/extract-visitorids-usecase.md)
            + Eventi di successo {#success-events}
               + [Panoramica degli eventi di successo](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/success-event.md)
               + [Configurare eventi di successo](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/t-success-events.md)
               + [Informazioni sulla modifica del tipo di evento](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/event-type.md)
         + [Canali marketing](admin/c-manage-report-suites/c-edit-report-suites/marketing-channels-admin.md)
         + Gestione traffico {#traffic-management}
            + [Gestione del traffico](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-management/traffic-management.md)
            + [Pianificare un picco di traffico](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-management/t-traffic-schedule-spike.md)
            + [Stimare chiamate server passate e pianificare un picco di traffico](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-management/traffic-spike-estimate-past-server-calls.md)
            + [Specificare aumento traffico permanente](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-management/t-traffic-permanent.md)
            + [Tempo di lead richiesto per aumento di traffico](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-management/traffic-lead-time.md)
         + [Impostazioni suite di rapporti singole](admin/c-manage-report-suites/c-edit-report-suites/individual-rs-settings.md)
         + [Gestione delle app](admin/c-manage-report-suites/c-edit-report-suites/mobile-management.md)
         + Rapporti in tempo reale {#real-time-reports}
            + [Panoramica rapporti in tempo reale](admin/c-manage-report-suites/c-edit-report-suites/realtime/realtime.md)
            + [Configurazione rapporti in tempo reale](admin/c-manage-report-suites/c-edit-report-suites/realtime/t-realtime-admin.md)
            + [Metriche e dimensioni in tempo reale supportate](admin/c-manage-report-suites/c-edit-report-suites/realtime/realtime-metrics.md)
   + Impostazioni aziendali {#company-settings}
      + [Panoramica delle impostazioni aziendali](admin/company/c-company-settings.md)
      + [Livelli di accesso alle funzionalità](admin/company/feature-access-levels.md)
      + [Servizi web](admin/company/web-services-admin.md)
      + [Rapporti di Report Builder](admin/company/report-builder-reports-admin.md)
      + [Single Sign-On](admin/company/single-signon-admin.md)
      + [Azioni in sospeso](admin/company/pending-actions-admin.md)
      + [Co-branding](admin/company/co-branding-admin.md)
      + [Nascondere le suite di rapporti](admin/company/c-hide-report-suites.md)
      + [Security Manager](admin/company/security-manager.md)
   + [Menu dei rapporti semplificati](admin/t-simplified-menu.md)
   + [Gestione video](admin/video-management.md)
   + Utilizzo delle chiamate server {#server-call-usage}
      + [Guida per il primo amministratore di Adobe Analytics](admin/c-server-call-usage/overage-overview.md)
      + [Visualizzazione dell&#39;utilizzo della chiamata server corrente](admin/c-server-call-usage/server-call-usage-dashboard.md)
      + [Visualizzazione dell&#39;utilizzo della suite di rapporti](admin/c-server-call-usage/report-suite-usage.md)
      + [Avvisi di utilizzo delle chiamate al server](admin/c-server-call-usage/scu-alerts.md)
      + [Domande frequenti sull&#39;utilizzo delle chiamate server](admin/c-server-call-usage/overage-faq.md)
+ Governance dei dati {#data-governance}
   + [Flusso di lavoro sulla privacy dei dati di Adobe Analytics](c-data-governance/an-gdpr-workflow.md)
   + [Domande frequenti](c-data-governance/gdpr-faq.md)
   + Etichettatura dei dati {#data-labels}
      + [Etichette Privacy dei dati per i componenti di Analytics](c-data-governance/data-labeling/gdpr-labels.md)
      + [Etichettare i dati della suite di rapporti](c-data-governance/data-labeling/gdpr-setup-reportsuite.md)
      + [Visualizzare/gestire le etichette di privacy della suite di rapporti](c-data-governance/data-labeling/gdpr-view-settings.md)
      + [Tecniche di etichettatura consigliate](c-data-governance/data-labeling/gdpr-analytics-ids.md)
      + [Esempi di etichettatura](c-data-governance/data-labeling/gdpr-labeling-example.md)
      + [Namespace](c-data-governance/data-labeling/gdpr-namespaces.md)
   + [Espansione dell’ID](c-data-governance/gdpr-id-expansion.md)
   + [Esenzione dal consenso CNIL](c-data-governance/cnil-consent-exemption.md)
+ [Amministratore API](c-admin-api/c-admin-api.md)
