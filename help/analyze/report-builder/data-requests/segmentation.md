---
description: Come aggiungere, modificare, applicare e filtrare  segmenti Adobe Analytics nel Report Builder.
title: Gestire segmenti
topic: Generatore di report
uuid: 4e4edc39-ed93-498f-913d-7b231b10e7a0
translation-type: tm+mt
source-git-commit: d0fe97b9368cbc4c9e79f9e56adf9786b58dce1a
workflow-type: tm+mt
source-wordcount: '896'
ht-degree: 9%

---


# Gestire segmenti

Come aggiungere, modificare, applicare e filtrare  segmenti Adobe Analytics nel Report Builder.

Il Report Builder include un pannello di segmentazione nel Passaggio 1 della Richiesta guidata che consente di creare e gestire i segmenti.

![](assets/seg_dialog.png)

## Aggiunta o modifica di segmenti {#section_B2BC136F9A53498D90C7C2ECC5DB892B}

>[!NOTE]
>
>Per aggiungere o modificare segmenti, l’interfaccia del segmento del Report Builder avvia il generatore di segmenti di Analytics in una finestra di Microsoft Internet Explorer. La sessione del generatore di report rimarrà attiva. I browser diversi da Internet Explorer non sono supportati per questa operazione.

1. Nel pannello dei segmenti del Passaggio 1 della Richiesta guidata, fate clic su **[!UICONTROL Add]**.
1. Viene aperta una finestra di Internet Explorer che apre l’interfaccia di Analytics Segment Builder. Per informazioni su come creare segmenti, fare riferimento a [Segmentazione di Analytics](https://docs.adobe.com/content/help/it-IT/analytics/components/segmentation/seg-home.html).
1. Dopo aver definito e salvato il segmento, tornate alla Richiesta guidata.
1. Fai clic sull’icona Aggiorna per aggiornare l’elenco dei segmenti.

>[!IMPORTANT]
>
>Questo elenco è memorizzato nella cache e il segmento appena creato non verrà visualizzato a meno che non si esegua un aggiornamento.

## Creare segmenti contestuali {#section_6DD2C663B2854469AA1075438F907678}

Potrebbero essere presenti combinazioni specifiche di dimensioni del rapporto che si desidera trasformare in un segmento. Puoi creare questi segmenti dall’interfaccia del Report Builder. Ad esempio, seleziona alcune pagine da un output di richiesta Pagina e crea un segmento basato su questi valori.

1. Selezionare gli elementi di output del rapporto che si desidera trasformare in un segmento.
1. Fare clic con il pulsante destro del mouse per selezionare **[!UICONTROL Create In-Context Segment in]** e specificare il contenitore destro (Contenitore hit, Contenitore visite, Contenitore visitatori).

   ![](assets/seg_in_context.png)

   Per ulteriori informazioni sui contenitori, vedere la [Guida alla segmentazione](https://docs.adobe.com/content/help/en/analytics/components/segmentation/seg-home.html).

1. L&#39;interfaccia utente di Segment Builder (Generatore di segmenti) verrà ora avviata in Internet Explorer. L’interfaccia utente di Generatore di segmenti verrà inizializzata con il contenitore e il filtro specificati.
1. Dopo aver aggiunto un nome e una descrizione al segmento, salvatelo.
1. Torna al generatore di report e fai clic sull&#39;icona Aggiorna per aggiornare l&#39;elenco dei segmenti.
1. È ora possibile applicare questo segmento.

## Ricerca e applicazione di segmenti {#section_CACA269B48E94CFD91C2D5A15E9C77B7}

Tutti i segmenti creati in Reporting e analisi, Report Builder o Date Warehouse vengono visualizzati in questo elenco di segmenti. Per aggiornare l&#39;elenco, fare clic sull&#39;icona Aggiorna ( ![](assets/refresh_icon.png).

Puoi applicare uno o più segmenti a una determinata richiesta. Comprende segmenti sequenziali.

1. Andate all&#39;elenco a discesa **[!UICONTROL Segment]** e fate clic sulla freccia piccola nella casella **[!UICONTROL Choose Segment]** per visualizzare tutti i segmenti.

   ![](assets/seg_list.png)

1. Verificare i segmenti da applicare.

>[!NOTE]
>
>Sia che siate un amministratore o un non amministratore, nel Report Builder potete visualizzare solo i segmenti di proprietà e quelli che sono stati condivisi con voi. (nell&#39;interfaccia utente Reporting e analisi di marketing, l&#39;amministratore può visualizzare tutti i segmenti nell&#39;organizzazione.)

## Filtrare segmenti {#section_376E986D3E684999A7CDB08E53854159}

**Filtrare** i segmenti facendo clic sull’icona Filtro:   ![](assets/segment_filter.png)

I filtri disponibili includono:

| Nome filtro | Descrizione |
|---|---|
| Tag | Consente di filtrare i segmenti con tag specifici. I filtri tag utilizzano l&#39;operatore AND. Se si controllano due tag, il riquadro a destra mostra i segmenti ai quali sono stati assegnati tag **entrambi i tag**. |
| Proprietari | Consente di filtrare i segmenti in base al proprietario. I filtri Proprietari utilizzano l&#39;operatore OR. Se si verificano due proprietari, il riquadro a destra mostra i segmenti di proprietà del proprietario **o**. |
| Altri filtri > Solo *nome suite di rapporti* | Se applicate il filtro &quot;Only *report suite name*&quot; nel Generatore di segmenti in [!DNL marketing reports & analytics] e quindi visualizzate il filtro avanzato in [!DNL report builder], il filtro Avanzate visualizzerà solo il segmento per la suite di rapporti selezionata. |
| Altri filtri > Personali | Mostra tutti i segmenti di tua proprietà. |
| Altri filtri > Condivisi con me | Mostra tutti i segmenti che altri utenti hanno condiviso con te. |
| Altri filtri > Preferiti | Mostra tutti i segmenti contrassegnati come Preferiti. |
| Altri filtri > Approvati | Mostra tutti i segmenti approvati ufficialmente. |

## Aggiungere un controllo di segmento a una cartella di lavoro {#section_E3E5149A8464441FA5445A98DBD520AC}

L&#39;aggiunta di un controllo per i segmenti consente di cambiare i segmenti dall&#39;interno di una cartella di lavoro invece di dover passare alla Richiesta guidata.

1. Fate clic sull&#39;icona Controllo ( ![](assets/control_icon.png)) accanto al menu a discesa del segmento.

   ![](assets/seg_control.png)

1. Controllare tutti i segmenti che si desidera visualizzare nel controllo del segmento oppure selezionare **[!UICONTROL Select All]**.
1. Notate l&#39;opzione **[!UICONTROL Automatically refresh linked requests upon item selection]**.

   * Se questa opzione è selezionata, tutte le richieste che utilizzano questo controllo vengono aggiornate.
   * Se non è selezionata, i parametri di richiesta associati vengono aggiornati, ma le richieste non vengono aggiornate.

1. Specificare la posizione della cella superiore sinistra del controllo del segmento.
1. Fare clic su **[!UICONTROL OK]** e il controllo del segmento viene visualizzato nella posizione specificata.

   ![](assets/seg_control2.png)

## Aggiorna l&#39;elenco dei segmenti {#section_22E4A86789444B4A998532396B476EFB}

Ogni volta che aggiungete un nuovo segmento o ne modificate uno esistente, fate clic sull&#39;icona Aggiorna ( ![](assets/refresh_icon.png)) per aggiornare l&#39;elenco dei segmenti nella cache.

## Gestire i segmenti tra le richieste {#section_C3D63FCBE1A94369A319243313B03C93}

Prima di v5.4, l’Report Builder consente agli utenti di cambiare segmenti su più richieste. Tuttavia, questo processo ha sempre sostituito i segmenti esistenti. Gli utenti che volevano aggiungere un nuovo segmento a ciascuna richiesta non potevano farlo, poiché l&#39;aggiunta del segmento rimuoverebbe il set precedente di segmenti già assegnati a ciascuna richiesta.

L&#39;Report Builder 5.4 consente di aggiungere, rimuovere, sostituire e sostituire tutti i segmenti all&#39;interno di più richieste:

1. Selezionare più richieste in una cartella di lavoro.
1. Fare clic con il pulsante destro del mouse e selezionare **[!UICONTROL Edit Requests]** > **[!UICONTROL By Segment]**.

   ![](assets/edit_by_segment.png)

1. Nella finestra di dialogo Modifica gruppo, selezionate una delle quattro opzioni seguenti:

   | Opzione | Descrizione |
   |---|---|
   | Zona di rilascio | Consente di scegliere uno o più segmenti da aggiungere all’elenco dei segmenti correnti. |
   | Sostituisci segmenti | Consente di scegliere quali segmenti sostituire con uno o più segmenti. |
   | Sostituisci tutti i segmenti per | Consente di scegliere uno o più segmenti con cui sostituire i segmenti correnti. |
   | Rimuovi segmenti | Consente di rimuovere segmenti dalle richieste. |

