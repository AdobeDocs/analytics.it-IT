---
description: Questa integrazione di e-mail  Adobe® Data Connectors™ combina le informazioni comportamentali di  Adobe Analytics® con il marketing e-mail per creare uno strumento potente per ridefinire la misurazione del successo e indirizzare i tipi di pubblico con messaggi più pertinenti.
title: Connettore dati Neolane Ozon per Adobe Analytics
uuid: a0415fc2-9bf3-445d-92a3-705895ff740c
translation-type: tm+mt
source-git-commit: 3850dc3503ca57ba4f13f0de63e8420e484db501
workflow-type: tm+mt
source-wordcount: '776'
ht-degree: 2%

---


# Connettore dati Neolane Ozon per Adobe Analytics{#neolane-ozon-data-connector-for-adobe-analytics}

>[!IMPORTANT]
>
>La tecnologia del Connettore dati del Adobe  terminerà il 1 agosto 2021. [Ulteriori informazioni...](/help/import/data-connectors/data-connectors-eol.md)

Questa integrazione di e-mail  Adobe® Data Connectors™ combina le informazioni comportamentali di  Adobe Analytics® con il marketing e-mail per creare uno strumento potente per ridefinire la misurazione del successo e indirizzare i tipi di pubblico con messaggi più pertinenti.

L&#39;invio di messaggi e-mail pertinenti a questi segmenti di mercato può dare luogo a opportunità di profitto completamente nuove, aumentando la conversione e i ricavi tra campagne e-mail nuove ed esistenti. Ad esempio, la distribuzione di messaggi e-mail pertinenti basati su prodotti visualizzati durante una visita o prodotti lasciati in un carrello abbandonato ha avuto un impatto drammatico sulle entrate, con un impatto minimo sui costi, in quanto si tratta semplicemente di sfruttare i visitatori che il sito sta già ricevendo.

Questo aumento dell&#39;efficienza del marketing è uno dei vantaggi chiave dell&#39;integrazione di [!DNL Adobe Analytics] con [!DNL ~Partner~]. Inoltre, questa integrazione sincronizzerà automaticamente le metriche delle e-mail con i dati [!DNL Adobe Analytics] con la frequenza oraria per il reporting a circuito chiuso.

## Vantaggi e funzionalità principali{#key-benefits-and-features}

Questa integrazione include i seguenti vantaggi principali:

* Consolidare i dati di marketing e analisi e-mail in un&#39;unica interfaccia di reporting.
* Ottimizzate le campagne e-mail mediante la conversione e il contributo alle entrate e al successo del sito.
* Rivendita i visitatori principali e i segmenti di mercato basati su segmenti di marketing dinamici.

## Segmenti di marketing dinamici{#dynamic-marketing-segments}

Questa integrazione offre i seguenti segmenti di marketing dinamici:

* **Profili di acquisto:** aumentare gli ordini ripetuti e il valore medio degli ordini attraverso le campagne mirate dai pattern di acquisto dei visitatori.
* **Profilo comportamentale visualizzazione prodotti/contenuti:** raggiungere potenziali clienti attraverso segmenti di marketing basati sulle viste dei prodotti e sui profili di accesso ai contenuti.
* **Profilo di abbandono carrello:** Aiuta i visitatori a convertirsi ai clienti attraverso campagne di messa a punto appositamente progettate per coloro che esitano a completare i carrelli.
* I clienti possono anche creare e pianificare segmenti di remarketing personalizzati in base alle esigenze dei propri utenti.

## Prima di attivare{#before-you-activate}

Prima di avviare l&#39;integrazione dei Connettori dati per , completa i seguenti requisiti:

###  requisiti Adobe Analytics {#section-960e70fd2eae4a1cb88a2e4b53a97313}

* **Suite di rapporti specifica:** questa integrazione è specifica per la suite di rapporti. Prima di attivare l&#39;integrazione, accertatevi di aver selezionato la suite di rapporti desiderata.
* **Disponibili e configurate  variabili Adobe Analytics:** Questa integrazione richiede eventi personalizzati e eVar personalizzati, ed eventualmente eventi aggiuntivi e eVar aggiuntive.
* **Rappresentante autorizzato:** Ricorda che l&#39;abilitazione di questa integrazione potrebbe indurre la tua azienda a pagare le tariffe in conformità al tuo contratto di servizio con  Adobe, Inc. o al tuo contratto di servizio con uno  Adobe  partner fidati, a seconda dei casi. Attivando questa integrazione, l&#39;Utente dichiara di essere un rappresentante autorizzato della sua azienda; e, come tale, la vostra azienda accetta di pagare le eventuali tariffe indicate nel contratto di servizio sopra descritto.
* **Data Warehouse™:** questa integrazione richiede l&#39;attivazione della Data Warehouse per generare segmenti di remarketing. Se non avete attivato l&#39;Data Warehouse, contattate  Adobe per ulteriori informazioni.
* **`[~Partner~]`:** L&#39;integrazione richiede l&#39;acquisizione e la memorizzazione di un &quot;`[~Partner~]`&quot; all&#39;interno di una variabile Adobe Analytics  ( eVar). Questo ID è una rappresentazione codificata o numerica di un indirizzo e-mail dal sistema `[~Partner~]`. Questo &quot; [!DNL ~Partner~]&quot; è associato al comportamento dei visitatori a valle sul sito (carrelli abbandonati, acquisti, ecc.) che viene trasferito nel sistema `[~Partner~]` e può essere sfruttato a scopo di remarketing. Durante il processo di configurazione, è necessario identificare un eVar  a tale scopo, quando richiesto dalla procedura guidata.
* **Tracciamento esterno:** se al momento non segui la procedura ottimale per abilitare il tracciamento esterno per ogni campagna e-mail inviata, devi farlo per garantire il successo dell&#39;integrazione. Per ulteriori informazioni, vedere la sezione `[~Partner~]` di seguito.
* **Conformità alla privacy:** devi comprendere che abilitando il tracciamento dell&#39;ID del destinatario o del visitatore, questa funzione può tenere traccia delle informazioni personali dei visitatori del tuo sito. Questo ha implicazioni sulla privacy che richiedono l&#39;implementazione di procedure appropriate da parte dell&#39;organizzazione, ad esempio l&#39;informativa e il consenso dei visitatori del sito.

## Prezzi{#pricing}

L&#39;abilitazione di questa integrazione potrebbe indurre l&#39;azienda a pagare le tariffe in conformità al contratto di servizio con  Adobe, Inc. o al contratto di assistenza con uno dei  partner  fidati, a seconda dei casi.

Attivando questa integrazione, l&#39;Utente dichiara di essere un rappresentante autorizzato della sua azienda; e, come tale, la vostra azienda accetta di pagare le eventuali tariffe indicate nel contratto di servizio sopra descritto.

### Considerazioni sui prezzi  Adobe {#section-1f4f46c0d969435db57d38c1c310a05a}

Potrebbero verificarsi costi ricorrenti e costi di implementazione associati a questa integrazione, inclusi i costi per un numero maggiore di chiamate server sostenute tramite questa integrazione. Per informazioni sui prezzi, contattate il rappresentante commerciale  Adobe.

### ~Considerazioni ~ sui prezzi dei partner  {#section-f8ca71df32224412a5101efb6e356529}

Questa integrazione potrebbe comportare costi ricorrenti per l&#39;implementazione. Per informazioni sui prezzi, contattare `[~Partner~]`.
