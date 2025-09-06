---
description: Utilizza le regole di elaborazione per semplificare la raccolta dati e gestire i contenuti quando viene inviato al reporting.
subtopic: Processing rules
title: Panoramica sulle regole di elaborazione
feature: Processing Rules
role: Admin
exl-id: 0244aba2-4345-463a-8528-d4dcd2f872ff
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '630'
ht-degree: 3%

---

# Panoramica sulle regole di elaborazione

Le regole di elaborazione ti consentono di modificare la modalità di raccolta dei dati prima che vengano scritti in una suite di rapporti.

**[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > Seleziona suite di rapporti > **[!UICONTROL Edit Settings]** > **[!UICONTROL General]** > **[!UICONTROL Processing rules]**

>[!WARNING]
>
>Le regole di elaborazione influiscono direttamente sulla raccolta dei dati e, se utilizzate in modo errato, possono causare la perdita di dati. Prima di abilitare le regole in una suite di rapporti di produzione per attenuare i problemi di qualità dei dati, testa sempre le regole di elaborazione in una suite di rapporti di sviluppo.

I due casi d’uso principali per le regole di elaborazione includono:

* **Utilizza il flusso di lavoro di implementazione della variabile di dati di contesto**: invece di impostare direttamente le variabili nell&#39;implementazione, puoi utilizzare [Variabili di dati di contesto](/help/implement/vars/page-vars/contextdata.md) per impostare coppie chiave/valore. Ad esempio, invece di impostare:

  ```js
  s.eVar1 = "Robert Munch";
  s.eVar2 = "Books";
  s.eVar3 = "Youth";
  ```

  È invece possibile impostare:

  ```js
  s.contextData['author'] = "Robert Munch";
  s.contextData['section'] = "Books";
  s.contextData['genre'] = "Youth";
  ```

  Puoi quindi mappare le variabili di dati di contesto alle dimensioni e alle metriche desiderate nell’interfaccia utente di Analytics.

  Quando si comunica con gli sviluppatori dell’organizzazione per implementare Analytics su una proprietà, l’utilizzo di variabili di dati di contesto semplifica il processo di comunicazione. Gli sviluppatori possono semplicemente implementare ogni coppia chiave/valore una volta, quindi come amministratore di Analytics puoi assicurarti che i dati arrivino alla variabile di implementazione corretta.

* **Modifica i dati durante la raccolta**: questo caso d&#39;uso include un&#39;ampia gamma di applicazioni, ad esempio correzioni temporanee alla qualità dei dati o per colmare le lacune nell&#39;implementazione. Per ulteriori informazioni ed esempi specifici, vedi [Casi di utilizzo delle regole di elaborazione](pr-use-cases.md).

## Autorizzazioni

Per impostazione predefinita, gli amministratori dei prodotti hanno accesso alle regole di elaborazione. È possibile concedere l&#39;accesso alle regole di elaborazione agli utenti non amministratori includendole in un profilo di prodotto che includa l&#39;elemento di autorizzazione **[!UICONTROL Processing rules]**. Per ulteriori informazioni, consulta [Autorizzazioni del profilo di prodotto per gli strumenti delle suite di rapporti](/help/admin/admin-console/permissions/report-suite-tools.md).

## Considerazioni durante la creazione o la modifica delle regole di elaborazione

Quando crei o modifichi regole di elaborazione, prendi in considerazione quanto segue:

* **Possibili valori vuoti**: quando crei una regola, considera i casi in cui il valore di sovrascrittura è vuoto. Ad esempio, se disponi di una regola che sovrascrive eVar1 con eVar2 e eVar2 è vuoto, entrambe le variabili risultano vuote. Adobe consiglia di aggiungere una condizione che verifichi la presenza di un valore di variabile prima di utilizzarlo per sovrascrivere un altro valore.
* **Applica immediatamente al salvataggio**: le regole di elaborazione vengono applicate ai dati raccolti al momento del salvataggio. Non si applicano retroattivamente ai dati già raccolti.
* **Ordine di elaborazione all&#39;interno delle regole**: se sono presenti più regole di elaborazione, l&#39;ordine di esecuzione conta. Se utilizzi una determinata variabile in più regole, assicurati che vengano eseguite nell’ordine corretto. Se sovrascrivi eVar3 nella regola 1, il valore eVar3 originale non è disponibile in alcuna regola successiva.
* **Ordine di elaborazione all&#39;interno della pipeline di raccolta dati**: vedere [Ordine di elaborazione per i dati in Adobe Analytics](/help/technotes/processing-order.md) per capire dove si applicano le regole di elaborazione nella pipeline di raccolta dati complessiva.
* **Codifica**: attenersi alla codifica UTF-8 in quasi tutti i casi.
* **Distinzione tra maiuscole e minuscole**: nelle regole di elaborazione i confronti tra stringhe non fanno distinzione tra maiuscole e minuscole. I valori stringa utilizzati per sovrascrivere i valori utilizzano le stesse regole utilizzate per popolare direttamente la variabile.
* **Singola suite di rapporti**: quando modifichi le regole di elaborazione, queste si applicano a una sola suite di rapporti. Se si selezionano più suite di rapporti nel Report Suite Manager, viene forzata la selezione di una singola suite di rapporti. Dopo aver creato o modificato le regole di elaborazione desiderate, puoi [copiarle in altre suite di rapporti](pr-copy.md).
* **Nessuna esclusione di dati**: l&#39;esclusione di dati non è una caratteristica prevista delle regole di elaborazione. Prendere in considerazione l&#39;utilizzo di [`abort`](/help/implement/vars/config-vars/abort.md) a livello di raccolta dati o utilizzare [regole VISTA](/help/technotes/vista.md) dopo la raccolta dei dati.
* **Variabili disponibili**: non tutte le dimensioni e le metriche sono disponibili nelle regole di elaborazione. Per l&#39;elenco completo delle opzioni supportate, vedere [Dimensioni e metriche disponibili per le regole di elaborazione](pr-variables.md).
* **Numero di regole consentite**: ogni suite di rapporti può contenere fino a 150 regole. Ogni regola può contenere fino a 30 condizioni.

>[!MORELIKETHIS]
>
>![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Mappa le variabili di dati di contesto in prop ed eVar con regole di elaborazione](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/implementation/implementation-basics/map-contextdata-variables-into-props-and-evars-with-processing-rules){target="_blank"}
