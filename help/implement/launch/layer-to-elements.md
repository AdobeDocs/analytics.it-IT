---
description: 'null'
title: Mappa oggetti livello dati su elementi dati
uuid: null
translation-type: tm+mt
source-git-commit: 283fcd5832abe4c09caa332c2ebc3a22029e6707

---


# Mappa oggetti livello dati su elementi dati


Dopo aver [creato un livello](https://docs.adobe.com/content/help/en/analytics/implementation/prepare/data-layer.html) dati per l’implementazione, puoi mappare gli oggetti al suo interno su elementi [dati in Launch](https://docs.adobe.com/content/help/en/launch/using/reference/manage-resources/data-elements.html#create-a-data-element). Gli elementi dati sono elementi costitutivi della mappa dati che possono essere utilizzati in diversi modi. Puoi utilizzare gli elementi dati per raccogliere, organizzare e distribuire dati tra le soluzioni Adobe Platform, inclusi i report di Analytics.

Per mappare gli oggetti livello dati su elementi di dati di Launch:

1. In Launch, fare clic sul nome della proprietà a cui si desidera aggiungere l&#39;elemento dati. Se non è già stata impostata una proprietà, vedere le istruzioni per [creare una proprietà](https://docs.adobe.com/content/help/en/core-services-learn/implementing-in-websites-with-launch/configure-launch/launch.html)di avvio.

2. Fai clic su **Elementi** dati e quindi su **Crea nuovo elemento** dati.

   ![crea elemento dati](assets/createelement.png)


3. Inserisci un nome per l’elemento dati. Questo nome deve essere una semplice etichetta che corrisponde a una variabile JavaScript nel livello dati da monitorare.

4. Per Estensione, selezionate **Core.** Questa estensione include tutte le variabili necessarie.

5. For **Data Element Type**, select **JavaScript Variable**. Immettete il nome **della variabile** Javascript nel campo applicabile. Deve corrispondere al nome esatto dell&#39;oggetto nel livello dati JavaScript.

6. Per Valore **** predefinito, immettete il valore da stabilire per impostazione predefinita oppure lasciatelo vuoto, se appropriato.

7. In base alle procedure, è possibile selezionare le opzioni per applicare valori in lettere minuscole e applicare testo pulito (Launch applica la spaziatura convenzionale).

8. Specificate la durata per la quale desiderate avere i valori dello store Launch per il nuovo elemento dati.

9. Fai clic su **Salva.**

L’esempio seguente mostra un elemento dati Nome pagina in Launch creato per la variabile JavaScript ``pageName`` nel livello dati:

![Specifica elemento](assets/new_element.png)


Con gli oggetti livello dati mappati a elementi dati, puoi utilizzarli per compilare le variabili Analytics. Per ulteriori informazioni, vedi [Mappare gli elementi dati alle variabili](https://docs.adobe.com/content/help/en/analytics/implementation/prepare/data-layer.html)Analytics.
