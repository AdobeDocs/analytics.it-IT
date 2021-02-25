---
description: Scopri le linee guida e le raccomandazioni per il consenso degli utenti a memorizzare o leggere cookie non essenziali su dispositivi o browser.
title: Quali sono le linee guida CNIL per il consenso degli utenti e i cookie
translation-type: tm+mt
source-git-commit: c5ebc92622e012699d64c27701b24a88429e9f4f
workflow-type: tm+mt
source-wordcount: '504'
ht-degree: 1%

---


# Esenzione dal consenso CNIL

Il 1° ottobre 2020 l’autorità francese per la protezione dei dati (il &quot;CNIL&quot;) ha pubblicato una versione rivista delle sue linee guida sui cookie (le &quot;Linee guida&quot;) e le sue raccomandazioni finali per ottenere il consenso degli utenti a memorizzare o leggere cookie non essenziali e tecnologie simili sui dispositivi o browser degli utenti (il &quot;Recommendations&quot;).

Gli orientamenti prevedono un’esenzione limitata dall’obbligo di autorizzazione (&quot;esenzione del consenso&quot;). L&#39;esenzione dal consenso si applica ai cookie di analisi il cui scopo è limitato alla misurazione del pubblico del sito o dell&#39;app solo per conto dell&#39;editore Web. Gli orientamenti prevedono che, ai fini dell&#39;applicazione dell&#39;esenzione dal consenso, si applichino le seguenti condizioni:

* Massimo di conservazione dei dati di 25 mesi  Puoi esaminare le impostazioni di conservazione dei dati correnti in Analytics > Amministratore > Governance dei dati.  [Conservazione dati](https://experienceleague.adobe.com/docs/analytics/technotes/data-retention.html)
* Limite di 13 mesi per i cookie.  Puoi ignorare la scadenza del cookie di analisi utilizzando la variabile `cookieLifetime`.  [cookieLifetime](https://experienceleague.adobe.com/docs/analytics/implementation/vars/config-vars/cookielifetime.html)
* Ambito limitato. L&#39;ambito del cookie deve essere limitato a un solo sito o applicazione. [Cookie browser](https://experienceleague.adobe.com/docs/analytics/technotes/cookies.html?lang=en&quot;\l&quot;implementazioni di cookie di terze parti)
* Anonimizzazione. Anonimizzare l&#39;ultimo ottetto dell&#39;indirizzo IP. [Impostazioni account generali](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/general-acct-settings-admin.html)
* Nascondere l’ID visitatore dal reporting.  Per impostazione predefinita, gli ID visitatore non sono visibili in ’area di lavoro Adobi e ’Reports and Analytics Adobe.  Gli ID visitatore sono disponibili in Feed dati e Data Warehouse.  L&#39;accesso ai feed di dati e alle Date Warehouse può essere limitato da [Autorizzazioni di accesso in  Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=en&quot;\l&quot;task_040673FE3E3E429B9531FBCB8B6A4391)
* Parametri di geolocalizzazione. La geolocalizzazione non può essere più precisa del livello del codice postale. [Opzioni Zip ](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/zip.html?lang=en&quot;\l&quot;zip-in-adobe-experience-platform-launch) e impostazioni  [generali dell&#39;account](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/general-acct-settings-admin.html?lang=en&quot;\l&quot;admin-tools)
* Impostate le opzioni di consenso.  Il servizio di consenso consente di impostare i protocolli dei visitatori per determinare se è possibile impostare un cookie sul dispositivo o sul browser dell&#39;utente durante la visita al sito. [Servizio di consenso](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html)
* Impedisci la condivisione dei dati.  Per impedire la condivisione dei dati su Adobe Audience Manager, utilizzate la variabile di contesto `opt.dmp` per [Privacy Reporting](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/consent-variables.html?lang=en&quot;\l&quot;variables) per bloccare la condivisione degli hit.
* Accesso ed eliminazione. Utilizzate il Privacy Service per le richieste di accesso ed eliminazione. [Analytics e Privacy Service](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/an-gdpr-overview.html)

## Considerazioni aggiuntive per la raccolta dei dati

Si applicano le seguenti considerazioni aggiuntive:

* Nessuna misura all&#39;esterno del sito o dell&#39;app senza previo consenso, ad esempio nessuna campagna off-site, campagne e-mail o iFrame.
* La raccolta di informazioni personali in variabili non è consentita senza consenso.
* I dati devono essere utilizzati solo per produrre statistiche anonime, senza combinazione con altri dati.
* I dati non vengono utilizzati per le azioni di riferimento incrociato.
* I dati di geolocalizzazione GPS non vengono raccolti.

Per ulteriori informazioni, consultare il sito Web [CNIL Cookie Exception](https://www.cnil.fr/en/sheet-ndeg16-use-analytics-your-websites-and-applications).
