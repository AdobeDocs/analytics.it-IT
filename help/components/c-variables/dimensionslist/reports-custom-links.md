---
description: Visualizza i collegamenti preferiti dai visitatori del sito. Ad esempio, la home page del sito probabilmente contiene più collegamenti che visualizzano la stessa pagina. È possibile che sia presente un collegamento grafico che un collegamento testuale colleghino entrambi alla stessa pagina. Questo rapporto mostra la percentuale di visitatori che hanno utilizzato il collegamento grafico rispetto al collegamento di testo.
title: Collegamento personalizzato
topic: Reports
uuid: 2e0d0175-d5e4-4919-b601-3f488ef3e090
translation-type: tm+mt
source-git-commit: 3fe3442eae1bdd8b90acffc9c25d184714613c16

---


# Collegamento personalizzato

Visualizza i collegamenti preferiti dai visitatori del sito. Ad esempio, la home page del sito probabilmente contiene più collegamenti che visualizzano la stessa pagina. È possibile che sia presente un collegamento grafico che un collegamento testuale colleghino entrambi alla stessa pagina. Questo rapporto mostra la percentuale di visitatori che hanno utilizzato il collegamento grafico rispetto al collegamento di testo.

I collegamenti specifici che si desidera tracciare devono essere modificati con tag speciali, vedi Tracciamento [](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-linktrackvars.html)collegamenti.

È possibile utilizzare [!UICONTROL Custom Links Report] per:

* Ottimizzate la progettazione del sito conoscendo quali tipi di collegamenti preferite dai visitatori
* Convalida della necessità di collegamenti ridondanti a pagine singole

## Nomi di collegamenti SDK per dispositivi mobili {#section_70C91FE794104B5FBF289B19CC02EA8E}

Gli SDK per [dispositivi mobili](https://docs.adobe.com/content/help/it-IT/mobile-services/using/home.html) utilizzano collegamenti personalizzati per tenere traccia delle azioni e delle metriche del ciclo di vita. Nelle suite di rapporti utilizzate per misurare le app mobili, l’SDK potrebbe impostare i seguenti nomi di collegamento:

| ADBINTERNO:Ciclo Di Vita | Inviato dalla chiamata &quot;lifecycle&quot; negli SDK 4.x. |
|---|---|
| AMACTION:nome[azione] | Inviato dal metodo trackAction() negli SDK 4.x, dove action name è il nome impostato al momento della chiamata del metodo. |
| Evento ADMS BP | Inviato dalla chiamata &quot;lifecycle&quot; negli SDK 3.x. |

