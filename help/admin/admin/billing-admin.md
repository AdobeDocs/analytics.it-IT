---
description: La pagina Fatturazione consente di accedere alle informazioni di fatturazione, inclusi i dettagli sul traffico per ogni suite di rapporti. Solo un amministratore autorizzato può accedere a questa pagina.
seo-description: La pagina Fatturazione consente di accedere alle informazioni di fatturazione, inclusi i dettagli sul traffico per ogni suite di rapporti. Solo un amministratore autorizzato può accedere a questa pagina.
seo-title: Fatturazione
solution: Analytics
title: Fatturazione
topic: Strumenti di amministrazione
uuid: ad 6 ee 1 c 4-d 317-4320-a 36 e-ee 966 c 8 f 145 e
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Fatturazione

La pagina Fatturazione consente di accedere alle informazioni di fatturazione, inclusi i dettagli sul traffico per ogni suite di rapporti. Solo un amministratore autorizzato può accedere a questa pagina.

>[!NOTE]
>
>Se l'accesso alla scheda di fatturazione è disabilitato per la società, contattate l'Account Manager.

I dati panoramica del traffico provenienti dalla pagina di fatturazione ti consentono di correlare i dati di visualizzazione delle pagine nei rapporti con chiamate fatturabili sulla fattura. [!UICONTROL Billing] La pagina consente di effettuare le seguenti operazioni:

* Controlla la fattura.
* Suddividere i costi per suite di rapporti per allocazione di contabilità interna.
* Visualizzare la distribuzione delle chiamate server primaria e secondaria.

[!UICONTROL Billing] La pagina organizza le informazioni per mese.

To view monthly traffic overview data, locate the month where you want to view traffic data, then click **[!UICONTROL View]**.

The resulting [!UICONTROL Monthly Invoice] report includes the following information:

| Colonna | Descrizione |
|--- |--- |
| Suite di rapporti | La suite di rapporti coinvolta nell'attività della raccolta dati. |
| Posizione | Il datacenter che archivia i dati della suite di rapporti: San Jose (California), Dallas (Texas), Pacifico Northwest (US), Londra (Regno Unito) o Singapore. Nella maggior parte dei casi, tutte le suite di rapporti della società si trovano nello stesso centro dati. |
| Chiamate server principale | Richieste ricevute direttamente dai browser dei visitatori del sito Web o dall'API di inserimento dati. Include Hit principali (Visualizzazioni pagina), Eventi personalizzati principali, Eventi di download principali e Exit Exit Events principali. |
| Chiamate server secondarie | Copie delle chiamate server principali create da tag multisuite o copiate/spostate da una regola VISTA. Se una chiamata server secondaria è stata spostata (non copiata) in una suite di rapporti diversa da una regola VISTA, la pagina Fatturazione identifica questo trasferimento con un numero negativo. In questo caso, le chiamate secondarie accumulate vengono deformate dalle chiamate server principali. |
| Chiamate server totali | Il totale combinato delle chiamate server primaria e secondaria per questa suite di rapporti nel percorso specificato. |
| Visualizzazioni pagina | Totali della visualizzazione della pagina per ogni suite di rapporti. Potete confermare i valori di visualizzazione della pagina in Metriche del sito &gt; Visualizzazioni pagina. |
| Download | Scarica i totali per ogni suite di rapporti. Potete confermare i valori di download in Contenuto sito &gt; Collegamenti &gt; Download file. |
| Collegamenti personalizzati | Totali di collegamento personalizzati per ogni suite di rapporti. Puoi confermare i valori di collegamento personalizzati in Contenuto sito &gt; Collegamenti &gt; Collegamenti personalizzati. |
| Uscita dai collegamenti | Esci dai totali del collegamento per ogni suite di rapporti. Potete confermare i valori di collegamento uscita in Contenuto sito &gt; Collegamenti &gt; Esci da collegamenti. |

>[!NOTE]
>
>To obtain a working copy of the [!UICONTROL Monthly Invoice] report, copy it onto your clipboard, then paste it into a spreadsheet program such as Microsoft Excel*.

## Reporting Date vs. Processing Date {#section_51A48C2F223F4904BE1407C13333C457}

In the reporting user interface, the data presented is always attached to the **Reporting Date**, which is the timestamp that is attached to the event.

Usage/Billing, on the other hand, always uses the **Processing Date**, or when the data was actually processed in the system. A causa della latenza di base, delle importazioni di dati o delle differenze di fuso orario (tutto viene elaborato in ora del Pacifico), la Data dei rapporti e la Data elaborazione in genere non corrispondono completamente.
