---
description: Problemi comuni quando si utilizza Report Builder con Power BI.
title: Risoluzione dei problemi di integrazione di Power BI
feature: Report Builder
role: User, Admin
exl-id: adb13a0e-99fb-48f5-add2-204d155e467f
source-git-commit: 73c0210ac931f3e7f823e033a3bffdc22e159ddb
workflow-type: tm+mt
source-wordcount: '311'
ht-degree: 2%

---

# Risoluzione dei problemi di integrazione di Power BI

{{legacy-arb}}

Cerca e risolvi i problemi comuni quando utilizzi Report Builder con Power BI.

## Pubblicazione su Power BI non riuscita

Le cartelle di lavoro pianificate che richiedono la pubblicazione in Power BI dipendono dai servizi Power BI per essere operativi. Due motivi principali della mancata pubblicazione sono:

* I servizi Power BI potrebbero non essere disponibili.
* L&#39;utente che ha pianificato la cartella di lavoro non dispone più di credenziali di account Microsoft valide.

Ogni attività pianificata di Report Builder ottiene tre tentativi per esecuzione pianificata:

* Dopo il primo tentativo non riuscito, verrà visualizzato il seguente messaggio: &quot;Impossibile pubblicare la cartella di lavoro pianificata in Microsoft Power BI. Riproveremo a breve.&quot;
* Dopo il secondo tentativo non riuscito, non riceverai alcun messaggio.
* Dopo il terzo tentativo non riuscito, verrà visualizzato il seguente messaggio: &quot;Non è stato possibile pubblicare la cartella di lavoro in Power BI&quot;.

## Visualizzazioni interrotte in Power BI

Di seguito sono elencati i principali motivi per cui potresti ritrovarti con visualizzazioni interrotte dopo la pubblicazione delle richieste di Report Builder in Power BI:

* Hai modificato una richiesta in Report Builder, ad esempio modificando metriche o dimensioni, e quindi l’hai ripubblicata in Power BI. La modifica delle richieste può interrompere le visualizzazioni.
* Hai eliminato una richiesta utilizzata in una visualizzazione.

>[!IMPORTANT]
>
>Report Builder richiede un amministratore per autorizzare l’accesso alle risorse della tua organizzazione. Se hai bisogno di accedere, chiedi a un amministratore di concederti l’autorizzazione.
>&#x200B;> Un amministratore di Microsoft può esaminare l&#39;impostazione *Gli utenti possono registrare l&#39;applicazione* trovata in: **[!UICONTROL Microsoft Azure]** > **[!UICONTROL Azure Active Directory]** > **[!UICONTROL User Settings allows options]**. Se questa opzione è impostata su **No**, l&#39;amministratore può registrare questi tipi di applicazioni.

Gli utenti possono concedere l&#39;accesso accedendo al proprio [account Microsoft Power BI](https://login.microsoftonline.com/common/oauth2/authorize?response_type=code&prompt=logint&client_id=8d84f6d8-29a4-4484-a670-589b32400278&redirect_uri=https%3a%2f%2fmy.omniture.com%2fsc15%2farb%2flogin.html&resource=https%3a%2f%2fanalysis.windows.net%2fpowerbi%2fapi&locale=en_US).

Gli amministratori possono concedere l&#39;accesso a ogni account effettuando l&#39;accesso all&#39;account Microsoft Power BI [dell&#39;amministratore](https://login.microsoftonline.com/common/oauth2/authorize?response_type=code&prompt=admin_consent&client_id=8d84f6d8-29a4-4484-a670-589b32400278&redirect_uri=https%3a%2f%2fmy.omniture.com%2fsc15%2farb%2flogin.html&resource=https%3a%2f%2fanalysis.windows.net%2fpowerbi%2fapi&locale=en_US).

## Raggiungimento del limite API

Il reporting in Power BI funziona con l’API di reporting di Analytics, pertanto si applicano i limiti di soglia API.
