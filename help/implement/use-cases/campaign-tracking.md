---
title: Flusso di lavoro di tracciamento delle campagne
description: Utilizza Adobe Analytics per tenere traccia delle tue attività di marketing.
feature: Implementation Basics
exl-id: 9f7920e0-471c-46bc-9314-7b0a7c93fdce
source-git-commit: c118d42667c4a1af55929834b87d148a5973bed9
workflow-type: tm+mt
source-wordcount: '579'
ht-degree: 0%

---

# Flusso di lavoro di tracciamento delle campagne

Se la tua organizzazione desidera tenere traccia delle prestazioni e del tasso di click-through delle attività di marketing, puoi utilizzare la seguente procedura. Ognuno di questi passaggi dispone di sezioni dedicate qui sotto che contengono maggiori dettagli.

1. [Stabilire un processo di generazione del codice di tracciamento](#establish-a-tracking-code-generation-process)
1. [Aggiungi il codice di tracciamento desiderato all’e-mail](#add-the-desired-tracking-code-to-the-email)
1. [Imposta o regola l’implementazione Adobe Analytics per includere i dati del codice di tracciamento](#include-campaign-variables-in-your-implementation)
1. [Visualizzare i rapporti in Analysis Workspace](#view-the-reports-in-analysis-workspace)

[Adobe Campaign](https://business.adobe.com/products/campaign/adobe-campaign.html) può contribuire a semplificare ciascuno di questi passaggi per sfruttare al massimo il valore delle tue attività di marketing. Per ulteriori informazioni, contatta il tuo rappresentante commerciale Adobe.

## Stabilire un processo di generazione del codice di tracciamento

Ogni organizzazione ha esigenze diverse per i codici di tracciamento. Alcune organizzazioni potrebbero avere esigenze minime in cui i codici di tracciamento creati manualmente sono più che sufficienti. Altre organizzazioni potrebbero volere un maggiore controllo sul tracciamento e disporre di più sistemi per creare i codici di tracciamento desiderati. Se l’organizzazione utilizza Google Analytics oltre ad Adobe Analytics, è possibile che nell’organizzazione sia già presente un `utm` modello di codice di tracciamento stabilito.

Indipendentemente da come scegli di creare o generare codici di tracciamento, l’attivazione di un sistema coerente consente alla tua organizzazione di disporre di un tempo molto più semplice quando desideri raggruppare i codici di tracciamento per il reporting. Codici di tracciamento strutturati in modo coerente consentono di creare [Regole di classificazione](/help/components/classifications/crb/classification-rule-builder.md) per ottenere informazioni sulle prestazioni categoriche.

## Aggiungi il codice di tracciamento desiderato a un URL

Una volta ottenuto il valore desiderato per il codice di tracciamento, puoi aggiungerlo a qualsiasi collegamento pubblicato online, ad esempio annunci pubblicitari, social media o e-mail. L’aggiunta di questi codici di tracciamento avviene in genere nella stringa di query di un collegamento. Il parametro della stringa di query utilizzato dipende dai requisiti di tracciamento della tua organizzazione; un parametro di stringa di query comune è `cid` (breve per ID campagna). Alcune organizzazioni che utilizzano anche Google Analytics potrebbero avere già più parametri di stringa della query della campagna come `utm_source`, `utm_medium`e altri.

L’aggiunta di stringhe di query a un collegamento in un messaggio e-mail avrà un aspetto simile al seguente:

```text
https://example.com?cid=EM989027
```

## Includere le variabili di campagna nell’implementazione

Adobe Analytics ha un [Codice di tracciamento](/help/components/dimensions/tracking-code.md) che puoi utilizzare per misurare diverse attività di marketing all’interno della tua organizzazione. Tuttavia, organizzazioni diverse possono avere requisiti di tracciamento diversi. È importante fare riferimento a [Documento di progettazione della soluzione](../prepare/solution-design.md) per tenere traccia in modo coerente dei valori corretti nelle variabili corrette.

Se la tua organizzazione non ha ancora configurato il tracciamento della campagna, puoi regolare la tua implementazione per impostare la [`campaign`](/help/implement/vars/page-vars/campaign.md) variabile. Consulta la sezione [`getQueryParam`](/help/implement/vars/plugins/getqueryparam.md) per scoprire come raccogliere i valori dei parametri della stringa di query specifici per l&#39;implementazione della tua organizzazione.

Se l’organizzazione raccoglie `utm` stringhe di query, puoi scegliere di:

* Invia tutto `utm` cerca le stringhe nella dimensione Codice di tracciamento come valori concatenati. È quindi possibile utilizzare [Regole di classificazione](/help/components/classifications/crb/classification-rule-builder.md) per creare dimensioni aggiuntive per ciascuna `utm` parametro . Questo metodo ha una curva di apprendimento più complessa, ma non utilizza eVar aggiuntivi.
* Invia ogni `utm` stringa query in un&#39;altra [eVar](/help/components/dimensions/evar.md). Questo metodo è più semplice da implementare nel complesso, ma richiede l’utilizzo di eVar aggiuntivi.

## Visualizzare i rapporti in Analysis Workspace

Una volta impostata correttamente l’implementazione per raccogliere i dati del codice di tracciamento, puoi visualizzare i rapporti in Analysis Workspace.

1. Accedi a [Adobe Experience Cloud](https://experience.adobe.com) e seleziona [!UICONTROL Adobe Analytics].
1. Crea un [Progetto Workspace](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md).
1. Nell’elenco dei componenti a sinistra, trascina la [Codice di tracciamento](/help/components/dimensions/tracking-code.md) nell’area di lavoro.
1. Trascina la metrica desiderata, ad esempio [Visite](/help/components/metrics/visits.md) o [Ordini](/help/components/metrics/orders.md) sul lato destro dell’area di lavoro.

![Rapporto di tracciamento delle campagne](../assets/campaign-tracking-report.png)
