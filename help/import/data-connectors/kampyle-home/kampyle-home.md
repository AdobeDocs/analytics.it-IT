---
description: Utilizza il connettore dati Kampyle con Adobe Analytics.
title: Connettore dati Kampyle per Adobe Analytics
uuid: f7733c81-93f5-4c50-b83a-721a6fbd4e8e
translation-type: tm+mt
source-git-commit: 5d8032a9806836e7d0ecbd7fa3652ed1fd137e89
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 5%

---


# Connettore dati Kampyle per Adobe Analytics{#kampyle-data-connector-for-adobe-analytics}

>[!IMPORTANT]
>
>La tecnologia Adobe Data Connector terminerà il 1° agosto 2021. [Ulteriori informazioni...](/help/import/data-connectors/data-connectors-eol.md)

Il Connettore dati Kampyle per Adobe Analytics combina il sistema di feedback integrato di Kampyle e il reporting comportamentale di Adobe Analytics® per creare potenti opportunità di analisi e ottimizzazione per la tua organizzazione.

Gli esperti di marketing online stanno diventando sempre più consapevoli della rilevanza del feedback dei clienti nella creazione di marchi e nella promozione dei risultati aziendali. Il Connettore dati Kampyle per Adobe Analytics® aggiunge metriche e dimensioni di feedback dei visitatori ad Adobe Analytics. Ti consente di analizzare il comportamento dei visitatori nel contesto dei loro atteggiamenti e opinioni. Questo consente di ottimizzare in base al feedback e migliora i tassi di conversione.

## Prerequisiti per l’integrazione{#integration-prerequisites}

Prerequisiti da considerare prima di poter attivare il connettore dati.

### Prerequisiti per i clienti di Adobe: {#section-d9c2e266931249e596de5f4406b5b6f0}

* Devi essere un cliente Adobe Analytics corrente.
* Devi essere un utente amministratore.
* Nella suite di rapporti devi disporre di 1 variabile eVar disponibile e abilitata.
* Nella suite di rapporti devono essere disponibili 3 eventi personalizzati disponibili e attivati (tipo: contatore).

### Prerequisiti per i clienti Kampyle: {#section-4bbbca50e74d4f218414ae0cc535b8e9}

* Devi essere un cliente attuale di Kampyle per Siti web.
* Devi essere un utente amministratore di Adobe Experience Cloud con autorizzazioni per abilitare i connettori dati.
* È necessario essere in grado di recuperare la chiave privata Kampyle dall’interfaccia utente di gestione del modulo di feedback Kampyle.

## Recupera la chiave privata Kampyle{#retrieve-the-kampyle-private-key}

Passaggi per recuperare la chiave all’interno dell’interfaccia Kampyle.

1. Accedi al tuo account Kampyle all&#39;indirizzo [https://www.kampyle.com/login](https://www.kampyle.com/login).
1. Nella navigazione a sinistra, vai a **[!UICONTROL Feedback Form]** > **[!UICONTROL Feedback Form Customization]**.

   ![](assets/retrieve_key1.png)

1. Trova la Chiave privata elencata nella parte inferiore del riquadro del contenuto principale.

   ![](assets/retrieve_key2.png)
