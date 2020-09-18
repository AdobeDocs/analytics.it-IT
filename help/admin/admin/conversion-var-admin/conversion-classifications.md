---
description: Le classificazioni vengono utilizzate per classificare i valori in gruppi e per creare rapporti a livello di gruppo. Ad esempio, puoi classificare tutte le campagne di ricerca a pagamento in una categoria come i termini musicali pop e generare report sul successo di quella categoria in relazione a metriche come Istanze (click-through) e conversione in eventi di successo.
title: Classificazioni di conversione
translation-type: tm+mt
source-git-commit: ec93137d0b5334e312fe0ec42953457243117d4a
workflow-type: tm+mt
source-wordcount: '511'
ht-degree: 4%

---


# Classificazioni di conversione

Le classificazioni vengono utilizzate per classificare i valori in gruppi e per creare rapporti a livello di gruppo. Ad esempio, puoi classificare tutte le campagne di ricerca a pagamento in una categoria come i termini *musicali* pop e generare report sul successo di quella categoria in relazione a metriche come Istanze (click-through) e conversione in eventi di successo.

Le classificazioni di conversione consentono di classificare le variabili di conversione. Una volta classificati, qualsiasi rapporto che è possibile generare utilizzando i dati chiave può essere generato anche utilizzando le proprietà dati associate.

Dopo aver attivato le classificazioni, utilizzare Importazione [](/help/components/classifications/importer/c-working-with-saint.md) classificazione per assegnare valori specifici alla classificazione appropriata.

>[!WARNING]
>
>La ridenominazione di una classificazione può causare problemi con le regole esistenti create nel generatore [di regole di](/help/components/classifications/crb/classification-rule-builder.md)classificazione. Se si rinomina una classificazione con regole di classificazione, assicurarsi di correggere ogni regola in modo che punti alla classificazione rinominata.

## Descrizioni classificazioni conversione

| Elemento | Descrizione |
| --- | --- |
| Nome | Nome classificazione |
| Data Attivata (Solo Testo) | Indica se la classificazione di testo è un intervallo di date per le variabili della campagna. |
| Opzioni (solo testo) | Crea un elenco di valori di classificazione disponibili per questa classificazione. Utilizzate Opzioni con variabili di campagna per fornire agli utenti un elenco di valori supportati per la classificazione in Campaign Manager. |
| Tipo di numero (solo numerico) | Specifica il tipo di numero nella classificazione numerica. Le opzioni includono Numerico, Percentuale e Valuta. |

## Aggiungi classificazioni conversione

Procedura che descrive come aggiungere classificazioni di conversione in Amministratore.

1. Fai clic su **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. Seleziona una suite di rapporti.
1. Fai clic su **[!UICONTROL Edit Settings]** > **[!UICONTROL Conversion]** > **[!UICONTROL Conversion Classifications]**.
1. Dall’elenco a **[!UICONTROL Select Classification Type]** discesa, selezionate la variabile in cui desiderate aggiungere una classificazione.

   ![Informazioni sul passaggio](../assets/sub_class_create.png)

1. Passate il puntatore del mouse sull&#39; **[!UICONTROL Edit Classification]** icona, quindi selezionate **[!UICONTROL Add Classification]**.
1. Nel **[!UICONTROL Select Type]** campo, selezionare il tipo di classificazione che si desidera aggiungere alla variabile.

   Le opzioni includono **[!UICONTROL Text]** e **[!UICONTROL Numeric]**. Per ulteriori informazioni sui tipi di classificazione, vedere [Informazioni sulle classificazioni](/help/components/classifications/c-classifications.md).
1. Nella finestra di **[!UICONTROL Text Classifications]** dialogo, configurare la classificazione come desiderato.

1. Nella finestra di **[!UICONTROL Dropdown List]** dialogo, aggiungere o rimuovere le opzioni.

   L&#39;aggiunta di opzioni crea un elenco di valori di classificazione disponibili per questa classificazione. Puoi utilizzare questa opzione con le variabili Campaign per fornire agli utenti un elenco di valori supportati per la classificazione in Campaign Manager. Utilizzate questa opzione per le dimensioni di classificazione in cui è presente un numero limitato di valori consentiti che raramente o mai cambiano. Ad esempio, potete eseguire diverse campagne mirate a diversi livelli di fedeltà dei clienti: Argento, Oro e Platinum. Potreste quindi utilizzare l&#39;elenco a discesa per assicurarvi che gli unici valori accettati siano quelli che corrispondono ai vostri tre livelli. Se qualcuno tenta di utilizzare un valore diverso, viene eliminato.

1. Fai clic su **[!UICONTROL Save]**.

## Eliminare una classificazione di conversione

Elimina una classificazione di conversione quando non è più necessaria.

1. Aprite il Gestore delle suite di rapporti facendo clic su **[!UICONTROL Admin]**> **[!UICONTROL Report Suites]** nell’intestazione della suite.
1. Seleziona una suite di rapporti.
1. Fai clic su **[!UICONTROL Edit Settings]** > **[!UICONTROL Conversion]** > **[!UICONTROL Conversion Classifications]**.
1. Dall’elenco a **[!UICONTROL Select Classification Type]** discesa, selezionate la variabile da cui desiderate eliminare una classificazione.
1. Passate il puntatore del mouse sull&#39; **[!UICONTROL Edit Classification]** icona, quindi selezionate **[!UICONTROL Delete Classification]**.
1. Nella finestra di dialogo Elimina classificazione, fare clic su **[!UICONTROL Delete]**.
