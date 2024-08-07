---
description: Utilizzare gli avvisi in Analysis Workspace.
title: Panoramica di Alert Builder
feature: Alerts
exl-id: 82e51357-4a32-4db1-bc56-95a72dbaa1be
source-git-commit: 93099d36a65ca2bf16fbd6342f01bfecdc8c798e
workflow-type: tm+mt
source-wordcount: '455'
ht-degree: 80%

---

# Alert Builder (Generatore di avvisi)

>[!IMPORTANT]
>
>Gli avvisi intelligenti sono disponibili solo per i clienti Adobe [!DNL Analytics] Prime e Adobe [!DNL Analytics] Ultimate.

Accedere al generatore di avvisi in uno dei tre modi seguenti:

* Utilizzando la seguente scelta rapida in Analysis Workspace:

  `ctrl (or cmd) + shift + a`
* Da **[!UICONTROL Workspace]** > **[!UICONTROL Components]** > **[!UICONTROL New Alert]**.
* Selezionando uno o più elementi della tabella a forma libera, facendo clic con il pulsante destro del mouse e selezionando **[!UICONTROL Create Alert from Selection]**.

L&#39;interfaccia del Generatore di avvisi è familiare a coloro che hanno creato segmenti o metriche calcolate in [!DNL Analytics]:

![](assets/alert_builder.png)

**Alert Name (Nome avviso)**

Inserisci un nome per l’avviso. Il nome può contenere il nome del rapporto o la soglia di metrica.

**Time Granularity (Granularità tempo)**

Specifica quando occorre controllare la metrica: ogni ora, giorno, settimana o mese.

>[!NOTE]
>
>Nelle suite per rapporti con un calendario personalizzato non è supportata la granularità mensile nel generatore di avvisi.

**Recipients (Destinatari)**

Specifica a chi deve essere inviato l’avviso. È possibile inviare un avviso a un utente [!DNL Analytics], a un gruppo [!DNL Analytics], a un indirizzo e-mail non elaborato o a un numero di telefono.

>[!IMPORTANT]
>
>Il numero telefonico deve essere preceduto dal segno “+” e dal [prefisso del paese](https://countrycode.org/).

**Expiration Date (Data di scadenza)**

Imposta la data di scadenza dell’avviso.

**Send an Alert When... (Invia un avviso quando...)**

*... Any of These Metrics trigger (...si verifica uno di questi attivatori di metrica)*

* Trascina la metrica nell’area di lavoro per l’aggiunta degli attivatori.

  Si noti che verrà visualizzato un messaggio di **&quot;componenti incompatibili&quot;** se non tutti i componenti (metriche, dimensioni o segmenti) nell&#39;avviso sono compatibili con la suite di rapporti attualmente selezionata.

* Determina la soglia che dovrà essere superata affinché venga attivato l’avviso. Puoi impostare questo valore su una soglia e quindi su una delle seguenti condizioni:

   * anomaly exists (l’anomalia esiste)
   * anomaly is above expected (l’anomalia supera il valore previsto)
   * l’anomalia è inferiore al valore previsto
   * l’anomalia eccede
   * è superiore o uguale a
   * is below or equals (è inferiore o uguale a)
   * cambia di

* “L’anomalia eccede” è una nuova condizione che va oltre le soglie esistenti (statiche). Richiama gli algoritmi di rilevamento anomalie che definiscono l’attivatore in modo dinamico. Puoi impostare una soglia di 90%, 95%, 99%, 99,75% o 99,9%.
* Le granularità orarie sono impostate con una soglia di 99,75% e quelle giornaliere con una soglia del 99%.
* È anche possibile utilizzare metriche calcolate.

*... With These Filters (...con questi filtri)*

Trascina segmenti o dimensioni per aggiungere i filtri. Ad esempio, se si aggiunge un segmento “Mobile Devices Only” (Solo dispositivi mobili) la regola viene attivata solo per i dispositivi mobili.

Per aggiungere altri segmenti si utilizza l’operatore AND.

**Aggiungere una regola**

Per aggiungere una regola AND o OR, fai clic sull’icona a forma di ingranaggio.

## Anteprima avvisi {#section_10D75BA7B77E4C5FAF58A719C082E070}

L’anteprima interattiva degli avvisi mostra la frequenza approssimativa di un avviso sulla base dell’esperienza passata.

Ad esempio, se imposti la granularità su Ogni giorno, l’anteprima indicherà che l’avviso è stato attivato x volte per una specifica metrica negli ultimi 30 o 31 giorni.

Se sono stati attivati troppi avvisi, puoi regolare la soglia in [Alert Manager](/help/components/c-alerts/alert-manager.md) (Gestione avvisi).

![](assets/alert_preview.png)
