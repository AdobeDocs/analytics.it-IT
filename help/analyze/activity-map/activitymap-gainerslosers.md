---
description: Le sovrapposizioni offrono diversi metodi per configurare la visualizzazione dei dati in modo da poter vedere e comprendere facilmente la popolarità dei collegamenti su una pagina.
title: Sovrapposizioni personalizzabili
topic: Activity map
uuid: c1e56480-c1df-4a81-8a2a-42ea1362175c
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 1%

---


# Sovrapposizioni personalizzabili

Le sovrapposizioni offrono diversi metodi per configurare la visualizzazione dei dati in modo da poter vedere e comprendere facilmente la popolarità dei collegamenti su una pagina.

Le sovrapposizioni consentono di visualizzare i dati dei clic direttamente sulla pagina. Questo è ciò che separa uno strumento di analisi visiva come  Activity Map dagli strumenti principalmente tabulari e grafici come Reports &amp;  Analytics.

 Activity Map offre tre tipi di sovrapposizioni:

* Sovrapposizione sfumatura (Heatmap)
* Sovrapposizione bolla
* Sovrapposizione Guadagni e Perdite

Potete anche configurare il rendering delle [sovrapposizioni per il contenuto](/help/analyze/activity-map/activitymap-link-tracking/activitymap-stl-track-custom-elements.md)dinamico.

Per apportare modifiche alle sovrapposizioni, aprite il pannello [Impostazioni](/help/analyze/activity-map/activitymap-overlay-settings.md) sovrapposizione e modificate le opzioni disponibili.

Quando si passa il mouse su una sovrapposizione, vengono visualizzati [i relativi dettagli](/help/analyze/activity-map/activitymap-overlay-details.md).

## Sovrapposizione sfumatura (Heatmap) {#section_06AF13DE05A1454D960176CD0DA921A6}

Con la sovrapposizione sfumatura, l’intensità del colore si basa sulla popolarità del collegamento. Questa intensità può essere normalizzata per le prime 30 classificazioni, o per una funzione del valore della metrica assoluta.

Queste metriche vengono sovrapposte ai collegamenti della pagina come una sorta di &quot;mappa termica&quot; per rispondere a domande critiche, tra cui:

* Qual è il valore di una singola pagina?
* Qual è il valore di un singolo elemento in una pagina?
* Qual è il &quot;patrimonio immobiliare digitale&quot; più prezioso di una pagina?

![](assets/gradient.png)

## Sovrapposizione bolla {#section_A657AB3F64CB47F881BBFFD72B37D9D4}

La sovrapposizione Bolla mostra il contenuto della sovrapposizione (metrica, percentuale o classificazione) in una piccola bolla di callout.

Le sovrapposizioni delle bolle vengono visualizzate quando selezionate questa sovrapposizione nel tipo di sovrapposizione nella barra degli strumenti. . Le sovrapposizioni delle bolle vengono visualizzate per tutti i collegamenti che corrispondono alla selezione in Impostazioni [Activity Map](/help/analyze/activity-map/activitymap-overlay-settings.md) (primi 30, primi 50, tutti...). Se questa opzione non è selezionata, vengono visualizzate le sovrapposizioni sfumatura.

![](assets/bubble_overlay.png)

>[!NOTE]
>
>Le sovrapposizioni per i sottomenu vengono visualizzate solo quando viene visualizzato il sottomenu:
>
>![](assets/bubbles_submenu.png)>

## Sovrapposizioni per guadagno e perdenti {#section_EE80278E20C14824869BF5A27A4634C8}

**[!UICONTROL Gainers and losers overlays]** sono disponibili solo in modalità Live. Segnalano le modifiche in tempo reale nell&#39;attività dei collegamenti confrontando le metriche del periodo corrente con quelle dell&#39;ultimo periodo. Offrono un modo visivamente accattivante per visualizzare le tendenze in tempo reale.

Questa sovrapposizione in tempo reale classifica i clic in base alle modifiche nel valore della metrica tra il periodo precedente e quello corrente.

![](assets/gainers_losers.png)

