---
description: Problemi comuni quando si utilizza il Report Builder con Power BI.
title: Risoluzione dei problemi di integrazione di Power BI
feature: Report Builder
role: User, Admin
exl-id: adb13a0e-99fb-48f5-add2-204d155e467f
source-git-commit: f6f65f34c4d8caf04eb3ea47108e36e5b9adf24f
workflow-type: tm+mt
source-wordcount: '405'
ht-degree: 1%

---

# Risoluzione dei problemi di integrazione di Power BI

Ricercare e risolvere i problemi comuni quando si utilizza il Report Builder con Power BI.

## Mancata pubblicazione in Power BI

Le cartelle di lavoro pianificate che richiedono la pubblicazione di Power BI dipendono dal funzionamento dei servizi Power BI. Due motivi principali dell’omessa pubblicazione sono:

* I servizi di Power BI potrebbero non essere disponibili.
* L&#39;utente che ha pianificato la cartella di lavoro non dispone più di credenziali account Microsoft valide.

A ogni attività pianificata del Report Builder vengono assegnati tre tentativi per esecuzione pianificata:

* Dopo il primo tentativo non riuscito, riceverai questo messaggio: &quot;&quot;Impossibile pubblicare la cartella di lavoro pianificata in Microsoft Power BI. Riproveremo tra breve.&quot;
* Dopo il secondo tentativo non riuscito, non riceverai alcun messaggio.
* Dopo il terzo tentativo non riuscito, riceverai questo messaggio: &quot;Impossibile pubblicare la cartella di lavoro in Power BI.&quot;

## Visualizzazioni interrotte in Power BI

Ecco i motivi principali per cui potresti ritrovarti con visualizzazioni interrotte dopo aver pubblicato le richieste dei Report Builder su Power BI:

* È stata modificata una richiesta in un Report Builder, ad esempio la modifica di metriche o dimensioni e quindi ripubblicata in Power BI. La modifica delle richieste può interrompere le visualizzazioni.
* Hai eliminato una richiesta utilizzata in una visualizzazione.

## Il Report Builder deve essere autorizzato ad accedere alle risorse dell&#39;organizzazione. Questo accesso può essere concesso solo da un amministratore. Chiedi a un amministratore di concederti l&#39;autorizzazione.

Chiedi a un amministratore Microsoft di rivedere l&#39;impostazione &quot;Gli utenti possono registrare l&#39;applicazione&quot; trovata in: **[!UICONTROL Microsoft Azure]** > **[!UICONTROL Azure Active Directory]** > **[!UICONTROL User Settings allows options]**. Se questa opzione è impostata su No, l’amministratore può registrare questi tipi di applicazioni.

Gli utenti possono concedere l&#39;accesso utilizzando i seguenti [collegamento](https://login.microsoftonline.com/common/oauth2/authorize?response_type=code&amp;prompt=logint&amp;client_id=8d84f6d8-29a4-4484-a670-589b32400278&amp;redirect_uri=https%3a%2f%2fmy.omniture.com%2fsc15%2farb%2flogin.html&amp;resource=https%3a%2f%2fanalysis.windows.net%2fpowerbi%2fapi&amp;locale=en_US).

Gli amministratori hanno concesso l’accesso per ciascuno di essi utilizzando i seguenti [collegamento](https://login.microsoftonline.com/common/oauth2/authorize?response_type=code&amp;prompt=admin_consent&amp;client_id=8d84f6d8-29a4-4484-a670-589b32400278&amp;redirect_uri=https%3a%2f%2fmy.omniture.com%2fsc15%2farb%2flogin.html&amp;resource=https%3a%2f%2fanalysis.windows.net%2fpowerbi%2fapi&amp;locale=en_US).

## Raggiungere il limite API

Il reporting in Power BI funziona con l’API di reporting di Analytics, pertanto si applicano i limiti di soglia API. Per ulteriori informazioni consulta [Codici di errore dei servizi web](https://github.com/AdobeDocs/analytics-1.4-apis/blob/3dda746890743c2098256719d6595109b7748262/docs/getting-started/c_Web_Services_Error_Codes.md).
