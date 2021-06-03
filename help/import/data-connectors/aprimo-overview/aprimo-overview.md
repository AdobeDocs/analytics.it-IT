---
description: Questa integrazione e-mail Adobe® Data Connectors™ combina le informazioni comportamentali provenienti da Adobe Analytics® con il marketing via e-mail per creare uno strumento potente per ridefinire la misurazione del successo e indirizzare i tipi di pubblico con messaggi più pertinenti.
title: Connettore dati Aprimo per Adobe Analytics
uuid: 590ded4b-b250-43b4-9cec-68508b853e00
exl-id: cd5191c9-68fb-42ad-98f6-23d5a72878da
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '824'
ht-degree: 1%

---

# Connettore dati Aprimo per Adobe Analytics{#aprimo-data-connector-for-adobe-analytics}

>[!IMPORTANT]
>
>La tecnologia Adobe Data Connector terminerà il 1° agosto 2021. [Ulteriori informazioni...](/help/import/data-connectors/data-connectors-eol.md)

Questa integrazione e-mail Adobe® Data Connectors™ combina le informazioni comportamentali provenienti da Adobe Analytics® con il marketing via e-mail per creare uno strumento potente per ridefinire la misurazione del successo e indirizzare i tipi di pubblico con messaggi più pertinenti.

L’invio di messaggi e-mail pertinenti a questi segmenti di mercato può comportare opportunità di ricavo completamente nuove, incrementando le conversioni e i ricavi tra campagne e-mail nuove ed esistenti. Ad esempio, la distribuzione di messaggi e-mail pertinenti basati sui prodotti visualizzati durante una visita o sui prodotti rimasti in un carrello abbandonato ha avuto un impatto notevole sui ricavi, con un impatto minimo sui costi, in quanto si tratta semplicemente di sfruttare i visitatori che il sito sta già ricevendo.

Questo aumento dell&#39;efficienza di marketing è uno dei vantaggi principali dell&#39;integrazione di [!DNL Adobe Analytics] con Aprimo. Inoltre, questa integrazione sincronizzerà automaticamente le metriche e-mail con i dati [!DNL Adobe Analytics] con la stessa frequenza oraria per i rapporti a ciclo chiuso.

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

### Requisiti di Adobe Analytics {#section-960e70fd2eae4a1cb88a2e4b53a97313}

* **Specifiche della suite di rapporti:** considera questa integrazione come specifica della suite di rapporti. Assicurati di aver selezionato la suite di rapporti desiderata prima di attivare l’integrazione.
* **Variabili Adobe Analytics disponibili e configurate:** questa integrazione richiede eventi personalizzati ed eVar personalizzate ed eventualmente eventi aggiuntivi ed eVar aggiuntive.
* **Rappresentante autorizzato:** ricorda che l’abilitazione di questa integrazione potrebbe comportare per la tua azienda costi in conformità con il contratto di servizio stipulato con Adobe, Inc. o con uno dei partner fidati di Adobe, a seconda dei casi. Attivando questa integrazione, l&#39;utente dichiara di essere un rappresentante autorizzato della sua azienda; e in quanto tale, la tua azienda accetta di pagare le eventuali tariffe stabilite nel contratto di servizio sopra descritto.
* **Data Warehouse™:** questa integrazione richiede l’abilitazione di Data Warehouse per generare segmenti di remarketing. Se non hai abilitato la Data Warehouse, contatta l’Adobe per ulteriori informazioni.
* **[!UICONTROL Partner~]:** L’integrazione richiede l’acquisizione e l’archiviazione di un &quot;  [!DNL ~partner~]&quot; all’interno di una variabile Adobe Analytics (eVar). Questo ID è una rappresentazione codificata o numerica di un indirizzo e-mail dal sistema [!DNL ~Partner~]. Questo &quot; [!DNL ~Partner~]&quot; è associato al comportamento dei visitatori a valle sul sito (carrelli abbandonati, acquisti, ecc.) che viene inserito nel sistema [!DNL ~Partner~] e può essere utilizzato a scopo di remarketing. Come parte del processo di configurazione, è necessario identificare un eVar a questo scopo quando richiesto dalla procedura guidata.
* **Tracciamento esterno:** se al momento non segui la best practice per abilitare il tracciamento esterno per ogni campagna e-mail inviata, devi farlo per garantire il successo dell’integrazione. Per ulteriori informazioni, consulta la sezione [!DNL ~Partner~] riportata di seguito.
* **Conformità in materia di privacy:** devi capire che abilitando il tracciamento dell’ID destinatario o visitatore, questa funzione può tracciare informazioni personali dei visitatori del tuo sito. Questo ha implicazioni in materia di privacy che richiedono l’implementazione di procedure appropriate da parte dell’organizzazione, ad esempio l’invio di avvisi ai visitatori del sito e il loro consenso.

## Prezzi{#pricing}

L’abilitazione di questa integrazione potrebbe comportare costi per l’azienda in conformità al contratto di servizio con Adobe, Inc. o al contratto di servizio con uno dei partner fidati di Adobe, a seconda dei casi.

Attivando questa integrazione, l&#39;utente dichiara di essere un rappresentante autorizzato della sua azienda; e in quanto tale, la tua azienda accetta di pagare le eventuali tariffe stabilite nel contratto di servizio sopra descritto.

### Considerazioni sui prezzi di Adobe {#section-1f4f46c0d969435db57d38c1c310a05a}

Potrebbero esserci costi ricorrenti e di implementazione associati a questa integrazione, incluso il costo per un numero maggiore di chiamate server sostenute tramite questa integrazione. Contatta il tuo rappresentante commerciale Adobe per i dettagli dei prezzi.

### ~~ Considerazioni sui prezzi dei partner  {#section-f8ca71df32224412a5101efb6e356529}

Questa integrazione potrebbe comportare costi ricorrenti per l’implementazione. Per informazioni sui prezzi, contattare [!DNL ~Partner~].

## Variabili Adobe Analytics{#adobe-analytics-variables}

Questa integrazione richiede che le variabili Adobe Analytics tengano traccia delle metriche.

Dopo aver identificato gli eventi e le eVar da utilizzare con questa integrazione, devono essere abilitate nell’Admin Console Adobe Analytics (per istruzioni, consulta [Suite di rapporti](https://experienceleague.adobe.com/docs/analytics/admin/manage-report-suites/report-suites-admin.html) ).
