---
description: 'null'
title: Alert Builder (Generatore di avvisi)
uuid: ebc2d457-4abd-4b1a-9357-489b5aeb3f64
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Alert Builder (Generatore di avvisi)

>[!IMPORTANT]
>
>Gli Avvisi intelligenti sono disponibili solo per i clienti di Adobe Analytics Prime e Adobe Analytics Ultimate.

## Accedere al generatore di avvisi

Accedi al Generatore di avvisi in quattro modi:

* Utilizzando la seguente scelta rapida in Analysis Workspace:

   `ctrl (or cmd) + shift + a`
* Da **[!UICONTROL Workspace]** (Workspace) > **[!UICONTROL Components]** (Componenti) > **[!UICONTROL New Alert]** (Nuovo avviso).
* Selezionando uno o più elementi della tabella a forma libera, facendo clic con il pulsante destro del mouse e selezionando **[!UICONTROL Create Alert from Selection]** (Crea avviso da selezione).
* Da un rapporto Reports &amp; Analytics, scegliendo **[!UICONTROL More]** (Altro) > **[!UICONTROL Add Alert]** (Aggiungi avviso).

## Creare avvisi

Se hai già avuto modo di creare segmenti o metriche calcolate in Analytics, l’interfaccia di Alert Builder (Generatore di avvisi) ti risulterà familiare:

![](assets/alert_builder.png)

<!--Meike, I edited this table for validation -->

**Alert Name (Nome avviso)**

Specificate un nome per l’avviso. Il nome dell&#39;avviso può contenere il nome del rapporto o la soglia delle metriche.

**Time Granularity (Granularità tempo)**

Specifica quando occorre controllare la metrica: ogni ora, giorno, settimana o mese.

>[!NOTE] Nelle suite per rapporti con un calendario personalizzato non è supportata la granularità mensile nel generatore di avvisi.

**Recipients (Destinatari)**

Specifica dove può essere inviato l’avviso. Un avviso può essere inviato a un utente Analytics, a un gruppo Analytics, a un indirizzo e-mail non elaborato o a un numero di telefono.

>[!IMPORTANT]
>
>Il numero telefonico deve essere preceduto dal segno “+” e dal [prefisso del paese](https://countrycode.org/).

Il messaggio e-mail che un utente riceve dopo l’attivazione di un avviso è simile al seguente:

![](assets/alerts-email.PNG)

**Expiration Date (Data di scadenza)**

Imposta la data di scadenza dell’avviso.

**Send an Alert When... (Invia un avviso quando...)**

*... Any of These Metrics trigger (...si verifica uno di questi attivatori di metrica)*

* Trascina la metrica nell’area di lavoro per l’aggiunta degli attivatori.

   Se non tutti i componenti (metriche, dimensioni o segmenti) nell’avviso sono compatibili con la suite di rapporti selezionati, viene visualizzato un messaggio con riferimento a **“componenti non compatibili”**.
* Determinare la soglia che la metrica deve superare prima che venga impostato un avviso. Puoi impostare questo valore su una soglia e quindi su una delle seguenti condizioni:

   * anomalia esistente
   * anomalia al di sopra del previsto
   * anomalia al di sotto del previsto
   * è superiore o uguale a
   * è inferiore o uguale a
   * modifiche di
   * Puoi impostare una soglia di 90%, 95%, 99%, 99,75% o 99,9%.
   È anche possibile utilizzare metriche calcolate.

*... With These Filters (...con questi filtri)*

* Trascina segmenti o dimensioni per aggiungere filtri. Ad esempio, se si aggiunge un segmento &quot;Solo dispositivi mobili&quot; la regola viene attivata solo per i dispositivi mobili.
* Altri filtri verranno aggiunti utilizzando un&#39;istruzione AND.

**Aggiungere una regola**

Per aggiungere una regola AND o OR, fai clic sull’icona a forma di ingranaggio.

## Anteprima avvisi {#section_10D75BA7B77E4C5FAF58A719C082E070}

L’anteprima interattiva degli avvisi mostra la frequenza approssimativa di un avviso in base all’esperienza passata.

Ad esempio, se imposti la granularità dell’ora su Ogni giorno, l’anteprima indicherà che l’avviso sarebbe stato attivato x volte per una metrica specifica negli ultimi 30 o 31 giorni.

Se si è scoperto che troppi avvisi sarebbero stati attivati, è possibile regolare la soglia nella Gestione [](/help/components/c-alerts/alert-manager.md)avvisi.

![](assets/alert_preview.png)
