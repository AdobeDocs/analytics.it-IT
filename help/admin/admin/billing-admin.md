---
description: La pagina Fatturazione ti consente di accedere alle informazioni di fatturazione, inclusi i dettagli del traffico per ogni suite di rapporti. Solo un amministratore autorizzato ha accesso a questa pagina.
title: Fatturazione
feature: Admin Tools
exl-id: cea802e4-99c4-491e-99c2-8476870001f7
source-git-commit: 2c0aef13bdb88b0a7aa9f100c72c21f66a14c8dd
workflow-type: tm+mt
source-wordcount: '496'
ht-degree: 2%

---

# Fatturazione

La pagina Fatturazione ti consente di accedere alle informazioni di fatturazione, inclusi i dettagli del traffico per ogni suite di rapporti. Solo un amministratore autorizzato ha accesso a questa pagina.

>[!NOTE]
>
>Se l&#39;accesso alla scheda di fatturazione è disabilitato per la tua azienda, contatta il tuo Account Manager.

I dati della panoramica del traffico della pagina di fatturazione consentono di correlare i dati della visualizzazione della pagina nei rapporti con le chiamate al server fatturabili sulla fattura. La [!UICONTROL Billing] consente di effettuare le seguenti operazioni:

* Controlla la fattura.
* Suddividi i costi per suite di rapporti per le allocazioni contabili interne.
* Visualizza la distribuzione delle chiamate server primarie e secondarie.

La [!UICONTROL Billing] organizza le informazioni per mese.

Per visualizzare i dati mensili sulla panoramica del traffico, individua il mese in cui desideri visualizzare i dati sul traffico, quindi fai clic su **[!UICONTROL View]**.

Il risultato [!UICONTROL Monthly Invoice] il rapporto include le seguenti informazioni:

| Colonna | Descrizione |
|--- |--- |
| Suite di rapporti | La suite di rapporti coinvolta nell’attività di raccolta dati. |
| Posizione | Il data center che memorizza i dati della suite di rapporti: San Jose (California), Dallas (Texas), Pacific Northwest (USA), Londra (Regno Unito) o Singapore. Nella maggior parte dei casi, tutte le suite di rapporti aziendali si trovano nello stesso centro dati. |
| Chiamate server principali | Richieste ricevute direttamente dai browser visitatori del sito web o dall’API di inserimento dati. Include gli hit principali (visualizzazioni pagina), gli eventi personalizzati principali, gli eventi di download principali e gli eventi di uscita principali. |
| Chiamate server secondarie | Copie delle chiamate server principali create da tag con più suite o copiate/spostate da una regola VISTA.  Se una chiamata server secondaria è stata spostata (non copiata) in una suite di rapporti diversa da una regola VISTA, la pagina Fatturazione identifica questo trasferimento con un numero negativo. In questo caso, le chiamate secondarie accumulate vengono detratte dalle chiamate server principali. |
| Chiamate server totali | Totale combinato delle chiamate al server primario e secondario per questa suite di rapporti nella posizione specificata. |
| Visualizzazioni pagina | Visualizza la pagina i totali per ogni suite di rapporti. Puoi confermare i valori di visualizzazione della pagina in Metriche del sito > Visualizzazioni pagina. |
| Download | Scarica i totali per ogni suite di rapporti. Puoi confermare i valori di download in Contenuto sito > Collegamenti > Download file. |
| Collegamenti personalizzati | Totali di collegamento personalizzati per ogni suite di rapporti. Puoi confermare i valori dei collegamenti personalizzati in Contenuto sito > Collegamenti > Collegamenti personalizzati. |
| Esci dai collegamenti | Esci dai totali dei collegamenti per ogni suite di rapporti. Puoi confermare i valori dei collegamenti di uscita in Contenuto sito > Collegamenti > Esci da collegamenti. |

>[!NOTE]
>
>Per ottenere una copia di lavoro del [!UICONTROL Monthly Invoice] crea un rapporto, copialo negli Appunti, quindi incollalo in un programma per fogli di calcolo come Microsoft Excel*.

## Data di reporting e data di elaborazione {#section_51A48C2F223F4904BE1407C13333C457}

Nell’interfaccia utente di reporting, i dati presentati sono sempre collegati al **Data di segnalazione**, che è la marca temporale associata all’evento.

Utilizzo/Fatturazione, invece, utilizza sempre il **Data di elaborazione** oppure quando i dati sono stati effettivamente elaborati nel sistema. A causa della latenza di base, delle importazioni di dati o delle differenze di fuso orario dell’evento (tutto viene elaborato in Pacific Time), la data di reporting e la data di elaborazione in genere non corrispondono completamente.
