---
title: Interfaccia delle regole di elaborazione
description: Naviga nell’interfaccia per creare, modificare o eliminare le regole di elaborazione.
feature: Processing Rules
role: Admin
source-git-commit: c2adf6d2e328378332cc290ba2dfd75ee6587ef6
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 0%

---

# Interfaccia delle regole di elaborazione

L’interfaccia delle regole di elaborazione consente di creare, modificare o eliminare le regole di elaborazione.

**[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > Seleziona suite di rapporti > **[!UICONTROL Edit Settings]** > **[!UICONTROL General]** > **[!UICONTROL Processing rules]**

>[!WARNING]
>
>Le regole di elaborazione influiscono direttamente sulla raccolta dei dati e, se utilizzate in modo errato, possono causare la perdita di dati. Prima di abilitare le regole in una suite di rapporti di produzione per attenuare i problemi di qualità dei dati, testa sempre le regole di elaborazione in una suite di rapporti di sviluppo.

## Struttura generale

Questa interfaccia contiene due componenti principali:

* **[!UICONTROL Processing order]**: le regole vengono eseguite esattamente nell&#39;ordine specificato, a partire dalla regola 1. Ogni hit attraversa ogni regola; non ci sono condizioni di early-out. Assicurati che le condizioni di ogni regola di elaborazione includano ogni hit inviato alla suite di rapporti.
* **[!UICONTROL Rule sets]**: le definizioni di ciascuna delle regole di elaborazione.

Puoi avere fino a 150 regole di elaborazione e fino a 30 condizioni per regola di elaborazione. Non esiste un limite ragionevole al numero di azioni per regola di elaborazione.

## Struttura del set di regole

Ogni regola di elaborazione contiene le sezioni seguenti:

* **Titolo regola**: etichetta della regola. Non influisce sulla logica della regola di elaborazione, ma è utile per tenere traccia di ciò che fa la regola.
* **Condizione**: visualizzato come testo, &quot;[!UICONTROL If any/all of the following are true]&quot;. Se non includi una condizione, la regola viene sempre eseguita su ogni hit.
* **Azione**: se non esiste alcuna condizione, il testo verrà visualizzato come &quot;[!UICONTROL Always execute]&quot;. Se esiste una condizione, il testo viene visualizzato come &quot;[!UICONTROL Then do the following]&quot;. Se la condizione precedente restituisce `true`, ogni azione elencata in questa sezione viene potenzialmente eseguita. Oltre alla condizione di una regola, puoi _anche_ allegare condizioni alle singole azioni. Sono disponibili le seguenti azioni:
   * **[!UICONTROL Overwrite value of]**: sovrascrive la variabile desiderata con un&#39;altra variabile, un valore statico o un valore concatenato.
   * **[!UICONTROL Delete value of]**: elimina il valore di variabile desiderato per l&#39;hit.
   * **[!UICONTROL Set event]**: attiva l&#39;evento desiderato. In genere si impostano gli eventi su un valore personalizzato di `1`; è possibile impostare gli eventi su valori diversi da `1` o anche impostarli su valori impostati nelle variabili di dati di contesto.
* **Altrimenti azione**: se esiste una condizione, questa sezione verrà visualizzata come &quot;[!UICONTROL Otherwise do the following]&quot;. Se la condizione precedente restituisce `false`, ogni azione elencata in questa sezione viene potenzialmente eseguita. Questa sezione segue le stesse azioni delle regole precedenti, inclusa la possibilità di sovrascrivere valori, eliminare valori e impostare eventi.
* **Motivo**: record che ha richiesto la regola e da cosa dipende. Non influisce sulla logica della regola di elaborazione, ma è utile per tenere traccia del motivo per cui esiste la regola.

Per un elenco completo delle variabili utilizzabili in questa interfaccia, vedere [Dimensioni e metriche disponibili per le regole di elaborazione](pr-variables.md).

* Qualsiasi variabile che consente la lettura può essere utilizzata in una condizione.
* Qualsiasi variabile che consenta &quot;Write&quot; può essere utilizzata in un&#39;azione.
