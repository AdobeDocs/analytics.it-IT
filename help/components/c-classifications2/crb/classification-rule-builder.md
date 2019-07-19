---
description: Invece di mantenere e caricare classificazioni ogni volta che i codici di monitoraggio cambiano, puoi creare classificazioni automatiche basate su regole e applicarle tra più suite di rapporti. Le regole vengono elaborate a intervalli frequenti, a seconda del volume di traffico correlato.
seo-description: Invece di mantenere e caricare classificazioni ogni volta che i codici di monitoraggio cambiano, puoi creare classificazioni automatiche basate su regole e applicarle tra più suite di rapporti. Le regole vengono elaborate a intervalli frequenti, a seconda del volume di traffico correlato.
seo-title: Flusso di lavoro di Generatore regole di classificazione
solution: Analytics
subtopic: Classificazioni
title: Flusso di lavoro di Generatore regole di classificazione
topic: Strumenti di amministrazione
uuid: edb 1 f 07 e-fa 86-4055-8 f 4 b-cce 2 d 370 edbb
translation-type: tm+mt
source-git-commit: e71c24fa4762d7f0bc80fc7133ca1cd79dfaf7c5

---


# Flusso di lavoro di Generatore regole di classificazione

Invece di mantenere e caricare classificazioni ogni volta che i codici di monitoraggio cambiano, puoi creare classificazioni automatiche basate su regole e applicarle tra più suite di rapporti. Le regole vengono elaborate a intervalli frequenti, a seconda del volume di traffico correlato.

## Avviso importante prima di iniziare

Tenetela presente prima di iniziare a utilizzare le regole di classificazione:

* Il sistema di classificazione corrente può esportare fino a 10 milioni di righe alla volta.
* Quando il generatore di regole di classificazione (CRB) richiede un'esportazione, estrae entrambi i valori E non classificati, con valori non classificati che entrano alla fine dell'esportazione. Questo significa che, nel tempo, potete riempire 10 milioni di valori classificati, senza passare mai ai valori non classificati.
* Poiché l'architettura è configurata in modo che CRB venga richiamata dal numero «n» di server, questo può portare a incongruenze rispetto alla selezione dei server e all'ordine. Per tale ragione, è molto difficile ottenere valori non classificati.

This is the **workaround** for those who have more than 10 million classified values for a dimension: You will need to export unclassified values via FTP, in 10-million batches, and manually classify them.

## Getting Started with Classification Rules {#section_3FF666EF9D5B4E37A23B3FB400CDA2E6}

**[!UICONTROL Admin]** &gt; **[!UICONTROL Classification Rule Builder]**

Di seguito sono descritti i passaggi di alto livello per implementare le regole di classificazione:

| Passaggio | Dove eseguire | Descrizione |
|--- |--- |--- |
| Step 1 (Prerequisite): [Set up your classification schema](https://marketing.adobe.com/resources/help/en_US/reference/?f=c_classifications). | [!UICONTROL Admin] &gt; [!UICONTROL Report Suites] &gt; [!UICONTROL Edit Settings] &gt; &lt; Classificazioni traffico o Classificazioni conversione &gt; | Scegliete una variabile e definite le classificazioni da utilizzare per quella variabile. <br>Le variabili devono avere almeno una colonna di classificazione creata prima che siano disponibili per l'uso nelle regole.<br>Una volta abilitate le classificazioni, potete usare l'importazione e il generatore di regole per classificare valori specifici. |
| Step 2: [Create a rule set](../../../components/c-classifications2/crb/classification-rule-set.md). | [!UICONTROL Admin] &gt;  [!UICONTROL Classification Rule Builder] &gt; [!UICONTROL Add Rule Set] | Un set di regole è un gruppo di regole di classificazione per una variabile specifica. |
| Passaggio 3: Configura suite di rapporti e variabili. | [!UICONTROL Classification Rule Builder] &gt; &lt; set regola &gt; | Applica la regola impostata sulle suite di rapporti e sulle variabili. |
| Step 4: [Add classification rules to the set](../../../components/c-classifications2/crb/classification-quickstart-rules.md). | [!UICONTROL Classification Rule Builder] &gt; &lt; set regola &gt; | Adattare una condizione a una classificazione e specificare l'azione da intraprendere per la regola. Be familiar with the information in  [How Rules Are Processed](../../../components/c-classifications2/crb/classification-quickstart-rules.md). |
| Step 5: [Test a Classification Rule Set](../../../components/c-classifications2/crb/classification-quickstart-rules.md) | [!DNL Testing Page] | Per verificare le regole per la convalida, modificarle in modalità Bozza. In modalità Bozza, le regole non possono essere eseguite.<br>Questo passaggio è importante quando si utilizzano [espressioni regolari](../../../components/c-classifications2/crb/classification-quickstart-rules.md). |
| Step 6: [Activate valid rules](../../../components/c-classifications2/crb/classification-rule-definitions.md). | [!DNL Rules Page] | Una volta applicate le regole, attivate il set di regole. Se necessario, potete sovrascrivere le chiavi esistenti. See [How Rules Are Processed](../../../components/c-classifications2/crb/classification-quickstart-rules.md). |
| Step 7 (Optional): [Delete unwanted rules](../../../components/c-classifications2/crb/classification-rule-definitions.md). | [!DNL Rules Page] | Elimina regole indesiderate da un set.<br>Nota: L'eliminazione delle regole non comporta l'eliminazione dei dati classificati caricati. See  [Delete classification data](../../../components/c-classifications2/c-classifications-importer/t-delete-classification-data.md) if you need to delete classified data. |

>[!NOTE]
>
>I gruppi con autorizzazioni per utilizzare lo strumento di importazione di classificazione possono utilizzare le regole di classificazione. See [How Rules Are Processed](../../../components/c-classifications2/crb/classification-quickstart-rules.md) for important processing information.

**Risorse aggiuntive**

**Blog**: Per ulteriori informazioni su questa funzione, consultate il blog di Digital Marketing: [Classificazioni basate su regole](https://blogs.adobe.com/digitalmarketing/analytics/rule-based-classifications-part-1-making-classifications-easier/?utm_source=feedburner&utm_medium=feed&utm_campaign=Feed%3A+AdobeDigitalMarketing+%28Adobe+Digital+Marketing+Blog%29).

**Video**: Per [visualizzare il video,](https://www.youtube.com/watch?v=6laI5SBXY-I) visita [!UICONTROL Classifications Overview] YouTube.
