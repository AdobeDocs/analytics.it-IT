---
title: Configurare Report Builder
description: Scopri attraverso una guida completa per installare e configurare Adobe Analytics Report Builder for Excel. Istruzioni dettagliate per la configurazione per un’integrazione perfetta.
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: 9d0161a9-ee7b-43a9-92ad-4079cf4b9c6c
source-git-commit: 1e893ce94ee3da46bbf22d7a90573681950d1135
workflow-type: tm+mt
source-wordcount: '528'
ht-degree: 1%

---

# Configurare Report Builder

Questo articolo descrive i requisiti per utilizzare Report Builder per Adobe Analytics in [!DNL Microsoft] [!DNL Excel]. Come installare e configurare il componente aggiuntivo.

## Requisiti

Report Builder per Adobe Analytics è supportato dai seguenti sistemi operativi e browser web.

### macOS

- macOS versione 10.x o successiva
- Tutte le [!DNL Microsoft] [!DNL Excel] versioni

### Windows

- Windows 10, versione 1904 o successiva
- [!DNL Excel] versione 2106 o successiva

  Per utilizzare il componente aggiuntivo, tutti gli utenti di Windows Desktop [!DNL Excel] devono installare Microsoft Edge Webview2. Per installare il controller:

   1. Vai a <https://aka.ms/webview2installer>.
   1. Selezionare e scaricare il programma di installazione autonomo Evergreen.
   1. Seguire le istruzioni di installazione.

### Ufficio web

- Supporta tutti i browser e le versioni


## Componente aggiuntivo Report Builder Excel

È necessario installare il componente aggiuntivo Report Builder [!DNL Excel] per utilizzare [!DNL Report Builder] per Adobe Analytics. Dopo aver installato il componente aggiuntivo Report Builder [!DNL Excel], è possibile accedere a Report Builder da una cartella di lavoro [!DNL Excel] aperta.

### Scaricare e installare il componente aggiuntivo Report Builder

Per scaricare e installare il componente aggiuntivo Report Builder

1. Avviare [!DNL Excel] e aprire una nuova cartella di lavoro.

1. Seleziona **[!UICONTROL Insert]** > **[!UICONTROL Get Add-ins]**.

1. Nella finestra di dialogo Componenti aggiuntivi di Office selezionare la scheda Archivio.

1. Cercare &quot;Report Builder&quot; e fare clic su **[!UICONTROL Add]**.

1. Nella finestra di dialogo Condizioni di licenza e informativa sulla privacy fare clic su **[!UICONTROL Continue]**.

**Se la scheda Store non è visualizzata**

1. In [!DNL Excel], selezionare File > Account > Gestisci impostazioni.

1. Seleziona la casella accanto a &quot;Abilita esperienze collegate facoltative&quot;

1. Riavvia [!DNL Excel].

**Se l&#39;organizzazione blocca l&#39;accesso a Microsoft Store**

- Rivolgiti al tuo team IT o di sicurezza per richiedere l’approvazione per il componente aggiuntivo Report Builder. Dopo l&#39;approvazione, nella finestra di dialogo Componenti aggiuntivi di Office selezionare la scheda **[!UICONTROL Admin Managed]**.

  ![Scheda Amministrazione gestita nella finestra di dialogo Componenti aggiuntivi di Office.](./assets/image1.png)

- In alternativa, è possibile recuperare manualmente il [file manifesto](https://reportbuilder.an.adobe.com/manifest.xml) e ospitare il file nella propria infrastruttura IT. <br/>Seguire la [documentazione in linea](https://learn.microsoft.com/en-us/office/dev/add-ins/publish/publish) di Microsoft Office per istruzioni su come installare un file manifesto di Excel non fornito da Microsoft Store.

Dopo aver installato il componente aggiuntivo Report Builder, l&#39;icona Report Builder viene visualizzata sulla barra multifunzione [!DNL Excel] nella scheda Home.

![Icona Report Builder in Excel](/help/analyze/report-builder/assets/rb_app_icon.png)

## Accedi a Report Builder

Dopo aver installato il componente aggiuntivo Report Builder for Excel per la piattaforma operativa o il browser in uso, eseguire la procedura seguente per accedere a Report Builder.

1. Aprire una cartella di lavoro di Excel.

1. Fai clic sull’icona Report Builder per avviare Report Builder.

1. Dalla barra degli strumenti di Adobe Report Builder, fare clic su **[!UICONTROL Login]**.

   ![Fare clic sul pulsante di accesso a Report Builder.](/help/analyze/report-builder/assets/rb_login.png)

1. Immetti le informazioni del tuo account Adobe Experience ID. Le informazioni sull’account devono corrispondere alle credenziali di Adobe Analytics.

   ![Icona di accesso e organizzazione.](/help/analyze/report-builder/assets/image4.png)

Dopo l’accesso, l’icona di accesso e l’organizzazione vengono visualizzate nella parte superiore del pannello

## Cambiare organizzazione

La prima volta che accedi, accedi all’organizzazione predefinita assegnata al tuo profilo.

1. Fare clic sul nome dell&#39;organizzazione visualizzata all&#39;accesso.

1. Seleziona un’organizzazione dall’elenco delle organizzazioni disponibili. Vengono elencate solo le organizzazioni a cui hai accesso.

   ![Elenco delle organizzazioni a cui è possibile accedere.](/help/analyze/report-builder/assets/image5.png)

## Uscire

Puoi uscire da Report Builder dal profilo utente.

1. Salvare le modifiche apportate alle cartelle di lavoro aperte.

1. Fai clic sull’icona dell’avatar per visualizzare il profilo utente.

   ![Avatar del tuo profilo utente e pulsante Disconnetti.](/help/analyze/report-builder/assets/image6.png)

1. Fai clic su **Esci**.
