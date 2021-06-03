---
description: Questa integrazione e-mail Adobe® Data Connectors™ combina le informazioni comportamentali di Analytics® con quelle di e-mail marketing per creare uno strumento potente per ridefinire la misurazione del successo e indirizzare i tipi di pubblico con messaggi più pertinenti.
title: Connettore dati DreamMail per Adobe Analytics
uuid: f6c01bf8-4e6a-4163-9d41-f24fb5f06bdc
exl-id: a37bf616-0f2a-4009-825f-92c30e79336f
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '803'
ht-degree: 2%

---

# Connettore dati DreamMail per Adobe Analytics{#dreammail-data-connector-for-adobe-analytics}

>[!IMPORTANT]
>
>La tecnologia Adobe Data Connector terminerà il 1° agosto 2021. [Ulteriori informazioni...](/help/import/data-connectors/data-connectors-eol.md)

Questa integrazione e-mail Adobe® Data Connectors™ combina le informazioni comportamentali di Analytics® con quelle di e-mail marketing per creare uno strumento potente per ridefinire la misurazione del successo e indirizzare i tipi di pubblico con messaggi più pertinenti.

L’invio di messaggi e-mail pertinenti a questi segmenti di mercato può comportare opportunità di ricavo completamente nuove, incrementando le conversioni e i ricavi tra campagne e-mail nuove ed esistenti. Ad esempio, la distribuzione di messaggi e-mail pertinenti basati sui prodotti visualizzati durante una visita o sui prodotti rimasti in un carrello abbandonato ha avuto un impatto notevole sui ricavi, con un impatto minimo sui costi, in quanto si tratta semplicemente di sfruttare i visitatori che il sito sta già ricevendo.

Questo aumento dell&#39;efficienza di marketing è uno dei vantaggi principali dell&#39;integrazione di [!DNL Analytics] con [!DNL ~Partner~]. Inoltre, questa integrazione sincronizzerà automaticamente le metriche e-mail con i dati [!DNL Analytics] con la stessa frequenza oraria per i rapporti a ciclo chiuso.

## Vantaggi e caratteristiche principali{#key-benefits-and-features}

Questa integrazione include i seguenti vantaggi principali:

* Consolidare i dati di marketing e analisi e-mail in un’unica interfaccia di reporting.
* Ottimizza le campagne e-mail in base alla conversione e al contributo ai ricavi e al successo del sito.
* Effettua il remarketing per visitatori chiave e segmenti di mercato basati su segmenti di marketing dinamici.

## Segmenti di marketing dinamici{#dynamic-marketing-segments}

Questa integrazione presenta i seguenti segmenti di marketing dinamici:

* **Profili di acquisto:** aumenta gli ordini ripetuti e il valore medio dell’ordine attraverso le campagne mirate dai pattern di acquisto dei visitatori.
* **Profilo comportamentale visualizzazione prodotto/contenuto:** raggiungi i potenziali clienti attraverso segmenti di marketing basati sulle visualizzazioni dei prodotti e sulla profilazione dell’accesso ai contenuti.
* **Profilo di abbandono del carrello:** aiuta i visitatori a convertirsi ai clienti attraverso campagne ottimizzate appositamente progettate per coloro che esitano a completare i carrelli.
* I clienti possono inoltre creare e pianificare segmenti di remarketing personalizzati specifici in base alle esigenze dei loro utenti.

## Prima di attivare{#before-you-activate}

Prima di avviare l’integrazione dei Data Connectors per , completa i seguenti requisiti:

## Requisiti di Adobe Analytics {#section-960e70fd2eae4a1cb88a2e4b53a97313}

* **Specifiche della suite di rapporti:** considera questa integrazione come specifica della suite di rapporti. Assicurati di aver selezionato la suite di rapporti desiderata prima di attivare l’integrazione.
* **Variabili disponibili e configurate di Analytics:** questa integrazione richiede eventi personalizzati ed eVar personalizzate ed eventualmente eventi aggiuntivi ed eVar aggiuntive.

* **Rappresentante autorizzato:** ricorda che l’abilitazione di questa integrazione potrebbe comportare per la tua azienda costi in conformità con il contratto di servizio stipulato con Adobe, Inc. o con uno dei partner fidati di Adobe, a seconda dei casi. Attivando questa integrazione, l&#39;utente dichiara di essere un rappresentante autorizzato della sua azienda; e in quanto tale, la tua azienda accetta di pagare le eventuali tariffe stabilite nel contratto di servizio sopra descritto.
* **Data Warehouse™:** questa integrazione richiede l’abilitazione di Data Warehouse per generare segmenti di remarketing. Se non hai abilitato la Data Warehouse, contatta l’Adobe per ulteriori informazioni.
* **[!DNL ~Partner~]:** l’integrazione richiede l’acquisizione e l’archiviazione di un indirizzo e-mail all’interno di una variabile Analytics (eVar). Il &quot; [!DNL ~Partner~]&quot; è associato al comportamento dei visitatori a valle sul sito (carrelli abbandonati, acquisti, ecc.) che viene inserito nel sistema [!DNL ~Partner~] e può essere utilizzato a scopo di remarketing. Come parte del processo di configurazione, è necessario identificare un eVar a questo scopo quando richiesto dalla procedura guidata.
* **Tracciamento esterno:** se al momento non segui la best practice per abilitare il tracciamento esterno per ogni campagna e-mail inviata, devi farlo per garantire il successo dell’integrazione. Per ulteriori informazioni, consulta la sezione [!DNL ~Partner~] di seguito.
* **Conformità in materia di privacy:** devi capire che abilitando il tracciamento dell’ID destinatario o visitatore, questa funzione può tracciare informazioni personali dei visitatori del tuo sito. Questo ha implicazioni in materia di privacy che richiedono l’implementazione di procedure appropriate da parte dell’organizzazione, ad esempio l’invio di avvisi ai visitatori del sito e il loro consenso.

## Prezzi{#pricing}

L’abilitazione di questa integrazione potrebbe comportare costi per l’azienda in conformità al contratto di servizio con Adobe, Inc. o al contratto di servizio con uno dei partner fidati di Adobe, a seconda dei casi.

Attivando questa integrazione, l&#39;utente dichiara di essere un rappresentante autorizzato della sua azienda; e in quanto tale, la tua azienda accetta di pagare le eventuali tariffe stabilite nel contratto di servizio sopra descritto.

### Considerazioni sui prezzi di Adobe {#section-1f4f46c0d969435db57d38c1c310a05a}

Potrebbero esserci costi ricorrenti e di implementazione associati a questa integrazione, incluso il costo per un numero maggiore di chiamate server sostenute tramite questa integrazione. Contatta il tuo rappresentante commerciale Adobe per i dettagli dei prezzi.

### ~~ Considerazioni sui prezzi dei partner  {#section-f8ca71df32224412a5101efb6e356529}

Questa integrazione potrebbe comportare costi ricorrenti per l’implementazione. Contatta [!DNL DreamMail] per informazioni sui prezzi.

## Variabili dell&#39;integrazione di Analytics{#analytics-integration-variables}

Questa integrazione richiede che le variabili Analytics tengano traccia delle metriche.

Dopo aver identificato gli eventi e le eVar da utilizzare con questa integrazione, devono essere attivati nell’Admin Console di Analytics (per istruzioni consulta [Suite di rapporti](https://experienceleague.adobe.com/docs/analytics/admin/manage-report-suites/report-suites-admin.html) ).
