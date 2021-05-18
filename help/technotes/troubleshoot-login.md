---
title: Risoluzione dei problemi di accesso ad Adobe Analytics
description: Procedura da seguire quando non è possibile accedere ad Adobe Analytics.
exl-id: e670a043-c55b-4717-9b60-613ea4d04382
source-git-commit: d198e8ef0ec8415a4a555d3c385823baad6104fe
workflow-type: tm+mt
source-wordcount: '588'
ht-degree: 3%

---

# Risoluzione dei problemi di accesso ad Adobe Analytics

Adobe Analytics utilizza più metodi di autenticazione per accedere:

* Adobe ID tramite l’Experience Cloud
* ID Analytics legacy
* Single Sign-On

**Se accedi regolarmente ad Analytics e inizi a incontrare casualmente problemi di accesso, la cancellazione dei cookie e della cache del browser risolve la maggior parte dei problemi.**

A volte, problemi di disponibilità possono influire sulla capacità di accesso. Controlla [status.adobe.com](https://status.adobe.com) per eventuali problemi aperti. In caso contrario, utilizza la sezione appropriata a seconda del metodo di autenticazione dell’organizzazione.

## Adobe ID

Risolvere i problemi relativi all’accesso ad Adobe Analytics utilizzando l’Experience Cloud .

1. Passa a [experience.adobe.com](https://experience.adobe.com). Se non riesci ad accedere a questo sito, la tua organizzazione potrebbe non consentire l&#39;accesso a questo dominio attraverso il firewall. Collabora con il team IT della tua organizzazione per consentirlo. Per informazioni utili da fornire al team IT, consulta [IP e domini utilizzati in Adobe Experience Cloud](https://helpx.adobe.com/it/analytics/kb/adobe-ip-addresses.html) .

2. Autenticazione tramite Adobe ID: Fare clic su **[!UICONTROL Sign In with an Adobe ID]**. Se non riesci ad accedere, controlla che il tuo indirizzo e-mail sia stato digitato correttamente. In caso contrario, fai clic su **[!UICONTROL Reset password]** e segui le istruzioni per reimpostare la password Adobe ID.

3. Accedi ad Analytics dopo l&#39;autenticazione: Fai clic sull’icona a 9 griglie in alto a destra, quindi fai clic su Analytics. Se non disponi di questa opzione o è disattivata, collabora con un amministratore di prodotto all’interno della tua organizzazione per assicurarti di disporre delle autorizzazioni corrette per accedere ad Analytics.

## ID Analytics legacy

Un utente della tua organizzazione può ricevere il seguente errore quando tenta di accedere:

*Come precauzione di sicurezza, questo account è stato bloccato a causa di troppi tentativi di accesso non riusciti.*

Se la cancellazione dei cookie/della cache del browser non risolve il problema, rivolgiti a un amministratore Analytics della tua organizzazione per reimpostare la password dell’utente.

>[!IMPORTANT]
>
>I passaggi seguenti per reimpostare la password di un utente si applicano solo agli ID Analytics legacy, non ad Adobe ID. Se la tua organizzazione utilizza Adobe ID, puoi gestire gli account utente in [adminconsole.adobe.com](https://adminconsole.adobe.com).

1. Accedi ad Adobe Analytics con un account con diritti amministrativi.
2. Passa a **[!UICONTROL Admin]** > **[!UICONTROL All admin]** > **[!UICONTROL User management]**.
3. Fai clic sulla scheda **[!UICONTROL Users]** , quindi fai clic su **[!UICONTROL Edit]** accanto all’utente desiderato.
4. Modifica la password con qualsiasi valore e seleziona la casella **[!UICONTROL Require user to change password on next login]**.
5. Informare l&#39;utente della nuova password.

## Single Sign-On

Per risolvere i problemi relativi al single sign-on, contatta un amministratore dell’organizzazione.

## login scaduti

Un utente della tua organizzazione può ricevere il seguente errore quando tenta di accedere:

*Errore: Accesso scaduto.*

Questo errore funziona come previsto. Adobe Analytics offre agli amministratori la possibilità di impostare un intervallo di date valido per un account utente. Se la data corrente si trova al di fuori dell’intervallo di date valido per l’account, non è possibile effettuare l’accesso. Rivolgiti a un amministratore di Analytics nella tua organizzazione per estendere l’intervallo di date valido dell’accesso. L’Assistenza clienti di Adobe non è autorizzata a modificare intervalli di date di accesso validi per gli account utente.

## Altri problemi di accesso

Se nessuno dei passaggi precedenti funziona, determina l’ampiezza del problema di accesso:

* Il problema si verifica quando si utilizza un browser diverso o si verifica in tutti i browser?
* Il problema si verifica su un computer diverso della rete o si verifica su più computer?
* Prova ad accedere utilizzando una rete diversa, ad esempio una connessione dati mobile, una libreria o una rete domestica. Il problema è presente nelle reti?

Se il problema è isolato all’interno della rete, collabora con il team IT della tua organizzazione per risolverlo. Se non è limitato a una singola rete, contatta l’Assistenza clienti Adobe.
