---
description: Come aggiungere, modificare, applicare e filtrare segmenti di Adobe Analytics nel Report Builder.
title: Gestire i segmenti (Report Builder)
feature: Report Builder
role: User, Admin
exl-id: c4ad89e0-91c9-47e1-a226-69d82fdb8918
source-git-commit: a979fc8787fa96f8fa8317996ac66341a6f54354
workflow-type: tm+mt
source-wordcount: '937'
ht-degree: 4%

---

# Gestire segmenti

Come aggiungere, modificare, applicare e filtrare segmenti di Adobe Analytics nel Report Builder.

Nel passaggio 1 della Creazione guidata richieste, il Report Builder dispone di un pannello di segmentazione che consente di creare e gestire i segmenti.

![Schermata che mostra le opzioni Segmento per aggiungere, modificare o cancellare segmenti ed evidenzia le icone Controllo, Filtro e Aggiornamento.](assets/seg_dialog.png)

## Aggiungere o modificare segmenti {#section_B2BC136F9A53498D90C7C2ECC5DB892B}

>[!NOTE]
>
>Per aggiungere o modificare segmenti, l’interfaccia dei segmenti di Report Builder avvia il Generatore di segmenti di Analytics in una finestra di Microsoft Internet Explorer. La sessione di Report Builder rimarrà attiva. I browser diversi da Internet Explorer non sono supportati per questa operazione.

1. Nel pannello dei segmenti del passaggio 1 della Creazione guidata richieste, fare clic su **[!UICONTROL Add]**.
1. Viene visualizzata una finestra di Internet Explorer che apre l’interfaccia del Generatore di segmenti di Analytics. Per informazioni su come creare i segmenti, consulta [Segmentazione di Analytics](https://experienceleague.adobe.com/docs/analytics/components/segmentation/seg-home.html?lang=it).
1. Dopo aver definito e salvato il segmento, torna alla Creazione guidata richieste.
1. Fai clic sull’icona Aggiorna per aggiornare l’elenco dei segmenti.

>[!IMPORTANT]
>
>L’elenco è memorizzato nella cache e il segmento appena creato non verrà visualizzato, a meno che non esegui un aggiornamento.

## Creare segmenti nel contesto {#section_6DD2C663B2854469AA1075438F907678}

Puoi avere combinazioni specifiche di dimensioni di rapporto che desideri trasformare in un segmento. Puoi creare questi segmenti dall’interfaccia di Report Builder. Ad esempio, seleziona alcune pagine dall’output di una richiesta di pagina e crea un segmento basato su questi valori.

1. Seleziona gli elementi di output del rapporto che desideri trasformare in un segmento.
1. Fare clic con il pulsante destro del mouse per selezionare **[!UICONTROL Create In-Context Segment in]** e specificare il contenitore corretto (Contenitore Hit, Contenitore Visite, Contenitore Visitatore).

   ![Schermata che mostra Crea segmento nel contesto nelle opzioni contenitore selezionate e disponibili.](assets/seg_in_context.png)

   Per ulteriori informazioni sui contenitori, vedere la [Guida alla segmentazione](https://experienceleague.adobe.com/docs/analytics/components/segmentation/seg-home.html?lang=it).

1. L’interfaccia utente del Generatore di segmenti verrà ora avviata in Internet Explorer. L’interfaccia utente del Generatore di segmenti verrà inizializzata con il contenitore e il filtro specificati.
1. Dopo aver aggiunto un nome e una descrizione al segmento, salvalo.
1. Torna al Report Builder e fai clic sull’icona Aggiorna per aggiornare l’elenco dei segmenti.
1. Ora puoi applicare questo segmento.

## Cercare e applicare segmenti {#search}

Tutti i segmenti creati in Reports &amp; Analytics (ora al termine del ciclo di vita), Report Builder o Data Warehouse vengono visualizzati in questo elenco di segmenti. Per aggiornare l&#39;elenco, fare clic sull&#39;icona Aggiorna ![](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg).

Puoi applicare uno o più segmenti a una determinata richiesta. Sono inclusi i segmenti sequenziali.

1. Passare all&#39;elenco a discesa **[!UICONTROL Segment]** e fare clic sulla piccola freccia giù nella casella **[!UICONTROL Choose Segment]** per visualizzare tutti i segmenti.

1. Seleziona i segmenti da applicare.

   ![Schermata che mostra i segmenti selezionati.](assets/seg_list.png)

>[!NOTE]
>
>Che tu sia un amministratore o un non amministratore, nel Report Builder puoi visualizzare solo i segmenti che possiedi e quelli che sono stati condivisi con te.

## Filtrare segmenti {#filter}

**Filtra** segmenti facendo clic sull&#39;icona Filtro: ![Icona Filtro](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg)

I filtri disponibili includono:

| Nome filtro | Descrizione |
|---|---|
| Tag | Consente di filtrare i segmenti con tag specifici. I filtri di tag utilizzano l’operatore AND. Se selezioni due tag, nel riquadro a destra vengono visualizzati i segmenti a cui sono stati assegnati tag **entrambi**. |
| Proprietari | Consente di filtrare i segmenti in base al proprietario. I filtri Proprietari utilizzano l’operatore OR. Se selezioni due proprietari, nel riquadro a destra vengono visualizzati i segmenti di proprietà del proprietario **uno**. |
| Altri filtri > Solo *nome suite di rapporti* | Se applichi il filtro &quot;Only *report suite name*&quot; (Solo nome suite di rapporti) nel Generatore di segmenti in Adobe Analytics e quindi visualizzi il filtro avanzato in [!DNL Report Builder], il filtro Avanzato visualizzerà il segmento solo per la suite di rapporti selezionata. |
| Altri filtri > Personali | Mostra tutti i segmenti di tua proprietà. |
| Altri filtri > Condivisi con me | Mostra tutti i segmenti che altri utenti hanno condiviso con te. |
| Altri filtri > Preferiti | Mostra tutti i segmenti contrassegnati come Preferiti. |
| Altri filtri > Approvati | Mostra tutti i segmenti approvati ufficialmente. |

## Aggiungere un controllo segmento a una cartella di lavoro {#segment-control}

L&#39;aggiunta di un controllo segmento consente di cambiare i segmenti all&#39;interno di una cartella di lavoro anziché passare alla Richiesta guidata.

1. Fare clic sull&#39;icona Controllo ![](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg) accanto al menu a discesa del segmento.

1. Controllare tutti i segmenti che si desidera visualizzare nel controllo segmento oppure selezionare **[!UICONTROL Select All]**.

   ![Schermata della finestra di dialogo Impostazioni controllo con tutte le impostazioni selezionate.](assets/seg_control.png)

1. Osservare l&#39;opzione **[!UICONTROL Automatically refresh linked requests upon item selection]**.

   * Se questa opzione è selezionata, tutte le richieste che utilizzano questo controllo vengono aggiornate.
   * Se non è selezionata, i parametri di richiesta associati vengono aggiornati, ma le richieste non vengono aggiornate.

1. Specificare la posizione della cella superiore sinistra del controllo segmento.

1. Fare clic su **[!UICONTROL OK]** e il controllo del segmento viene visualizzato nella posizione specificata.

   ![Schermata che mostra il campo a discesa Scegli campo segmento.](assets/seg_control2.png)

## Aggiorna l’elenco dei segmenti {#refresh}

Ogni volta che aggiungi un nuovo segmento o ne modifichi uno esistente, fai clic sull&#39;icona Aggiorna ![](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) per aggiornare l&#39;elenco dei segmenti memorizzati nella cache.

## Gestire i segmenti in più richieste {#manage}

Prima della versione 5.4, Report Builder consentiva agli utenti di modificare i segmenti su più richieste. Tuttavia, questo processo ha sempre sostituito i segmenti esistenti. Gli utenti che desideravano aggiungere un nuovo segmento a ciascuna richiesta non potevano farlo, poiché l’aggiunta del segmento rimuoveva il precedente set di segmenti già assegnato a ogni richiesta.

Il Report Builder 5.4 consente di aggiungere, rimuovere e sostituire tutti i segmenti all’interno di più richieste:

1. Selezionare più richieste in una cartella di lavoro.
1. Fare clic con il pulsante destro del mouse e selezionare **[!UICONTROL Edit Requests]** > **[!UICONTROL By Segment]**.

   ![Schermata che mostra le richieste di modifica e per segmento selezionate.](assets/edit_by_segment.png)

1. Nella finestra di dialogo Modifica gruppo, selezionate una delle quattro opzioni seguenti:

   | Opzione | Descrizione |
   |---|---|
   | Zona di rilascio | Consente di scegliere uno o più segmenti da aggiungere all’elenco dei segmenti correnti. |
   | Sostituisci segmenti | Consente di scegliere quali segmenti sostituire con uno o più segmenti. |
   | Sostituisci tutti i segmenti con | Consente di scegliere uno o più segmenti per sostituire i segmenti correnti con. |
   | Rimuovi segmenti | Consente di rimuovere segmenti dalle richieste. |
