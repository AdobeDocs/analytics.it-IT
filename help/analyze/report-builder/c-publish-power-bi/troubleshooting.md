---
description: Problemi comuni quando si utilizza l'Report Builder con Power BI.
title: Risoluzione dei problemi di integrazione di Power BI
uuid: c1e7e164-4bc6-4513-9332-92c53be021cc
translation-type: tm+mt
source-git-commit: 3aae3b00db1d7f720641ed5ccbefd8acc03460e3
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 2%

---


# Risoluzione dei problemi di integrazione di Power BI

Ricerca e risoluzione di problemi comuni quando si utilizza il Report Builder con Power BI.

## Pubblicazione in Power BI non riuscita

Le cartelle di lavoro pianificate che richiedono la pubblicazione di Power BI dipendono dal funzionamento dei servizi di Power BI. Due motivi principali per la mancata pubblicazione sono:

* I servizi di Power BI potrebbero non funzionare.
* L&#39;utente che ha pianificato la cartella di lavoro non dispone più di credenziali account Microsoft valide.

Ogni attività pianificata di Report Builder ottiene tre tentativi per esecuzione programmata:

* Dopo il primo tentativo non riuscito, riceverai il messaggio seguente: &quot;&quot;Impossibile pubblicare la cartella di lavoro pianificata in Microsoft Power BI. Riproveremo a breve.&quot;
* Dopo il secondo tentativo non riuscito, non verrà visualizzato alcun messaggio.
* Dopo il terzo tentativo non riuscito, riceverai il messaggio seguente: &quot;Impossibile pubblicare la cartella di lavoro su Power BI.&quot;

## Visualizzazioni interrotte in Power BI

Ecco i motivi principali per cui potresti ritrovarti con visualizzazioni interrotte dopo la pubblicazione delle richieste di Report Builder su Power BI:

* Avete modificato una richiesta in un Report Builder, ad esempio modificando metriche o dimensioni, e quindi ripubblicato in Power BI. Le richieste di modifica possono interrompere le visualizzazioni.
* Hai eliminato una richiesta utilizzata in una visualizzazione.

## Il Report Builder deve essere autorizzato ad accedere alle risorse aziendali. Questo accesso può essere concesso solo da un amministratore. Chiedete a un amministratore di concedervi l&#39;autorizzazione.

Chiedi a Microsoft Admin di rivedere l&#39;impostazione &quot;Gli utenti possono registrare l&#39;applicazione&quot; trovata in: **[!UICONTROL Microsoft Azure]** > **[!UICONTROL Azure Active Directory]** > **[!UICONTROL User Settings allows options]**. Se questa opzione è impostata su No, l&#39;amministratore può registrare questi tipi di applicazioni.

Gli utenti possono concedere l&#39;accesso utilizzando il seguente [collegamento](https://login.microsoftonline.com/common/oauth2/authorize?response_type=code&amp;prompt=logint&amp;client_id=8d84f6d8-29a4-4484-a670-589b32400278&amp;redirect_uri=https%3a%2f%2fmy.omniture.com%2fsc15%2farb%2flogin.html&amp;resource=https%3a%2f%2fanalysis.windows.net%2fpowerbi%2fapi&amp;locale=en_US).

Agli amministratori è stato concesso l’accesso per ogni utente utilizzando il seguente [collegamento](https://login.microsoftonline.com/common/oauth2/authorize?response_type=code&amp;prompt=admin_consent&amp;client_id=8d84f6d8-29a4-4484-a670-589b32400278&amp;redirect_uri=https%3a%2f%2fmy.omniture.com%2fsc15%2farb%2flogin.html&amp;resource=https%3a%2f%2fanalysis.windows.net%2fpowerbi%2fapi&amp;locale=en_US).
