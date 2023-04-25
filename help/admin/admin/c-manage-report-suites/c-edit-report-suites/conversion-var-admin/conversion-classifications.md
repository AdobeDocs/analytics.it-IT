---
description: Le classificazioni vengono utilizzate per categorizzare i valori in gruppi e generare rapporti a livello di gruppo. Ad esempio, puoi classificare tutte le campagne di ricerca a pagamento in una categoria come i termini della musica pop e generare rapporti sul successo di tale categoria in relazione a metriche quali Istanze (click-through) e conversione in eventi di successo.
title: Classificazioni di conversione
feature: Classifications
exl-id: b4855000-adf3-4e3b-af36-f4803383126d
source-git-commit: 78cfb1f3c4d45fc983982a8da11b66f2b2c9ecbc
workflow-type: tm+mt
source-wordcount: '516'
ht-degree: 96%

---

# Classificazioni di conversione

Le classificazioni vengono utilizzate per categorizzare i valori in gruppi e generare rapporti a livello di gruppo. Ad esempio, puoi classificare tutte le campagne [!UICONTROL Paid Search] in una categoria come *termini musicali pop* e genera rapporti sul successo di quella categoria in relazione a metriche quali Istanze (click-through) e conversione in eventi di successo. Puoi aggiungere fino a 255 classificazioni a una variabile.

Le classificazioni di conversione ti consentono di classificare le variabili di conversione. Una volta effettuata la classificazione, qualsiasi rapporto che puoi generare utilizzando la variabile chiave può essere generato anche utilizzando le proprietà dati.

Dopo aver abilitato le classificazioni, utilizza l’[Importatore di classificazione](/help/components/classifications/importer/c-working-with-saint.md) per assegnare valori specifici alla classificazione appropriata.

>[!WARNING]
>
>La ridenominazione di una classificazione può causare problemi con le regole esistenti create in [Generatore di regole di classificazione](/help/components/classifications/crb/classification-rule-builder.md). Se rinomini una classificazione con regole di classificazione, assicurati di correggere ogni regola in modo che punti alla classificazione rinominata.

## Descrizioni delle classificazioni di conversione

| Elemento | Descrizione |
| --- | --- |
| Nome | Nome della classificazione |
| Data Abilitata (Solo Testo) | Indica se la classificazione di testo è un intervallo di date per le variabili della campagna. |
| Opzioni (solo testo) | Crea un elenco di valori di classificazione disponibili per questa classificazione. Utilizza le opzioni con le variabili della campagna per fornire agli utenti un elenco di valori supportati per la classificazione in Campaign Manager. |
| Tipo di numero (solo numerico) | Specifica il tipo di numero nella classificazione numerica. Le opzioni disponibili sono Numerico, Percentuale e Valuta. |

## Aggiungere classificazioni di conversione

Per aggiungere classificazioni di conversione in Amministratore:

1. Fai clic su **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. Seleziona una suite di rapporti.
1. Fai clic su **[!UICONTROL Edit Settings]** > **[!UICONTROL Conversion]** > **[!UICONTROL Conversion Classifications]**.
1. Dall’**[!UICONTROL Select Classification Type]** elenco a discesa, seleziona la variabile in cui desideri aggiungere una classificazione.

   ![Informazioni sul passaggio](/help/admin/admin/assets/sub_class_create.png)

1. Passa il puntatore del mouse sopra l’icona **[!UICONTROL Edit Classification]**, quindi seleziona **[!UICONTROL Add Classification]**.
1. Nel campo **[!UICONTROL Select Type]**, seleziona il tipo di classificazione da aggiungere alla variabile.

   Le opzioni includono **[!UICONTROL Text]** e **[!UICONTROL Numeric]**. Per ulteriori informazioni sui tipi di classificazione, consulta [Informazioni sulle classificazioni](/help/components/classifications/c-classifications.md).
1. Nella finestra di dialogo **[!UICONTROL Text Classifications]**, configura la classificazione come desiderato.

1. Aggiungi o rimuovi le opzioni nella finestra di dialogo dell’elenco a discesa.

   Aggiungi opzioni crea un elenco dei valori di classificazione disponibili per questa classificazione. Puoi utilizzare questa opzione con le variabili di Campaign per fornire agli utenti un elenco di valori supportati per la classificazione in Campaign Manager. Utilizza questa opzione per le dimensioni di classificazione in cui si dispone di un numero limitato di valori consentiti che cambiano raramente o mai. Ad esempio, puoi eseguire diverse campagne indirizzate a diversi livelli di fedeltà dei clienti: Argento, Oro e Platino. È quindi possibile utilizzare l’elenco a discesa per assicurarsi che gli unici valori accettati siano quelli corrispondenti ai tre livelli. Se qualcuno cerca di utilizzare un valore diverso, viene scartato.

1. Fai clic su **[!UICONTROL Save]**.

## Eliminare una classificazione di conversione

Elimina una classificazione di conversione quando non è più necessaria.

1. Apri Report Suite Manager facendo clic su **[!UICONTROL Admin]**> **[!UICONTROL Report Suites]** nell’intestazione Suite.
1. Seleziona una suite di rapporti.
1. Fai clic su **[!UICONTROL Edit Settings]** > **[!UICONTROL Conversion]** > **[!UICONTROL Conversion Classifications]**.
1. Dall’elenco a discesa **[!UICONTROL Select Classification Type]**, seleziona la variabile in cui desideri eliminare una classificazione.
1. Passa il puntatore del mouse sopra l’icona **[!UICONTROL Edit Classification]**, quindi seleziona **[!UICONTROL Delete Classification]**.
1. Nella finestra di dialogo Elimina classificazione, fai clic su **[!UICONTROL Delete]**.
