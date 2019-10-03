---
description: Importa dati di monitoraggio da applicazioni di terze parti in Analytics.
seo-description: Accedere ai connettori dati; importare dati di tracciamento da applicazioni di terze parti in Analytics, aggiungere integrazioni e connettori dati.
seo-title: Connettori dati di Analytics
title: Guida introduttiva ai connettori dati di Analytics
translation-type: tm+mt
source-git-commit: f326b29bb73fd6e8630957c43dfd89f47b711986

---


# Panoramica dei connettori dati

Adobe fornisce alle organizzazioni informazioni fruibili e in tempo reale sulle strategie e le iniziative di marketing digitali. I connettori dati consentono di importare dati di tracciamento da applicazioni di terze parti in Analytics, in modo da raccogliere e utilizzare dati da una singola posizione centrale. Se utilizzi uno dei prodotti partner, puoi creare un'integrazione che importa i dati dell'applicazione nei rapporti di marketing. Una volta integrati, potete generare rapporti che includono dati dall'applicazione.

Ad esempio, un'integrazione e-mail potrebbe voler utilizzare un partner e-mail per distribuire una campagna e-mail. Quando i visitatori accedono al sito Web, è necessario sapere quali sono arrivati in risposta alla campagna e-mail. I connettori dati integrano i dati del partner e-mail nei rapporti di marketing in modo da poter determinare l’efficacia della campagna e-mail.

**Requisiti di sistema**

I connettori dati devono essere integrati in modo appropriato con la maggior parte dei browser più diffusi. Tuttavia, i report hanno un aspetto e funzioni ottimali nei sistemi che soddisfano le seguenti raccomandazioni:

* Browser: Microsoft Internet Explorer versione 6 e successive
* Cookie:Obbligatorio
* JavaScript: Abilitato
* Sistema operativo: Basato su Windows
* Macromedia Flash Player: versione 6 o successiva
* Risoluzione monitor: 1024x768 (800x600 funzionerà)
* Profondità colore: 16 bit o superiore

Inoltre, la raccolta dei dati migliora quando i browser Web degli utenti dispongono di JavaScript abilitato.

**Prerequisiti**

Prima di configurare l'integrazione dei connettori dati per il prodotto, effettuare le seguenti operazioni:

* Disponi delle credenziali di accesso necessarie per l'account del prodotto partner, con i diritti di accesso a tutti i dati da integrare nei rapporti di marketing. Potreste desiderare di creare un account e-mail speciale per i distributori di report e per le notifiche relative alle operazioni integrate.
* Identificate le variabili personalizzate che contengono le informazioni sulla campagna. Questo è comunemente definito codice di tracciamento campagna, ma l'organizzazione potrebbe usare altri termini.
* Determinare gli eventi che si desidera ricevere le impression e fare clic sui dati. È possibile rinominare gli eventi di conseguenza.
* Inserite il codice appropriato nella pagina di destinazione in modo che Analytics possa eseguire la modellazione appropriata con i dati provenienti dal prodotto partner. Specific instructions for each partner product are found in the in the Data Connectors Showcase on the Resources tab.

## Add an integration

Per accedere alla pagina di [!UICONTROL Data Connectors] destinazione (console) è necessario disporre di un account corrente. It is also recommended that you are familiar with Adobe Analytics.

1. Log into the Adobe Experience Cloud.
1. Clic **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Data Connectors]**.
1. Fai clic su **[!UICONTROL Add New]**.
1. Step through the **[!UICONTROL Add Integration]** interface.

   Depending on the individual product integration, you might need to provide specific configuration information as part of the integration process.

   Al termine dell'integrazione, l'icona del prodotto partner viene visualizzata nella pagina Rete Connettori dati ed è disponibile nei menu.

## Data Connectors Console

After you activate an integration, it displays on the  page. [!UICONTROL Data Connectors] You can view details and make configuration changes on the console. You can view active integrations and integrations across all report suites in your company. You can also view an activity log, set an integration as a dashboard, configure an integration, and find help.

![Data Connectors console](assets/data-connectors-console.png)

## Remarketing segments in data connectors

Remarketing segments are data files that are created based on the variables used in a data connectors integration.

Adobe Analytics sends these in separate daily files via data warehouse to an FTP created by Adobe for the third party. Il terzo distribuisce quindi questi file al client. Le aziende comunemente utilizzano questi per ricommercializzare quelli che possono aver visitato il sito e guardato un prodotto, ma non hanno acquistato. Ad esempio, un cliente può offrire uno sconto a un prodotto che ha visualizzato ma che non ha finito per acquistarlo.

**Segmenti**

* [!UICONTROL Cart Abandonment]: La percentuale di visitatori ha aggiunto un elemento al carrello ma non l'ha acquistato. Tecnicamente è una metrica calcolata composta da Ordini divisi per Cart Add.
* [!UICONTROL Purchases]: ID destinatario (o ID visitatore) che hanno effettuato acquisti in base all'ID messaggio in un prodotto specifico.
* [!UICONTROL Product Views]: Simile a [!UICONTROL Cart Abandonment], anche questa è una metrica calcolata. Viene [!UICONTROL Product Views] divisa per Ordini, in quanto la visualizzazione del prodotto da parte dei clienti mostra un certo interesse.

**Esempi di implementazione**

Per implementare correttamente i segmenti di remarketing, è necessario soddisfare le seguenti condizioni:

* È stato creato un contratto relativo ai connettori dati e la tua organizzazione ha completato la fase di implementazione con un consulente Adobe.
* L'evento corrispondente viene attivato contemporaneamente alla variabile products:
   * Abbandono carrello: `scAdd` evento
   * Acquisti: `purchase` evento
   * Visualizzazioni prodotto: `prodView` evento

**** Nota: Se il prodotto è definito senza un evento associato, l'evento prodView si attiva automaticamente.
Se i requisiti di cui sopra non sono soddisfatti, i segmenti di remarketing corrispondenti non vengono segnalati correttamente.

[!UICONTROL Cart Abandonment]: viene attivato dopo che l'utente aggiunge un prodotto al carrello:

```
s.products=";cat";
s.events="scAdd";
```

[!UICONTROL Purchases]: viene attivato nella pagina di conferma dell'acquisto:

```
s.products=";
cat;1;50";
s.events="purchase";
//Note: Though optional, adding the purchaseID variable increases accuracy by preventing duplicate purchases
```

**Common Issues**

| Problema | Descrizione |
| -----------| ---------- |  
| Nessuna informazione ID prodotto visualizzata nel file Segmento di creazione commenti. | Si verifica quando viene attivato l'evento corretto, ma non è presente alcuna variabile di prodotto nella stessa richiesta di immagine. Per correggere questo problema, accertatevi che la variabile "products" e l'evento corrispondente vengano attivati sulla stessa pagina, come mostrato negli esempi di implementazione riportati sopra. |
| I file dei segmenti di commento non vengono ricevuti. | Se non ricevi i file, chiedi a ClientCare di contattare uno degli utenti supportati della tua organizzazione per indagare sulla causa della mancata ricezione dei rapporti. |


> [!IMPORTANT] È comune per i consulenti impostare una richiesta data warehouse come rapporto pianificato giornaliero, oltre al file del segmento di remarketing dei connettori dati standard. Questa richiesta di data warehouse includerebbe variabili di connettori dati e variabili di connettori non dati, e la richiesta può essere pianificata solo in base alla richiesta specifica della tua organizzazione. Per evitare confusione durante la risoluzione dei problemi, specificare se il file in questione è il file del segmento di remarketing effettivo o una richiesta data warehouse contenente variabili non di genetica.
