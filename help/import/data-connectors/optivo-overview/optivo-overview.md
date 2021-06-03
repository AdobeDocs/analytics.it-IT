---
description: Questa integrazione combina la potenza del sistema di feedback integrato del software di marketing e-mail con la generazione di rapporti comportamentali di Adobe Analytics per creare potenti opportunità di analisi e ottimizzazione per la tua organizzazione.
title: Connettore dati optivo® broadmail per Adobe Analytics
uuid: bd713080-9d1a-49ee-aad0-86dd5c37c34a
exl-id: fff63047-afa6-420d-9188-ec8ebe407a46
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '1082'
ht-degree: 0%

---

# Connettore dati optivo® broadmail per Adobe Analytics{#optivo-broadmail-data-connector-for-adobe-analytics}

>[!IMPORTANT]
>
>La tecnologia Adobe Data Connector terminerà il 1° agosto 2021. [Ulteriori informazioni...](/help/import/data-connectors/data-connectors-eol.md)

Questa integrazione combina la potenza del sistema di feedback integrato del software di marketing e-mail con la generazione di rapporti comportamentali di Adobe Analytics per creare potenti opportunità di analisi e ottimizzazione per la tua organizzazione.

[!DNL ~~] I partner sono un software di marketing e-mail professionale. La sua funzione principale è quella di creare, inviare e valutare newsletter e campagne e-mail. `[~Partner~]` è disponibile come servizio cloud (software as a service).

L’ integrazione `[~Partner~]` offre remarketing automatizzato e sincronizzazione dati, con conseguente aumento delle conversioni e dei ricavi. L’integrazione consente agli addetti al marketing di sincronizzare automaticamente i segmenti per i loro clienti in base all’interazione e-mail e al comportamento del sito. Lo scambio automatizzato di dati di segmenti personalizzabili consente di creare campagne e-mail altamente mirate che incrementano le vendite, come l’abbandono del carrello e il remarketing post acquisto per prodotti cross-up e resell.

Questa integrazione scambia anche le metriche delle campagne e-mail di successo da `[~Partner~]` ad Adobe Analytics. I dati cruciali vengono visualizzati centralmente nella panoramica della campagna e-mail.

## Programma di laboratorio dei Data Connectors {#section-51f9864851b64d96873127b9ac9c9a2b}

Questo programma è un metodo di monitoraggio rapido per i partner di piattaforme terze di Adobe per creare integrazioni e consegnarle al nostro mercato comune. Le integrazioni sono completamente sviluppate dai nostri partner e rese disponibili su Adobe Experience Cloud secondo le metodologie della community. Sono disponibili gratuitamente per i clienti di Adobe di Adobe Analytics e di altre soluzioni e vengono fornite regolarmente senza garanzie implicite di Adobe, a causa della natura di terze parti delle integrazioni.

In caso di domande relative al servizio corrente, al buono o alla licenza, contatta il tuo Adobe Account Manager.

## Vantaggi e caratteristiche principali{#key-benefits-and-features}

Questa integrazione include i seguenti vantaggi principali:

* Recupera gli acquirenti che navigano e abbandonano
* Aumento delle vendite con il remarketing di cross-selling e up-selling mirato
* Campagne automatiche basate su segmenti
* Campagne ottimizzate in corso
* Segmenti in [!DNL ~Partner~] per il remarketing mirato
* Aggiornamenti costanti delle metriche delle campagne
* Attivazione di conversazioni automatizzate

## Segmenti di marketing dinamici{#dynamic-marketing-segments}

Questa integrazione presenta i seguenti segmenti di marketing dinamici:

* **Profili di acquisto:** aumenta gli ordini ripetuti e il valore medio dell’ordine attraverso le campagne mirate dai pattern di acquisto dei visitatori.
* **Profilo comportamentale visualizzazione prodotto/contenuto:** raggiungi i potenziali clienti attraverso segmenti di marketing basati sulle visualizzazioni dei prodotti e sulla profilazione dell’accesso ai contenuti.
* **Profilo di abbandono del carrello:** aiuta i visitatori a convertirsi ai clienti attraverso campagne ottimizzate appositamente progettate per coloro che esitano a completare i carrelli.
* **Remarketing efficace:** i clienti possono anche creare e pianificare segmenti di remarketing personalizzati specifici per le esigenze dei propri utenti.

## Prima di attivare{#before-you-activate}

Prima di avviare l’integrazione dei Data Connectors per , completa i seguenti requisiti:

## Requisiti di Adobe Analytics {#section-960e70fd2eae4a1cb88a2e4b53a97313}

* **Specifiche della suite di rapporti:** considera questa integrazione come specifica della suite di rapporti. Assicurati di aver selezionato la suite di rapporti desiderata prima di attivare l’integrazione.
* **Variabili Adobe Analytics disponibili e configurate:** questa integrazione richiede eventi personalizzati ed eVar personalizzate.

* **Rappresentante autorizzato:** ricorda che l’abilitazione di questa integrazione potrebbe comportare per la tua azienda costi in conformità con il contratto di servizio stipulato con Adobe, Inc. o con uno dei partner fidati di Adobe, a seconda dei casi. Attivando questa integrazione, l&#39;utente dichiara di essere un rappresentante autorizzato della sua azienda; e in quanto tale, la tua azienda accetta di pagare le eventuali tariffe stabilite nel contratto di servizio sopra descritto.
* **ID messaggio:** l’integrazione richiede l’acquisizione e la memorizzazione di un &quot;ID messaggio&quot; all’interno di una variabile Adobe Analytics (eVar). Questi ID sono necessari per identificare gli invii. Come parte del processo di configurazione, è necessario identificare un eVar a questo scopo quando richiesto dalla procedura guidata.
* **Partner:** l’integrazione richiede l’acquisizione e l’archiviazione di un  [!UICONTROL ~~] partner all’interno di una variabile Adobe Analytics (eVar). Questo ID è una rappresentazione codificata o numerica di un indirizzo e-mail dal sistema [!UICONTROL ~Partner~]. Questo [!UICONTROL ~Partner~] è associato al comportamento dei visitatori a valle sul sito (abbandoni del carrello, acquisti, ecc.) che viene inserito nel sistema [!UICONTROL ~Partner~] e può essere utilizzato a scopo di remarketing. Come parte del processo di configurazione, è necessario identificare un eVar a questo scopo quando richiesto dalla procedura guidata.
* **Ora clic post:** come parte del processo di configurazione, questa integrazione richiede un&#39;assegnazione a un eVar che corrisponde al tempo di un&#39;azione post clic. Questo è necessario per trasmettere informazioni su un&#39;azione del destinatario a [!UICONTROL ~Partner~] dopo che il destinatario ha fatto clic su un collegamento in un&#39;e-mail.

* **Post-clic Prodotto:** come parte del processo di configurazione, questa integrazione richiede un&#39;assegnazione a un eVar che corrisponde al prodotto offerto associato a un&#39;azione post-clic. Questo è necessario per trasmettere informazioni su un&#39;azione del destinatario a [!UICONTROL ~Partner~] dopo che il destinatario ha fatto clic su un collegamento in un&#39;e-mail.

* **Tipo di azione post-clic:** come parte del processo di configurazione, questa integrazione richiede un&#39;assegnazione a un eVar che corrisponde al tipo di azione post-clic. Questo è necessario per trasmettere informazioni su un&#39;azione del destinatario a [!UICONTROL ~Partner~] dopo che il destinatario ha fatto clic su un collegamento in un&#39;e-mail.

* **Conformità in materia di privacy:** devi capire che abilitando il tracciamento dell’ID destinatario o visitatore, questa funzione può tracciare informazioni personali dei visitatori del tuo sito. Questo ha implicazioni in materia di privacy che richiedono l’implementazione di procedure appropriate da parte dell’organizzazione, ad esempio l’invio di avvisi ai visitatori del sito e il loro consenso.

## Prezzi{#pricing}

L’abilitazione di questa integrazione potrebbe comportare costi per l’azienda in conformità al contratto di servizio con Adobe, Inc. o al contratto di servizio con uno dei partner fidati di Adobe, a seconda dei casi.

Attivando questa integrazione, l&#39;utente dichiara di essere un rappresentante autorizzato della sua azienda; e in quanto tale, la tua azienda accetta di pagare le eventuali tariffe stabilite nel contratto di servizio sopra descritto.

### Considerazioni sui prezzi di Adobe {#section-1f4f46c0d969435db57d38c1c310a05a}

Gli attuali clienti della soluzione Adobe Analytics non hanno costi aggiuntivi associati all&#39;utilizzo di questa integrazione dei Data Connectors. I clienti che non si sono ancora trasferiti al nuovo prodotto Adobe Analytics devono contattare il proprio rappresentante commerciale Adobe per ulteriori informazioni.

### Considerazioni sui prezzi dei partner {#section-f8ca71df32224412a5101efb6e356529}

Questa integrazione è disponibile per i clienti [!DNL ~Partner~] , ma sono previste tariffe di integrazione aggiuntive. Per informazioni sui prezzi, contattare sales@optivo.com. Per informazioni sui prezzi, contattare [!DNL ~Partner~].

## Variabili Adobe Analytics{#adobe-analytics-variables}

Questa integrazione richiede che le variabili Adobe Analytics tengano traccia delle metriche.

Dopo aver identificato gli eventi e le eVar da utilizzare con questa integrazione, devono essere attivati nell’Admin Console di Analytics (per istruzioni consulta [Suite di rapporti](https://experienceleague.adobe.com/docs/analytics/admin/manage-report-suites/report-suites-admin.html) ).
