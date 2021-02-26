---
product: analytics
audience: admin
user-guide-title: Guida dell’amministratore di Analytics
breadcrumb-title: Guida dell’amministratore
user-guide-description: Scopri come gestire utenti e prodotti nell’Admin Console di Experience Cloud, configurare suite di rapporti e altro ancora.
translation-type: tm+mt
source-git-commit: 6dcdbf7d49000e4e04d590b83da47d49f8e53ebf
workflow-type: tm+mt
source-wordcount: '734'
ht-degree: 99%

---


# Guida dell’amministratore di Analytics {#admin}

+ [Guida dell’amministratore di Analytics](home.md)
+ Panoramica dell&#39;amministrazione di Analytics {#admin-overview}
   + [Quale strumento Adobe Analytics usare?](c-analytics-product-comparison/which-analytics-tool.md)
   + [Requisiti e confronto dei prodotti Analytics](c-analytics-product-comparison/analytics-product-comparison.md)
+ [Requisiti di sistema](sys-reqs.md)
+ Strumenti di amministrazione {#admin-tools}
   + [Strumenti di amministrazione](admin/c-admin-tools.md)
   + [Fatturazione](admin/billing-admin.md)
   + Rimozione bot {#bot-removal}
      + [Rimozione bot](admin/bot-removal/bot-removal.md)
      + [Panoramica delle regole dei bot](admin/bot-removal/bot-rules.md)
      + [Firme bot comuni](admin/bot-removal/bot-signatures.md)
      + [Metodi di esclusione bot](admin/bot-removal/bot-exclusion-methods.md)
   + [Gestore codici](admin/code-manager-admin.md)
   + Variabili di conversione {#conversion-variables}
      + [Conversion Variables (Variabili di conversione) (eVars)](admin/conversion-var-admin/conversion-var-admin.md)
      + [Modificare le variabili di conversione](admin/conversion-var-admin/t-conversion-variables-admin.md)
      + [Classificazioni di conversione](admin/conversion-var-admin/conversion-classifications.md)
      + [Gerarchie di classificazione](admin/conversion-var-admin/classification-hierarchies.md)
      + [Variabili elenco](admin/conversion-var-admin/list-var-admin.md)
   + [Codici valuta](admin/currency.md)
   + [Descrizioni report personalizzati](admin/custom-desc-admin.md)
   + [Personalizza calendario](admin/custom-calendar.md)
   + [Origini dati](admin/data-sources.md)
   + [Metriche predefinite](admin/default-metrics.md)
   + [Escludi per indirizzo IP](admin/exclude-ip.md)
   + [Metodi di ricerca](admin/finding-methods.md)
   + [Impostazioni account generali](admin/general-acct-settings-admin.md)
   + [Gestione dei gruppi](admin/group.md)
   + [Filtri URL interni](admin/internal-url-filter-admin.md)
   + [Registri](admin/logs.md)
   + [Canali marketing](admin/marketing-channels-admin.md)
   + [Personalizzazione del menu](admin/customize-menus.md)
   + [Visibilità delle metriche](admin/metric-visibility.md)
   + [Gestione delle app](admin/mobile-management.md)
   + Rilevamento di ricerca a pagamento {#paid-search-detection}
      + [Panoramica sul rilevamento di ricerca a pagamento](admin/paid-search-detection/paid-search-detection.md)
      + [Configurazione del rilevamento di ricerche a pagamento](admin/paid-search-detection/t-paid-search-detection.md)
   + [Elenchi di pubblicazione](admin/publishing-list.md)
   + [Pubblicazione Widget](admin/publishing-widgets-admin.md)
   + [Preferenze Manager](admin/preferences-manager.md)
   + [Impostazioni privacy](admin/privacy-settings.md)
   + [Impostazioni privacy](admin/privacy-reporting.md)
   + Regole di elaborazione {#processing-rules}
      + [Panoramica sulle regole di elaborazione](admin/c-processing-rules/processing-rules.md)
      + Configurazione delle regole di elaborazione {#processing-rules-configuration}
         + [Funzionamento delle regole di elaborazione](admin/c-processing-rules/c-processing-rules-configuration/processing-rules-about.md)
         + [Ordine di elaborazione](admin/c-processing-rules/c-processing-rules-configuration/processing-rule-order.md)
         + [Creare regole di elaborazione](admin/c-processing-rules/c-processing-rules-configuration/t-processing-rules.md)
         + [Visualizzare le regole di elaborazione attive](admin/c-processing-rules/c-processing-rules-configuration/t-processing-rules-view.md)
         + [Visualizzare la cronologia delle regole di elaborazione](admin/c-processing-rules/c-processing-rules-configuration/t-processing-rule-view-history.md)
         + [Ripristinare le regole di elaborazione](admin/c-processing-rules/c-processing-rules-configuration/t-processing-rules-restore.md)
         + [Copiare le regole di elaborazione in un&#39;altra suite di rapporti](admin/c-processing-rules/c-processing-rules-configuration/t-processing-rules-copy-to-rs.md)
      + [Dimensioni disponibili per le regole di elaborazione](admin/c-processing-rules/processing-rule-dimensions.md)
      + Regole di elaborazione, esempi {#processing-rules-examples}
         + [Esempi di regole di elaborazione](admin/c-processing-rules/processing-rules-examples/processing-rules-examples.md)
         + [Compilare un ID campagna da un parametro di stringa query](admin/c-processing-rules/processing-rules-examples/processing-rules-populate-campaign-id.md)
         + [Impostare l&#39;evento di visualizzazione prodotto dalla pagina di panoramica prodotto](admin/c-processing-rules/processing-rules-examples/setting-the-product-view-event.md)
         + [Aggiungere una sottocategoria concatenando la categoria e il nome della pagina](admin/c-processing-rules/processing-rules-examples/subcategory-concatenating.md)
         + [Determinare un percorso copiando un valore eVar in un prop](admin/c-processing-rules/processing-rules-examples/processing-rules-determining-path.md)
         + [Pulizia dei valori in un rapporto](admin/c-processing-rules/processing-rules-examples/clean-up-values-in-a-report.md)
         + [Compilare termini di ricerca interni utilizzando un parametro di stringa query](admin/c-processing-rules/processing-rules-examples/processing-rules-populating-internal-search.md)
         + [Copiare una variabile di dati di contesto in una eVar](admin/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data.md)
         + [Impostare un evento utilizzando una variabile di dati di contesto](admin/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data-event.md)
         + [Rimozione di un evento da un&#39;occorrenza](admin/c-processing-rules/processing-rules-examples/processing-rules-remove-event.md)
      + [Suggerimenti e trucchi per le regole di elaborazione](admin/c-processing-rules/processing-rules-tips.md)
   + Rapporti in tempo reale {#real-time-reports}
      + [Panoramica rapporti in tempo reale](admin/realtime/realtime.md)
      + [Configurazione rapporti in tempo reale](admin/realtime/t-realtime-admin.md)
      + [Metriche e dimensioni in tempo reale supportate](admin/realtime/realtime-metrics.md)
   + [Coda dei report pianificati](admin/scheduled-reports-admin.md)
   + Inoltro lato server {#server-side-forwarding}
      + [Panoramica sull&#39;inoltro lato server](admin/c-server-side-forwarding/ssf.md)
      + [Conformità a RGPD/ePrivacy e inoltro lato server](admin/c-server-side-forwarding/ssf-gdpr.md)
      + [Requisiti per l&#39;inoltro lato server](admin/c-server-side-forwarding/ssf-requirements.md)
      + [Dati inoltri lato server e riferimento al codice](admin/c-server-side-forwarding/ssf-reference.md)
      + [Verificare l&#39;implementazione lato server](admin/c-server-side-forwarding/ssf-verify.md)
      + [Domande frequenti sull&#39;inoltro lato server](admin/c-server-side-forwarding/ssf-faq.md)
   + [Menu dei rapporti semplificati](admin/t-simplified-menu.md)
   + [Gestione social](admin/social-management.md)
   + Eventi di successo {#success-events}
      + [Panoramica eventi di successo](admin/c-success-events/success-event.md)
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
+ Analytics in Adobe Admin Console {#admin-console}
   + [Analytics in Adobe Admin Console](admin-console/home.md)
   + Autorizzazioni {#permissions}
      + [Autorizzazioni di Analytics in Admin Console](admin-console/permissions/summary-tables.md)
      + [Profili di prodotto per Adobe Analytics](admin-console/permissions/product-profile.md)
      + [Autorizzazioni del profilo di prodotto per gli strumenti Report Suite](admin-console/permissions/report-suite-tools.md)
      + [Autorizzazioni del profilo di prodotto per gli strumenti Analytics](admin-console/permissions/analytics-tools.md)
   + [Prima guida dell&#39;amministratore di Adobe Analytics](admin-console/first-admin-guide.md)
+ Impostazioni aziendali {#company-settings}
   + [Panoramica delle impostazioni aziendali](company/c-company-settings.md)
   + [Livelli di accesso alle funzionalità](company/feature-access-levels.md)
   + [Servizi web](company/web-services-admin.md)
   + [Report del Report Builder](company/report-builder-reports-admin.md)
   + [Single sign-on](company/single-signon-admin.md)
   + [Azioni in sospeso](company/pending-actions-admin.md)
   + [Co-branding](company/co-branding-admin.md)
   + [Nascondere suite di rapporti](company/c-hide-report-suites.md)
   + [Sicurezza Manager](company/security-manager.md)
   + [Fine di &quot;Applica restrizioni di accesso IP&quot;](company/login-restrictions-eol.md)
+ Gestione suite di rapporti {#manage-report-suites}
   + [Report Suite Manager](c-manage-report-suites/report-suites-admin.md)
   + [Suite di rapporti rollup e globali](c-manage-report-suites/rollup-report-suite.md)
   + [Creare una suite di rapporti rollup](c-manage-report-suites/t-rollups.md)
   + Modelli suite di rapporti {#report-suite-templates}
      + [Panoramica dei modelli delle suite di rapporti](c-manage-report-suites/c-report-suite-templates/report-suite-templates.md)
      + [Portale Aggregator](c-manage-report-suites/c-report-suite-templates/aggregator-portal.md)
      + [Commercio](c-manage-report-suites/c-report-suite-templates/commerce-admin.md)
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
      + [Impostazioni non copiate da un&#39;origine di rapporti](c-manage-report-suites/c-new-report-suite/settings-not-copied-from-rs.md)
   + [Creare un gruppo suite di rapporti](c-manage-report-suites/t-create-rs-group.md)
+ Gestione di utenti e prodotti (Legacy) {#user-product-management}
   + [Gestione di utenti e prodotti](user-management2/user-management.md)
   + [Assegnare gruppi di utenti a una suite di rapporti](user-management2/t-group-access-report-suite.md)
   + Gestione utente {#user-management}
      + [Panoramica sulla gestione utente](user-management2/c-user-management/users.md)
      + [Aggiungere un account utente](user-management2/c-user-management/t-add-user-account.md)
      + [Modifiche alle autorizzazioni Utente e Gruppo](user-management2/c-user-management/permissions-changes.md)
      + [Trasferimento elementi dell&#39;account utente](user-management2/c-user-management/t-transfer-user-accout-privileges.md)
      + [Aggiungere un utente a un gruppo](user-management2/c-user-management/t-add-user-to-group.md)
      + Migrazione utenti ad Adobe Admin Console {#migrate-users}
         + [Migrazione degli utenti di Analytics all’Admin Console](user-management2/user-migration/c-migration-tool.md)
         + [Eseguire la migrazione degli account utente di Analytics per Adobe ID](user-management2/user-migration/t-migrate-users.md)
         + [Eseguire la migrazione degli account utente di Analytics per Enterprise ID e Federated ID](user-management2/user-migration/migrate-enterprise.md)
         + [Disattivazione degli accessi legacy](user-management2/user-migration/t-disable-legacy-login.md)
         + [API interessate dalla migrazione](user-management2/user-migration/developer.md)
      + [Gestione degli utenti Ad Hoc Analysis](user-management2/c-user-management/t-manage-dsc-users-admin.md)
   + Gruppi utente {#user-groups}
      + [Aggiungere un gruppo utenti](user-management2/c-user-groups/t-user-group.md)
      + [Impostazioni gruppo utenti](user-management2/c-user-groups/groups.md)
   + Personalizzare l&#39;accesso ai rapporti {#customize-report-access}
      + [Panoramica di personalizzazione accesso ai rapporti](user-management2/c-customize-report-access/groups-customize-report-access.md)
      + [Personalizzare le autorizzazioni degli strumenti di Analytics](user-management2/c-customize-report-access/groups-analytics-tools.md)
      + [Personalizzare le autorizzazioni degli strumenti delle suite di rapporti](user-management2/c-customize-report-access/groups-report-suite-tools.md)
      + [Personalizzare le autorizzazioni delle metriche](user-management2/c-customize-report-access/groups-metrics.md)
      + [Personalizzare le autorizzazioni della dimensione](user-management2/c-customize-report-access/groups-dimensions.md)
   + [Invia e-mail agli utenti](user-management2/t-email-users.md)
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
   + [Variabili per la generazione di rapporti sulla privacy](c-data-governance/consent-variables.md)
+ Utilizzo delle chiamate server {#server-call-usage}
   + [Panoramica sull&#39;utilizzo delle chiamate server](c-server-call-usage/overage-overview.md)
   + [Visualizzazione dell&#39;utilizzo della chiamata server corrente](c-server-call-usage/server-call-usage-dashboard.md)
   + [Visualizzazione dell&#39;utilizzo della suite di rapporti](c-server-call-usage/report-suite-usage.md)
   + [Avvisi di utilizzo delle chiamate server](c-server-call-usage/scu-alerts.md)
   + [Domande frequenti sull&#39;utilizzo delle chiamate server](c-server-call-usage/overage-faq.md)
+ Gestione traffico {#traffic-management}
   + [Gestione del traffico](c-traffic-management/traffic-management.md)
   + [Pianificare un picco di traffico](c-traffic-management/t-traffic-schedule-spike.md)
   + [Stimare chiamate server passate e pianificare un picco di traffico](c-traffic-management/traffic-spike-estimate-past-server-calls.md)
   + [Specificare aumento traffico permanente](c-traffic-management/t-traffic-permanent.md)
   + [Tempo di lead richiesto per aumento di traffico](c-traffic-management/traffic-lead-time.md)
+ [Amministratore API](c-admin-api/c-admin-api.md)
