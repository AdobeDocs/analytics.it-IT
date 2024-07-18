---
description: Scopri le linee guida e le raccomandazioni per il consenso degli utenti a memorizzare o leggere cookie non essenziali su dispositivi o browser.
title: Quali sono le linee guida CNIL per il consenso degli utenti e i cookie
feature: Data Governance
role: Admin
exl-id: 04179e58-dbba-45e2-ba57-7fe5fdedc483
source-git-commit: 43c39b99cbae3e714b7f017dec14dd02fa350790
workflow-type: tm+mt
source-wordcount: '646'
ht-degree: 65%

---

# Esenzione dal consenso CNIL

Il 1° ottobre 2020 l’Autorità francese per la protezione dei dati (il &quot;CNIL&quot;) ha pubblicato una versione rivista delle sue linee guida sui cookie (le &quot;Linee guida&quot;) e le raccomandazioni finali per ottenere il consenso degli utenti a memorizzare o leggere cookie non essenziali e tecnologie simili sui dispositivi o browser degli utenti (il &quot;Recommendations&quot;).

Le Linee guida prevedono un’esenzione limitata dall’obbligo di consenso (&quot;Esenzione dal consenso&quot;). L’Esenzione dal consenso si applica ai cookie di analisi il cui scopo è limitato alla misurazione del pubblico del sito o dell’app solo per conto dell’editore Web. Le Linee guida prevedono che, ai fini dell’applicazione dell’Esenzione dal consenso, si adottino le seguenti condizioni:

* Periodo massimo di conservazione dei dati di 25 mesi.  È possibile rivedere le impostazioni di conservazione dei dati correnti in [!UICONTROL Analytics] > [!UICONTROL Admin] > [!UICONTROL Data Governance].  [Conservazione dati](https://experienceleague.adobe.com/docs/analytics/technotes/data-retention.html?lang=it)
* Disattiva i cookie di terze parti in ECID. [disableThirdPartyCalls](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disablethirdpartycalls.html?lang=it#id-service-api), [disableThirdPartyCookies](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disable-cookies.html?lang=it#id-service-api) e [disableIdSyncs](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disableidsync.html?lang=it#id-service-api)
* Limite di 13 mesi per i cookie.   Puoi modificare la scadenza dei cookie di analisi utilizzando la variabile `cookieLifetime`.  I cookie di Experience Cloud, tra cui Analytics ed ECID, estendono la data di scadenza del cookie a ogni visita.  Per impostare una scadenza dei cookie statica e non continua, puoi: (1) scrivere un codice personalizzato per impostare una data in cui eliminare il cookie, oppure (2) utilizzare la tua CMP per gestire la data della reimpostazione del cookie. [cookieLifetime](https://experienceleague.adobe.com/docs/analytics/implementation/vars/config-vars/cookielifetime.html?lang=it) e [cookie di Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-privacy.html?lang=it#ec-cookies)
* Ambito limitato. L’ambito del cookie deve essere limitato a un solo sito o applicazione. [Cookie del browser](https://experienceleague.adobe.com/docs/analytics/technotes/cookies/cookies.html#third-party-cookie-limitations)
* Anonimizzazione. Anonimizza l’ultimo ottetto dell’indirizzo IP. [Impostazioni account generali](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md)
* Nascondi l’ID visitatore dal reporting.   Per impostazione predefinita, gli ID visitatore non sono visibili in Adobe Workspace e Adobe Reports and Analytics.   Gli ID visitatore sono disponibili in Data Feeds e Data Warehouse.   L&#39;accesso ai feed di dati e alla Data Warehouse può essere limitato da [Autorizzazioni di accesso nell&#39;Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/administration/admin-getting-started.html?lang=it) e [Riferimento colonna feed di dati](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=it#columns%2C-descriptions%2C-and-data-types)
* Parametri di geolocalizzazione. La geolocalizzazione non può essere più precisa del livello del codice postale. [Opzioni Zip](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/zip.html) e [Impostazioni account generali](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/general-acct-settings-admin.html?lang=it)
* Imposta le opzioni opt-in.   Il servizio opt-in consente di impostare i protocolli visitatore per determinare se è possibile impostare un cookie sul dispositivo o sul browser dell&#39;utente che visita il sito. [Servizio Opt-in](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html?lang=it)
* Impedisci la condivisione dei dati.   Per impedire la condivisione dei dati su Adobe Audience Manager, utilizza la variabile di contesto `opt.dmp` per [Privacy Reporting](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/privacy-reporting.md) per bloccare la condivisione degli hit.
* Capacità di accesso ed eliminazione. Utilizza Privacy Service per le richieste di accesso ed eliminazione. [Analytics &amp; Privacy Service](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/an-gdpr-overview.html?lang=it)

## Considerazioni aggiuntive per la raccolta dei dati

Si applicano le seguenti considerazioni aggiuntive:

* Adobe Analytics gestisce centri di elaborazione dati negli Stati Uniti, nel Regno Unito e a Singapore al fine di fornire flessibilità a tutti i clienti per raccogliere, elaborare e archiviare i propri dati a livello regionale. Durante la configurazione della configurazione iniziale di Adobe Analytics, i clienti possono selezionare la posizione desiderata del centro di elaborazione dati. I dati dei clienti vengono infine memorizzati nell’area selezionata per il prodotto Analytics di base.
* Prendi in considerazione la raccolta dello stato di consenso (opt-in) in una variabile Analytics al fine di separare i dati con e senza consenso per la segmentazione, per le suite di rapporti virtuali o per l’indirizzamento a end-point diversi.
* Nessuna misurazione all’esterno del sito o dell’app senza previo consenso, ad esempio nessuna campagna off-site, campagne e-mail o iFrame.
* La raccolta di informazioni personali in variabili non è consentita senza consenso. [Controllare le attività Experience Cloud in base al consenso degli utenti](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/use-opt-in-to-control-experience-cloud-activities-based-on-user-consent.html#implementing-opt-in-on-the-page)
* I dati devono essere utilizzati solo per produrre dati statistici anonimi, senza essere combinati con altri dati.
* I dati non vengono utilizzati per azioni di riferimento incrociato.
* I dati di geolocalizzazione GPS non vengono raccolti.
* Se si ottiene il consenso dell’utente finale, è possibile modificare le impostazioni di cui sopra e attenuare le restrizioni.

>[!IMPORTANT]
>
>Il presente documento non ha valore di consulenza legale o regolamentare e non costituisce alcuna garanzia o impegno contrattuale da parte dell&#39;Adobe. Incoraggiamo i clienti a richiedere una consulenza legale indipendente sugli obblighi legali e normativi del cliente su questioni relative a questo argomento.


Per ulteriori informazioni, consulta il sito Web [Esenzione dai cookie CNIL](https://www.cnil.fr/en/sheet-ndeg16-use-analytics-your-websites-and-applications).

