---
description: Invece di mantenere e caricare le classificazioni ogni volta che i codici di monitoraggio cambiano, puoi creare classificazioni automatiche basate su regole e applicarle su più suite di rapporti. Le regole vengono elaborate a intervalli frequenti, a seconda del volume di traffico correlato alla classificazione.
subtopic: Classifications
title: Flusso di lavoro di Generatore regole di classificazione
topic: Admin tools
uuid: edb1f07e-fa86-4055-8f4b-cce2d370edbb
translation-type: tm+mt
source-git-commit: 0870ace3fea8e3ef650d2de2960006a0d655cf9f
workflow-type: tm+mt
source-wordcount: '549'
ht-degree: 2%

---


# Flusso di lavoro di Generatore regole di classificazione

Invece di mantenere e caricare le classificazioni ogni volta che i codici di monitoraggio cambiano, puoi creare classificazioni automatiche basate su regole e applicarle su più suite di rapporti. Le regole vengono elaborate a intervalli frequenti, a seconda del volume di traffico correlato alla classificazione.

## Avviso importante prima di iniziare

Tenete presente questo aspetto prima di iniziare a utilizzare le regole di classificazione:

* Le sottocategorie non sono supportate con Generatore regole di classificazione (CRB).
* Il nostro attuale sistema di classificazione può esportare solo fino a 10 milioni di righe alla volta.
* Quando CRB richiede un&#39;esportazione, richiama sia valori classificati che non classificati, con valori non classificati che arrivano alla fine dell&#39;esportazione. Ciò significa che, nel tempo, si potrebbe riempire 10 milioni di valori classificati - senza mai arrivare ai valori non classificati.
* Poiché l&#39;architettura è impostata in modo che CRB possa essere estratto dal numero &quot;n&quot; di server, ciò può portare a incoerenze su quali server vengono raccolti e in quale ordine. Per questo motivo, è molto difficile arrivare a valori non classificati.

Questa è la **soluzione alternativa** per coloro che hanno più di 10 milioni di valori classificati per una dimensione: Sarà necessario esportare valori non classificati tramite FTP, in 10 milioni di batch, e classificarli manualmente.

## Guida introduttiva alle regole di classificazione {#section_3FF666EF9D5B4E37A23B3FB400CDA2E6}

**[!UICONTROL Admin]** > **[!UICONTROL Classification Rule Builder]**

Di seguito sono riportati i passaggi di alto livello da effettuare per implementare le regole di classificazione:

| Passaggio | Dove eseguito | Descrizione |
|--- |--- |--- |
| Passaggio 1 (prerequisito): [Configurare lo schema](https://docs.adobe.com/content/help/en/analytics/components/classifications/c-classifications.html)di classificazione. | [!UICONTROL Admin] > [!UICONTROL Report Suites] > [!UICONTROL Edit Settings] > &lt;Classificazioni traffico o classificazioni conversione> | Scegliete una variabile e definite le classificazioni da utilizzare per tale variabile. <br>Prima di poter essere utilizzate nelle regole, le variabili devono avere almeno una colonna di classificazione.<br>Una volta abilitate le classificazioni, potete utilizzare l&#39;utilità di importazione e il generatore di regole per classificare valori specifici. |
| Passaggio 2: [Creare un set](/help/components/classifications/crb/classification-rule-set.md)di regole. | [!UICONTROL Admin] >  [!UICONTROL Classification Rule Builder] > [!UICONTROL Add Rule Set] | Un set di regole è un gruppo di regole di classificazione per una specifica variabile. |
| Passaggio 3: Configurare suite di rapporti e variabili. | [!UICONTROL Classification Rule Builder] > &lt;set di regole> | Applica il set di regole alle suite di rapporti e alle variabili. |
| Passaggio 4: [Aggiungete le regole di classificazione al set](/help/components/classifications/crb/classification-quickstart-rules.md). | [!UICONTROL Classification Rule Builder] > &lt;set di regole> | Associare una condizione a una classificazione, quindi specificare l&#39;azione da intraprendere per la regola.  Conoscere le informazioni in [Modalità di elaborazione](/help/components/classifications/crb/classification-quickstart-rules.md)delle regole. |
| Passaggio 5: [Test di un set di regole di classificazione](/help/components/classifications/crb/classification-quickstart-rules.md) | [!DNL Testing Page] | È necessario verificare le regole per la convalida modificandole in modalità Bozza. In modalità Bozza non è possibile eseguire le regole.<br>Questo passaggio è importante quando si utilizzano le espressioni [](/help/components/classifications/crb/classification-quickstart-rules.md)regolari. |
| Passaggio 6: [Attiva regole](/help/components/classifications/crb/classification-rule-definitions.md)valide. | [!DNL Rules Page] | Una volta che le regole sono valide, attivare il set di regole.  Se necessario, potete sovrascrivere le chiavi esistenti. Vedere [Modalità Di Elaborazione](/help/components/classifications/crb/classification-quickstart-rules.md)Delle Regole. |
| Passaggio 7 (facoltativo): [Eliminate le regole](/help/components/classifications/crb/classification-rule-definitions.md)indesiderate. | [!DNL Rules Page] | Eliminare le regole indesiderate da un set.<br>Nota:  L&#39;eliminazione delle regole non comporta l&#39;eliminazione dei dati classificati caricati.  Per eliminare i dati classificati, vedere [Eliminare i dati](/help/components/classifications/importer/t-delete-classification-data.md) di classificazione. |

>[!NOTE]
>
>I gruppi con autorizzazioni per utilizzare lo strumento di importazione classificazione possono utilizzare le regole di classificazione. Per informazioni importanti sull&#39;elaborazione, vedere [Elaborazione](/help/components/classifications/crb/classification-quickstart-rules.md) delle regole.

**Risorse aggiuntive**

**Blog**: Per ulteriori informazioni su questa funzione, consultate Digital Marketing Blog: [Classificazioni](https://theblog.adobe.com/rule-based-classifications-part-1-making-classifications-easier/)basate su regole.

**Video**: Visitate [YouTube](https://www.youtube.com/watch?v=6laI5SBXY-I) per visualizzare il [!UICONTROL Classifications Overview] video.
