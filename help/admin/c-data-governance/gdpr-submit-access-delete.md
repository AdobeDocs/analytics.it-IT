---
description: 'null'
title: Inviare richieste di accesso e cancellazione
uuid: d006cd5c-e3cd-4385-8683-acaf73cb681b
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '1302'
ht-degree: 100%

---


# Inviare richieste di accesso e cancellazione


## Panoramica {#section_BD70882995894C1CA19C205C49FEC23C}

Se i tuoi clienti (consumatori/persone interessate) desiderano sapere quali dei loro dati sono in tuo possesso o decidono di voler essere cancellati dalle proprietà di Analytics, in qualità di titolare del trattamento dei dati, rispondere a queste richieste rientra nelle tue responsabilità. Il titolare del trattamento dei dati determina in che modo l’azienda interagirà con le persone interessate (ad esempio attraverso un portale per gli utenti dedicato alle persone interessate) e gestisce le interazioni con gli interessati. Inoltre rientra tra le responsabilità del titolare chiudere il ciclo con la persona interessata quando la richiesta viene soddisfatta. In altre parole, Adobe Experience Cloud, in qualità di responsabile del trattamento dei dati, non riceverà direttamente le richieste dalle persone interessate né restituirà loro i dati. Piuttosto, Adobe potrà solo interagire con te, come titolare del trattamento dei dati, per la ricezione delle richieste e la restituzione dei dati.

È consigliabile accertarsi che le app per dispositivi mobili e i siti web siano dotati di avvisi pop-up e materiale di supporto pertinenti sui diritti della persona interessata per quanto riguarda i dati personali direttamente o indirettamente identificabili e altri dati raccolti.

## Gestire il consenso dei clienti {#section_3012015E7E8942519FB9279CF7057EAB}

In qualità di titolare del trattamento, è tua responsabilità ottenere il consenso esplicito delle persone interessate prima di raccogliere i dati personali (che potrebbero includere i dati di Adobe Analytics) e [implementare un meccanismo di rinuncia](https://docs.adobe.com/content/help/it-IT/dtm/using/tools/opt-in.html) sul sito Web. Questo consentirà alle persone interessate di negare future raccolte di dati di Adobe Experience Cloud.

## Convalidare gli utenti e i relativi dati {#section_AFB2CC225AA94AF6A3CE9F24EF788358}

In qualità di titolare del trattamento dei dati, rientra nelle tue responsabilità verificare l’identità della persona interessata e il suo diritto a ricevere i dati che richiede. Inoltre rientra tra le tue responsabilità accertarsi che alla persona interessata siano restituiti i dati corretti e che non riceva inavvertitamente i dati di un’altra persona interessata.

Questo prevede il controllo dei dati restituiti da Adobe Analytics, come parte della richiesta di accesso alla Privacy dei dati, prima di inviarli alla persona interessata. Particolare attenzione è richiesta nel caso di uso di ID personali e nel caso in cui vengano restituiti non solo i dati in cui è presente l’ID, ma anche i dati per altri risultati su un dispositivo condiviso in cui l’ID era talvolta presente. Consulta [Espansione dell’ID.](/help/admin/c-data-governance/gdpr-id-expansion.md)

Ogni file combina i dati di tutte le suite di rapporti, rimuovendo automaticamente le copie in più dei risultati replicati. Puoi decidere quali di questi file restituire alla persona interessata, oppure puoi estrarre alcuni di questi dati e combinarli con i dati di altri sistemi prima di restituirli alla persona interessata.

## Inviare le richieste {#submit-requests}

Puoi inviare l’accesso alla Privacy dei dati e cancellare le richieste tramite il nostro [portale Interfaccia utente Privacy dei dati](https://docs.adobe.com/content/help/it-IT/experience-platform/privacy/home.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md) o tramite la nostra [API Privacy dei dati.](https://www.adobe.io/apis/experienceplatform/gdpr.html)

>[!NOTE]
>
>L’API Privacy dei dati supporta gli invii in batch per più utenti in una sola richiesta. Il limite attualmente supportato è 1.000 utenti (è possibile avere più ID per ciascun utente) in un unico file JSON della richiesta.

## Richiesta JSON di esempio {#sample-json-request}

Segue un esempio di codice JSON che potrebbe essere inviato tramite l’API o l’interfaccia utente Privacy dei dati per richiedere l’elaborazione Privacy dei dati per tre utenti.

```
{ 
    "companyContexts": [ 
        { 
            "namespace": "imsOrgID", 
            "value": "5D7236525AA6D9580A495C6C@AdobeOrg" 
        } 
    ], 
    "users": [ 
        { 
            "key": "Data Privacy-1234", 
            "action": ["access"], 
            "userIDs": [ 
                { 
                    "namespace": "AAID", 
                    "namespaceId", 10, 
                    "type": "standard", 
                    "description": "Legacy Visitor ID", 
                    "value": "2D783E5885312539-4000010360000181", 
                } 
            ] 
        }, 
        { 
            "key": "Data Privacy-1235", 
            "action": ["access"], 
            "userIDs": [ 
                { 
                    "namespace": "ECID", 
                    "namespaceId": 4, 
                    "type": "standard", 
                    "description": "This is the ID generated by the Adobe ID service.", 
                    "value": "22470866493385587460528148368265592748", 
                } 
            ] 
        }, 
        { 
            "key": "Data Privacy-1236", 
            "action": ["access","delete"], 
            "userIDs": [ 
                { 
                    "namespace": "CRM-ID", 
                    "type": "analytics", 
                    "description": "namespace defined on eVar17 in some report suites", 
                    "value": "ACME-12345678"
                }, 
                { 
                    "namespace": "email address", 
                    "type": "analytics", 
                    "description": "namespace defined on eVar23 in some report suites", 
                    "value": "john@mail.com" 
                } 
            ] 
        } 
    ], 
    "expandIds": true 
} 
```

Nota che ci sono tre blocchi nella sezione dell’utente, che rappresentano tre richieste diverse, presumibilmente per tre diverse persone interessate.

* La prima richiesta è una richiesta di accesso che usa un tradizionale cookie di ID Adobe Analytics (AAID).
* La seconda è una richiesta di accesso che però usa un cookie MCID/ECID.
* La terza richiede sia l’accesso che la cancellazione per ID specifici. Sebbene l’espansione dell’ID sia specificata per tutte le richieste, essa si applica maggiormente alla terza richiesta perché è l’unica che non usa ID cookie. Di conseguenza questa richiesta individuerà anche gli ID cookie associati a dispositivi con questo CRM-ID o indirizzo e-mail ed espanderà la richiesta per includere anche questi ID.

Nota bene

* Il valore “5D7236525AA6D9580A495C6C@AdobeOrg” nella sezione “companyContexts” deve essere aggiornato con il valore dell’organizzazione Experience Cloud.
* I campi “type” e “namespace” sono descritti più dettagliatamente nella sezione [Namespaces](/help/admin/c-data-governance/gdpr-namespaces.md).
* I campi “description” vengono ignorati.
* I campi “key” possono contenere qualsiasi valore desiderato. Se disponi di un ID interno che usi per monitorare le richieste di Privacy dei dati, puoi inserirne il valore qui, per facilitare la corrispondenza tra le richieste nel sistema di Adobe e quelle nei tuoi sistemi.

## Dettagli sulle risposte {#section_93F554F65DBB48A18B75EB5784056C96}

Questa sezione contiene i dettagli sulle risposte in merito a richieste di accesso ed eliminazione.

**Dettagli sulle risposte a richieste di accesso**

I dati restituiti per una richiesta di accesso ti forniscono, come titolare del trattamento, l’URL da usare per scaricare un file ZIP contenente una directory per ogni prodotto Adobe che possiedi. Nella cartella di Analytics possono essere presenti:

* File di persona: derivanti da risultati che contengono un’etichetta ID-PERSON corrispondente

   * File CSV con una riga per ogni risultato corrispondente e una colonna per ogni campo con un’etichetta ACC-ALL o ACC-PERSON, ordinate per marca temporale.
   * File di riepilogo HTML con una voce per ogni etichetta ACC-ALL o ACC-PERSON. Ogni voce elenca tutti i valori univoci per quel campo e il numero di occorrenze. I campi contenenti la marca temporale vengono arrotondati per specificare solo giorni univoci.

* File di dispositivo: derivanti da risultati in cui uno dei campi corrisponde a un ID-DEVICE specifico ma nessuno di questi corrisponde a un ID-PERSON specifico

   * File CSV con una riga per ogni risultato corrispondente e una colonna per ogni campo con un’etichetta ACC-ALL, ordinate per marca temporale.
   * File di riepilogo HTML con una voce per ogni etichetta ACC-ALL. Ogni voce elencherà tutti i valori univoci per quel campo e il numero di occorrenze. I campi contenenti la marca temporale vengono arrotondati per specificare solo giorni univoci.

Ogni file combina i dati di tutte le suite di rapporti, rimuovendo automaticamente le copie in più dei risultati replicati.

Puoi decidere quali di questi restituire alla persona interessata, oppure puoi estrarre alcuni di questi dati e combinarli con i dati di altri sistemi prima di restituirli alla persona interessata.

**Dettagli sulle risposte alle richieste di cancellazione**

Per le richieste di cancellazione non viene restituito alcun dato, solo uno stato per l’API Privacy dei dati che attesta che la richiesta è stata completata correttamente.

## Verifica dell’elaborazione della Privacy dei dati sui tuoi dati {#section_FBA843DBFAE64D979D8DB8A3C56784D7}

In genere, i clienti di Analytics configurano alcune suite di rapporti di prova per verificare la funzionalità prima che venga rilasciata al pubblico. I siti web o le applicazioni in preproduzione invieranno dati in queste suite di rapporti test/dev/QA per valutare come funzionano quando viene rilasciato il codice prima che il traffico vero e proprio venga inviato alle suite di rapporti di produzione.

Tuttavia, con una normale configurazione, l’elaborazione delle richieste RGDP non può essere verificata inizialmente su queste suite di rapporti di prova, prima di applicare le richieste alle suite di rapporti di produzione. Il motivo è che una richiesta di Privacy dei dati viene applicata automaticamente a tutte le suite di rapporti nell’organizzazione Experience Cloud, che spesso sono tutte le suite di rapporti per l’azienda.

Sono disponibili alcuni modi per verificare l’elaborazione Privacy dei dati prima di applicarla a tutte le suite di rapporti:

* Un’opzione consiste nell’impostare un’organizzazione Experience Cloud diversa che contiene solo suite di rapporti di prova. Quindi si utilizza questa organizzazione Experience Cloud per il test Privacy dei dati e la normale organizzazione Experience Cloud per l’elaborazione effettiva Privacy dei dati.
* Un’altra opzione consiste nell’assegnare namespace diversi agli ID nelle suite di rapporti di prova rispetto a quelle presenti nelle suite di rapporti di produzione.

   Ad esempio, puoi usare il prefisso “qa-” per ogni namespace nelle suite di rapporti di prova. Quando si inviano richieste di Privacy dei dati con solo namespace con il prefisso qa, queste richieste verranno eseguite solo sulle suite di rapporti di prova. Successivamente, quando si inviano le richieste senza il prefisso qa, vengono applicate alle suite di rapporti di produzione. **Questo è l’approccio consigliato, a meno che non si utilizzino i namespace visitorId, AAID, ECID o customVisitorId, perché questi hanno una codifica fissa e non possono essere specificati nelle suite di rapporti di prova**.
