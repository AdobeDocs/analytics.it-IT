---
description: Invece di mantenere e caricare le classificazioni ogni volta che i codici di tracciamento cambiano, puoi creare classificazioni automatiche basate su regole e applicarle su più suite di rapporti. Le regole vengono elaborate a intervalli frequenti, a seconda del volume di traffico correlato alla classificazione.
subtopic: Classifications
title: Flusso di lavoro di Generatore regole di classificazione
feature: Strumenti di amministrazione
uuid: edb1f07e-fa86-4055-8f4b-cce2d370edbb
exl-id: cdb20dcc-0635-4d5e-9c54-f102d17a0a3d
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '554'
ht-degree: 97%

---

# Flusso di lavoro di Generatore regole di classificazione

Invece di mantenere e caricare le classificazioni ogni volta che i codici di tracciamento cambiano, puoi creare classificazioni automatiche basate su regole e applicarle su più suite di rapporti. Le regole vengono elaborate a intervalli frequenti, a seconda del volume di traffico correlato alla classificazione.

## Avviso importante prima di iniziare

Tieni presente i punti seguenti prima di iniziare a utilizzare le regole di classificazione:

* Le sottoclassificazioni non sono supportate nel Generatore di regole di classificazione (CRB).
* Il nostro sistema di classificazione attuale può esportare solo fino a 10 milioni di righe alla volta.
* Quando il CRB richiede un’esportazione, richiama sia valori classificati che non classificati e i valori non classificati arrivano alla fine dell’esportazione. Ciò significa che, nel tempo, potresti riempire 10 milioni di righe con i valori classificati senza mai arrivare ai valori non classificati.
* Poiché l’architettura è impostata in modo che il CRB possa richiamare i valori da un numero “n” di server, ciò può portare a incongruenze su quali server vengono scelti e in quale ordine. Per questo motivo, è molto difficile arrivare ai valori non classificati.

Questa è la **soluzione alternativa** per coloro che hanno più di 10 milioni di valori classificati per una dimensione: sarà necessario esportare i valori non classificati tramite FTP, in batch da 10 milioni, e classificarli manualmente.

## Guida introduttiva alle regole di classificazione {#section_3FF666EF9D5B4E37A23B3FB400CDA2E6}

**[!UICONTROL Admin]** > **[!UICONTROL Classification Rule Builder]**

Di seguito sono riportati i passaggi di alto livello da effettuare per implementare le regole di classificazione:

| Passaggio | Dove viene eseguito | Descrizione |
|--- |--- |--- |
| Passaggio 1 (prerequisito): [configurare lo schema di classificazione](https://docs.adobe.com/content/help/it-IT/analytics/components/classifications/c-classifications.html). | [!UICONTROL Admin] > [!UICONTROL Report Suites] > [!UICONTROL Edit Settings] > &lt;Classificazioni di traffico o conversione> | Scegli una variabile e definisci le classificazioni da utilizzare per tale variabile. <br>Prima di poter essere utilizzate nelle regole, le variabili devono avere almeno una colonna di classificazione.<br>Una volta abilitate le classificazioni, puoi utilizzare l’importazione e il generatore di regole per classificare valori specifici. |
| Passaggio 2: [creare un set di regole](/help/components/classifications/crb/classification-rule-set.md). | [!UICONTROL Admin] >  [!UICONTROL Classification Rule Builder] > [!UICONTROL Add Rule Set] | Un set di regole è un gruppo di regole di classificazione per una variabile specifica. |
| Passaggio 3: configurare suite di rapporti e variabili. | [!UICONTROL Classification Rule Builder] > &lt;set di regole> | Applica il set di regole alle suite di rapporti e alle variabili. |
| Passaggio 4: [aggiungere le regole di classificazione al set](/help/components/classifications/crb/classification-quickstart-rules.md). | [!UICONTROL Classification Rule Builder] > &lt;set di regole> | Associa una condizione a una classificazione, quindi specifica l’azione da intraprendere per la regola.  Fai riferimento alle informazioni in [Modalità di elaborazione delle regole](/help/components/classifications/crb/classification-quickstart-rules.md). |
| Passaggio 5: [testare un set di regole di classificazione](/help/components/classifications/crb/classification-quickstart-rules.md) | [!DNL Testing Page] | È necessario testare la convalida delle regole modificandole in modalità Bozza. Non è possibile eseguire le regole in modalità Bozza.<br>Questo passaggio è importante quando si utilizzano [espressioni regolari](/help/components/classifications/crb/classification-quickstart-rules.md). |
| Passaggio 6: [attivare le regole valide](/help/components/classifications/crb/classification-rule-definitions.md). | [!DNL Rules Page] | Quando le regole sono state rese valide, attiva il set di regole.  Puoi sovrascrivere le chiavi esistenti se necessario. Consulta [Modalità di elaborazione delle regole](/help/components/classifications/crb/classification-quickstart-rules.md). |
| Passaggio 7 (facoltativo): [eliminare le regole indesiderate](/help/components/classifications/crb/classification-rule-definitions.md). | [!DNL Rules Page] | Elimina le regole indesiderate da un set.<br>Nota: l’eliminazione delle regole non comporta l’eliminazione dei dati classificati caricati.  Se hai necessità di eliminare i dati classificati, consulta [Eliminare i dati di classificazione](/help/components/classifications/importer/t-delete-classification-data.md). |

>[!NOTE]
>
>I gruppi con autorizzazioni per utilizzare lo strumento di importazione delle classificazioni possono utilizzare le regole di classificazione. Per informazioni importanti sull’elaborazione, vedi [Modalità di elaborazione delle regole](/help/components/classifications/crb/classification-quickstart-rules.md).

**Risorse aggiuntive**

**Blog**: per ulteriori informazioni su questa funzione, consulta l’articolo del blog di digital marketing [Classificazioni basate sulle regole](https://theblog.adobe.com/rule-based-classifications-part-1-making-classifications-easier/).

**Video**: Visualizza il video  [Classificazioni ](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/components/classifications/overview-of-classifications.html) generali.
