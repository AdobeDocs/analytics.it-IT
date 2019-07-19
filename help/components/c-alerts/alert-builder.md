---
description: nulle
seo-description: nulle
seo-title: Alert Builder (Generatore di avvisi)
title: Alert Builder (Generatore di avvisi)
uuid: 86 d 00 a 33-dc 99-4 dc 3-a 732-0 b 895 ba 487 bc
translation-type: tm+mt
source-git-commit: 8b2feced9fd503395d06dc12c8e5d7985ca89161

---


# Alert Builder (Generatore di avvisi)

>[!IMPORTANT]
>
>Intelligent Alerts are available to Adobe [!DNL Analytics] Prime and Adobe [!DNL Analytics] Ultimate customers only.

Puoi accedere a Alert Builder (Generatore di avvisi) in quattro modi:

* Utilizzando la seguente scelta rapida in Analysis Workspace:

   `ctrl (or cmd) + shift + a`
* By going to **[!UICONTROL Workspace]** &gt; **[!UICONTROL Components]** &gt; **[!UICONTROL New Alert]**.
* By selecting one or more freeform table line items, right-clicking and selecting **[!UICONTROL Create Alert from Selection]**.
* From within a [!UICONTROL Reports & Analytics] report, by going to **[!UICONTROL More]** &gt; **[!UICONTROL Add Alert]**.

The Alert Builder interface is familiar to those who have built segments or calculated metrics in [!DNL Analytics]:

![](assets/alert_builder.png)

**Alert Name (Nome avviso)**

Inserisci un nome per l’avviso. Il nome può contenere il nome del rapporto o la soglia di metrica.

**Time Granularity (Granularità tempo)**

Specifica quando occorre controllare la metrica: ogni ora, giorno, settimana o mese.

>[!NOTE]
>
>Per le suite di rapporti con un calendario personalizzato, nel Generatore di avvisi non è supportata la granularità mensile.

**Recipients (Destinatari)**

Specifica a chi deve essere inviato l’avviso. An alert can be sent to an [!DNL Analytics] user, an [!DNL Analytics] group, a raw email address, or to a phone number.

>[!IMPORTANT]
>
>The phone number must be preceded by a "+" and a [country code](https://countrycode.org/).

**Expiration Date (Data di scadenza)**

Imposta la data di scadenza dell’avviso.

**Send an Alert When... (Invia un avviso quando...)**

*... Any of These Metrics trigger (...si verifica uno di questi attivatori di metrica)*

* Trascina la metrica nell’area per l’aggiunta degli attivatori.

   Note that an **"incompatible components”** message will appear if not all the components (metrics/dimensions/segments) in the alert are compatible with the currently selected report suite.

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
