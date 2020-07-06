---
description: 'null'
title: Alert Builder (Generatore di avvisi)
uuid: 86d00a33-dc99-4dc3-a732-0b895ba487bc
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '449'
ht-degree: 81%

---


# Alert Builder (Generatore di avvisi)

>[!IMPORTANT]
>
>Intelligent Alerts are available to Adobe [!DNL Analytics] Prime and Adobe [!DNL Analytics] Ultimate customers only.

Puoi accedere a Alert Builder (Generatore di avvisi) in quattro modi:

* Utilizzando la seguente scelta rapida in Analysis Workspace:

   `ctrl (or cmd) + shift + a`
* Da **[!UICONTROL Workspace]** (Workspace) > **[!UICONTROL Components]** (Componenti) > **[!UICONTROL New Alert]** (Nuovo avviso).
* Selezionando uno o più elementi della tabella a forma libera, facendo clic con il pulsante destro del mouse e selezionando **[!UICONTROL Create Alert from Selection]** (Crea avviso da selezione).
* From within a [!UICONTROL Reports & Analytics] report, by going to **[!UICONTROL More]** > **[!UICONTROL Add Alert]**.

The Alert Builder interface is familiar to those who have built segments or calculated metrics in [!DNL Analytics]:

![](assets/alert_builder.png)

**Alert Name (Nome avviso)**

Inserisci un nome per l’avviso. Il nome può contenere il nome del rapporto o la soglia di metrica.

**Time Granularity (Granularità tempo)**

Specifica quando occorre controllare la metrica: ogni ora, giorno, settimana o mese.

>[!NOTE]
>
>Nelle suite per rapporti con un calendario personalizzato non è supportata la granularità mensile nel generatore di avvisi.

**Recipients (Destinatari)**

Specifica a chi deve essere inviato l’avviso. An alert can be sent to an [!DNL Analytics] user, an [!DNL Analytics] group, a raw email address, or to a phone number.

>[!IMPORTANT]
>
>Il numero telefonico deve essere preceduto dal segno “+” e dal [prefisso del paese](https://countrycode.org/).

**Expiration Date (Data di scadenza)**

Imposta la data di scadenza dell’avviso.

**Send an Alert When... (Invia un avviso quando...)**

*... Any of These Metrics trigger (...si verifica uno di questi attivatori di metrica)*

* Trascina la metrica nell’area di lavoro per l’aggiunta degli attivatori.

   Note that an **&quot;incompatible components&quot;** message will appear if not all the components (metrics/dimensions/segments) in the alert are compatible with the currently selected report suite.

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
