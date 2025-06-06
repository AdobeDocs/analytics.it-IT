---
title: Regole del set di classificazione
description: Visualizzare e modificare le regole per un singolo set di classificazione.
exl-id: 1ccb6a20-1993-4fd3-90eb-9154d12d0ec7
feature: Classifications
source-git-commit: de12253f6db798f49d0cae34bf9cb6b7a3de17db
workflow-type: tm+mt
source-wordcount: '428'
ht-degree: 3%

---

# Regole del set di classificazione

Le regole del set di classificazione consentono di classificare automaticamente i valori in base al valore su cui è impostata la variabile. Queste regole si applicano a tutti i valori delle variabili in entrata per tutte le sottoscrizioni del set di classificazione.

**[!UICONTROL Components]** > **[!UICONTROL Classification sets]** > **[!UICONTROL Sets]** > Fai clic sul nome del set di classificazione desiderato > **[!UICONTROL Rules]**

![interfaccia utente regole set di classificazione](../../assets/csets-rules.png)

## Impostazioni delle regole

Impostazioni applicabili all&#39;intero set di regole.

* **[!UICONTROL Rules overwrite]**: determina il comportamento di tutte le regole nei casi in cui esiste un valore di classificazione.
   * **[!UICONTROL Apply to all values]**: se una regola corrisponde, sovrascrivi sempre il valore di classificazione.
   * **[!UICONTROL Apply only to unset values]**: se una regola corrisponde, scrivi il valore di classificazione solo se è vuoto. Se esiste un valore di classificazione, non viene eseguita alcuna operazione.
* **[!UICONTROL Lookback window]**: quando questa regola viene attivata, tutte le regole vengono eseguite su tutti i valori univoci visualizzati nell&#39;intervallo di lookback impostato qui.

## Regole

Un elenco di regole che vengono eseguite per ogni valore univoco.

* **[!UICONTROL Search]**: casella di ricerca che consente di filtrare le regole in base ai criteri di corrispondenza.
* **[!UICONTROL Add rule]**: aggiunge una riga vuota alla tabella delle regole.
* **[!UICONTROL Test rule set]**: visualizza un&#39;interfaccia utente di prova che consente di convalidare le regole. A sinistra puoi digitare manualmente i valori chiave oppure trascinare un file di classificazione per importare più valori su cui eseguire il test. A destra è riportata una tabella che mostra i risultati preliminari dell’aspetto dei valori classificati se il set di regole fosse attivato. Poiché questa interfaccia è solo a scopo di convalida, non viene classificato alcun valore.

Seleziona una o più regole facendo clic sulla casella di controllo accanto alla regola desiderata. Selezionando una regola vengono visualizzate le seguenti opzioni:

* **[!UICONTROL Delete]**: elimina la riga dalla tabella delle regole.
* **[!UICONTROL Duplicate]**: copia le righe selezionate in nuove righe nella tabella delle regole.

## Tabella delle regole

La tabella delle regole è separata verticalmente in due parti principali: condizione di corrispondenza e azione di classificazione. Ogni riga (una singola regola) contiene una condizione di corrispondenza e un’azione di classificazione.

* **Regola numero**: le regole vengono eseguite nello stesso ordine in cui si configura la tabella delle regole. Se [!UICONTROL Rules overwrite] è impostato su [!UICONTROL Apply to all values], l&#39;ultima regola corrispondente sovrascrive eventuali regole precedenti per la stessa dimensione di classificazione. Se [!UICONTROL Rules overwrite] è impostato su [!UICONTROL Apply to only unset values], viene applicata la prima regola che imposta un valore di classificazione.
* **[!UICONTROL Select rule type]**: i criteri della regola. Le opzioni includono [!UICONTROL Contains], [!UICONTROL Ends with], [!UICONTROL Regular expression], [!UICONTROL Regular expression] e [!UICONTROL Starts with].
* **[!UICONTROL Enter match criteria]**: stringa di testo da trovare. Se si seleziona [!UICONTROL Regular expression] come tipo di regola, viene visualizzata una sovrapposizione che consente di immettere il valore, verificare l&#39;espressione regolare e fornire una sintassi di esempio.
* **[!UICONTROL Set classification]**: elenco a discesa che imposta la dimensione di classificazione a cui assegnare un valore. Le opzioni valide includono elementi nello [schema](schema.md).
* **[!UICONTROL To]**: stringa di testo su cui impostare il valore classificato. Se il tipo di regola è [!UICONTROL Regular expression], è possibile includere una combinazione di testo e gruppi di corrispondenza.
