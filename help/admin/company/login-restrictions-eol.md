---
title: Fine del ciclo di vita per [!UICONTROL Applica restrizioni di accesso IP]
description: Scopri i tempi di fine ciclo di vita e le implicazioni per [!UICONTROL Applica le restrizioni di accesso IP]
translation-type: tm+mt
source-git-commit: 67dd053b71a2e718539956fbfe775f782ec26557
workflow-type: tm+mt
source-wordcount: '531'
ht-degree: 1%

---


# Fine del ciclo di vita [!UICONTROL Enforce IP login restrictions]

La funzione **[Applica restrizioni](/help/admin/company/security-manager.md)**di accesso IP in Adobe Analytics consente di aggiungere indirizzi IP specifici (considerati sicuri) a un elenco &quot;consentito&quot;, in modo da consentire l’accesso e l’accesso all’ambiente Adobe Analytics. In molti casi, questa funzione viene utilizzata per impostare un indirizzo IP aziendale come unico indirizzo IP protetto da cui gli utenti possono accedere. Pertanto, per utilizzare Adobe Analytics, questo richiede che gli utenti si trovino in un ufficio aziendale o che accedano alla rete tramite VPN.

Stiamo pianificando di terminare il ciclo di vita di questa funzione nel mese di gennaio 2021.

## Perché stiamo terminando questa funzione?

Questa funzione viene interrotta in alcune circostanze dalla migrazione dell&#39;accesso a Experience Cloud e/o dall&#39;accesso a Experience Cloud. È noto per interrompere per i clienti che utilizzano **[!UICONTROL Customer Attributes]** o **[!UICONTROL Audience Library]**.

Inoltre, se disponi di più soluzioni Experience Cloud, puoi eludere questo requisito effettuando l&#39;accesso a Experience Cloud con una delle altre soluzioni, in quanto questa funzione non esiste o non è supportata al di fuori di Analytics stesso. Gli utenti potrebbero anche aggirare questo problema tramite lo spoofing IP.

Infine, Adobe dispone di una soluzione alternativa efficiente e di gran lunga superiore tramite Single Sign-On e Federated ID. Questa funzione offre maggiore controllo e sicurezza sull’esperienza di accesso degli utenti. Per ulteriori informazioni, vedi sotto.

## In che modo la rimozione di questa funzione ha un impatto su di te?

Per tutti i clienti che hanno **[!UICONTROL Enforce IP login restrictions]** configurato questa funzione, questa verrà rimossa a gennaio 2021. In quel momento, eventuali restrizioni di accesso IP ancora in vigore non saranno più applicate. Se devi comunque limitare l’accesso per indirizzo IP, consulta e implementa la soluzione consigliata per ID Single Sign-On e Federated ID (ulteriori informazioni e risorse di seguito).

Inoltre, l&#39; **[!UICONTROL Enforce IP login restrictions]** impostazione verrà rimossa dall&#39; **[!UICONTROLAamministratore > Impostazioni società > Gestione]** sicurezza nell&#39;interfaccia utente di Analytics (come mostrato di seguito).

![](assets/sec-manager2.png)

## Quali sono le altre opzioni?

Come già detto, questa funzione di Analytics terminerà. Per darti il tempo di implementare SSO e Federated ID, abbiamo posticipato la data EOL a gennaio 2021.

Sia SSO che Federated ID sono soluzioni superiori alla funzione Limitazione di accesso IP che abbiamo già installato oggi e vi fornirà maggiore controllo, sicurezza e funzionalità. Per informazioni su come impostare SSO/Federated ID, è disponibile la seguente documentazione di aiuto. Consigliamo di leggerli accuratamente e di collaborare con il reparto IT per implementarli:

* [Single Sign-On e Experience Cloud](https://spark.adobe.com/page/JeSB8EPEQIvjD/)
* [Admin Console - Documentazione di impostazione identità](https://helpx.adobe.com/it/enterprise/using/set-up-identity.html)
* [Admin Console - Esercitazione sull’impostazione dell’identità (video)](https://helpx.adobe.com/enterprise/how-to/identity-directories-domains.html?playlist=/ccx/v1/collection/product/enterprise/topics/enterprise-identity/collection.ccx.js&amp;ref=helpx.adobe.com)
* [Configurare l’esercitazione Federated ID (video)](https://helpx.adobe.com/enterprise/how-to/identity-configure-ids.html?playlist=/ccx/v1/collection/product/enterprise/topics/enterprise-identity/collection.ccx.js&amp;ref=helpx.adobe.com)
* [Single Sign-On - Domande frequenti](https://helpx.adobe.com/enterprise/using/sso-faq.html)
* [Tipi di identità supportati da Adobe](https://helpx.adobe.com/it/enterprise/using/identity.html)

Se desiderate continuare a supportare le restrizioni di accesso IP e richiedete che siano fornite da Experience Cloud, potete votare questa funzione nella nostra pagina [](https://forums.adobe.com/ideas/11648)Forum.