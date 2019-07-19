---
description: Configura utenti e scopri il campionamento dei dati.
seo-description: Configura utenti e scopri il campionamento dei dati.
seo-title: Amministrazione
title: Amministrazione
uuid: 12 f 90223-139 f -4 a 8 d-bfd 3-5 cd 9 af 7489 d 2
translation-type: tm+mt
source-git-commit: 99078f95e45821bcee5017b4d480006c85f1c9e4

---


# Amministrazione

Configura utenti e scopri il campionamento dei dati.

For [!DNL Admin Console] help, see the [Analytics Reference](https://marketing.adobe.com/resources/help/en_US/reference/index.html).

## User Licenses {#concept_C1440741C77C471EB38A243B013EA620}

Prima che un utente possa effettuare l'accesso, è necessario concedere all'utente una licenza per l'utente. Le licenze utente sono licenze di uso simultaneo. Gli utenti possono condividere licenze utente, ma il numero di utenti in un determinato momento è limitato al numero di licenze acquistate.

<!-- 

c_user_license.html

 -->

Quando il numero di utenti connessi supera il numero di licenze disponibili, una finestra di dialogo notifica all'utente che tutte le licenze disponibili sono utilizzate. La posizione dell'utente nella coda viene visualizzata insieme a un collegamento per ricontrollare la posizione della coda. Quando una licenza diventa disponibile, l'utente riceve una notifica con un'e-mail e una finestra di dialogo a comparsa per indicare che l'analisi ad hoc è disponibile per l'accesso. L'utente quindi ha 15 minuti per rispondere prima di perdere la posizione nella coda.

## Grant User Licenses {#task_22AE669703EC48BA9685414538D8B1FA}

Procedura che descrive in che modo gli amministratori locali di reporting e analisi possono concedere licenze agli utenti tramite il sistema di autorizzazioni.

<!-- 

t_user_licenses.xml

 -->

1. Log in to the [!DNL Experience Cloud].
1. Click **[!UICONTROL Admin]** &gt; **[!UICONTROL User Management]**.
1. Fai clic su **[!UICONTROL Edit Groups]**.

   If your company has purchased user licenses, the [!UICONTROL Ad Hoc Analysis License Users] group appears in the [!UICONTROL Group Name] column. Viene visualizzato anche il numero di licenze disponibili per gli accessi utente.

1. Fai clic su **[!UICONTROL Edit]**.
1. Under [!UICONTROL Assign User Logins], select the users you want to add to the group, then click **[!UICONTROL Add.]**
1. Fai clic su **[!UICONTROL Save Group]**.

   Il sistema di licenza non limita il numero di utenti aggiunti a un gruppo. Esiste un utilizzo limitato per il numero di licenze acquistate dall'utente.

## Manage User Sessions {#task_868C3DD9CB3F45D19B98EEF60F5E0B32}

Procedura che descrive il modo in cui un amministratore può interrompere la sessione di un utente. Questa funzione non impedisce a un utente interrotto di effettuare nuovamente l'accesso.

<!-- 

t_managing_users.xml

 -->

1. Click **[!UICONTROL Adobe Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL User Management]**, then click **[!UICONTROL Manage Users]**.
1. Locate the user, then click **[!UICONTROL Terminate.]**

   On the [!UICONTROL Active Ad Hoc Analysis Sessions] page, the user who has been idle the longest displays at the top of list.

## Permissions {#concept_A7F2A7600BFF47C38D7C980E08D395B8}

<!-- 

c_permissions.xml

 -->

You set up access to report suites in the [!DNL Administration Console]. Puoi configurare l'autorizzazione a livello di suite di rapporti. Ad esempio, se hai abilitato più suite di rapporti, ma non vuoi concedere a tutti gli utenti l'accesso a tutte le suite di rapporti, puoi creare gruppi con suite di rapporti specifiche, e quindi assegnare tali utenti al gruppo applicabile.

## Add a User to the All Report Access Group {#task_E821BF3B4FDB434D844A98AAB15487A9}

Procedura che descrive come concedere agli utenti non amministratori l'accesso a tutte le suite di rapporti.

<!-- 

t_permissions.xml

 -->

1. Log in to the **[!UICONTROL Experience Cloud]**.
1. Click **[!UICONTROL Adobe Analytics > Admin]** &gt; **[!UICONTROL User Management]** &gt; **[!UICONTROL Edit Groups]**.
1. Fai clic su **[!UICONTROL All Report Access]**.
1. In [!UICONTROL Available Users], select the user, then click **[!UICONTROL Add.]**
1. Fai clic su **[!UICONTROL Save Group]**.

## Create Permission Groups {#task_65A4C2E58B13475B9B2606CEB93B7CBD}

Crea gruppi di autorizzazioni per utenti non amministratori per suite di rapporti specifiche.

<!-- 

t_permission_groups.xml

 -->

1. Log in to the **[!UICONTROL Experience Cloud]**.
1. Click **[!UICONTROL Adobe Analytics > Admin]** &gt; **[!UICONTROL User Management]** &gt; **[!UICONTROL Edit Groups]**.
1. Crea un gruppo di autorizzazioni per utenti non amministratori che includono le suite di rapporti attivate ad hoc che desideri rendere accessibili agli utenti.

   The report suites available to the user are displayed in the [!UICONTROL Report Cloud] menu when you create a new project.

## Set Up Proxy Policies in Java {#task_3B03F58519544025B55CF54FACF8F4F5}

Procedura che descrive come configurare i criteri proxy se si riceve un errore di connessione server.

<!-- 

t_proxy_policies.xml

 -->

Ad Hoc Analysis usa HTTP per comunicare con il server. È soggetto agli stessi criteri proxy di altri traffico HTTP.

1. In the [!DNL Windows Control Panel], launch the [!UICONTROL Java Control Panel].
1. On the **[!UICONTROL General]** tab, click **[!UICONTROL Network Settings]**.
1. Select **[!UICONTROL Use browser settings]**, or manually configure the proxy settings.
1. Click **[!UICONTROL OK]**, then click **[!UICONTROL OK]** on the [!UICONTROL Java Control Panel].

## How Data is Sampled {#concept_8433CFD38E0243849E92DF4F1E743AC3}

Esempi di dati visitatore vengono presi per produrre rapporti significativi e precisi. L'intervallo di date viene utilizzato come sezione dati per un progetto caricato. Una sezione rappresenta in genere il mese corrente e i due mesi precedenti.

<!-- 

c_overview_data_sampling.xml

 -->

Per un'elaborazione ottimale, l'analisi ad hoc usa circa 750 milioni come hit massimi per sezione. (Hit = visualizzazioni pagina + eventi.)

Per arrivare alla frequenza di campionamento prevista, gli hit proiettati vengono calcolati per set di dati, quindi dividili per 750 milioni, come illustrato:

* (Avg. hit giornalieri x numero di giorni nella sezione)/750 milioni

Ad esempio, se hai 10 milioni di hit al giorno, con una sezione di dati di 90 giorni:

* (10,000,000 x 90)/750,000,000 = 1.2

Pertanto, per mantenere il numero di hit per questa sezione di 90 giorni al di sotto del 750,000,000, i dati possono essere campionati alle 1.2:1, ma dato che sono utilizzati alcuni esempi, la frequenza di campionamento è 2:1.

Come un altro esempio, se hai 10 milioni di hit al giorno, con una sezione dati per 365 giorni:

* (10,000,000 x 365)/750,000,000 = 4.8

Pertanto, per mantenere il numero di hit per questa sezione di 365 giorni inferiori al 750,000,000, i dati possono essere campionati alle 4.8:1. Con valori interi, la frequenza di campionamento è 5:1.

>[!MORE_ LIKE_ THIS]
>
>* [Utenti](https://marketing.adobe.com/resources/help/en_US/reference/index.html?f=users)
>* [Gruppi](https://marketing.adobe.com/resources/help/en_US/reference/index.html?f=groups)

