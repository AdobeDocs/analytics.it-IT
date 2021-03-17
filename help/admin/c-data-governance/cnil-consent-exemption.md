---
description: Scopri le linee guida e le raccomandazioni per il consenso degli utenti a memorizzare o leggere cookie non essenziali su dispositivi o browser.
title: Quali sono le linee guida CNIL per il consenso degli utenti e i cookie
translation-type: tm+mt
source-git-commit: fefc2433ef42bae232a9a9afc1040be8d04b2bbe
workflow-type: tm+mt
source-wordcount: '637'
ht-degree: 79%

---


# Esenzione dal consenso CNIL

Il 1° ottobre 2020 l’autorità francese per la protezione dei dati (il “CNIL”) ha pubblicato una versione aggiornata delle sue linee guida sui cookie (le “Linee guida”) e le raccomandazioni definitive per ottenere il consenso degli utenti a memorizzare o leggere cookie non essenziali, e tecnologie simili, sui dispositivi o browser degli utenti (le “Raccomandazioni”).

Le Linee guida prevedono un’esenzione limitata dall’obbligo del consenso (“Esenzione del consenso”). L’Esenzione dal consenso si applica ai cookie di analisi il cui scopo è limitato alla misurazione del pubblico del sito o dell’app solo per conto dell’editore Web. Le Linee guida prevedono che, ai fini dell’applicazione dell’Esenzione dal consenso, si adottino le seguenti condizioni:

* Periodo massimo di conservazione dei dati di 25 mesi. Puoi controllare le impostazioni attuali per la conservazione dei dati in Analytics > Admin > Data Governance. [Conservazione dati](https://experienceleague.adobe.com/docs/analytics/technotes/data-retention.html?lang=it)
* Disattiva i cookie di terze parti in ECID. [disableThirdPartyCalls](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disablethirdpartycalls.html?lang=en#id-service-api),  [disableThirdPartyCookies](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disable-cookies.html?lang=en#id-service-api) e  [disableIdSyncs](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disableidsync.html?lang=en#id-service-api)
* Limite di cookie a 13 mesi impostato su una data statica, senza scorrimento.  Puoi modificare la scadenza dei cookie di analisi utilizzando la variabile `cookieLifetime`.   [cookieLifetime](https://experienceleague.adobe.com/docs/analytics/implementation/vars/config-vars/cookielifetime.html?lang=it)
* Ambito limitato. L’ambito del cookie deve essere limitato a un solo sito o applicazione. [Cookie del browser](https://experienceleague.adobe.com/docs/analytics/technotes/cookies.html?lang=it&quot;\l&quot;third-party-cookie-implementations)
* Anonimizzazione. Anonimizza l’ultimo ottetto dell’indirizzo IP. [Impostazioni account generali](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/general-acct-settings-admin.html?lang=it)
* Nascondi l’ID visitatore dal reporting.   Per impostazione predefinita, gli ID visitatore non sono visibili in Adobe Workspace e Adobe Reports and Analytics.   Gli ID visitatore sono disponibili in Data Feeds e Data Warehouse.   L’accesso a Data Feeds e Data Warehouse può essere limitato da [Autorizzazioni di accesso in Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=it&quot;\l&quot;task_040673FE3E3E429B9531FBCB8B6A4391) e [Riferimento colonna feed dati](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=en#columns%2C-descriptions%2C-and-data-types)
* Parametri di geolocalizzazione. La geolocalizzazione non può essere più precisa del livello del codice postale. [Opzioni Zip](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/zip.html?lang=it&quot;\l&quot;zip-in-adobe-experience-platform-launch) e [Impostazioni account generali](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/general-acct-settings-admin.html?lang=it&quot;\l&quot;admin-tools)
* Imposta le opzioni opt-in.   Il servizio Opt-in consente di configurare i protocolli visitatore per identificare se è possibile impostare un cookie sul dispositivo o sul browser dell’utente che visita il tuo sito. [Servizio Opt-in](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html?lang=it)
* Impedisci la condivisione dei dati.   Per impedire la condivisione dei dati su Adobe Audience Manager, utilizza la variabile di contesto `opt.dmp` per [Privacy Reporting](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/consent-variables.html?lang=it&quot;\l&quot;variables) per bloccare la condivisione degli hit.
* Capacità di accesso ed eliminazione. Utilizza Privacy Service per le richieste di accesso ed eliminazione. [Analytics &amp; Privacy Service](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/an-gdpr-overview.html?lang=it)

## Considerazioni aggiuntive per la raccolta dei dati

Si applicano le seguenti considerazioni aggiuntive:

* Prendi in considerazione la raccolta dello stato di consenso in una variabile Analytics al fine di separare i dati di consenso dai dati di rinuncia per la segmentazione, le suite di rapporti virtuali o per indirizzare a punti finali separati.
* Nessuna misurazione all’esterno del sito o dell’app senza previo consenso, ad esempio nessuna campagna off-site, campagne e-mail o iFrame.
* La raccolta di informazioni personali in variabili non è consentita senza consenso. [Controllare le attività Experience Cloud in base al consenso degli utenti](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/use-opt-in-to-control-experience-cloud-activities-based-on-user-consent.html?lang=en%22%20\l%20%22implementation#implementation)
* I dati devono essere utilizzati solo per produrre dati statistici anonimi, senza essere combinati con altri dati.
* I dati non vengono utilizzati per azioni di riferimento incrociato.
* I dati di geolocalizzazione GPS non vengono raccolti.
* Quando viene concesso il consenso dell’utente finale, le impostazioni di cui sopra possono essere modificate e le restrizioni possono essere attenuate.

Per ulteriori informazioni, consulta il sito Web [Esenzione dai cookie CNIL](https://www.cnil.fr/en/sheet-ndeg16-use-analytics-your-websites-and-applications).
