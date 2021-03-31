---
description: Le sovrapposizioni consentono di configurare la visualizzazione dei dati in modo da poter vedere e comprendere facilmente la popolarità dei collegamenti in una pagina.
title: Sovrapposizioni personalizzabili
uuid: c1e56480-c1df-4a81-8a2a-42ea1362175c
feature: Activity Map
role: Business Practices, amministratore
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 1%

---


# Sovrapposizioni personalizzabili

Le sovrapposizioni consentono di configurare la visualizzazione dei dati in modo da poter vedere e comprendere facilmente la popolarità dei collegamenti in una pagina.

Le sovrapposizioni consentono di visualizzare i dati dei clic direttamente sulla pagina. Questo è ciò che separa uno strumento di analisi visiva come Activity Map da strumenti grafici e tabulari come Reports &amp; Analytics.

Activity Map offre tre tipi di sovrapposizioni:

* Sovrapposizione sfumatura (mappa di calore)
* Sovrapposizione bolla
* Sovrapposizione profitti e perdite

Puoi anche configurare il rendering di sovrapposizione [per il contenuto dinamico](/help/analyze/activity-map/activitymap-link-tracking/activitymap-stl-track-custom-elements.md).

Per apportare modifiche alle sovrapposizioni, apri il [pannello Impostazioni sovrapposizione](/help/analyze/activity-map/activitymap-overlay-settings.md) e modifica le opzioni disponibili.

Passando il puntatore del mouse su una sovrapposizione verranno visualizzati i relativi [dettagli](/help/analyze/activity-map/activitymap-overlay-details.md).

## Sovrapposizione sfumatura (mappa di calore) {#section_06AF13DE05A1454D960176CD0DA921A6}

Con la sovrapposizione sfumatura, l&#39;intensità del colore si basa sulla popolarità del collegamento. Questa intensità può essere normalizzata per le prime 30 classificazioni, o per una funzione del valore della metrica assoluta.

Queste metriche vengono sovrapposte ai collegamenti della pagina come una sorta di &quot;mappa di calore&quot; per rispondere a domande critiche, tra cui:

* Qual è il valore di una singola pagina?
* Qual è il valore di un singolo elemento in una pagina?
* Qual è il &quot;digital real estate&quot; più prezioso su una pagina?

![](assets/gradient.png)

## Sovrapposizione bolla {#section_A657AB3F64CB47F881BBFFD72B37D9D4}

La sovrapposizione a bolla mostra il contenuto di sovrapposizione (metrica, percentuale o classificazione) in una piccola fumetto di callout.

Le sovrapposizioni a bolle vengono visualizzate quando selezioni questa sovrapposizione nel tipo di sovrapposizione nella barra degli strumenti. . Le sovrapposizioni a bolle vengono visualizzate per tutti i collegamenti che corrispondono alla selezione in [Impostazioni Activity Map](/help/analyze/activity-map/activitymap-overlay-settings.md) (top 30, top 50, all...). Se questa opzione non è selezionata, vengono visualizzate le sovrapposizioni sfumatura.

![](assets/bubble_overlay.png)

>[!NOTE]
>
>Le sovrapposizioni a bolle per i sottomenu vengono visualizzate solo quando si visualizza il sottomenu:
>
>![](assets/bubbles_submenu.png)>

## Sovrapposizioni vincitori e perdenti {#section_EE80278E20C14824869BF5A27A4634C8}

**[!UICONTROL Gainers and losers overlays]** sono disponibili solo in modalità Live. Segnala cambiamenti in tempo reale nell’attività di collegamento confrontando le metriche del periodo corrente con quelle dell’ultimo periodo. Offrono un modo visivamente accattivante per visualizzare le tendenze in tempo reale.

Questa sovrapposizione in tempo reale classifica i clic in base alle modifiche del valore della metrica tra il periodo precedente e quello corrente.

![](assets/gainers_losers.png)

