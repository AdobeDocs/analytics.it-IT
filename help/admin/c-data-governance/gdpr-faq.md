---
description: Domande frequenti sulla governance dei dati in Adobe Analytics
title: Domande frequenti sulla governance dei dati
feature: Data Governance
exl-id: 57399c1b-cf08-405b-8c1b-9d23e4c38716
source-git-commit: 82c69131fcc5a22795e44ed97246240aec31f4d9
workflow-type: tm+mt
source-wordcount: '1867'
ht-degree: 88%

---

# Domande frequenti

+++ **In che modo Adobe Analytics supporta le richieste di accesso e di cancellazione per gli utenti finali (persone interessate) convalidate dai clienti (titolari del trattamento)?**

Quando entreranno in vigore varie regole sulla privacy dei dati (RGPD, CCPA), Adobe Analytics supporterà l’elaborazione delle richieste verificate inviate dai titolari del trattamento all’API Privacy dei dati di Experience Cloud per consentire un processo più automatizzato. L’API della Privacy dei dati per Adobe è stata pensata per favorire l’elaborazione delle richieste di diritti emesse dagli individui (ad esempio, richieste di accesso e di cancellazione) per i dati dei clienti archiviati nelle soluzioni Adobe Experience Cloud. È flessibile e scalabile in base al numero di richieste di accesso e di cancellazione dei dati che la società riceve dalle persone interessate.

Inoltre, l’API di Privacy Service consente ai clienti di controllare lo stato del processo tramite il quale le richieste di accesso e di cancellazione dei dati vengono soddisfatte. Per altre informazioni consulta la [](https://developer.adobe.com/experience-platform-apis/references/privacy-service/)Documentazione sull’API di Privacy Service.

+++

+++ **Quale figura si occupa di ricevere, accettare e soddisfare le richieste di Privacy dei dati degli utenti finali?**

Il Titolare del trattamento (ossia il Cliente Adobe) ha la sola responsabilità di fornire alle persone interessate i dati personali in risposta a una richiesta di diritti individuali ai sensi della Privacy dei dati. Il titolare del trattamento è anche responsabile della ricezione e dell’accettazione delle richieste, tramite la verifica dell’identità della persona interessata e il soddisfacimento delle richieste. Per questo potrebbe essere necessario contattare Adobe con gli ID delle persone interessate che possono essere associate ai dati archiviati in Adobe Analytics.

In qualità di responsabile dei dati, Adobe deve fornire sufficiente assistenza al titolare del trattamento per consentirgli di elaborare le richieste verificate entro un periodo di tempo accettabile.

+++

+++ **In che modo i clienti di Adobe (titolari del trattamento) individueranno le richieste di Privacy dei dati da mappare in corrispondenza agli ID in Adobe Analytics per l’elaborazione della Privacy dei dati?**

I titolari del trattamento determineranno come risolvere le identità per le richieste delle persone interessate. Prendi in considerazione la distribuzione del  tag di recupero degli ID Privacy dei dati di Adobe. I team di sviluppo risparmieranno molto tempo usando il tag di recupero degli ID Privacy dei dati per acquisire gli ID degli utenti (ID cookie) e l’API della Privacy dei dati per inviare gli ID degli utenti alle soluzioni pertinenti in Adobe Experience Cloud per l’elaborazione della richiesta di Privacy dei dati. L’API della Privacy dei dati può supportare una vasta gamma di ID dei clienti su più soluzioni di Adobe.

Se una persona interessata invia una richiesta insieme a un identificatore (variabile personalizzata: proprietà o eVar), Adobe Analytics analizzerà tutta la cronologia dei dati raccolti per l’identificatore specifico. Per ulteriori informazioni su come configurare gli ID personalizzati memorizzati nelle proprietà o eVar di Analytics, consulta la sezione [Documentazione di Analytics sui namespace](/help/admin/c-data-governance/data-labeling/gdpr-namespaces.md).

+++

+++ **In che modo la governance dei dati di Adobe Analytics supporterà l’elaborazione delle richieste di Privacy dei dati?**

Il nuovo strumento di Adobe Analytics, la governance dei dati, consente ai titolari del trattamento di applicare i controlli e le classificazioni ai dati di Analytics. Questo nuovo strumento permette ai clienti di Adobe di personalizzare l’elaborazione delle richieste di accesso e di cancellazione dei dati della Privacy dei dati. Nella console della governance dei dati, gli amministratori possono definire le impostazioni desiderate da applicare alle diverse colonne di dati in Adobe Analytics. Una volta definite queste etichette, Adobe rispetterà ed elaborerà tutte le richieste di accesso o di cancellazione downstream in base alle impostazioni delle etichette desiderate dai clienti. È responsabilità del titolare del trattamento consultare e discutere con i rappresentanti legali le impostazioni delle etichette. Adobe Analytics incoraggia i clienti a configurare correttamente l’etichettatura dei dati prima della data di entrata in vigore del RGPD, che è il 25 maggio 2018 per consentire il completamento della richiesta tramite l’API Privacy dei dati.

Lo strumento per la governance dei dati contiene le seguenti etichette per i dati:

* Etichette per i dati di identità:  usate per classificare i dati che possono identificare un individuo direttamente o indirettamente in combinazione con altri dati. (Nessuno, I1, I2)

* Etichette per i dati sensibili:  vengono usate per classificare i dati come dati che potrebbero essere definiti sensibili in base alle leggi applicabili. (Nessuno, S1, S2). Al momento l’uso dei dati sensibili in Adobe Analytics è generalmente vietato, ad eccezione dei dati di geolocalizzazione ottenuti in modo adeguato in base alle leggi applicabili e che alcune giurisdizioni potrebbero considerare dati sensibili.

* Etichette per i dati Privacy dei dati:  vengono usate per definire i campi che possono contenere gli identificatori personali da usare nelle richieste relative alla Privacy dei dati o che possono essere rimosse come parte di una richiesta di cancellazione nell’ambito della Privacy dei dati. In alcuni casi queste etichette possono sovrapporsi alle etichette per l’identità e per i dati sensibili.

Per altre informazioni sulle etichette per la governance dei dati, vedi [ Etichette Privacy dei dati per le variabili di Analytics](/help/admin/c-data-governance/data-labeling/gdpr-labels.md).

+++

+++ **Dove trovo informazioni su come prepararmi alla Privacy dei dati con Adobe Analytics?**

Per informazioni dettagliate su come prepararsi alle normative sulla Privacy dei dati, consulta [ Flusso di lavoro sulla privacy dei dati di Adobe Analytics](/help/admin/c-data-governance/an-gdpr-workflow.md).

+++

+++ **In che modo i titolari del trattamento devono considerare il consenso quando si tratta di coinvolgere l’utente?**

Il RGPD e il CCPA rappresentano una buona opportunità per riconsiderare la strategia e le pratiche di gestione del consenso, che implica la determinazione della necessità del consenso e la considerazione della proposta di valore per l’utente. Considera la proposta di valore rispetto alla privacy del cliente: questo contribuisce a guidare la conversione e la fedeltà.  Lo spazio di gestione del consenso (ad esempio, strumenti, standard, pratiche consigliate) si evolve rapidamente e deve essere sempre controllato. Per ridurre al minimo l’impatto sul coinvolgimento dell’utente, i titolari del trattamento devono consultare i fornitori e i propri legali in questo spazio, oltre a seguire le leggi e le disposizioni europee sul consenso e i cookie. Una buona strategia è considerare la “privacy sperimentale” usando un’esperienza sul marchio pertinente a livello contestuale che definisca la proposta di valore delle attività di raccolta dei dati.

In qualità di titolare del trattamento, è tua responsabilità ottenere il consenso esplicito delle persone interessate prima di raccogliere i dati personali (che potrebbero includere i dati di Adobe Analytics) e implementare un [meccanismo di opt-out](https://www.adobe.com/it/privacy/opt-out.html#customeruse) sul sito web. Questo consentirà alle persone interessate di negare future raccolte di dati di Adobe Experience Cloud.

+++

+++ **In che modo i titolari del trattamento devono considerare la conservazione dei dati quando si tratta di Privacy dei dati?**

La Privacy dei dati indica che in genere i dati personali non devono essere conservati per un periodo più lungo del tempo necessario a raggiungere lo scopo per cui sono stati raccolti.  Come indicato da Adobe nella comunicazione ai clienti di febbraio, applicheremo un piano di conservazione dei dati di 25 mesi per la maggior parte dei clienti, a meno che non siano stati presi accordi diversi (soggetti alla notifica e all’autorizzazione dei clienti). Ai clienti verrà richiesto di impostare i criteri di conservazione dei dati per consentire ad Adobe di elaborare le richieste di Privacy dei dati.

Adobe Analytics richiede ai clienti di impostare la conservazione dei propri dati per elaborare le richieste di Privacy dei dati. I criteri di conservazione dei dati correnti di ogni suite di report vengono visualizzati nella nuova interfaccia utente Admin Governance dei dati. Se è necessario modificare i criteri di conservazione dei dati, i clienti devono contattare il proprio rappresentante Adobe. Fai riferimento a [Domande frequenti sulla conservazione dei dati in Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/technotes/data-retention.html?lang=en).

+++

+++ **Un cliente può ridurre o estendere il periodo di conservazione dei dati predefinito?**

I clienti possono chiedere che i propri dati vengano cancellati prima dei 25 mesi telefonando all’assistenza clienti. I clienti possono estendere il periodo di conservazione dei dati oltre i 25 mesi acquistando un’estensione. Sono disponibili proroghe di 1 (uno) anno supplementare, fino a un massimo di 8 (otto) anni aggiuntivi (10 anni totali). Per attivare queste estensioni potrebbe essere necessario aggiornare i termini del contratto e pagare una tariffa aggiuntiva.

+++

+++ **Quali considerazioni sulla privacy un titolare del trattamento dovrebbe fare quando si esportano dati personali da Adobe Analytics?**

Se un cliente usa i feed dei dati di Adobe Analytics per esportare i dati da Analytics nel data warehouse aziendale o in altri sistemi esterni ad Adobe, è responsabilità del cliente (titolare del trattamento) assicurarsi che le richieste di cancellazione vengano applicate ai dati. Questo vale anche per le implementazioni on-premise di Adobe Data Workbench, in cui un feed di dati Adobe Analytics continuo popola i dati della Data Workbench. Adobe può fornire gli strumenti di supporto nell’individuazione e nella cancellazione dei record di determinati tipi di feed di dati, inclusi quelli usati per Data Workbench, ma è ancora responsabilità del cliente (titolare del trattamento) assicurarsi che i dati vengano cancellati coerentemente con i propri criteri interni di conservazione e cancellazione dei dati.

Considera anche i casi in cui i dipendenti hanno scaricato rapporti di Adobe Analytics che contengono dati personali. È possibile che sia necessario aggiornare o cancellare questi rapporti se si riceve una richiesta di Privacy dei dati di cancellazione correlata alla privacy che implica la presenza di un ID nel rapporto. I clienti devono consultare i legali della società per determinare i periodi di conservazione e i requisiti di privacy e sicurezza che devono essere applicati a questi tipi di documenti.

+++

+++ **Alcuni dati che non dovevamo raccogliere sono stati accidentalmente inviati ad Adobe Analytics. È possibile usare l’API Privacy dei dati per pulire questi dati?**

La [API di Data Privacy Service](https://developer.adobe.com/experience-platform-apis/references/privacy-service/) è stato fornito per aiutarti a soddisfare le richieste relative alla Privacy dei dati, soggette a scadenza. L’utilizzo di questa API per altri scopi non è supportato da Adobe e potrebbe influire sulla capacità di Adobe di fornire tempestivamente richieste di Privacy dei dati avviate dall’utente ad alta priorità per altri clienti Adobe. Chiediamo all’utente di non utilizzare l’API Privacy dei dati per altri scopi, come la cancellazione dei dati che sono stati accidentalmente inviati in grandi gruppi di visitatori. È inoltre necessario tenere presente che ogni visitatore con un hit eliminato (aggiornato o anonimizzato) a seguito di una richiesta di cancellazione di Privacy dei dati avrà le informazioni sullo stato reimpostate. La prossima volta che il visitatore ritorna sul tuo sito web, sarà un nuovo visitatore. Tutte le attribuzioni eVar ricominceranno, così come informazioni quali numeri di visita, referrer, prima pagina visitata, ecc. Questo effetto collaterale non è opportuno nelle situazioni in cui si desidera cancellare i campi di dati ed evidenzia un motivo per cui l’API Privacy dei dati è inappropriata per questo utilizzo.

Contatta il tuo Account Manager (CSM) per coordinarti con il nostro team di consulenza ingegneristico per eseguire un’ulteriore esame e rimuovere eventuali problemi di PII o dati.

+++

+++ **Il nostro team legale ha stabilito che i valori che raccogliamo in una variabile da anni non sono più conformi alla nostra politica sulla privacy aggiornata. È possibile usare l’API Privacy dei dati per cancellare tutti i valori da questa variabile?**

La [API di Data Privacy Service](https://developer.adobe.com/experience-platform-apis/references/privacy-service/) è stato fornito per aiutarti a soddisfare le richieste relative alla Privacy dei dati, soggette a scadenza. L’utilizzo di questa API per altri scopi non è supportato da Adobe e potrebbe influire sulla capacità di Adobe di fornire tempestivamente richieste di Privacy dei dati avviate dall’utente ad alta priorità per altri clienti Adobe. Chiediamo all’utente di non utilizzare l’API Privacy dei dati per altri scopi, come la cancellazione dei dati che sono stati accidentalmente inviati in grandi gruppi di visitatori.

È inoltre necessario tenere presente che ogni visitatore con un hit eliminato (aggiornato o anonimizzato) a seguito di una richiesta di cancellazione di Privacy dei dati avrà le informazioni sullo stato reimpostate. La prossima volta che il visitatore ritorna sul tuo sito web, sarà un nuovo visitatore. Tutte le attribuzioni eVar ricominceranno, così come informazioni quali numeri di visita, referrer, prima pagina visitata, ecc. Questo effetto collaterale non è opportuno nelle situazioni in cui si desidera cancellare i campi di dati ed evidenzia un motivo per cui l’API Privacy dei dati è inappropriata per questo utilizzo.

Contatta il tuo Account Manager (CSM) per coordinarti con il nostro team di consulenza ingegneristico al fine di eseguire un’ulteriore esame e rimuovere eventuali problemi di PII o dati.

+++


Ulteriori risorse sulla Privacy dei dati:

* [Termini comuni sul RGPD](https://landing.adobe.com/dam/uploads/2018/in/adobe_gdpr_commonterms.pdf)
* [Pacchetto di assistenza](https://landing.adobe.com/dam/uploads/2018/in/adobe_gdpr_carepackage.pdf) per la Privacy dei dati di Experience Cloud
* [Post di blog](https://theblog.adobe.com/experiential-privacy-an-investment-opportunity-for-the-experience-business/) sulla privacy sperimentale
