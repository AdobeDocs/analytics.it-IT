---
product: analytics
audience: admin
user-guide-title: Guida dell’amministratore di Analytics
breadcrumb-title: Guida dell’amministratore
user-guide-description: Scopri le attività di amministrazione di Analytics, come gestire utenti e prodotti nell’Admin Console di Experience Cloud, configurare suite di rapporti e altro ancora.
source-git-commit: 72c35538b0e5d0ffaa103b3159b4e9835a6c1602
workflow-type: tm+mt
source-wordcount: '673'
ht-degree: 96%

---


# Guida dell’amministratore di Adobe Analytics {#admin}

+ [Guida dell’amministratore di Analytics](home.md)
+ [Note sulla versione di Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=it)
+ Guida introduttiva all’amministrazione di Analytics {#admin-overview}
   + [Quale strumento Adobe Analytics usare?](get-started/which-analytics-tool.md)
   + [Confronto dei prodotti Analytics e requisiti](get-started/analytics-product-comparison.md)
   + [Requisiti di sistema](get-started/sys-reqs.md)
   + Impostazioni aziendali {#company-settings}
      + [Panoramica delle impostazioni aziendali](get-started/company/c-company-settings.md)
      + [Livelli di accesso alle funzionalità](get-started/company/feature-access-levels.md)
      + [Servizi web](get-started/company/web-services-admin.md)
      + [Rapporti di Report Builder](get-started/company/report-builder-reports-admin.md)
      + [Single Sign-On](get-started/company/single-signon-admin.md)
      + [Azioni in sospeso](get-started/company/pending-actions-admin.md)
      + [Co-branding](get-started/company/co-branding-admin.md)
      + [Nascondere suite di rapporti](get-started/company/c-hide-report-suites.md)
      + [Security Manager](get-started/company/security-manager.md)
+ Autorizzazioni utente in Adobe Admin Console {#admin-console}
   + [Analytics in Adobe Admin Console](admin-console/home.md)
   + [Prima guida per l’amministratore di Adobe Analytics](admin-console/first-admin-guide.md)
   + [Ruoli di amministratore in Adobe Analytics](admin-console/admin-roles-in-analytics.md)
   + Autorizzazioni {#permissions}
      + [Autorizzazioni di Analytics in Admin Console](admin-console/permissions/summary-tables.md)
      + [Profili di prodotto per Adobe Analytics](admin-console/permissions/product-profile.md)
      + [Autorizzazioni del profilo di prodotto per gli strumenti Report Suite](admin-console/permissions/report-suite-tools.md)
      + [Autorizzazioni del profilo di prodotto per gli strumenti Analytics](admin-console/permissions/analytics-tools.md)
+ Strumenti di amministrazione {#admin-tools}
   + [Strumenti di amministrazione](admin/c-admin-tools.md)
   + [Fatturazione](admin/billing-admin.md)
   + Rimozione bot {#bot-removal}
      + [Rimozione bot](admin/bot-removal/bot-removal.md)
      + [Panoramica delle regole bot](admin/bot-removal/bot-rules.md)
      + [Firme bot comuni](admin/bot-removal/bot-signatures.md)
      + [Metodi di esclusione bot](admin/bot-removal/bot-exclusion-methods.md)
   + [Gestione codici](admin/code-manager-admin.md)
   + Variabili di conversione {#conversion-variables}
      + [Variabili di conversione (eVar)](admin/conversion-var-admin/conversion-var-admin.md)
      + [Modificare le variabili di conversione](admin/conversion-var-admin/t-conversion-variables-admin.md)
      + [Classificazioni di conversione](admin/conversion-var-admin/conversion-classifications.md)
      + [Gerarchie di classificazione](admin/conversion-var-admin/classification-hierarchies.md)
      + [Variabili elenco](admin/conversion-var-admin/list-var-admin.md)
      + [eVar di Merchandising](admin/conversion-var-admin/merchandising-evars.md)
   + [Codici valuta](admin/currency.md)
   + [Descrizioni report personalizzati](admin/custom-desc-admin.md)
   + [Personalizza calendario](admin/custom-calendar.md)
   + [Origini dati](admin/data-sources.md)
   + [Metriche predefinite](admin/default-metrics.md)
   + [Escludi per indirizzo IP](admin/exclude-ip.md)
   + [Metodi di ricerca](admin/finding-methods.md)
   + [Impostazioni account generali](admin/general-acct-settings-admin.md)
   + [Filtri URL interni](admin/internal-url-filter-admin.md)
   + [Registri](admin/logs.md)
   + [Canali di marketing](admin/marketing-channels-admin.md)
   + [Personalizzazione del menu](admin/customize-menus.md)
   + [Visibilità delle metriche](admin/metric-visibility.md)
   + [Gestione delle app](admin/mobile-management.md)
   + Rilevamento di ricerca a pagamento {#paid-search-detection}
      + [Panoramica sul rilevamento di ricerca a pagamento](admin/paid-search-detection/paid-search-detection.md)
      + [Configurare il rilevamento di ricerche a pagamento](admin/paid-search-detection/t-paid-search-detection.md)
   + [Preferenze Manager](admin/preferences-manager.md)
   + [Impostazioni privacy](admin/privacy-settings.md)
   + [Rapporti sulla privacy](admin/privacy-reporting.md)
   + Regole di elaborazione {#processing-rules}
      + [Panoramica sulle regole di elaborazione](admin/c-processing-rules/processing-rules.md)
      + Configurazione delle regole di elaborazione {#processing-rules-configuration}
         + [Funzionamento delle regole di elaborazione](admin/c-processing-rules/c-processing-rules-configuration/processing-rules-about.md)
         + [Creare regole di elaborazione](admin/c-processing-rules/c-processing-rules-configuration/t-processing-rules.md)
         + [Visualizzare le regole di elaborazione attive](admin/c-processing-rules/c-processing-rules-configuration/t-processing-rules-view.md)
         + [Visualizzare la cronologia delle regole di elaborazione](admin/c-processing-rules/c-processing-rules-configuration/t-processing-rule-view-history.md)
         + [Ripristinare le regole di elaborazione](admin/c-processing-rules/c-processing-rules-configuration/t-processing-rules-restore.md)
         + [Copiare le regole di elaborazione in un&#39;altra suite di rapporti](admin/c-processing-rules/c-processing-rules-configuration/t-processing-rules-copy-to-rs.md)
      + [Dimensioni disponibili per le regole di elaborazione](admin/c-processing-rules/processing-rule-dimensions.md)
      + Regole di elaborazione, esempi {#processing-rules-examples}
         + [Esempi di regole di elaborazione](admin/c-processing-rules/processing-rules-examples/processing-rules-examples.md)
         + [Compilare un ID campagna da un parametro di stringa di query](admin/c-processing-rules/processing-rules-examples/processing-rules-populate-campaign-id.md)
         + [Impostare l&#39;evento di visualizzazione prodotto dalla pagina di panoramica prodotto](admin/c-processing-rules/processing-rules-examples/setting-the-product-view-event.md)
         + [Aggiungere una sottocategoria concatenando la categoria e il nome della pagina](admin/c-processing-rules/processing-rules-examples/subcategory-concatenating.md)
         + [Determinare un percorso copiando un valore eVar in un prop](admin/c-processing-rules/processing-rules-examples/processing-rules-determining-path.md)
         + [Pulire i valori in un rapporto](admin/c-processing-rules/processing-rules-examples/clean-up-values-in-a-report.md)
         + [Compilare termini di ricerca interni utilizzando un parametro di stringa di query](admin/c-processing-rules/processing-rules-examples/processing-rules-populating-internal-search.md)
         + [Copiare una variabile di dati di contesto in una eVar](admin/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data.md)
         + [Impostare un evento utilizzando una variabile di dati di contesto](admin/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data-event.md)
         + [Rimuovere un evento da un hit](admin/c-processing-rules/processing-rules-examples/processing-rules-remove-event.md)
      + [Suggerimenti e trucchi per le regole di elaborazione](admin/c-processing-rules/processing-rules-tips.md)
   + Rapporti in tempo reale {#real-time-reports}
      + [Panoramica rapporti in tempo reale](admin/realtime/realtime.md)
      + [Configurazione rapporti in tempo reale](admin/realtime/t-realtime-admin.md)
      + [Metriche e dimensioni in tempo reale supportate](admin/realtime/realtime-metrics.md)
   + [Reporting Activity Manager](admin/reporting-activity.md)
   + [Coda dei report pianificati](admin/scheduled-reports-admin.md)
   + Inoltro lato server {#server-side-forwarding}
      + [Panoramica sull&#39;inoltro lato server](admin/c-server-side-forwarding/ssf.md)
      + [Conformità a RGPD/ePrivacy e inoltro lato server](admin/c-server-side-forwarding/ssf-gdpr.md)
      + [Requisiti per l&#39;inoltro lato server](admin/c-server-side-forwarding/ssf-requirements.md)
      + [Dati inoltro lato server e codice](admin/c-server-side-forwarding/ssf-reference.md)
      + [Verificare l’implementazione dell’inoltro lato server](admin/c-server-side-forwarding/ssf-verify.md)
      + [Domande frequenti sull&#39;inoltro lato server](admin/c-server-side-forwarding/ssf-faq.md)
   + [Menu dei rapporti semplificati](admin/t-simplified-menu.md)
   + Eventi di successo {#success-events}
      + [Panoramica degli eventi di successo](admin/c-success-events/success-event.md)
      + [Configurare eventi di successo](admin/c-success-events/t-success-events.md)
      + [Informazioni sulla modifica del tipo di evento](admin/c-success-events/event-type.md)
   + [Marca temporale opzionale](admin/timestamp-optional.md)
   + Variabili traffico {#traffic-variables}
      + [Panoramica della variabile traffico (prop)](admin/c-traffic-variables/traffic-var.md)
      + [Abilitare i rapporti sulle variabili traffico](admin/c-traffic-variables/t-traffic-variable.md)
      + [Classificazioni traffico](admin/c-traffic-variables/traffic-classifications.md)
   + Variabile Visitatore univoco {#unique-visitor-variable}
      + [Specificare la variabile Visitatore univoco](admin/unique-visitor-variable-admin/t-unique-visitor-variable.md)
      + [Caso di utilizzo: estrazione degli ID visitatore](admin/unique-visitor-variable-admin/extract-visitorids-usecase.md)
   + [Gestione video](admin/video-management.md)
+ Gestione suite di rapporti {#manage-report-suites}
   + [Report Suite Manager](c-manage-report-suites/report-suites-admin.md)
   + [Suite di rapporti rollup e globali](c-manage-report-suites/rollup-report-suite.md)
   + [Creare una suite di rapporti di aggregazione dati](c-manage-report-suites/t-rollups.md)
   + Modelli suite di rapporti {#report-suite-templates}
      + [Panoramica dei modelli delle suite di rapporti](c-manage-report-suites/c-report-suite-templates/report-suite-templates.md)
      + [Portale Aggregator](c-manage-report-suites/c-report-suite-templates/aggregator-portal.md)
      + [Commerce](c-manage-report-suites/c-report-suite-templates/commerce-admin.md)
      + [Contenuto e media](c-manage-report-suites/c-report-suite-templates/content-media.md)
      + [Modello predefinito](c-manage-report-suites/c-report-suite-templates/default-rs-template.md)
      + [Servizi finanziari](c-manage-report-suites/c-report-suite-templates/financial-services.md)
      + [Portale dei processi](c-manage-report-suites/c-report-suite-templates/job-portal.md)
      + [Generazione di lead](c-manage-report-suites/c-report-suite-templates/lead-generation.md)
      + [Supporto media](c-manage-report-suites/c-report-suite-templates/support-media.md)
   + [Salvare una ricerca suite di rapporti](c-manage-report-suites/t-report-suite-saved-search.md)
   + [Impostazioni suite di rapporti singole](c-manage-report-suites/individual-rs-settings.md)
   + [Scaricare le impostazioni delle suite di rapporti](c-manage-report-suites/t-download-rs-settings.md)
   + New Report Suite (Nuova suite di rapporti) {#new-report-suite}
      + [Creare una suite di rapporti](c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md)
      + [Nuova suite di rapporti: impostazioni](c-manage-report-suites/c-new-report-suite/new-report-suite.md)
      + [Impostazioni non copiate da una suite di rapporti di origine](c-manage-report-suites/c-new-report-suite/settings-not-copied-from-rs.md)
   + [Creare un gruppo suite di rapporti](c-manage-report-suites/t-create-rs-group.md)
+ Gestione di utenti e prodotti (Legacy) {#user-product-management}
   + [Gestione di utenti e prodotti](user-management2/user-management.md)
   + Migrazione utenti ad Adobe Admin Console {#migrate-users}
      + [Migrazione degli utenti di Analytics all’Admin Console](user-management2/user-migration/c-migration-tool.md)
      + [Eseguire la migrazione degli account utente di Analytics per Adobe ID](user-management2/user-migration/t-migrate-users.md)
      + [Eseguire la migrazione degli account utente di Analytics per Enterprise ID e Federated ID](user-management2/user-migration/migrate-enterprise.md)
      + [Disattivazione degli accessi legacy](user-management2/user-migration/t-disable-legacy-login.md)
      + [API interessate dalla migrazione](user-management2/user-migration/developer.md)
+ Governance dei dati {#data-governance}
   + [Adobe Analytics e RGPD](c-data-governance/an-gdpr-overview.md)
   + [Adobe Analytics e CCPA](c-data-governance/an-ccpa-overview.md)
   + [Esenzione dal consenso CNIL](c-data-governance/cnil-consent-exemption.md)
   + [Domande frequenti](c-data-governance/gdpr-faq.md)
   + [Flusso di lavoro sulla privacy dei dati di Adobe Analytics](c-data-governance/an-gdpr-workflow.md)
   + [Visualizzare/gestire le impostazioni di governance dei dati della suite di rapporti](c-data-governance/gdpr-view-settings.md)
   + [Etichettare i dati della suite di rapporti](c-data-governance/gdpr-setup-reportsuite.md)
   + [Inviare richieste di accesso e cancellazione](c-data-governance/gdpr-submit-access-delete.md)
   + [Etichette Privacy dei dati per le variabili di Analytics](c-data-governance/gdpr-labels.md)
   + [Namespace](c-data-governance/gdpr-namespaces.md)
   + [Espansione dell’ID](c-data-governance/gdpr-id-expansion.md)
   + [Tecniche di etichettatura consigliate](c-data-governance/gdpr-analytics-ids.md)
   + [Esempi di etichettatura](c-data-governance/gdpr-labeling-example.md)
   + [Privacy dei dati e Data Connectors (Genesis)](c-data-governance/data-connectors-gdpr.md)
   + [Terminologia sulla privacy dei dati](c-data-governance/gdpr-terminology.md)
+ Utilizzo delle chiamate server {#server-call-usage}
   + [Guida per il primo amministratore di Adobe Analytics](c-server-call-usage/overage-overview.md)
   + [Visualizzazione dell&#39;utilizzo della chiamata server corrente](c-server-call-usage/server-call-usage-dashboard.md)
   + [Visualizzazione dell&#39;utilizzo della suite di rapporti](c-server-call-usage/report-suite-usage.md)
   + [Avvisi di utilizzo delle chiamate al server](c-server-call-usage/scu-alerts.md)
   + [Domande frequenti sull&#39;utilizzo delle chiamate server](c-server-call-usage/overage-faq.md)
+ Gestione traffico {#traffic-management}
   + [Gestione del traffico](c-traffic-management/traffic-management.md)
   + [Pianificare un picco di traffico](c-traffic-management/t-traffic-schedule-spike.md)
   + [Stimare chiamate server passate e pianificare un picco di traffico](c-traffic-management/traffic-spike-estimate-past-server-calls.md)
   + [Specificare aumento traffico permanente](c-traffic-management/t-traffic-permanent.md)
   + [Tempo di lead richiesto per aumento di traffico](c-traffic-management/traffic-lead-time.md)
+ [Amministratore API](c-admin-api/c-admin-api.md)
