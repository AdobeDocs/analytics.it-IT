---
title: Risoluzione dei problemi di accesso a  Adobe Analytics
description: Procedura da seguire quando non è possibile accedere a  Adobe Analytics.
translation-type: tm+mt
source-git-commit: 0870ace3fea8e3ef650d2de2960006a0d655cf9f
workflow-type: tm+mt
source-wordcount: '490'
ht-degree: 3%

---


# Risoluzione dei problemi di accesso a  Adobe Analytics

 Adobe Analytics utilizza più metodi di autenticazione per effettuare l&#39;accesso:

*  Adobe ID tramite il Experience Cloud 
* ID Analytics legacy
* Single Sign-On

**Se accedete regolarmente ad Analytics e iniziate a riscontrare problemi di accesso in modo casuale, la cancellazione dei cookie e della cache del browser risolve la maggior parte dei problemi.**

Talvolta, i problemi di disponibilità possono influire sulla capacità di accesso. Controlla [status.adobe.com](https://status.adobe.com) per eventuali incidenti aperti. In caso contrario, utilizzate la sezione appropriata in base al metodo di autenticazione dell&#39;organizzazione.

## Adobe ID

Risolvete i problemi relativi all&#39;accesso a  Adobe Analytics utilizzando l&#39;Experience Cloud .

1. Andate a [experience.adobe.com](https://experience.adobe.com/it). Se non riuscite ad accedere a questo sito, l&#39;organizzazione potrebbe non consentire l&#39;accesso a questo dominio attraverso il firewall. Collaborate con il team IT della vostra organizzazione per consentirne l&#39;utilizzo. Consulta [IP e domini utilizzati nell&#39;Adobe Experience Cloud](https://helpx.adobe.com/it/analytics/kb/adobe-ip-addresses.html) per informazioni utili da fornire al team IT.

2. Effettuare l&#39;autenticazione tramite  Adobe ID: Fate clic **[!UICONTROL Sign In with an Adobe ID]**. Se non riuscite ad accedere, verificate che l’indirizzo e-mail sia stato digitato correttamente. In caso contrario, fate clic **[!UICONTROL Reset password]** e seguite le istruzioni visualizzate per ripristinare la password Adobe ID .

3. Accesso ad Analytics dopo l&#39;autenticazione: Fai clic sull&#39;icona a 9 griglie in alto a destra, quindi fai clic su Analytics. Se non disponi di questa opzione o è disattivata, lavora con un amministratore di prodotto all&#39;interno dell&#39;organizzazione per essere certi di disporre delle autorizzazioni corrette per accedere ad Analytics.

## ID Analytics legacy

Talvolta, un utente nell’organizzazione riceve il seguente messaggio di errore al momento dell’accesso:

*Come precauzione di protezione, questo account è stato bloccato a causa di troppi tentativi di accesso non riusciti.*

Se cancellare i cookie/la cache del browser non risolve il problema, utilizzate un amministratore Analytics nella vostra organizzazione per ripristinare la password dell&#39;utente.

>[!IMPORTANT]
>
>La procedura seguente per ripristinare la password di un utente si applica solo agli ID Analytics legacy, non  Adobe ID. Se la vostra azienda utilizza  Adobe ID, potete gestire gli account utente all&#39;indirizzo [adminconsole.adobe.com](https://adminconsole.adobe.com).

1. Accedete a  Adobe Analytics con un account dotato di diritti amministrativi.
2. Passa a **[!UICONTROL Admin]** > **[!UICONTROL User Management]**.
3. Fate clic sulla **[!UICONTROL Users]** scheda, quindi fate clic **[!UICONTROL Edit]** accanto all’utente desiderato.
4. Modificate la password impostando qualsiasi valore e selezionate la casella **[!UICONTROL Require user to change password on next login]**.
5. Informa l&#39;utente della nuova password.

## Single Sign-On

Contatta un amministratore dell’organizzazione per risolvere i problemi relativi al single sign-on.

## Altri problemi di accesso

Se nessuno dei passaggi descritti sopra funziona, determina l’ampiezza del problema di accesso:

* Il problema si verifica quando si utilizza un altro browser o si verifica in tutti i browser?
* Il problema si verifica su un computer diverso della rete, o si verifica su più computer?
* Provare ad accedere utilizzando una rete diversa, ad esempio una connessione dati mobile, una libreria o una rete domestica. Il problema è presente tra le reti?

Se il problema è isolato all&#39;interno della rete, collaborate con il team IT dell&#39;organizzazione per risolverlo. Se non è limitato a una singola rete, contatta  Adobe l&#39;Assistenza clienti.
