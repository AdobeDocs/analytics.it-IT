---
description: Invece di mantenere e caricare le classificazioni ogni volta che i codici di monitoraggio cambiano, puoi creare classificazioni automatiche basate su regole e applicarle su più suite di rapporti.  Le regole vengono elaborate a intervalli frequenti, a seconda del volume di traffico correlato alla classificazione.
seo-description: Invece di mantenere e caricare le classificazioni ogni volta che i codici di monitoraggio cambiano, puoi creare classificazioni automatiche basate su regole e applicarle su più suite di rapporti. Le regole vengono elaborate a intervalli frequenti, a seconda del volume di traffico correlato alla classificazione.
seo-title: Flusso di lavoro di Generatore regole di classificazione
solution: Analytics
subtopic: Classificazioni
title: Flusso di lavoro di Generatore regole di classificazione
topic: Strumenti di amministrazione
uuid: edb1f07e-fa86-4055-8f4b-cce2d370edbb
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# Flusso di lavoro di Generatore regole di classificazione

Invece di mantenere e caricare le classificazioni ogni volta che i codici di monitoraggio cambiano, puoi creare classificazioni automatiche basate su regole e applicarle su più suite di rapporti.  Le regole vengono elaborate a intervalli frequenti, a seconda del volume di traffico correlato alla classificazione.

## Avviso importante prima di iniziare

Ricordate questo prima di iniziare a utilizzare le regole di classificazione:

* Il nostro attuale sistema di classificazione può esportare solo fino a 10 milioni di righe alla volta.
* Quando un Generatore di regole di classificazione (CRB) richiede un'esportazione, richiama sia valori classificati AND non classificati, con valori non classificati che arrivano alla fine dell'esportazione. Ciò significa che, nel tempo, si potrebbe riempire 10 milioni di valori classificati - senza mai arrivare ai valori non classificati.
* Poiché l'architettura è impostata in modo che CRB possa essere estratto dal numero "n" di server, ciò può portare a incoerenze su quali server vengono raccolti e in quale ordine. Per questo motivo, è molto difficile arrivare a valori non classificati.

Questa è la **soluzione alternativa** per coloro che hanno più di 10 milioni di valori classificati per una dimensione: Sarà necessario esportare valori non classificati tramite FTP, in 10 milioni di batch, e classificarli manualmente.

## Guida introduttiva alle regole di classificazione {#section_3FF666EF9D5B4E37A23B3FB400CDA2E6}

**[!UICONTROL Admin]** &gt; **[!UICONTROL Classification Rule Builder]**

Di seguito sono riportati i passaggi di alto livello da effettuare per implementare le regole di classificazione:

| Passaggio | Dove eseguito | Descrizione |
|--- |--- |--- |
| Passaggio 1 (prerequisito): [Configurare lo schema](https://marketing.adobe.com/resources/help/en_US/reference/c_classifications.html)di classificazione. | [!UICONTROL Admin] &gt; [!UICONTROL Report Suites] &gt; [!UICONTROL Edit Settings] &gt; &lt;Classificazioni traffico o classificazioni conversione&gt; | Scegliete una variabile e definite le classificazioni da utilizzare per tale variabile. <br>Prima di poter essere utilizzate nelle regole, le variabili devono avere almeno una colonna di classificazione.<br>Una volta abilitate le classificazioni, potete utilizzare l'utilità di importazione e il generatore di regole per classificare valori specifici. |
| Passaggio 2: [Creare un set](../../../components/c-classifications2/crb/classification-rule-set.md)di regole. | [!UICONTROL Admin] &gt;  [!UICONTROL Classification Rule Builder] &gt; [!UICONTROL Add Rule Set] | Un set di regole è un gruppo di regole di classificazione per una specifica variabile. |
| Passaggio 3: Configurare suite di rapporti e variabili. | [!UICONTROL Classification Rule Builder] &gt; &lt;set di regole&gt; | Applica il set di regole alle suite di rapporti e alle variabili. |
| Passaggio 4: [Aggiungere regole di classificazione al set](../../../components/c-classifications2/crb/classification-quickstart-rules.md). | [!UICONTROL Classification Rule Builder] &gt; &lt;set di regole&gt; | Associare una condizione a una classificazione, quindi specificare l'azione da intraprendere per la regola.  Conoscere le informazioni in [Modalità di elaborazione](../../../components/c-classifications2/crb/classification-quickstart-rules.md)delle regole. |
| Passaggio 5: [Test di un set di regole di classificazione](../../../components/c-classifications2/crb/classification-quickstart-rules.md) | [!DNL Testing Page] | È necessario verificare le regole per la convalida modificandole in modalità Bozza. In modalità Bozza non è possibile eseguire le regole.<br>Questo passaggio è importante quando si utilizzano le espressioni [](../../../components/c-classifications2/crb/classification-quickstart-rules.md)regolari. |
| Passaggio 6: [Attiva regole](../../../components/c-classifications2/crb/classification-rule-definitions.md)valide. | [!DNL Rules Page] | Una volta che le regole sono valide, attivare il set di regole.  You can overwrite existing keys, if necessary. See How Rules Are Processed.[](../../../components/c-classifications2/crb/classification-quickstart-rules.md) |
| Passaggio 7 (facoltativo): [Eliminare le regole](../../../components/c-classifications2/crb/classification-rule-definitions.md)indesiderate. | [!DNL Rules Page] | Eliminare le regole indesiderate da un set.<br>Nota:  L'eliminazione delle regole non comporta l'eliminazione dei dati classificati caricati.  Per eliminare i dati classificati, vedere [Eliminare i dati](../../../components/c-classifications2/c-classifications-importer/t-delete-classification-data.md) di classificazione. |

>[!NOTE]
>
>I gruppi con autorizzazioni per utilizzare lo strumento di importazione classificazione possono utilizzare le regole di classificazione. Per informazioni importanti sull'elaborazione, vedere [Elaborazione](../../../components/c-classifications2/crb/classification-quickstart-rules.md) delle regole.

**Risorse aggiuntive**

**Blog**: Per ulteriori informazioni su questa funzione, consultate Digital Marketing Blog: Classificazioni [basate su](https://blogs.adobe.com/digitalmarketing/analytics/rule-based-classifications-part-1-making-classifications-easier/?utm_source=feedburner&utm_medium=feed&utm_campaign=Feed%3A+AdobeDigitalMarketing+%28Adobe+Digital+Marketing+Blog%29)regole.

**Video**: Visitate [YouTube](https://www.youtube.com/watch?v=6laI5SBXY-I) per visualizzare il [!UICONTROL Classifications Overview] video.
