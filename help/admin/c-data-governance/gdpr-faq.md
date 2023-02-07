---
description: Domande frequenti sulla governance dei dati in Adobe Analytics
title: Domande frequenti sulla governance dei dati
feature: Data Governance
exl-id: 57399c1b-cf08-405b-8c1b-9d23e4c38716
source-git-commit: f135138de15f3fc788e637128daeb064d0d453af
workflow-type: tm+mt
source-wordcount: '2076'
ht-degree: 52%

---

# Domande frequenti

+++ **In che modo Adobe Analytics supporta le richieste di accesso e di cancellazione per gli utenti finali (persone interessate) convalidate dai clienti (titolari del trattamento)?**

Quando entreranno in vigore varie regole sulla privacy dei dati (RGPD, CCPA), Adobe Analytics supporterà l’elaborazione delle richieste verificate inviate dai titolari del trattamento all’API Privacy dei dati di Experience Cloud per consentire un processo più automatizzato. L’API della Privacy dei dati per Adobe è stata pensata per favorire l’elaborazione delle richieste di diritti emesse dagli individui (ad esempio, richieste di accesso e di cancellazione) per i dati dei clienti archiviati nelle soluzioni Adobe Experience Cloud. È flessibile e scalabile in base al numero di richieste di accesso e cancellazione dei dati che la tua azienda riceve dagli interessati.

Inoltre, l’API di Privacy Service consente al cliente di controllare lo stato del soddisfacimento delle richieste di accesso e cancellazione dei dati. Per altre informazioni consulta la [](https://developer.adobe.com/experience-platform-apis/references/privacy-service/)Documentazione sull’API di Privacy Service.

+++

+++ **Quale figura si occupa di ricevere, accettare e soddisfare le richieste di Privacy dei dati degli utenti finali?**

Il Titolare del trattamento dei dati ha la sola responsabilità di ricevere e accettare le richieste. Il titolare del trattamento convalida l’identità dell’interessato e quindi soddisfa la richiesta. Parte di questa responsabilità può comportare il contatto di Adobi con gli ID degli interessati che possono essere associati ai dati archiviati in Adobe Analytics.

In qualità di responsabile del trattamento dei dati, l’Adobe deve fornire al titolare del trattamento un’assistenza ragionevole per elaborare le richieste verificate entro un periodo di tempo accettabile.

+++

+++ **In che modo i clienti di Adobe (titolari del trattamento) individueranno le richieste di Privacy dei dati da mappare in corrispondenza agli ID in Adobe Analytics per l’elaborazione della Privacy dei dati?**

I Titolari del trattamento dei dati determinano come risolvere l’identità per le richieste degli interessati. Prendi in considerazione la distribuzione del  tag di recupero degli ID Privacy dei dati di Adobe. I team di sviluppo risparmiano tempo usando il tag di recupero degli ID Privacy dei dati per acquisire gli ID degli utenti (ID cookie). Possono quindi utilizzare la nostra API Privacy dei dati per inviare gli ID utente alle soluzioni pertinenti in Adobe Experience Cloud per l’elaborazione della richiesta di Privacy dei dati. L’API della Privacy dei dati può supportare una vasta gamma di ID dei clienti su più soluzioni di Adobe.

Se un interessato invia una richiesta insieme a un identificatore (variabile personalizzata: prop o eVar), Adobe Analytics analizza l’intera cronologia dei dati raccolti per l’identificatore specificato. Per ulteriori informazioni su come configurare gli ID personalizzati memorizzati nelle proprietà o eVar di Analytics, consulta la sezione [Documentazione di Analytics sui namespace](/help/admin/c-data-governance/data-labeling/gdpr-namespaces.md).

+++

+++ **In che modo la governance dei dati di Adobe Analytics supporterà l’elaborazione delle richieste di Privacy dei dati?**

La governance dei dati è un nuovo strumento all’interno di Adobe Analytics che consente ai titolari del trattamento dei dati di applicare controlli e classificazioni ai dati di Analytics. Questo nuovo strumento permette ai clienti di Adobe di personalizzare l’elaborazione delle richieste di accesso e di cancellazione dei dati della Privacy dei dati. Nella console della governance dei dati, gli amministratori possono definire le impostazioni desiderate da applicare alle diverse colonne di dati in Adobe Analytics. Una volta definite queste etichette, Adobe rispetterà ed elaborerà tutte le richieste di accesso o di cancellazione downstream in base alle impostazioni delle etichette desiderate dai clienti. È responsabilità del titolare del trattamento consultare e discutere con i propri rappresentanti legali le impostazioni delle etichette.

Lo strumento per la governance dei dati contiene le seguenti etichette per i dati:

* **Etichette per i dati di identità**: Utilizzato per classificare i dati che possono identificare un individuo direttamente o indirettamente in combinazione con altri dati. (Nessuno, I1, I2)

* **Etichette per i dati sensibili**: Utilizzato per classificare i dati come dati che possono essere definiti sensibili in base alle leggi applicabili. (Nessuno, S1, S2). Al momento l’uso dei dati sensibili in Adobe Analytics è generalmente vietato, ad eccezione dei dati di geolocalizzazione ottenuti in modo adeguato in base alle leggi applicabili e che alcune giurisdizioni potrebbero considerare dati sensibili.

* **Etichette per i dati sulla privacy dei dati**: Utilizzato per definire i campi che possono contenere gli identificatori personali da utilizzare nelle richieste di Privacy dei dati o che devono essere rimossi come parte di una richiesta di cancellazione della Privacy dei dati. In alcuni casi queste etichette possono sovrapporsi alle etichette per l’identità e per i dati sensibili.

Per altre informazioni sulle etichette per la governance dei dati, vedi [ Etichette Privacy dei dati per le variabili di Analytics](/help/admin/c-data-governance/data-labeling/gdpr-labels.md).

+++

+++ **Come posso verificare che le richieste Privacy Service funzionino correttamente per eliminare i dati da Adobe Analytics?**

In genere, i clienti di Analytics impostano alcune suite di rapporti di prova per verificare la funzionalità prima che venga rilasciata al pubblico in generale. I siti web o le app di pre-produzione inviano dati a queste suite di rapporti test/dev/QA per valutare il funzionamento quando il codice viene rilasciato prima che il traffico reale venga inviato alle suite di rapporti di produzione.

Tuttavia, con una normale configurazione, l’elaborazione delle richieste RGDP non può essere verificata inizialmente su queste suite di rapporti di prova, prima di applicare le richieste alle suite di rapporti di produzione. Questo perché una richiesta di Privacy dei dati viene applicata automaticamente a tutte le suite di rapporti nell’organizzazione Experience Cloud, che spesso sono tutte le suite di rapporti per la tua azienda.

Tuttavia, esistono alcuni modi per verificare l’elaborazione Privacy dei dati prima di applicarla a tutte le suite di rapporti:

* Un’opzione consiste nell’impostare un’organizzazione Experience Cloud diversa che contiene solo suite di rapporti di prova. Quindi si utilizza questa organizzazione Experience Cloud per il test Privacy dei dati e la normale organizzazione Experience Cloud per l’elaborazione effettiva Privacy dei dati.

* Un’altra opzione consiste nell’assegnare namespace diversi agli ID nelle suite di rapporti di prova rispetto a quelle presenti nelle suite di rapporti di produzione. Ad esempio, puoi usare il prefisso “qa-” per ogni namespace nelle suite di rapporti di prova. Quando si inviano richieste di Privacy dei dati con solo namespace con il prefisso qa, queste richieste verranno eseguite solo sulle suite di rapporti di prova. Successivamente, quando si inviano le richieste senza il prefisso qa, vengono applicate alle suite di rapporti di produzione. **Questo è l’approccio consigliato, a meno che non si utilizzino i namespace visitorId, AAID, ECID o customVisitorId. Questi namespace sono codificati e non è possibile specificarne nomi alternativi nelle suite di rapporti di prova.**

+++

+++ **Dove trovo informazioni su come prepararmi alla Privacy dei dati con Adobe Analytics?**

Per informazioni dettagliate su come prepararsi alle normative sulla Privacy dei dati, consulta [ Flusso di lavoro sulla privacy dei dati di Adobe Analytics](/help/admin/c-data-governance/an-gdpr-workflow.md).

+++

+++ **In che modo i titolari del trattamento devono considerare il consenso quando si tratta di coinvolgere l’utente?**

Il RGPD e il CCPA sono buone opportunità per riconsiderare la strategia e le pratiche di gestione del consenso. Ciò include determinare quando è necessario il consenso e pensare alla proposta di valore per l&#39;utente. Considera la proposta di valore rispetto alla privacy del cliente: questo contribuisce a guidare la conversione e la fedeltà. Lo spazio di gestione del consenso (ad esempio, strumenti, standard, pratiche consigliate) si evolve rapidamente e deve essere sempre controllato. Per ridurre al minimo l&#39;impatto sul coinvolgimento dell&#39;utente, i titolari del trattamento devono collaborare con i fornitori in questo spazio e con il proprio consulente legale, per assicurarsi che stiano seguendo le leggi e le linee guida emergenti sul consenso e i cookie. Una buona strategia è considerare la “privacy sperimentale” usando un’esperienza sul marchio pertinente a livello contestuale che definisca la proposta di valore delle attività di raccolta dei dati.

In qualità di titolare del trattamento dei dati, è tua responsabilità ottenere il consenso esplicito degli interessati prima di raccogliere i dati su di essi (che potrebbero includere i dati di Adobe Analytics) e implementare un [meccanismo di rinuncia](https://www.adobe.com/it/privacy/opt-out.html#customeruse) sul sito web. Questo consente agli interessati di rinunciare alla futura raccolta di dati Adobe Experience Cloud.

+++

+++ **In che modo i titolari del trattamento devono considerare la conservazione dei dati quando si tratta di Privacy dei dati?**

I dati personali generalmente non devono essere conservati per un periodo più lungo del necessario per raggiungere lo scopo per cui sono stati raccolti. I Termini Generali di Adobe applicano un piano predefinito di conservazione dei dati di 25 mesi, a meno che non venga concordato un termine diverso per la conservazione dei dati. Ai clienti viene richiesto di impostare i criteri di conservazione dei dati per consentire ad Adobe di elaborare una richiesta di Privacy dei dati.

I criteri di conservazione dei dati correnti di ogni suite di report vengono visualizzati nella nuova interfaccia utente Admin Governance dei dati. Se è necessario modificare i criteri di conservazione dei dati, i clienti devono contattare il proprio rappresentante di Adobe. Fai riferimento a [Domande frequenti sulla conservazione dei dati in Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/technotes/data-retention.html?lang=en).

+++

+++ **Un cliente può ridurre o estendere il periodo predefinito di conservazione dei dati?**

I clienti possono richiedere che i loro dati vengano cancellati prima dei 25 mesi contattando l’Assistenza clienti. Inoltre i clienti possono estendere il periodo di conservazione dei dati oltre i 25 mesi acquistando un’estensione. Sono disponibili proroghe di 1 anno supplementare, fino a un massimo di 8 anni aggiuntivi (10 anni totali). Queste estensioni richiederanno termini di contratto aggiornati e tariffe aggiuntive.

+++

+++ **Quali considerazioni sulla privacy un titolare del trattamento dovrebbe fare quando si esportano dati personali da Adobe Analytics?**

Se un cliente usa i feed dei dati di Adobe Analytics per esportare i dati da Analytics nel data warehouse aziendale o in altri sistemi esterni ad Adobe, è responsabilità del cliente (titolare del trattamento) assicurarsi che le richieste di cancellazione vengano applicate ai dati. Questo vale anche per le implementazioni on-premise di Adobe Data Workbench, in cui un feed di dati Adobe Analytics continuo popola i dati della Data Workbench. Adobe può fornire gli strumenti di supporto nell’individuazione e nella cancellazione dei record di determinati tipi di feed di dati, inclusi quelli usati per Data Workbench, ma è ancora responsabilità del cliente (titolare del trattamento) assicurarsi che i dati vengano cancellati coerentemente con i propri criteri interni di conservazione e cancellazione dei dati.

Considera anche i casi in cui i dipendenti hanno scaricato rapporti Adobe Analytics contenenti dati personali. Questi rapporti possono dover essere aggiornati o eliminati se viene ricevuta una richiesta di cancellazione relativa alla Privacy dei dati che coinvolge un ID presente nel rapporto. I clienti devono collaborare con il consulente legale della propria azienda per determinare i periodi di conservazione e i requisiti di privacy e sicurezza che devono essere applicati a questi tipi di documenti.

+++

+++ **Alcuni dati che non dovevamo raccogliere sono stati accidentalmente inviati ad Adobe Analytics. È possibile utilizzare l’API Privacy dei dati per pulire questi dati?**

La [API di Data Privacy Service](https://developer.adobe.com/experience-platform-apis/references/privacy-service/) è stato fornito per aiutarti a soddisfare le richieste relative alla Privacy dei dati, soggette a scadenza. L’utilizzo di questa API per altri scopi non è supportato da Adobe e potrebbe influire sulla capacità di Adobe di fornire tempestivamente richieste di Privacy dei dati avviate dall’utente ad alta priorità per altri clienti Adobe.

Chiediamo all’utente di non utilizzare l’API Privacy dei dati per altri scopi, come la cancellazione dei dati che sono stati accidentalmente inviati in grandi gruppi di visitatori. È inoltre necessario tenere presente che ogni visitatore con un hit eliminato (aggiornato o anonimizzato) a seguito di una richiesta di cancellazione di Privacy dei dati avrà le informazioni sullo stato reimpostate. La prossima volta che il visitatore ritorna sul tuo sito web, sarà un nuovo visitatore. Tutte le attribuzioni eVar ricominceranno, così come informazioni quali numeri di visita, referrer, prima pagina visitata, ecc. Questo effetto collaterale non è opportuno nelle situazioni in cui si desidera cancellare i campi di dati ed evidenzia un motivo per cui l’API Privacy dei dati è inappropriata per questo utilizzo.

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
