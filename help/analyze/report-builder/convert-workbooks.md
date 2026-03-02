---
title: Conversione cartelle di lavoro legacy di Report Builder
description: Scopri come migrare e convertire le cartelle di lavoro legacy di Report Builder nel nuovo Report Builder. Segui le istruzioni dettagliate contenute in questa guida alla migrazione su come convertire facilmente le cartelle di lavoro basate su Adobe Analytics.
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: ff9011b2-fc18-456f-81dc-151b9e4fccd2
source-git-commit: 9743d7ac2a6c7e63d7a6701e60d05683c5680d36
workflow-type: tm+mt
source-wordcount: '1096'
ht-degree: 1%

---

# Conversione di cartelle di lavoro legacy di Report Builder

La versione precedente di Report Builder termina il ciclo di vita a giugno 2026. È necessario eseguire la migrazione delle cartelle di lavoro dal Report Builder legacy al nuovo Report Builder. Il nuovo Report Builder offre un modo pratico per migrare rapidamente le cartelle di lavoro create con il Report Builder legacy.

>[!IMPORTANT]
>
>Duplicare ogni cartella di lavoro e rinominare una versione prima di convertire la cartella di lavoro legacy. In questo modo è possibile disporre sempre di una copia della cartella di lavoro legacy originale, se necessario.


>[!BEGINSHADEBOX]

Per un video dimostrativo, consulta ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Converti cartelle di lavoro](https://experienceleague.adobe.com/it/docs/analytics-learn/tutorials/exporting/report-builder/upgrade-and-reschedule-workbooks){target="_blank"}.

>[!ENDSHADEBOX]


>[!NOTE]
>
>Per convertire le cartelle di lavoro legacy, è necessario aver prima [configurato il nuovo Report Builder](/help/analyze/report-builder/report-builder-setup.md).


## Aprire una cartella di lavoro legacy

Per aprire una cartella di lavoro legacy, è possibile:

* Aprire una cartella di lavoro legacy pianificata dalla scheda **[!UICONTROL Schedule]** nell&#39;[hub Report Builder](report-builder-hub.md). Questa azione è il metodo preferito per le cartelle di lavoro legacy pianificate. È possibile utilizzare la pianificazione associata alla cartella di lavoro legacy non appena si [pianifica la cartella di lavoro legacy convertita](#schedule-a-converted-legacy-workbook).

   1. Apri [!DNL Excel] e seleziona ![AdobeLogoRedonWhite](/help/assets/icons/AdobeLogoRedOnWhite.svg) **[!UICONTROL Report Builder]** dalla barra multifunzione [!DNL Excel].

   1. Selezionare **[!UICONTROL Login]** e accedere a Report Builder.

   1. Selezionare **[!UICONTROL Schedule]** nell&#39;[hub Report Builder](report-builder-hub.md).
   1. Seleziona la scheda **[!UICONTROL Legacy]**. Nella scheda sono elencate le cartelle di lavoro pianificate legacy basate su Report Builder create dall&#39;utente.

      ![Elementi precedenti](assets/upgrade-legacy-schedule.png)

   1. Selezionare ![SelectBox](/help/assets/icons/SelectBox.svg) la cartella di lavoro pianificata da convertire dall&#39;elenco e selezionare ![Scarica](/help/assets/icons/Download.svg). La cartella di lavoro viene scaricata e si apre in una nuova finestra in [!DNL Excel]. È ora possibile [convertire la cartella di lavoro legacy di Report Builder](#convert-a--workbook).


* Aprire una cartella di lavoro legacy direttamente dal computer locale o dalla rete. Quando si utilizza questo metodo, non viene offerto di utilizzare la pianificazione che potrebbe essere associata alla cartella di lavoro legacy. <br/>Quando la cartella di lavoro legacy è aperta in [!DNL Excel]:

   1. Seleziona ![AdobeLogoRedOnWhite](/help/assets/icons/AdobeLogoRedOnWhite.svg) **[!UICONTROL Report Builder]** dalla barra multifunzione [!DNL Excel].
   1. Selezionare **[!UICONTROL Login]** e accedere a Report Builder.
   1. Quindi [convertire la cartella di lavoro legacy](#convert-a-workbook).


## Convertire una cartella di lavoro legacy

Per convertire la cartella di lavoro legacy:

1. Una volta aperta una cartella di lavoro legacy, la nuova Report Builder rileva se la cartella di lavoro contiene [richieste Report Builder](/help/analyze/legacy-report-builder/home.md) legacy.

   ![Schermata del report di aggiornamento di Report Builder [!DNL Excel] che mostra l&#39;aggiornamento della migrazione](assets/upgrade-workbook.png){zoomable="yes"}

1. Se vengono trovate una o più richieste legacy, fare clic su **[!UICONTROL Upgrade]** nella finestra di dialogo **[!UICONTROL Upgrade workbook]** per aggiornare la cartella di lavoro.

   >[!NOTE]
   >
   >È necessario aggiornare ogni richiesta singolarmente. Aggiornamento in blocco non supportato.


1. Viene visualizzata una finestra di dialogo **[!UICONTROL Warning]** che avvisa l&#39;utente delle modifiche apportate alla cartella di lavoro se si esegue l&#39;aggiornamento. Viene inoltre richiesto di creare un backup della cartella di lavoro precedente prima di procedere.

   ![Schermata del report di aggiornamento di Report Builder [!DNL Excel] che mostra l&#39;avviso di migrazione](assets/upgrade-warning.png){zoomable="yes"}

1. Fare clic su **[!UICONTROL Proceed]** per continuare con l&#39;aggiornamento.

   Se l&#39;aggiornamento ha esito positivo, viene visualizzata una notifica **[!UICONTROL The workbook upgrade is now completed]**.

   ![Schermata del report di aggiornamento di Report Builder [!DNL Excel] che mostra la migrazione completata](assets/upgrade-complete.png)

   * Selezionare **[!UICONTROL Close]** per chiudere la notifica e continuare a utilizzare la cartella di lavoro con richieste aggiornate per il nuovo Report Builder.

   * Selezionare **[!UICONTROL Download upgrade report]** per scaricare e aprire una nuova cartella di lavoro [!DNL Excel] che mostri il risultato dell&#39;aggiornamento. Per un esempio, vedi di seguito.

     ![Schermata del report di aggiornamento di Report Builder [!DNL Excel] che mostra il report di migrazione](assets/upgrade-report.png)

È ora possibile [gestire i blocchi di dati](/help/analyze/report-builder/manage-reportbuilder.md) nella cartella di lavoro. Questi blocchi di dati sono il risultato dell’aggiornamento e sostituiscono le richieste legacy di Report Builder.


## Pianificare una cartella di lavoro legacy convertita

È possibile utilizzare i dettagli della pianificazione dalla cartella di lavoro legacy scaricata e aperta dalla scheda **[!UICONTROL Schedule]** nell&#39;hub Report Builder. Questa opzione non è disponibile per le cartelle di lavoro legacy con dettagli di pianificazione aperti dal computer locale o dalla rete.

1. Per pianificare una cartella di lavoro legacy convertita con una pianificazione precedente:

   * Selezionare **[!UICONTROL Send workbook]** dall&#39;hub Report Builder oppure
   * Selezionare **[!UICONTROL Schedule workbook]** dalla scheda **[!UICONTROL Workbooks]** disponibile nella scheda **[!UICONTROL Schedules]** di Report Builder.

1. È possibile utilizzare i dettagli della pianificazione della cartella di lavoro legacy come impostazioni di pianificazione predefinite.

   ![Schermata delle [!DNL Excel] opzioni delle impostazioni di pianificazione legacy di Report Builder](assets/upgrade-legacy-schedule-convert.png)

   * Selezionare **[!UICONTROL Use]** per utilizzare i dettagli della pianificazione legacy. I dettagli della pianificazione sono precompilati nell&#39;interfaccia [Invia cartella di lavoro](schedule-reportbuilder.md#schedule-a-workbook).
   * Selezionare **[!UICONTROL Don't use]** per non utilizzare i dettagli della pianificazione legacy.
   * Seleziona **[!UICONTROL Cancel]** per annullare.

   Selezionare **[!UICONTROL Remove legacy metadata from future use]** per non utilizzare in futuro i dettagli della pianificazione legacy per questa cartella di lavoro.


## Migrazione da Report Builder legacy

Alcune funzioni della versione precedente di Report Builder non sono supportate, parzialmente supportate o implementate in modo diverso in Report Builder:

* **Richieste in tempo reale**. Le richieste in tempo reale non sono supportate e vengono rimosse dalla cartella di lavoro legacy convertita.

* **Generazione rapporti percorso/fallout**. Le richieste di abbandono non sono supportate e vengono rimosse dalla cartella di lavoro legacy convertita.

* Opzione **[!DNL FTP]per i report pianificati**. L&#39;opzione per pianificare i report da inviare a una posizione [!DNL FTP] non è più disponibile.

* **Opzione Pubblica cartella di lavoro in [!DNL Power BI] per i report pianificati**. L&#39;opzione per pianificare i report per [!DNL Power BI] non è più disponibile.

* **Metriche visitatori**. Le metriche seguenti vengono convertite in *visitatori univoci* nella cartella di lavoro legacy convertita, anche se il risultato del reporting potrebbe non corrispondere esattamente: `visitorshourly`, `visitorsdaily`, `visitorsweekly`, `visitorsmonthly`, `visitorsquarterly` e `visitorsyearly`. Questa conversione si applica anche a `mobilevisitorshourly`, `mobilevisitorsdaily`, `mobilevisitorsweekly`, `mobilevisitorsmonthly`, `mobilevisitorsquarterly` e `mobilevisitorsyearly`.

* **Riautenticazione automatica**. Quando si apre un nuovo file [!DNL Excel], è necessario autenticare di nuovo in modo esplicito. Questa nuova autenticazione è una funzionalità di protezione della funzionalità [!DNL Office Add-ins].

* **Copiare un foglio di lavoro con un gruppo di blocchi di dati**. Per supportare la copia di un foglio di lavoro contenente più blocchi di dati:

   1. Selezionare la scheda del foglio di lavoro nella cartella di lavoro [!DNL Excel] da copiare.
   1. Dal menu di scelta rapida della scheda, selezionare **[!UICONTROL Move or Copy...]**
   1. Nella finestra di dialogo **[!UICONTROL Move or Copy]** (Crea elemento dati):
      1. Selezionare la posizione in cui copiare il foglio di lavoro copiato.
      1. Assicurati di abilitare **[!UICONTROL Create a copy]**.
      1. Seleziona **[!UICONTROL OK]**.
   1. Dal foglio di lavoro di origine:
      1. Seleziona l’intervallo di celle che include tutti i blocchi di dati.
      1. Seleziona ![Copia](/help/assets/icons/Copy.svg) **[!UICONTROL Copy data block]** dall&#39;hub [Report Builder](/help/analyze/report-builder/report-builder-hub.md).
   1. Nel foglio di lavoro di destinazione:
      1. Selezionare la cella in cui si desidera incollare l&#39;intervallo di celle copiato.
      1. Seleziona ![Incolla](/help/assets/icons/Paste.svg) **[!UICONTROL Paste data block]** dall&#39;hub [Report Builder](/help/analyze/report-builder/report-builder-hub.md).

* **Intervallo date**. Report Builder non esegue la migrazione delle opzioni di formattazione dell&#39;intervallo di date **[!UICONTROL Show start and end period as]** applicate a un&#39;etichetta di riga per un intervallo di date nel Report Builder legacy.

* **Media**. Report Builder non esegue la migrazione dell&#39;opzione di formattazione selezionata **[!UICONTROL Average options]** (**[!UICONTROL Daily Average]** fino a **[!UICONTROL Yearly Average]**) applicata a una metrica nel Report Builder legacy. Utilizza una metrica calcolata per sostituire l’opzione selezionata.

* **Anteporre/posporre testo**. Report Builder non esegue la migrazione di **[!UICONTROL Prepend/postpend text]** applicato a una metrica nel Report Builder legacy.

* **Subtotali**. Report Builder non esegue la migrazione dell&#39;opzione di formattazione **[!UICONTROL SubTotal(this request)]** applicata a una metrica nel Report Builder legacy. Quando si utilizza **[!UICONTROL SubTotal(this request)]** in una richiesta di cartella di lavoro legacy, la funzionalità viene convertita in **[!UICONTROL Total]**. Ad esempio: in un blocco di dati legacy con i primi 5 nomi di pagina in cui hai utilizzato **[!UICONTROL SubTotal(Page Views)]** per restituire la somma delle visualizzazioni di pagina per i primi 5 nomi di pagina. Dopo la migrazione, lo stesso blocco di dati con i primi 5 nomi di pagina restituisce la somma delle visualizzazioni di pagina per *tutti* i nomi di pagina. Utilizzare la funzionalità delle metriche calcolate per sostituire la funzionalità legacy **[!UICONTROL SubTotal]**.
