---
description: La pagina Fatturazione consente di accedere alle informazioni di fatturazione, inclusi i dettagli di traffico per ogni suite di rapporti. Solo un amministratore autorizzato ha accesso a questa pagina.
title: Fatturazione
topic: Admin tools
uuid: ad6ee1c4-d317-4320-a36e-ee966c8f145e
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '496'
ht-degree: 2%

---


# Fatturazione

La pagina Fatturazione consente di accedere alle informazioni di fatturazione, inclusi i dettagli di traffico per ogni suite di rapporti. Solo un amministratore autorizzato ha accesso a questa pagina.

>[!NOTE]
>
>Se l&#39;accesso alla scheda di fatturazione è disattivato per la società, contattate l&#39;Account Manager.

I dati della panoramica del traffico dalla pagina di fatturazione consentono di correlare i dati della visualizzazione della pagina nei rapporti con le chiamate fatturabili server sulla fattura. The [!UICONTROL Billing] page lets you do the following:

* Controlla la fattura.
* Scomposizione dei costi per suite di rapporti per le allocazioni contabili interne.
* Visualizzare la distribuzione delle chiamate server primarie e secondarie.

La [!UICONTROL Billing] pagina organizza le informazioni per mese.

Per visualizzare i dati mensili sulla panoramica del traffico, individuare il mese in cui si desidera visualizzare i dati sul traffico, quindi fare clic **[!UICONTROL View]**.

Il [!UICONTROL Monthly Invoice] rapporto risultante include le informazioni seguenti:

| Colonna | Descrizione |
|--- |--- |
| Suite di rapporti | La suite di rapporti coinvolta nell&#39;attività di raccolta dati. |
| Posizione | Il centro dati che memorizza i dati della suite di rapporti: San Jose (California), Dallas (Texas), Pacific Northwest (USA), Londra (Regno Unito) o Singapore. Nella maggior parte dei casi, tutte le suite di rapporti aziendali si trovano nello stesso centro dati. |
| Chiamate server principali | Richieste ricevute direttamente dai browser dei visitatori del sito Web o dall’API di inserimento dati. Include gli hit principali (Visualizzazioni di pagina), gli eventi personalizzati principali, gli eventi di download principali e gli eventi di uscita principali. |
| Chiamate server secondarie | Copie di chiamate server primarie create da tag con più suite o copiate/spostate da una regola VISTA.  Se una chiamata server secondaria è stata spostata (non copiata) in una suite di rapporti diversa da una regola VISTA, la pagina Fatturazione identifica il trasferimento con un numero negativo. In questo caso, le chiamate secondarie accumulate vengono detratte dalle chiamate server primarie. |
| Totale chiamate server | Totale combinato delle chiamate al server primario e secondario per questa suite di rapporti nel percorso specificato. |
| Visualizzazioni pagina | Totali della visualizzazione pagina per ciascuna suite di rapporti. Potete confermare i valori di visualizzazione della pagina in Metriche del sito > Visualizzazioni pagina. |
| Download | Scarica totali per ogni suite di rapporti. Potete confermare i valori di download in Contenuto sito > Collegamenti > Download file. |
| Collegamenti personalizzati | Totali di collegamento personalizzati per ciascuna suite di rapporti. Potete confermare i valori dei collegamenti personalizzati in Contenuto sito > Collegamenti > Collegamenti personalizzati. |
| Esci dai collegamenti | Esci dai totali dei collegamenti per ogni suite di rapporti. Potete confermare i valori di collegamento di uscita in Contenuto sito > Collegamenti > Esci da collegamenti. |

>[!NOTE]
>
>Per ottenere una copia di lavoro del [!UICONTROL Monthly Invoice] rapporto, copiatela negli Appunti, quindi incollatela in un programma per fogli di calcolo come Microsoft Excel*.

## Data rapporto e data elaborazione {#section_51A48C2F223F4904BE1407C13333C457}

Nell&#39;interfaccia utente del reporting, i dati presentati sono sempre associati alla Data **del** rapporto, che è il timestamp associato all&#39;evento.

Utilizzo/Fatturazione, invece, utilizza sempre la Data **di** elaborazione, o quando i dati sono stati effettivamente elaborati nel sistema. A causa di latenza di base, importazioni di dati o differenze di fuso orario dell&#39;evento (tutto viene elaborato in Ora del Pacifico), la Data di reporting e la Data di elaborazione generalmente non corrispondono completamente.
