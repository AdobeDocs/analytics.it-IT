---
title: Best practice per l’implementazione dei canali di marketing Adobe Analytics
description: Le best practice per l’utilizzo dei canali di marketing sono state aggiornate con informazioni sulla funzione Attribuzione e su Customer Journey Analytics
feature: Marketing Channels
exl-id: a0ab818d-7165-4f34-bc43-1ed8d6215800
TQID: https://experienceleague.adobe.com/mKq-l0nm-MFJjcvWoIwUfQ2QM-dYD6VlcfH-CszsUv8
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 669
ht-degree: 78%

---

# Attribuzione con canali di marketing - Best practice

I [canali di marketing](/help/components/c-marketing-channels/c-getting-started-mchannel.md) sono una funzione potente e utile di Adobe Analytics. Le attuali linee guida relative all’implementazione dei canali di marketing sono state formulate prima dell’introduzione della funzione [Attribuzione](/help/analyze/analysis-workspace/attribution/overview.md) e di [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=it#cja-usecases).

Al fine di garantire l’implementazione corretta per il futuro dei canali di marketing e la coerenza dei rapporti con la funzione Attribuzione e con Customer Journey Analytics, stiamo pubblicando una serie di best practice aggiornate. Se utilizzi già i canali di marketing, puoi scegliere le opzioni migliori tra queste nuove linee guida. Se non hai familiarità con i canali di marketing, ti consigliamo di attenerti a tutte le nuove best practice.

Al momento della loro introduzione, i canali di marketing erano dotati solo delle dimensioni primo contatto e ultimo contatto. La versione corrente dell’attribuzione non richiede più dimensioni esplicite di primo/ultimo contatto. Adobe fornisce dimensioni generiche “Canale marketing” e “Dettagli canale marketing” per consentirti di utilizzarle con il modello di attribuzione desiderato. Queste dimensioni generiche si comportano esattamente come le dimensioni di canale di primo contatto, ma hanno etichette diverse per evitare confusione quando si usano i canali di marketing con un modello di attribuzione diverso.

Poiché le dimensioni del canale di marketing dipendono da una definizione di visita tradizionale (come definita dalle relative regole di elaborazione), la definizione della visita non può essere modificata utilizzando le suite di rapporti virtuali. Queste procedure riviste consentono intervalli di lookback chiari e controllati con Attribution e con Adobe Analytics.

## Best practice n. 1: sfruttare Attribuzione per l’analisi controllata

Per ottimizzare l’analisi del canale di marketing, è preferibile utilizzare la funzione [Attribuzione](/help/analyze/analysis-workspace/attribution/overview.md) invece dell’attribuzione Canale di marketing esistente. Segui le altre best practice per garantire coerenza e solidi controlli sull’analisi con la funzione Attribuzione.

![](assets/attribution.png)

* La configurazione delle dimensioni Canale di marketing e Dettagli canale di marketing stabilisce i punti di contatto da valutare, corrispondenti a ogni istanza del canale di marketing.
* Per l’analisi delle metriche, l’organizzazione deve allinearsi a uno o più modelli di attribuzione. Salva le metriche personalizzate con questo modello per un facile riutilizzo.
* Per impostazione predefinita, i dati vengono assegnati utilizzando Ultimo contatto e l’impostazione Periodo di coinvolgimento del visitatore. I modelli di metriche di attribuzione offrono un maggiore controllo sulle finestre di lookback e una maggiore varietà, tra cui l’[attribuzione algoritmica](/help/analyze/analysis-workspace/attribution/algorithmic.md#analysis-workspace).

## Best practice n. 2: nessuna definizione dei canali Diretto e Aggiornamento sessione

Si consiglia di non utilizzare i canali Diretto e Interno/Aggiornamento sessione con modelli di attribuzione personalizzati.

Cosa succede se nella tua organizzazione sono già stati configurati i canali Diretto e Aggiornamento sessione? In questo caso, Adobe consiglia di [creare una classificazione](/help/admin/tools/manage-rs/edit-settings/marketing-channels/classifications-mchannel.md) per First Touch/Last Touch e lasciare i canali Direct e Session Refresh non classificati. La dimensione classificata produce risultati di attribuzione simili al caso in cui tali canali non sono mai stati configurati.

![](assets/direct-session-refresh.png)

Se disattivi questi canali e rimuovi le relative regole di elaborazione del canale di marketing, i risultati sono leggermente diversi dall’approccio di classificazione. Il valore `None` rappresenta le visite che non corrispondono ad alcuna regola di elaborazione del canale di marketing. Possono apparire differenze quando una visita che corrisponde a nessun canale segue una visita che corrisponde a un canale.

Puoi comunque utilizzare modelli di attribuzione personalizzati per applicare intervalli di lookback e modelli di attribuzione in entrambi i casi.

## Best practice n. 3: abilitare l’esclusione del canale di ultimo contatto per tutti i canali

I modelli di attribuzione personalizzati utilizzati con la dimensione Canale di marketing in Workspace funzionano meglio quando questa impostazione è abilitata. Quando questa impostazione è abilitata, un’istanza del canale di marketing viene conteggiata quando viene rilevato un nuovo canale o dettaglio. Abilita questa opzione per tutti i canali, a eccezione dei canali Diretto e Interno/Aggiornamento sessione, che non dovrebbero più essere utilizzati con modelli di attribuzione personalizzati.

![](assets/override.png)

## Best practice n. 4: ridurre al minimo il periodo di coinvolgimento dei visitatori

Se si imposta il periodo di coinvolgimento dei visitatori sul valore minimo di “1 giorno”, la probabilità di valori persistenti si riduce al minimo. Poiché i modelli di attribuzione personalizzati (AIQ) consentono finestre di lookback flessibili, si consiglia di impostare il valore minimo per ridurre al minimo l’impatto di questa impostazione.

![](assets/expiration.png)

## Best practice n. 5: le regole di elaborazione dei canali di marketing devono esistere solo per i canali abilitati

Assicurati di rimuovere tutte le regole di elaborazione dei canali di marketing per i canali disabilitati. Le regole devono esistere solo per i canali di marketing contrassegnati come abilitati.
