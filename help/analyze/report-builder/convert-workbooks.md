---
title: Conversione delle cartelle di lavoro legacy di Report Builder
description: Scopri come convertire le cartelle di lavoro legacy basate su Report Builder per utilizzare il nuovo Report Builder.
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: ff9011b2-fc18-456f-81dc-151b9e4fccd2
source-git-commit: 504cce24babdd8aefa5f819433139671904f2e1e
workflow-type: tm+mt
source-wordcount: '681'
ht-degree: 0%

---

# Conversione di cartelle di lavoro legacy di Report Builder

Nell&#39;ambito del passaggio a una nuova funzionalità di Report Builder, è possibile convertire rapidamente le cartelle di lavoro legacy di Report Builder (cartelle di lavoro legacy) esistenti per utilizzare la nuova funzionalità [datablock](create-a-data-block.md) di Report Builder.

>[!IMPORTANT]
>
>Duplicare ogni cartella di lavoro e rinominare una versione prima di convertire la cartella di lavoro legacy. In questo modo è possibile disporre sempre di una copia della cartella di lavoro legacy originale, se necessario.


>[!BEGINSHADEBOX]

Per un video dimostrativo, consulta ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Converti cartelle di lavoro](https://video.tv.adobe.com/v/3446190?captions=ita&quality=12&learn=on){target="_blank"}.

>[!ENDSHADEBOX]


>[!NOTE]
>
>Per convertire le cartelle di lavoro legacy, è necessario aver prima [configurato il nuovo Report Builder](/help/analyze/report-builder/report-builder-setup.md).


## Aprire una cartella di lavoro legacy

Per aprire una cartella di lavoro legacy, è possibile:

* Aprire una cartella di lavoro legacy pianificata dalla scheda **[!UICONTROL Schedule]** nell&#39;[hub Report Builder](report-builder-hub.md). Questo è il metodo preferito per le cartelle di lavoro legacy pianificate. È possibile utilizzare la pianificazione associata alla cartella di lavoro legacy non appena si [pianifica la cartella di lavoro legacy convertita](#schedule-a-converted-legacy-workbook).

   1. Apri Excel e seleziona ![AdobeLogoRedonWhite](/help/assets/icons/AdobeLogoRedOnWhite.svg) **[!UICONTROL Report Builder]** dalla barra multifunzione di Excel.

   1. Selezionare **[!UICONTROL Login]** e accedere a Report Builder.

   1. Selezionare **[!UICONTROL Schedule]** nell&#39;[hub Report Builder](report-builder-hub.md).
   1. Seleziona la scheda **[!UICONTROL Legacy]**. Nella scheda sono elencate le cartelle di lavoro pianificate legacy basate su Report Builder.

      ![Elementi precedenti](assets/upgrade-legacy-schedule.png)

   1. Selezionare ![SelectBox](/help/assets/icons/SelectBox.svg) la cartella di lavoro pianificata da convertire dall&#39;elenco e selezionare ![Scarica](/help/assets/icons/Download.svg). La cartella di lavoro viene scaricata e si apre in una nuova finestra in Excel. È ora possibile [convertire la cartella di lavoro legacy di Report Builder](#convert-a--workbook).


* Aprire una cartella di lavoro legacy direttamente dal computer locale o dalla rete. Quando si utilizza questo metodo, non viene offerto di utilizzare la pianificazione che potrebbe essere associata alla cartella di lavoro legacy. <br/>Quando la cartella di lavoro legacy è aperta in Excel:

   1. Seleziona ![AdobeLogoRedonWhite](/help/assets/icons/AdobeLogoRedOnWhite.svg) **[!UICONTROL Report Builder]** dalla barra multifunzione di Excel.
   1. Selezionare **[!UICONTROL Login]** e accedere a Report Builder.
   1. Quindi [convertire la cartella di lavoro legacy](#convert-a-workbook).


## Convertire una cartella di lavoro legacy

Per convertire la cartella di lavoro legacy:

1. Una volta aperta una cartella di lavoro legacy, la nuova Report Builder rileva se la cartella di lavoro contiene [richieste Report Builder](/help/analyze/legacy-report-builder/home.md) legacy.

   ![richiesta aggiornamento cartella di lavoro](assets/upgrade-workbook.png){zoomable="yes"}

1. Se vengono trovate una o più richieste legacy, fare clic su **[!UICONTROL Upgrade]** nella finestra di dialogo **[!UICONTROL Upgrade workbook]** per aggiornare la cartella di lavoro.

   >[!NOTE]
   >
   >È necessario aggiornare ogni richiesta singolarmente. Aggiornamento in blocco non supportato.


1. Viene visualizzata una finestra di dialogo **[!UICONTROL Warning]** che avvisa l&#39;utente delle modifiche apportate alla cartella di lavoro se si esegue l&#39;aggiornamento. Viene inoltre richiesto di creare un backup della cartella di lavoro precedente prima di procedere.

   ![avviso aggiornamento](assets/upgrade-warning.png){zoomable="yes"}

1. Fare clic su **[!UICONTROL Proceed]** per continuare con l&#39;aggiornamento.

   Se l&#39;aggiornamento ha esito positivo, viene visualizzata una notifica **[!UICONTROL The workbook upgrade is now completed]**.

   ![aggiornamento completato](assets/upgrade-complete.png)

   * Selezionare **[!UICONTROL Close]** per chiudere la notifica e continuare a utilizzare la cartella di lavoro con richieste aggiornate per il nuovo Report Builder.

   * Selezionare **[!UICONTROL Download upgrade report]** per scaricare e aprire una nuova cartella di lavoro di Excel con il risultato dell&#39;aggiornamento. Per un esempio, vedi di seguito.

     ![Cartella di lavoro del report di aggiornamento di Excel Report Builder](assets/upgrade-report.png)

È ora possibile [gestire i blocchi di dati](/help/analyze/report-builder/manage-reportbuilder.md) nella cartella di lavoro. Questi blocchi di dati sono il risultato dell’aggiornamento e sostituiscono le richieste legacy di Report Builder.


## Pianificare una cartella di lavoro legacy convertita

È possibile utilizzare i dettagli della pianificazione dalla cartella di lavoro legacy scaricata e aperta dalla scheda **[!UICONTROL Schedule]** nell&#39;hub Report Builder. Questa opzione non è disponibile per le cartelle di lavoro legacy con dettagli di pianificazione aperti dal computer locale o dalla rete.

1. Per pianificare una cartella di lavoro legacy convertita con una pianificazione precedente:

   * Selezionare **[!UICONTROL Send workbook]** dall&#39;hub Report Builder oppure
   * Selezionare **[!UICONTROL Schedule workbook]** dalla scheda **[!UICONTROL Workbooks]** disponibile nella scheda **[!UICONTROL Schedules]** di Report Builder.

1. È possibile utilizzare i dettagli della pianificazione della cartella di lavoro legacy come impostazioni di pianificazione predefinite.

   ![Migra pianificazione cartella di lavoro legacy](assets/upgrade-legacy-schedule-convert.png)

   * Selezionare **[!UICONTROL Use]** per utilizzare i dettagli della pianificazione legacy. I dettagli della pianificazione sono precompilati nell&#39;interfaccia [Invia cartella di lavoro](schedule-reportbuilder.md#schedule-a-workbook).
   * Selezionare **[!UICONTROL Don't use]** per non utilizzare i dettagli della pianificazione legacy.
   * Seleziona **[!UICONTROL Cancel]** per annullare.

   Selezionare **[!UICONTROL Remove legacy metadata from future use]** per non utilizzare in futuro i dettagli della pianificazione legacy per questa cartella di lavoro.


## Funzioni legacy di Report Builder non supportate {#unsupported}

Alcune funzionalità legacy di Report Builder non sono più disponibili nel nuovo Report Builder

* Richieste in tempo reale.

* Generazione di rapporti percorso/fallout.

* Opzione FTP per i rapporti pianificati.

* Metriche dei visitatori. Le metriche seguenti vengono convertite in *visitatori univoci*, anche se il risultato del reporting potrebbe non corrispondere esattamente: `visitorshourly`, `visitorsdaily`, `visitorsweekly`, `visitorsmonthly`, `visitorsquarterly` e `visitorsyearly`. Questa conversione si applica anche a `mobilevisitorshourly`, `mobilevisitorsdaily`, `mobilevisitorsweekly`, `mobilevisitorsmonthly`, `mobilevisitorsquarterly` e `mobilevisitorsyearly`.
