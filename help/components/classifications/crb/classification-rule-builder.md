---
description: Invece di mantenere e caricare le classificazioni ogni volta che i codici di tracciamento cambiano, puoi creare classificazioni automatiche basate su regole e applicarle su più suite di rapporti. Le regole vengono elaborate a intervalli frequenti, a seconda del volume di traffico correlato alla classificazione.
title: Flusso di lavoro di Generatore regole di classificazione
feature: Classifications
exl-id: cdb20dcc-0635-4d5e-9c54-f102d17a0a3d
source-git-commit: 8b1e25b9633b6db3e49da079f7014e6b7b595474
workflow-type: tm+mt
source-wordcount: '534'
ht-degree: 85%

---

# Panoramica del generatore di regole di classificazione (legacy)

{{classification-rulebuilder-deprecation}}

Invece di mantenere e caricare le classificazioni ogni volta che i codici di tracciamento cambiano, puoi creare classificazioni automatiche basate su regole e applicarle su più suite di rapporti. Le regole vengono elaborate a intervalli frequenti, a seconda del volume di traffico correlato alla classificazione.

>[!BEGINSHADEBOX]

Per un video dimostrativo, consulta ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Generatore regole di classificazione](https://experienceleague.adobe.com/it/docs/analytics-learn/tutorials/components/classifications/using-the-classification-rule-builder){target="_blank"}.

>[!ENDSHADEBOX]

## Avviso importante prima di iniziare

Tieni presente questi punti quando utilizzi le regole di classificazione:

* Puoi esportare fino a 10 milioni di righe alla volta.
* Quando il CRB richiede un’esportazione, richiama sia valori classificati che non classificati e i valori non classificati arrivano alla fine dell’esportazione. Ciò significa che, nel tempo, potresti riempire 10 milioni di righe con i valori classificati senza mai arrivare ai valori non classificati.
* Poiché l’architettura è impostata in modo che il CRB possa richiamare i valori da un numero “n” di server, ciò può portare a incongruenze su quali server vengono scelti e in quale ordine. Per questo motivo, è molto difficile arrivare ai valori non classificati.

Questa è la **soluzione alternativa** per coloro che hanno più di 10 milioni di valori classificati per una dimensione: sarà necessario esportare i valori non classificati tramite FTP, in batch da 10 milioni, e classificarli manualmente.

## Guida introduttiva alle regole di classificazione {#section_3FF666EF9D5B4E37A23B3FB400CDA2E6}

**[!UICONTROL Admin]** > **[!UICONTROL Classification Rule Builder]**

Di seguito sono riportati i passaggi di alto livello da effettuare per implementare le regole di classificazione:

| Passaggio | Dove viene eseguito | Descrizione |
|--- |--- |--- |
| Passaggio 1 (prerequisito): configurare lo schema di classificazione. | [!UICONTROL Admin] > [!UICONTROL Report Suites] > [!UICONTROL Edit Settings] > [!UICONTROL Traffic Classifications] o [!UICONTROL Conversion Classifications] | Scegli una variabile e definisci le classificazioni da utilizzare per tale variabile. <br>Prima di poter essere utilizzate nelle regole, le variabili devono avere almeno una colonna di classificazione.<br>Una volta abilitate le classificazioni, puoi utilizzare l’importazione e il generatore di regole per classificare valori specifici. |
| Passaggio 2: [creare un set di regole](classification-rule-set.md). | [!UICONTROL Admin] >  [!UICONTROL Classification Rule Builder] > [!UICONTROL Add Rule Set] | Un set di regole è un gruppo di regole di classificazione per una variabile specifica. |
| Passaggio 3: configurare suite di rapporti e variabili. | [!UICONTROL Classification Rule Builder] > &lt;set di regole> | Applica il set di regole alle suite di rapporti e alle variabili. |
| Passaggio 4: [aggiungere le regole di classificazione al set](classification-quickstart-rules.md). | [!UICONTROL Classification Rule Builder] > &lt;set di regole> | Associa una condizione a una classificazione, quindi specifica l’azione da intraprendere per la regola.  Fai riferimento alle informazioni in [Modalità di elaborazione delle regole](classification-quickstart-rules.md). |
| Passaggio 5: [testare un set di regole di classificazione](classification-quickstart-rules.md) | [!DNL Testing Page] | È necessario testare la convalida delle regole modificandole in modalità Bozza. Non è possibile eseguire le regole in modalità Bozza.<br>Questo passaggio è importante quando si utilizzano [espressioni regolari](classification-quickstart-rules.md). |
| Passaggio 6: [attivare le regole valide](classification-rule-definitions.md). | [!DNL Rules Page] | Quando le regole sono state rese valide, attiva il set di regole.  Puoi sovrascrivere le chiavi esistenti se necessario. Consulta [Modalità di elaborazione delle regole](classification-quickstart-rules.md). |
| Passaggio 7 (facoltativo): [eliminare le regole indesiderate](classification-rule-definitions.md). | [!DNL Rules Page] | Elimina le regole indesiderate da un set.<br>Nota: l&#39;eliminazione delle regole non comporta l&#39;eliminazione dei dati classificati caricati. Se devi eliminare i dati classificati, consulta [Elimina dati di classificazione](/help/components/classifications/importer/t-delete-classification-data.md). |

>[!NOTE]
>
>I gruppi con autorizzazioni per utilizzare lo strumento di importazione delle classificazioni possono utilizzare le regole di classificazione. Per informazioni importanti sull’elaborazione, vedi [Modalità di elaborazione delle regole](classification-quickstart-rules.md).

**Risorse aggiuntive**

**Blog**: per ulteriori informazioni su questa funzione, consulta l’articolo del blog di digital marketing [Classificazioni basate sulle regole](https://theblog.adobe.com/rule-based-classifications-part-1-making-classifications-easier/).

**Video**: visualizza il video [Panoramica classificazioni](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/components/classifications/overview-of-classifications.html).

