---
description: Le sovrapposizioni offrono diversi modi per configurare la visualizzazione dei dati in modo da poter vedere e comprendere facilmente la popolarità dei collegamenti in una pagina.
seo-description: Le sovrapposizioni offrono diversi modi per configurare la visualizzazione dei dati in modo da poter vedere e comprendere facilmente la popolarità dei collegamenti in una pagina.
seo-title: Sovrapposizioni personalizzabili
solution: Analytics
title: Sovrapposizioni personalizzabili
topic: Activity map
uuid: c 1 e 56480-c 1 df -4 a 81-8 a 2 a -42 ea 1362175 c
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Sovrapposizioni personalizzabili

Le sovrapposizioni offrono diversi modi per configurare la visualizzazione dei dati in modo da poter vedere e comprendere facilmente la popolarità dei collegamenti in una pagina.

Le sovrapposizioni consentono di visualizzare i dati di un clic direttamente sulla pagina. Questo è il risultato che separa uno strumento di analisi visiva come Activity Map da strumenti tabulare ed elementi grafici come Reporting e analisi.

Activity Map offre tre tipi di sovrapposizioni:

* Sovrapposizione sfumatura (Mappa di calore)
* Sovrapposizione bolle
* Sovrapposizione Gainers e Losers

You can also configure [overlay rendering for dynamic content](/help/analyze/activity-map/activitymap-link-tracking/activitymap-stl-track-custom-elements.md).

To make changes to overlays, open the [Overlay Settings Panel](/help/analyze/activity-map/activitymap-overlay-settings.md) and edit available options.

Hovering over an overlay will display its [details](/help/analyze/activity-map/activitymap-overlay-details.md).

## Gradient overlay (Heatmap) {#section_06AF13DE05A1454D960176CD0DA921A6}

Con la sovrapposizione sfumatura, l'intensità del colore si basa sulla popolarità del collegamento. Questa intensità può essere normalizzata per le primi 30 classificazioni, o una funzione del valore della metrica assoluta.

Queste metriche vengono sovrapposte ai collegamenti della pagina come tipo dì mappa di calore'per rispondere alle domande decisive, incluse le seguenti:

* Qual è il valore di una singola pagina?
* Qual è il valore di un singolo elemento su una pagina?
* Qual è la "beni reale digitale" più efficace su una pagina?

![](assets/gradient.png)

## Bubble overlay {#section_A657AB3F64CB47F881BBFFD72B37D9D4}

La sovrapposizione Bolle mostra il contenuto della sovrapposizione (metrica, percentuale o classifica) in una piccola bolla callout.

Le sovrapposizioni delle bolle vengono visualizzate quando selezionate questa sovrapposizione in Tipo sovrapposizione nella barra degli strumenti. Bubble overlays show for all links that match the selection in [Activity Map Settings](/help/analyze/activity-map/activitymap-overlay-settings.md) (top 30, top 50, all...). Se questa opzione non è selezionata, verrà visualizzata sovrapposizioni con sfumatura.

![](assets/bubble_overlay.png)

>[!NOTE]
>
>Le sovrapposizioni delle bolle per i sottomenu vengono visualizzate solo quando viene visualizzato il sottomenu:
>
>![](assets/bubbles_submenu.png)&gt;

## Gainers and losers overlays {#section_EE80278E20C14824869BF5A27A4634C8}

**[!UICONTROL Gainers and losers overlays]** sono disponibili solo in modalità Live. Essi segnalano modifiche in tempo reale nell'attività dei collegamenti confrontando le metriche dal periodo corrente con metriche dell'ultimo periodo. Offrono un modo visivamente più efficace di visualizzare il tendenza in tempo reale.

Questa sovrapposizione in tempo reale classifica i clic in base alle modifiche nel valore della metrica tra i periodi precedente e corrente.

![](assets/gainers_losers.png)

