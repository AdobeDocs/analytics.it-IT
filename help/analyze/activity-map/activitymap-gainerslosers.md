---
description: Le sovrapposizioni offrono diversi modi per configurare la visualizzazione dei dati in modo da poter vedere e comprendere facilmente la popolarità dei collegamenti su una pagina.
title: Sovrapposizioni personalizzabili
feature: Activity Map
role: User, Admin
exl-id: 1e83d470-36e4-47bb-a262-ac12472b21c3
source-git-commit: ab6d3267bd6b503fe96ceea2b870c2e7cdf5d9f4
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 1%

---

# Sovrapposizioni personalizzabili

Le sovrapposizioni offrono diversi modi per configurare la visualizzazione dei dati in modo da poter vedere e comprendere facilmente la popolarità dei collegamenti su una pagina.

Le sovrapposizioni consentono di visualizzare i dati dei clic direttamente sulla pagina. Questo è ciò che separa uno strumento di analisi visiva come Activity Map da strumenti principalmente tabulari e grafici come Reports &amp; Analytics.

Activity Map offre tre tipi di sovrapposizioni:

* Sovrapposizione sfumatura (mappa di calore)
* Sovrapposizione bolla
* Sovrapposizione di guadagni e perdenti

Puoi anche configurare [rendering di sovrapposizione per contenuti dinamici](/help/analyze/activity-map/activitymap-link-tracking/activitymap-stl-track-custom-elements.md).

Per apportare modifiche alle sovrapposizioni, apri [Pannello Impostazioni sovrapposizione](/help/analyze/activity-map/activitymap-overlay-settings.md) e modifica le opzioni disponibili.

Passando il puntatore del mouse su una sovrapposizione, vengono visualizzati i relativi [dettagli](/help/analyze/activity-map/activitymap-overlay-details.md).

## Sovrapposizione sfumatura (mappa di calore) {#section_06AF13DE05A1454D960176CD0DA921A6}

Con la sovrapposizione sfumatura, l&#39;intensità del colore si basa sulla popolarità del collegamento. Questa intensità può essere normalizzata per le prime 30 classifiche, o una funzione del valore metrico assoluto.

Queste metriche sono sovrapposte sui collegamenti della pagina come una sorta di &quot;mappa di calore&quot; per rispondere a domande critiche, tra cui le seguenti:

* Qual è il valore di una singola pagina?
* Qual è il valore di un singolo elemento su una pagina?
* Qual è il &quot;digital real estate&quot; più prezioso su una pagina?

![](assets/gradient.png)

## Sovrapposizione bolla {#section_A657AB3F64CB47F881BBFFD72B37D9D4}

La sovrapposizione bolla mostra il contenuto della sovrapposizione (metrica, percentuale o classificazione) in una piccola bolla di callout.

Le sovrapposizioni a bolla vengono visualizzate quando selezionate questa sovrapposizione in Tipo di sovrapposizione nella barra degli strumenti. . Le sovrapposizioni a bolla vengono visualizzate per tutti i collegamenti che corrispondono alla selezione in [Impostazioni Activity Map](/help/analyze/activity-map/activitymap-overlay-settings.md) (top 30, top 50, tutti...). Se questa opzione non è selezionata, verranno visualizzate le sovrapposizioni sfumatura.

![](assets/bubble_overlay.png)

>[!NOTE]
>
>Le sovrapposizioni a bolla per i sottomenu vengono visualizzate solo quando si visualizza il sottomenu:
>
>![](assets/bubbles_submenu.png)>

## Sovrapposizioni di guadagni e perdenti {#section_EE80278E20C14824869BF5A27A4634C8}

**[!UICONTROL Gainers and losers overlays]** sono disponibili solo in modalità Live. Segnalano le modifiche in tempo reale nell’attività di collegamento confrontando le metriche del periodo corrente con quelle dell’ultimo periodo. Offrono un modo visivamente convincente di visualizzare le tendenze in tempo reale.

Questa sovrapposizione in tempo reale classifica i clic in base alle modifiche nel valore della metrica tra il periodo precedente e quello corrente.

![](assets/gainers_losers.png)
