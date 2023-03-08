---
description: La pagina Fatturazione consente di accedere alle informazioni di fatturazione, inclusi i dettagli del traffico per ogni suite di rapporti. Solo un amministratore autorizzato ha accesso a questa pagina.
title: Fatturazione
feature: Admin Tools
exl-id: cea802e4-99c4-491e-99c2-8476870001f7
source-git-commit: b8640d1387a475e2a9dd082759f0514bd18c1b6e
workflow-type: tm+mt
source-wordcount: '496'
ht-degree: 8%

---

# Fatturazione

La pagina Fatturazione consente di accedere alle informazioni di fatturazione, inclusi i dettagli del traffico per ogni suite di rapporti. Solo un amministratore autorizzato ha accesso a questa pagina.

>[!NOTE]
>
>Se l’accesso alla scheda di fatturazione è disabilitato per la tua azienda, contatta il tuo Account Manager.

I dati di panoramica del traffico dalla pagina di fatturazione consentono di correlare i dati di visualizzazione della pagina nei rapporti con chiamate al server fatturabili nella fattura. Il [!UICONTROL Billing] pagina consente di effettuare le seguenti operazioni:

* Controlla la fattura.
* Suddividere i costi per suite di rapporti per allocazioni contabili interne.
* Visualizzare la distribuzione delle chiamate al server primarie e secondarie.

Il [!UICONTROL Billing] pagina organizza le informazioni per mese.

Per visualizzare i dati mensili di panoramica del traffico, individua il mese in cui desideri visualizzare i dati del traffico, quindi fai clic su **[!UICONTROL View]**.

Il risultato [!UICONTROL Monthly Invoice] Il rapporto include le seguenti informazioni:

| Colonna | Descrizione |
|--- |--- |
| Suite di rapporti | La suite di rapporti coinvolta nell’attività di raccolta dati. |
| Posizione | Il data center che memorizza i dati della suite di rapporti: San Jose (California), Dallas (Texas), Pacifico nord-occidentale (Stati Uniti), Londra (Regno Unito) o Singapore. Nella maggior parte dei casi, tutte le suite di rapporti aziendali si trovano nello stesso centro dati. |
| Chiamate server primarie | Richieste ricevute direttamente dai browser dei visitatori del sito web o dall’API di inserimento dati. Include gli hit primari (visualizzazioni di pagina), gli eventi personalizzati primari, gli eventi di download primari e gli eventi di uscita primari. |
| Chiamate server secondarie | Copie delle chiamate al server primarie create da tag multisuite o copiate/spostate da una regola VISTA.  Se una chiamata al server secondaria è stata spostata (non copiata) in una suite di rapporti diversa da una regola VISTA, la pagina Fatturazione identifica questo trasferimento con un numero negativo. In questo caso, le chiamate secondarie accumulate vengono detratte dalle chiamate al server primarie. |
| Totale chiamate server | Totale combinato delle chiamate al server primarie e secondarie per questa suite di rapporti nella posizione specificata. |
| Visualizzazioni pagina | Totali nella visualizzazione pagina per ogni suite di rapporti. Puoi confermare i valori di visualizzazione della pagina in Metriche del sito > Visualizzazioni pagina. |
| Download | Scarica i totali per ogni suite di rapporti. Puoi confermare i valori di download in Contenuto sito > Collegamenti > Download dei file. |
| Collegamenti personalizzati | Totali dei collegamenti personalizzati per ogni suite di rapporti. Puoi confermare i valori dei collegamenti personalizzati in Contenuto sito > Collegamenti > Collegamenti personalizzati. |
| Esci dai collegamenti | Totali dei collegamenti di uscita per ogni suite di rapporti. Puoi confermare i valori del collegamento di uscita in Contenuto sito > Collegamenti > Collegamenti di uscita. |

>[!NOTE]
>
>Per ottenere una copia di lavoro del [!UICONTROL Monthly Invoice] report, copiarlo negli Appunti, quindi incollarlo in un foglio di calcolo come Microsoft Excel&#42;.

## Data di reporting e data di elaborazione {#section_51A48C2F223F4904BE1407C13333C457}

Nell’interfaccia utente di reporting, i dati presentati sono sempre allegati al **Data rapporto**, che è la marca temporale associata all’evento.

Uso/Fatturazione, invece, utilizza sempre **Data di elaborazione** o quando i dati sono stati effettivamente elaborati nel sistema. A causa della latenza di base, delle importazioni di dati o delle differenze di fuso orario degli eventi (tutto viene elaborato in Ora del Pacifico), la Data di reporting e la Data di elaborazione in genere non corrispondono completamente.
