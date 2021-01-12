---
description: Questa integrazione combina la potenza del software di e-mail marketing integrato sistema di feedback e la generazione di rapporti comportamentali  Adobe Analytics per creare potenti opportunità di analisi e ottimizzazione per la vostra organizzazione.
title: optivo® Broadmail Data Connector per  Adobe Analytics
uuid: bd713080-9d1a-49ee-aad0-86dd5c37c34a
translation-type: tm+mt
source-git-commit: 3850dc3503ca57ba4f13f0de63e8420e484db501
workflow-type: tm+mt
source-wordcount: '1084'
ht-degree: 1%

---


# connettore dati di trasmissione opzionale® per  Adobe Analytics{#optivo-broadmail-data-connector-for-adobe-analytics}

>[!IMPORTANT]
>
>La tecnologia del Connettore dati del Adobe  terminerà il 1 agosto 2021. [Ulteriori informazioni...](/help/import/data-connectors/data-connectors-eol.md)

Questa integrazione combina la potenza del software di e-mail marketing integrato sistema di feedback e la generazione di rapporti comportamentali  Adobe Analytics per creare potenti opportunità di analisi e ottimizzazione per la vostra organizzazione.

[!DNL ~~] Partner è un software professionale di marketing e-mail. La sua funzione principale consiste nel creare, inviare e valutare campagne per newsletter ed e-mail. `[~Partner~]` è disponibile come servizio cloud (software come servizio).

L&#39;integrazione `[~Partner~]` offre la ricommercializzazione automatizzata e la sincronizzazione dei dati, con conseguente aumento delle conversioni e dei ricavi. L&#39;integrazione consente agli esperti di marketing di sincronizzare automaticamente i segmenti per i clienti, in base all&#39;interazione e-mail e al comportamento del sito. Lo scambio automatizzato di dati di segmenti personalizzabili consente di creare campagne e-mail altamente mirate per incrementare le vendite, come l&#39;abbandono del carrello e il remarketing post-acquisto per prodotti cross-up-selling e reselling.

Questa integrazione consente inoltre di scambiare le metriche delle campagne e-mail di successo da `[~Partner~]` a  Adobe Analytics. I dati fondamentali vengono visualizzati centralmente nella panoramica della campagna e-mail.

## Data Connectors Laboratory Program {#section-51f9864851b64d96873127b9ac9c9a2b}

Questo programma è un metodo veloce per  Adobe  partner di piattaforme terze per realizzare integrazioni e distribuirle nel nostro mercato comune. Le integrazioni sono completamente sviluppate dai nostri partner e messe a disposizione su Adobe Experience Cloud secondo le metodologie della community. Sono disponibili gratuitamente per  clienti Adobi dell&#39;Adobe Analytics  e di altre soluzioni e sono forniti su base continuativa senza garanzie implicite da  Adobe a causa della natura di terze parti delle integrazioni.

In caso di domande sul servizio, il mandato o la licenza corrente, contattate l&#39;Account Manager  Adobe.

## Vantaggi e funzionalità principali{#key-benefits-and-features}

Questa integrazione include i seguenti vantaggi principali:

* Recuperare gli acquirenti che navigano e abbandonano
* Aumento delle vendite con il cross-selling e il remarketing up-selling mirati
* Campagne basate su segmenti automatiche
* Campagne ottimizzate in corso
* Segmenti in [!DNL ~Partner~] per remarketing mirato
* Aggiornamenti costanti delle metriche delle campagne
* Attivazione di conversazioni automatizzate

## Segmenti di marketing dinamici{#dynamic-marketing-segments}

Questa integrazione offre i seguenti segmenti di marketing dinamici:

* **Profili di acquisto:** aumentare gli ordini ripetuti e il valore medio degli ordini attraverso le campagne mirate dai pattern di acquisto dei visitatori.
* **Profilo comportamentale visualizzazione prodotti/contenuti:** raggiungere potenziali clienti attraverso segmenti di marketing basati sulle viste dei prodotti e sui profili di accesso ai contenuti.
* **Profilo di abbandono carrello:** Aiuta i visitatori a convertirsi ai clienti attraverso campagne di messa a punto appositamente progettate per coloro che esitano a completare i carrelli.
* **Note efficaci:** i clienti possono anche creare e pianificare segmenti di remarketing personalizzati in base alle esigenze dei propri utenti.

## Prima di attivare{#before-you-activate}

Prima di avviare l&#39;integrazione dei Connettori dati per , completa i seguenti requisiti:

##  requisiti Adobe Analytics {#section-960e70fd2eae4a1cb88a2e4b53a97313}

* **Suite di rapporti specifica:** questa integrazione è specifica per la suite di rapporti. Prima di attivare l&#39;integrazione, accertatevi di aver selezionato la suite di rapporti desiderata.
* **Disponibili e configurate  variabili Adobe Analytics:** questa integrazione richiede eventi personalizzati e eVar personalizzate.

* **Rappresentante autorizzato:** Ricorda che l&#39;abilitazione di questa integrazione potrebbe indurre la tua azienda a pagare le tariffe in conformità al tuo contratto di servizio con  Adobe, Inc. o al tuo contratto di servizio con uno  Adobe  partner fidati, a seconda dei casi. Attivando questa integrazione, l&#39;Utente dichiara di essere un rappresentante autorizzato della sua azienda; e, come tale, la vostra azienda accetta di pagare le eventuali tariffe indicate nel contratto di servizio sopra descritto.
* **ID messaggio:** L&#39;integrazione richiede l&#39;acquisizione e la memorizzazione di un &quot;ID messaggio&quot; all&#39;interno di una  variabile Adobe Analytics ( eVar). Tali ID sono necessari per identificare le invii che hai inviato. Durante il processo di configurazione, è necessario identificare un eVar  a tale scopo, quando richiesto dalla procedura guidata.
* **Partner:** l&#39;integrazione richiede che venga acquisito e memorizzato un  [!UICONTROL ~~] partner all&#39;interno di una variabile Adobe Analytics  ( eVar). Questo ID è una rappresentazione codificata o numerica di un indirizzo e-mail dal sistema [!UICONTROL ~Partner~]. Questo [!UICONTROL ~Partner~] è associato al comportamento dei visitatori a valle sul sito (carrelli abbandonati, acquisti, ecc.) che viene incluso nel sistema [!UICONTROL ~Partner~] e può essere sfruttato a scopo di remarketing. Durante il processo di configurazione, è necessario identificare un eVar  a tale scopo, quando richiesto dalla procedura guidata.
* **Ora clic post:** Come parte del processo di configurazione, questa integrazione richiede un&#39;assegnazione a un eVar  corrispondente al tempo di un&#39;azione post clic. Questo è necessario per trasmettere informazioni su un&#39;azione del destinatario a [!UICONTROL ~Partner~] dopo che il destinatario ha fatto clic su un collegamento in una mailing.

* **Post Click Product (Prodotto post-clic):** Come parte del processo di configurazione, questa integrazione richiede un&#39;assegnazione a un eVar  corrispondente al prodotto offerto associato a un&#39;azione post clic. Questo è necessario per trasmettere informazioni su un&#39;azione del destinatario a [!UICONTROL ~Partner~] dopo che il destinatario ha fatto clic su un collegamento in una mailing.

* **Tipo di azione post-clic:** Come parte del processo di configurazione, questa integrazione richiede un&#39;assegnazione a un eVar  che corrisponda al tipo di azione post-clic. Questo è necessario per trasmettere informazioni su un&#39;azione del destinatario a [!UICONTROL ~Partner~] dopo che il destinatario ha fatto clic su un collegamento in una mailing.

* **Conformità alla privacy:** devi comprendere che abilitando il tracciamento dell&#39;ID del destinatario o del visitatore, questa funzione può tenere traccia delle informazioni personali dei visitatori del tuo sito. Questo ha implicazioni sulla privacy che richiedono l&#39;implementazione di procedure appropriate da parte dell&#39;organizzazione, ad esempio l&#39;informativa e il consenso dei visitatori del sito.

## Prezzi{#pricing}

L&#39;abilitazione di questa integrazione potrebbe indurre l&#39;azienda a pagare le tariffe in conformità al contratto di servizio con  Adobe, Inc. o al contratto di assistenza con uno dei  partner  fidati, a seconda dei casi.

Attivando questa integrazione, l&#39;Utente dichiara di essere un rappresentante autorizzato della sua azienda; e, come tale, la vostra azienda accetta di pagare le eventuali tariffe indicate nel contratto di servizio sopra descritto.

### Considerazioni sui prezzi  Adobe {#section-1f4f46c0d969435db57d38c1c310a05a}

Gli attuali clienti della soluzione Adobe Analytics  non hanno costi aggiuntivi associati all&#39;utilizzo di questa integrazione dei connettori dati. I clienti che non si sono ancora trasferiti al nuovo prodotto Adobe Analytics  devono contattare il proprio rappresentante commerciale  Adobe per ulteriori informazioni.

### Considerazioni sui prezzi dei partner {#section-f8ca71df32224412a5101efb6e356529}

Questa integrazione è disponibile per i clienti [!DNL ~Partner~], ma si applicheranno delle tariffe di integrazione aggiuntive. Per informazioni sui prezzi, contattate sales@optivo.com. Per informazioni sui prezzi, contattare [!DNL ~Partner~].

##  variabili Adobe Analytics{#adobe-analytics-variables}

Questa integrazione richiede  variabili Adobe Analytics per tenere traccia delle metriche.

Dopo aver identificato gli eventi e le eVar da utilizzare con questa integrazione, devono essere abilitate nel Admin Console di  di Analytics (consultate [Suite di rapporti](https://docs.adobe.com/content/help/it-IT/analytics/admin/manage-report-suites/report-suites-admin.html) per le istruzioni).
