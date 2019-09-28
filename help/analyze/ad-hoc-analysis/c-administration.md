---
description: Configura gli utenti e scopri ulteriori informazioni sul campionamento dei dati.
seo-description: Configura gli utenti e scopri ulteriori informazioni sul campionamento dei dati.
seo-title: Amministrazione
title: Amministrazione
uuid: 12f90223-139f-4a8d-bfd3-5cd9af7489d2
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# Amministrazione

Configura gli utenti e scopri ulteriori informazioni sul campionamento dei dati.

Per [!DNL Admin Console] assistenza, consulta [Analytics Reference](https://marketing.adobe.com/resources/help/en_US/reference/index.html).

## Licenze utente {#concept_C1440741C77C471EB38A243B013EA620}

Prima che un utente possa effettuare l’accesso, all’utente deve essere concessa una licenza. Le licenze utente sono licenze per uso simultaneo. Gli utenti possono condividere le licenze utente, ma il numero di utenti in un dato momento è limitato al numero di licenze utente acquistate.

<!-- 

c_user_license.html

 -->

Quando il numero di utenti connessi supera il numero di licenze disponibili, una finestra di dialogo notifica all'utente che tutte le licenze disponibili sono in uso. La posizione dell'utente nella coda viene visualizzata insieme a un collegamento per controllare nuovamente la posizione della coda. Quando una licenza diventa disponibile, all'utente viene inviata una notifica tramite e-mail e una finestra di dialogo a comparsa che indica che l'analisi ad hoc è disponibile per l'accesso. L'utente ha quindi 15 minuti per rispondere prima di perdere la posizione nella coda.

## Concedi licenze utente {#task_22AE669703EC48BA9685414538D8B1FA}

Procedura che descrive come gli amministratori di Reporting e analisi locali possono concedere licenze agli utenti tramite il sistema di autorizzazioni.

<!-- 

t_user_licenses.xml

 -->

1. Log in to the [!DNL Experience Cloud].
1. Clic **[!UICONTROL Admin]** &gt; **[!UICONTROL User Management]**.
1. Fai clic su **[!UICONTROL Edit Groups]**.

   Se la società ha acquistato licenze utente, il [!UICONTROL Ad Hoc Analysis License Users] gruppo viene visualizzato nella [!UICONTROL Group Name] colonna. Viene inoltre visualizzato il numero di licenze disponibili per gli accessi utente.

1. Fai clic su **[!UICONTROL Edit]**.
1. In [!UICONTROL Assign User Logins], selezionate gli utenti che desiderate aggiungere al gruppo, quindi fate clic su **[!UICONTROL Add.]**
1. Fai clic su **[!UICONTROL Save Group]**.

   Il sistema di licenze non limita il numero di utenti che vengono aggiunti a un gruppo. L'utilizzo simultaneo è limitato al numero di licenze utente acquistate.

## Gestisci sessioni utente {#task_868C3DD9CB3F45D19B98EEF60F5E0B32}

Procedura che descrive in che modo un amministratore può terminare la sessione di un utente. Questa funzione non impedisce a un utente terminato di effettuare nuovamente l'accesso.

<!-- 

t_managing_users.xml

 -->

1. Fate clic **[!UICONTROL Adobe Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL User Management]**, quindi fate clic su **[!UICONTROL Manage Users]**.
1. Individuate l'utente, quindi fate clic su **[!UICONTROL Terminate.]**

   Sulla [!UICONTROL Active Ad Hoc Analysis Sessions] pagina, l’utente che è rimasto inattivo più a lungo viene visualizzato nella parte superiore dell’elenco.

## Autorizzazioni {#concept_A7F2A7600BFF47C38D7C980E08D395B8}

<!-- 

c_permissions.xml

 -->

Puoi impostare l’accesso alle suite di rapporti nel [!DNL Administration Console]. Puoi configurare le autorizzazioni a livello di suite di rapporti. Ad esempio, se disponete di più suite di rapporti abilitate, ma non desiderate consentire a tutti gli utenti l'accesso a tutte le suite di rapporti, potete creare gruppi con suite di rapporti specifiche e quindi assegnare tali utenti al gruppo applicabile.

## Aggiunta di un utente al gruppo di accesso a tutti i rapporti {#task_E821BF3B4FDB434D844A98AAB15487A9}

Procedura che descrive come concedere agli utenti non amministratori l’accesso a tutte le suite di rapporti.

<!-- 

t_permissions.xml

 -->

1. Log in to the **[!UICONTROL Experience Cloud]**.
1. Clic **[!UICONTROL Adobe Analytics > Admin]** &gt; **[!UICONTROL User Management]** &gt; **[!UICONTROL Edit Groups]**.
1. Fai clic su **[!UICONTROL All Report Access]**.
1. In [!UICONTROL Available Users], selezionate l’utente e fate clic su **[!UICONTROL Add.]**
1. Fai clic su **[!UICONTROL Save Group]**.

## Crea gruppi di autorizzazioni {#task_65A4C2E58B13475B9B2606CEB93B7CBD}

Creazione di gruppi di autorizzazioni per utenti non amministratori per suite di rapporti specifiche.

<!-- 

t_permission_groups.xml

 -->

1. Log in to the **[!UICONTROL Experience Cloud]**.
1. Clic **[!UICONTROL Adobe Analytics > Admin]** &gt; **[!UICONTROL User Management]** &gt; **[!UICONTROL Edit Groups]**.
1. Create un gruppo di autorizzazioni per gli utenti non amministratori che includa le suite di rapporti attivate dall'analisi ad hoc e che desiderate rendere accessibili agli utenti.

   Le suite di rapporti disponibili per l'utente vengono visualizzate nel [!UICONTROL Report Cloud] menu quando create un nuovo progetto.

## Configurare i criteri proxy in Java {#task_3B03F58519544025B55CF54FACF8F4F5}

Procedura che descrive come impostare i criteri proxy in caso di errore di connessione al server.

<!-- 

t_proxy_policies.xml

 -->

Ad Hoc Analysis utilizza HTTP per comunicare con il server. È soggetta alle stesse policy proxy del traffico HTTP.

1. In [!DNL Windows Control Panel], avviate il [!UICONTROL Java Control Panel].
1. Nella **[!UICONTROL General]** scheda fare clic su **[!UICONTROL Network Settings]**.
1. Selezionate **[!UICONTROL Use browser settings]** o configurate manualmente le impostazioni proxy.
1. Fate clic **[!UICONTROL OK]**, quindi fate clic **[!UICONTROL OK]** sul [!UICONTROL Java Control Panel].

## Esempio dei dati {#concept_8433CFD38E0243849E92DF4F1E743AC3}

Esempi di dati dei visitatori vengono prelevati per generare rapporti significativi e precisi. L'intervallo di date viene utilizzato come sezione di dati per un progetto caricato. Una sezione rappresenta in genere il mese corrente più i due mesi precedenti.

<!-- 

c_overview_data_sampling.xml

 -->

Per un'elaborazione ottimale, l'analisi ad hoc utilizza circa 750 milioni di hit come hit massimo per sezione. (Hit = visualizzazioni pagina + eventi.)

Per ottenere il tasso di campionamento previsto, gli hit proiettati sono calcolati per set di dati, quindi suddivisi per 750 milioni, come illustrato:

* (Media. hit giornalieri x numero di giorni nella fetta) / 750 milioni

Ad esempio, se hai 10 milioni di hit al giorno, con una sezione di dati di 90 giorni:

* (10.000.000 x 90) / 750.000.000 = 1,2

Per mantenere il numero di hit per questa sezione di 90 giorni al di sotto di 750.000.000, i dati potrebbero essere campionati a 1.2:1, ma poiché si utilizzano campioni su numeri interi, la frequenza di campionamento è 2:1.

Ad esempio, se hai 10 milioni di hit al giorno, con una sezione dati per 365 giorni:

* (10.000.000 x 365) / 750.000.000 = 4,8

Per mantenere il numero di hit per questa sezione di 365 giorni al di sotto di 750.000.000, i dati potrebbero essere campionati a 4,8:1. Utilizzando numeri interi, la frequenza di campionamento è di 5:1.

>[!MORE_LIKE_THIS]
>
>* [Utenti](https://marketing.adobe.com/resources/help/en_US/reference/users.html)
>* [Gruppi](https://marketing.adobe.com/resources/help/en_US/reference/groups.html)

