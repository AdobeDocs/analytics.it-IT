---
description: Problemi comuni durante l’utilizzo del Report Builder con il Power BI.
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

Ricercare e risolvere i problemi comuni quando si utilizza il Report Builder con il Power BI.

## Pubblicazione su Power BI non riuscita

Le cartelle di lavoro pianificate che richiedono la pubblicazione dei Power BI dipendono dall&#39;operatività dei servizi di Power BI. Due motivi principali della mancata pubblicazione sono:

* I servizi di Power BI potrebbero essere inattivi.
* L&#39;utente che ha pianificato la cartella di lavoro non dispone più di credenziali di account Microsoft valide.

Ogni attività pianificata del Report Builder ottiene tre tentativi per esecuzione pianificata:

* Dopo il primo tentativo non riuscito, verrà visualizzato il seguente messaggio: &quot;Non è stato possibile pubblicare la cartella di lavoro pianificata in Microsoft Power BI. Riproveremo a breve.&quot;
* Dopo il secondo tentativo non riuscito, non riceverai alcun messaggio.
* Dopo il terzo tentativo non riuscito, verrà visualizzato il seguente messaggio: &quot;Non è stato possibile pubblicare la cartella di lavoro in Power BI&quot;.

## Visualizzazioni interrotte in Power BI

Di seguito sono elencati i principali motivi per cui potresti ritrovarti con visualizzazioni interrotte dopo la pubblicazione delle richieste di Power BI del Report Builder:

* Hai modificato una richiesta in Report Builder, ad esempio modificando metriche o dimensioni, e quindi l’hai ripubblicata in Power BI. La modifica delle richieste può interrompere le visualizzazioni.
* Hai eliminato una richiesta utilizzata in una visualizzazione.

## Il Report Builder deve essere autorizzato ad accedere alle risorse della tua organizzazione. Questo accesso può essere concesso solo da un amministratore. Chiedi a un amministratore di concederti l’autorizzazione.

Chiedi a un amministratore di Microsoft di verificare l’impostazione &quot;Users can register application&quot; (Gli utenti possono registrare l’applicazione) presente in: **[!UICONTROL Microsoft Azure]** > **[!UICONTROL Azure Active Directory]** > **[!UICONTROL User Settings allows options]**. Se questa opzione è impostata su No, l’amministratore può registrare questi tipi di applicazioni.

Gli utenti possono concedere l’accesso utilizzando quanto segue [link](https://login.microsoftonline.com/common/oauth2/authorize?response_type=code&amp;prompt=logint&amp;client_id=8d84f6d8-29a4-4484-a670-589b32400278&amp;redirect_uri=https%3a%2f%2fmy.omniture.com%2fsc15%2farb%2flogin.html&amp;resource=https%3a%2f%2fanalysis.windows.net%2fpowerbi%2fapi&amp;locale=en_US).

Gli amministratori a cui è concesso l’accesso per ciascuno di essi utilizzano quanto segue [link](https://login.microsoftonline.com/common/oauth2/authorize?response_type=code&amp;prompt=admin_consent&amp;client_id=8d84f6d8-29a4-4484-a670-589b32400278&amp;redirect_uri=https%3a%2f%2fmy.omniture.com%2fsc15%2farb%2flogin.html&amp;resource=https%3a%2f%2fanalysis.windows.net%2fpowerbi%2fapi&amp;locale=en_US).

## Raggiungimento del limite API

La generazione di rapporti in Power BI funziona con l’API di reporting di Analytics, pertanto si applicano i limiti di soglia API. Per ulteriori informazioni, consulta [Codici di errore dei servizi Web](https://github.com/AdobeDocs/analytics-1.4-apis/blob/3dda746890743c2098256719d6595109b7748262/docs/getting-started/c_Web_Services_Error_Codes.md).
