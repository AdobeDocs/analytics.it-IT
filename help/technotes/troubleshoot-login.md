---
title: Risoluzione dei problemi di accesso ad Adobe Analytics
description: Passaggi da eseguire quando non è possibile accedere ad Adobe Analytics.
feature: Analytics Basics
exl-id: e670a043-c55b-4717-9b60-613ea4d04382
source-git-commit: c8faf29262b9b04fc426f4a26efaa8e51293f0ec
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 2%

---

# Risoluzione dei problemi di accesso ad Adobe Analytics

Adobe Analytics utilizza più metodi di autenticazione per accedere:

* Adobe ID tramite l’Experience Cloud
* ID legacy di Analytics
* Single Sign-On

**Se accedi regolarmente ad Analytics e inizi a incontrare problemi di accesso in modo casuale, la cancellazione dei cookie e della cache del browser risolve la maggior parte dei problemi.**

Talvolta, possono verificarsi problemi di disponibilità che influiscono sulla capacità di accesso. Controlla [status.adobe.com](https://status.adobe.com/it) per eventuali problemi aperti. In caso contrario, utilizza la sezione appropriata a seconda del metodo di autenticazione della tua organizzazione.

## Adobe ID

Risolvere i problemi relativi all’accesso ad Adobe Analytics utilizzando l’Experience Cloud.

1. Passa a [experience.adobe.com](https://experience.adobe.com). Se non è possibile accedere al sito, è possibile che l&#39;organizzazione non consenta l&#39;accesso al dominio tramite il firewall. Collabora con il team IT della tua organizzazione per consentirlo. Per informazioni utili da fornire al team IT, vedere [IP e domini utilizzati in Adobe Experience Cloud](https://helpx.adobe.com/it/analytics/kb/adobe-ip-addresses.html).

2. Eseguire l&#39;autenticazione tramite Adobe ID: fare clic su **[!UICONTROL Sign In with an Adobe ID]**. Se non riesci ad accedere, controlla che l&#39;indirizzo e-mail sia stato digitato correttamente. In caso contrario, fai clic su **[!UICONTROL Reset password]** e segui le istruzioni per reimpostare la password di Adobe ID.

3. Accedi ad Analytics dopo l’autenticazione: fai clic sull’icona a 9 griglie in alto a destra, quindi fai clic su Analytics. Se non disponi di questa opzione o se è disattivata, rivolgiti a un amministratore di prodotto della tua organizzazione per assicurarti di disporre delle autorizzazioni corrette per accedere ad Analytics.

## ID legacy di Analytics

Un utente dell’organizzazione può ricevere il seguente errore quando tenta di accedere:

*Come precauzione di sicurezza, questo account è stato bloccato a causa di troppi tentativi di accesso non riusciti.*

Se la cancellazione dei cookie/cache del browser non risolve il problema, rivolgiti a un amministratore Analytics della tua organizzazione per reimpostare la password dell’utente.

>[!IMPORTANT]
>
>I passaggi seguenti per reimpostare la password di un utente si applicano solo agli ID Analytics precedenti, non a Adobe ID. Se la tua organizzazione utilizza Adobe ID, puoi gestire gli account utente all&#39;indirizzo [adminconsole.adobe.com](https://adminconsole.adobe.com).

1. Accedi ad Adobe Analytics con un account dotato di diritti di amministratore.
2. Passa a **[!UICONTROL Admin]** > **[!UICONTROL All admin]** > **[!UICONTROL User management]**.
3. Fare clic sulla scheda **[!UICONTROL Users]** e quindi su **[!UICONTROL Edit]** accanto all&#39;utente desiderato.
4. Modificare la password con qualsiasi valore e selezionare la casella **[!UICONTROL Require user to change password on next login]**.
5. Informa l’utente della nuova password.

## Single Sign-On

Contattare un amministratore dell&#39;organizzazione per risolvere i problemi di accesso singolo.

## Accessi scaduti

Un utente dell’organizzazione può ricevere il seguente errore quando tenta di accedere:

*Errore: l&#39;accesso è scaduto.*

Questo errore funziona come previsto. Adobe Analytics offre agli amministratori la possibilità di impostare un intervallo di date valido per un account utente. Se la data corrente non rientra nell’intervallo di date valido per l’account, non è possibile effettuare l’accesso. Rivolgiti a un amministratore Analytics della tua organizzazione per estendere l’intervallo di date valido per l’accesso. Adobe L’Assistenza clienti non è autorizzata a modificare intervalli di date di accesso validi per gli account utente.

## Altri problemi di accesso

Se nessuno dei passaggi precedenti funziona, determina l’ampiezza del problema di accesso:

* Il problema si verifica quando si utilizza un browser diverso o si verifica in tutti i browser?
* Il problema si verifica su un computer diverso della rete o si verifica su più computer?
* Prova ad accedere utilizzando una rete diversa, ad esempio una connessione dati mobile, una libreria o una rete domestica. Il problema è presente nelle reti?

Se il problema è isolato all’interno della rete, collabora con il team IT della tua organizzazione per risolverlo. Se non è limitato a una singola rete, contatta l’Assistenza clienti Adobe.
