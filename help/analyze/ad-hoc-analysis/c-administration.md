---
description: Configura gli utenti e scopri ulteriori informazioni sul campionamento dei dati.
title: Amministrazione
uuid: 12f90223-139f-4a8d-bfd3-5cd9af7489d2
translation-type: tm+mt
source-git-commit: d4cb2acb4ecaecce3644a2f3cf29913440e5cd6a
workflow-type: tm+mt
source-wordcount: '711'
ht-degree: 98%

---


# Amministrazione

>[!IMPORTANT]
>
> Adobe sta spostando  Ad Hoc Analysis a fine ciclo di vita il 1 marzo 2021. [Ulteriori informazioni...](https://adobe.ly/discoverworkspace).

Configura gli utenti e scopri ulteriori informazioni sul campionamento dei dati.

Per [!DNL Admin Console] assistenza, consulta [Analytics Reference](https://docs.adobe.com/content/help/it-IT/analytics/landing/home.html).

## Licenze utente {#concept_C1440741C77C471EB38A243B013EA620}

È necessario concedere una licenza all’utente prima che questo possa effettuare l’accesso. Le licenze utente sono licenze di utilizzo simultaneo. Gli utenti possono condividere le licenze utente, ma il numero di utenti in un dato momento è limitato al numero di licenze utente acquistate.

<!-- 

c_user_license.html

 -->

Quando il numero di utenti connessi supera il numero di licenze disponibili, una finestra di dialogo notifica all’utente che tutte le licenze disponibili sono in uso. La posizione dell’utente in coda viene visualizzata insieme a un collegamento per controllare nuovamente la posizione in coda. Quando una licenza diventa disponibile, all’utente viene inviata una notifica tramite e-mail e una finestra di dialogo a comparsa che indica che Ad Hoc Analysis è disponibile per l’accesso. L’utente ha quindi 15 minuti per rispondere prima di perdere la posizione nella coda.

## Concessione delle licenze utente {#task_22AE669703EC48BA9685414538D8B1FA}

Procedura che descrive come gli amministratori di Reports and Analytics locali possono concedere licenze agli utenti tramite il sistema di autorizzazioni.

<!-- 

t_user_licenses.xml

 -->

1. Accedi a [!DNL Experience Cloud].
1. Fai clic su **[!UICONTROL Admin]** > **[!UICONTROL User Management]**.
1. Fai clic su **[!UICONTROL Edit Groups]**.

   Se la società ha acquistato licenze utente, il gruppo [!UICONTROL Ad Hoc Analysis License Users] viene visualizzato nella colonna [!UICONTROL Group Name]. Viene inoltre visualizzato il numero di licenze disponibili per gli accessi utente.

1. Fai clic su **[!UICONTROL Edit]**.
1. In [!UICONTROL Assign User Logins], seleziona gli utenti che desideri aggiungere al gruppo, quindi fai clic su **[!UICONTROL Add.]**
1. Fai clic su **[!UICONTROL Save Group]**.

   Il sistema di licenze non limita il numero di utenti che vengono aggiunti a un gruppo. L’utilizzo simultaneo è limitato al numero di licenze utente acquistate.

## Gestione delle sessioni utente {#task_868C3DD9CB3F45D19B98EEF60F5E0B32}

Procedura che descrive in che modo un amministratore può terminare una sessione utente. Questa funzione non impedisce a un utente per cui è stata terminata la sessione di effettuare nuovamente l’accesso.

<!-- 

t_managing_users.xml

 -->

1. Fai clic su **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL User Management]**, quindi su **[!UICONTROL Manage Users]**.
1. Individua l’utente, quindi fai clic su **[!UICONTROL Terminate.]**

   Sulla pagina [!UICONTROL Active Ad Hoc Analysis Sessions], l’utente che è rimasto inattivo più a lungo viene visualizzato nella parte superiore dell’elenco.

## Autorizzazioni {#concept_A7F2A7600BFF47C38D7C980E08D395B8}

<!-- 

c_permissions.xml

 -->

Puoi impostare l’accesso alle suite di report in [!DNL Administration Console]. Puoi configurare le autorizzazioni a livello di suite di report. Ad esempio, se disponi di più suite di report abilitate, ma non desideri consentire a tutti gli utenti l’accesso a tutte le suite di rapporti, puoi creare gruppi con suite di rapporti specifiche e quindi assegnare tali utenti al gruppo appropriato.

## Aggiunta di un utente al gruppo Accesso a tutti i report {#task_E821BF3B4FDB434D844A98AAB15487A9}

Procedura che descrive come concedere agli utenti non amministratori l’accesso a tutte le suite di report.

<!-- 

t_permissions.xml

 -->

1. Accedi a **[!UICONTROL Experience Cloud]**.
1. Fai clic su **[!UICONTROL Adobe Analytics > Admin]** > **[!UICONTROL User Management]** > **[!UICONTROL Edit Groups]**.
1. Fai clic su **[!UICONTROL All Report Access]**.
1. In [!UICONTROL Available Users], seleziona l’utente e fai clic su **[!UICONTROL Add.]**
1. Fai clic su **[!UICONTROL Save Group]**.

## Creazione di gruppi di autorizzazioni {#task_65A4C2E58B13475B9B2606CEB93B7CBD}

Creazione di gruppi di autorizzazioni per utenti non amministratori per suite di report specifiche.

<!-- 

t_permission_groups.xml

 -->

1. Accedi a **[!UICONTROL Experience Cloud]**.
1. Fai clic su **[!UICONTROL Adobe Analytics > Admin]** > **[!UICONTROL User Management]** > **[!UICONTROL Edit Groups]**.
1. Crea un gruppo di autorizzazioni per gli utenti non amministratori che includa le suite di report attivate dall’analisi ad hoc che desideri rendere accessibili agli utenti.

   Le suite di report disponibili per l’utente vengono visualizzate nel menu [!UICONTROL Report Cloud] quando crei un nuovo progetto.

## Configurazione dei criteri proxy in Java {#task_3B03F58519544025B55CF54FACF8F4F5}

Procedura che descrive come impostare i criteri proxy in caso di errore di connessione al server.

<!-- 

t_proxy_policies.xml

 -->

Ad Hoc Analysis utilizza HTTP per comunicare con il server. È soggetta agli stessi criteri proxy del traffico HTTP.

1. Nel [!DNL Windows Control Panel], avvia il [!UICONTROL Java Control Panel].
1. Nella scheda **[!UICONTROL General]** fai clic su **[!UICONTROL Network Settings]**.
1. Seleziona **[!UICONTROL Use browser settings]** o configura manualmente le impostazioni proxy.
1. Fa clic su **[!UICONTROL OK]**, quindi fai clic su **[!UICONTROL OK]** sul [!UICONTROL Java Control Panel].

## Campionamento dei dati{#concept_8433CFD38E0243849E92DF4F1E743AC3}

Campioni di dati dei visitatori vengono acquisiti per generare report significativi e precisi. L’intervallo di dati viene utilizzato come sezione di dati per un progetto caricato. Una sezione rappresenta in genere il mese corrente più i due mesi precedenti.

<!-- 

c_overview_data_sampling.xml

 -->

Per un’elaborazione ottimale, l’analisi ad hoc utilizza circa 750 milioni di hit come hit massimi per sezione. (Hit = visualizzazioni pagina + eventi.)

Per ottenere il tasso di campionamento previsto, gli hit previsti sono calcolati per set di dati, quindi suddivisi per 750 milioni, come illustrato di seguito:

* (Media di hit giornalieri x numero di giorni nella sezione) / 750 milioni

Ad esempio, se ci sono 10 milioni di hit al giorno, con una sezione di dati di 90 giorni:

* (10.000.000 x 90) / 750.000.000 = 1,2

Per mantenere il numero di hit per questa sezione di 90 giorni al di sotto di 750.000.000, i dati potrebbero essere campionati a 1,2:1, ma poiché si utilizzano campioni su numeri interi, la frequenza di campionamento è 2:1.

Ad esempio, se hai 10 milioni di hit al giorno, con una sezione dati per 365 giorni:

* (10.000.000 x 365) / 750.000.000 = 4,8

Per mantenere il numero di hit per questa sezione di 365 giorni al di sotto di 750.000.000, i dati potrebbero essere campionati a 4,8:1. Utilizzando numeri interi, la frequenza di campionamento è di 5:1.
