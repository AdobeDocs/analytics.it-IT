---
description: Come aggiungere, modificare, applicare e filtrare i segmenti di Adobe Analytics in Generatore di report.
seo-description: Come aggiungere, modificare, applicare e filtrare i segmenti di Adobe Analytics in Generatore di report.
seo-title: Gestire i segmenti
solution: Analytics
title: Gestire i segmenti
topic: Generatore di report
uuid: 4 e 4 edc 39-ed 93-498 f -913 d -7 b 231 b 10 e 7 a 0
translation-type: tm+mt
source-git-commit: d75c58caf1220031fa36483a0ad50ea6f7be7c39

---


# Gestire i segmenti

Come aggiungere, modificare, applicare e filtrare i segmenti di Adobe Analytics in Generatore di report.

Generatore di report offre un pannello segmentazione al Passaggio 1 della richiesta guidata che consente di creare e gestire segmenti.

![](assets/seg_dialog.png)

## Add or edit segments {#section_B2BC136F9A53498D90C7C2ECC5DB892B}

>[!NOTE]
>
>Per aggiungere o modificare segmenti, l'interfaccia del segmento Generatore di report avvia il generatore di segmenti di Analytics in una finestra Microsoft Internet Explorer. La sessione del generatore di report rimarrà attiva. I browser diversi da Internet Explorer non sono supportati per questa operazione.

1. In the segment panel of Step 1 of the Request Wizard, click **[!UICONTROL Add]**.
1. Viene avviato un avvio della finestra di Internet Explorer che apre l'interfaccia di Generatore di segmenti di Analytics. For information on how to build segments, refer to [https://marketing.adobe.com/resources/help/en_US/analytics/segment/](https://marketing.adobe.com/resources/help/en_US/analytics/segment/).
1. Dopo aver definito e salvato il segmento, torna alla procedura guidata Richiesta.
1. Fate clic sull'icona Aggiorna per aggiornare l'elenco dei segmenti.

>[!IMPORTANT]
>
>Questo elenco viene memorizzato nella cache e il segmento appena creato non verrà visualizzato a meno che non venga eseguito un aggiornamento.

## Create in-context segments {#section_6DD2C663B2854469AA1075438F907678}

Potresti avere combinazioni specifiche di dimensioni del rapporto che desideri trasformare in segmenti. Puoi creare questi segmenti dall'interfaccia di Generatore di report. Ad esempio, selezionate alcune pagine dall'output della richiesta Pagina e create un segmento basato su tali valori.

1. Selezionate gli elementi di output del rapporto che desiderate trasformare in un segmento.
1. Right-click to select **[!UICONTROL Create In-Context Segment in]** and specify the right container (Hits Container, Visits Container, Visitor Container).

   ![](assets/seg_in_context.png)

   For more information on containers, see the [Segmentation Guide](https://marketing.adobe.com/resources/help/en_US/analytics/segment/).

1. L'interfaccia utente di Segment Builder (Generatore di segmenti) verrà ora avviata in Internet Explorer. L'interfaccia utente di Segment Builder (Generatore di segmenti) verrà inizializzata con il contenitore e il filtro specificato.
1. Dopo aver aggiunto un nome e una descrizione al segmento, salvatelo.
1. Torna al generatore di report e fai clic sull'icona Aggiorna per aggiornare l'elenco dei segmenti.
1. Ora sei pronto per applicare questo segmento.

## Search for and apply segments {#section_CACA269B48E94CFD91C2D5A15E9C77B7}

In questo elenco dei segmenti vengono visualizzati tutti i segmenti creati in Reporting e analisi, Analisi ad hoc, Generatore di report o Data Warehouse. To refresh the list, click the Refresh icon ( ![](assets/refresh_icon.png).

Potete applicare uno o più segmenti a una determinata richiesta. Questo include segmenti sequenziali.

1. Go to the **[!UICONTROL Segment]** drop-down list and click the small down arrow in the **[!UICONTROL Choose Segment]**box to display all the segments.

   ![](assets/seg_list.png)

1. Controllate i segmenti che desiderate applicare.

>[!NOTE]
>
>Sia che tu sia Amministratore o Non amministratore, nel Generatore di report puoi vedere solo i segmenti di tua proprietà e quelli che sono stati condivisi con te. Nell'interfaccia utente di Reporting e analisi di marketing, l'amministratore può vedere tutti i segmenti nell'organizzazione.

## Filter segments {#section_376E986D3E684999A7CDB08E53854159}

**Filtrare** i segmenti facendo clic sull'icona Filtro: ![](assets/segment_filter.png)

I filtri disponibili includono:

| Nome filtro | Descrizione |
|---|---|
| Tag | Consente di filtrare i segmenti con tag specifici. I filtri Tag utilizzano l'operatore AND. If you check two tags, the right pane shows segments that have been tagged with **both** tags. |
| Proprietari | Consente di filtrare i segmenti per proprietario. I filtri dei proprietari utilizzano l'operatore OR. If you check two owners, the right pane shows segments that are owned by **either** owner. |
| Other Filters &gt; Only *report suite name* | If you apply the "Only *report suite name*" filter in the Segment Builder in [!DNL marketing reports & analytics], and then display the Advanced Filter in [!DNL report builder], the Advanced filter will display the segment for the selected report suite only. |
| Altri filtri &gt; Personale | Mostra tutti i segmenti di cui sei titolare. |
| Altri filtri &gt; Condiviso con me | Mostra tutti i segmenti condivisi da altri utenti. |
| Altri filtri &gt; Preferiti | Mostra tutti i segmenti contrassegnati come Preferiti. |
| Altri filtri &gt; Approvato | Mostra tutti i segmenti ufficialmente approvati. |

## Add a segment control to a workbook {#section_E3E5149A8464441FA5445A98DBD520AC}

L'aggiunta di un controllo segmenti consente di cambiare segmenti all'interno di una cartella di lavoro invece di dover passare alla procedura guidata Richiesta.

1. Click the Control icon ( ![](assets/control_icon.png)) next to the segment drop-down.

   ![](assets/seg_control.png)

1. Check all the segments that you want to appear in the segment control, or check **[!UICONTROL Select All]**.
1. Notice the option **[!UICONTROL Automatically refresh linked requests upon item selection]**.

   * Se questa opzione è attivata, tutte le richieste che utilizzano questo controllo vengono aggiornate.
   * Se non sono stati selezionati, i parametri di richiesta associati vengono aggiornati, ma le richieste non vengono aggiornate.

1. Specifica la posizione della cella in alto a sinistra del controllo segmenti.
1. Click **[!UICONTROL OK]** and the segment control appears in the specified location.

   ![](assets/seg_control2.png)

## Refresh the list of segments {#section_22E4A86789444B4A998532396B476EFB}

Any time you add a new segment or edit an existing one, you should click the Refresh icon ( ![](assets/refresh_icon.png) to refresh the cached list of segments.

## Manage segments across requests {#section_C3D63FCBE1A94369A319243313B03C93}

Prima della release v 5.4, Generatore di report consente agli utenti di modificare i segmenti su più richieste. Tuttavia, questo processo sostituiva sempre i segmenti esistenti. Gli utenti che desiderano aggiungere un nuovo segmento a ogni richiesta non possono eseguire questa operazione, poiché l'aggiunta del segmento rimuove il precedente set di segmenti già assegnato a ogni richiesta.

Generatore di report 5.4 consente di aggiungere, rimuovere, sostituire e sostituire tutti i segmenti all'interno di più richieste:

1. Selezionate più richieste in una cartella di lavoro.
1. Right-click and select **[!UICONTROL Edit Requests]** &gt; **[!UICONTROL By Segment]**.

   ![](assets/edit_by_segment.png)

1. Nella finestra di dialogo Modifica gruppo, selezionate una delle quattro opzioni:

   | Opzione | Descrizione |
   |---|---|
   | Zona di rilascio | Consente di scegliere uno o più segmenti da aggiungere all'elenco dei segmenti/s correnti. |
   | Sostituisci segmenti | Consente di scegliere i segmenti da sostituire con uno o più segmenti. |
   | Sostituisci tutti i segmenti tramite | Consente di scegliere uno o più segmenti con cui sostituire i segmenti correnti. |
   | Rimuovi segmenti | Consente di rimuovere i segmenti dalle richieste. |

