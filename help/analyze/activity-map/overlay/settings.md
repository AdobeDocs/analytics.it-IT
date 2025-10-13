---
description: Modifica le impostazioni e le proprietà per tutti i tipi di visualizzazioni di sovrapposizione in Activity Map.
title: Configurare le impostazioni di Activity Map
uuid: 42a0309e-3efc-4506-989b-09b6fe419423
feature: Activity Map
role: User, Admin
exl-id: 65c9c690-81e0-4f0f-989d-586d247ed380
source-git-commit: 13ad9d40ad74a8dffe05d899db54f4d77cbcc34c
workflow-type: tm+mt
source-wordcount: '497'
ht-degree: 2%

---

# Configurare le impostazioni di Activity Map

Il pannello delle impostazioni di Activity Map consente di modificare le impostazioni e le proprietà per tutti i tipi di visualizzazioni di sovrapposizione.

**[!UICONTROL Activity Map overlay]** > **Mostra impostazioni (icona ingranaggio)** > **[!UICONTROL Settings]**

## Impostazioni generali

Modifica le impostazioni generali per l’estensione e le sovrapposizioni.

* **[!UICONTROL Companies]**: mostra l&#39;organizzazione Analytics corrente a cui hai effettuato l&#39;accesso.
* **[!UICONTROL Page name]**: mostra il nome della pagina corrente.
* **[!UICONTROL Language]**: modifica la lingua per le etichette delle estensioni Activity Map. Questa impostazione non modifica il contenuto del sito web o i nomi dei collegamenti nei rapporti. Le lingue supportate includono inglese, francese, cinese (semplificato), cinese (tradizionale), tedesco, giapponese, coreano, spagnolo e portoghese.
* **[!UICONTROL Label overlays with]**: determina la bolla o il testo sfumato. Impostazione predefinita: [!UICONTROL Rank]. Le opzioni includono:
   * **[!UICONTROL No label]**: nessun testo all&#39;interno delle etichette, con caselle colorate
   * **[!UICONTROL Value]**: visualizza il numero di clic sul collegamento ([Occorrenze](/help/components/metrics/occurrences.md))
   * **[!UICONTROL Percent]**: visualizza la proporzione di clic sul collegamento rispetto al numero totale di clic sul collegamento nella pagina
   * **[!UICONTROL Rank]**: classificazione numerica del collegamento in base al numero di clic.
* **[!UICONTROL Label font size]**: determina le dimensioni del testo all&#39;interno della bolla o della sfumatura.
* **[!UICONTROL Gradient color]**: consente di modificare il colore della sfumatura quando il tipo di visualizzazione è [!UICONTROL Gradient].
* **[!UICONTROL Bubble color]**: consente di modificare il colore della bolla quando il tipo di visualizzazione è [!UICONTROL Bubble].
* **[!UICONTROL Color gradient based on]**: determina la metrica su cui si basa l&#39;intensità del colore di un collegamento quando il tipo di visualizzazione è [!UICONTROL Gradient].
   * **[!UICONTROL Top 30 rankings]**: intensità colore normalizzata per i primi 30 collegamenti.
   * **[!UICONTROL Absolute metric value]**: l&#39;intensità del colore è una funzione del valore della metrica assoluto.
* **[!UICONTROL Gradient transparency]**: determina la trasparenza delle sovrapposizioni sfumature quando il tipo di visualizzazione è [!UICONTROL Gradient]. Questo cursore consente di rendere la sovrapposizione colore completamente trasparente, completamente opaca o in qualsiasi punto intermedio.

## Impostazioni standard

Regola le impostazioni per la visualizzazione standard.

* **[!UICONTROL Dynamic data filtering]**: consente di modificare i collegamenti visualizzati.
   * **[!UICONTROL Top]**: visualizza i collegamenti più popolari. Utilizza l’elenco a discesa numerico a destra per determinare il numero di collegamenti principali da visualizzare. Le opzioni includono 1, 10, 50 e 100.
   * **[!UICONTROL Bottom]**: visualizza i collegamenti meno popolari in base all&#39;elenco a discesa dei numeri. Utilizza l’elenco a discesa numerico a destra per determinare il numero di collegamenti inferiori da visualizzare. Le opzioni includono 1, 10, 50 e 100.
   * **[!UICONTROL All links]**: non applicare il filtro dati dinamico. L’elenco a discesa numerico non si applica quando questa opzione è selezionata.
* **[!UICONTROL Hide overlays for links that received no hits]**: i collegamenti sulla pagina con zero clic sul collegamento non mostrano una sovrapposizione. Questi collegamenti sono esclusi dal filtro dei dati dinamici.

## Impostazioni Live

* **[!UICONTROL Display top]**: visualizza il primo numero di guadagni o perdenti in base all&#39;elenco a discesa numerico a sinistra.
* **[!UICONTROL Exclude bottom (%)]**: escludi la percentuale inferiore di modifiche al collegamento per visualizzare solo i collegamenti con un numero di dati sufficiente per mostrare guadagni o perdite rilevanti. La percentuale viene calcolata in base al numero di collegamenti presenti nella pagina. Ad esempio, se si esclude il 10% inferiore di un elenco di 200 collegamenti, i 20 collegamenti inferiori verranno filtrati.
* **[!UICONTROL Auto update data]**: determina se i dati di Analytics mostrati nella sovrapposizione vengono aggiornati automaticamente quando viene calcolato un nuovo periodo.
* **[!UICONTROL Auto update period]**: se questa opzione è selezionata, aggiorna la pagina con ogni nuovo recupero di dati in modo che i collegamenti della pagina siano sincronizzati più strettamente con i dati raccolti.
