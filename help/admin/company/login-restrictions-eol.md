---
title: Terminazione di [!UICONTROL Enforce IP login restrictions]
description: Scopri la tempistica e le implicazioni per [!UICONTROL Enforce IP login restrictions]
exl-id: 67d822ee-005b-46cf-80b4-a5aa4412d746
source-git-commit: d198e8ef0ec8415a4a555d3c385823baad6104fe
workflow-type: tm+mt
source-wordcount: '515'
ht-degree: 1%

---

# Terminazione di [!UICONTROL Enforce IP login restrictions]

La funzione **[Applica restrizioni di accesso IP](/help/admin/company/security-manager.md)** in Adobe Analytics consente di aggiungere a un inserire nell&#39;elenco Consentiti indirizzi IP specifici (ritenuti sicuri), in modo da consentire accessi e accesso efficaci all’ambiente Adobe Analytics. In molti casi, questa funzione viene utilizzata per impostare un indirizzo IP aziendale come l’unico indirizzo IP sicuro da cui gli utenti possono effettuare l’accesso. Pertanto, per utilizzare Adobe Analytics, questo richiede agli utenti di essere in un ufficio aziendale o di accedere alla rete tramite VPN.

Stiamo pianificando la fine di questa funzione a gennaio 2021.

## Perché terminiamo questa funzione?

Questa funzione è interrotta in alcune circostanze dalla migrazione dell’accesso di Experience Cloud e/o dall’accesso di Experience Cloud. È noto per interrompere i clienti che utilizzano **[!UICONTROL Customer Attributes]** o **[!UICONTROL Audience Library]**.

Inoltre, se possiedi più soluzioni Experience Cloud, puoi soddisfare questo requisito accedendo all’Experience Cloud con una delle altre soluzioni, in quanto questa funzione non esiste o non è supportata al di fuori di Analytics stesso. Gli utenti possono anche aggirare questo problema tramite spoofing IP.

Infine, Adobe dispone di una soluzione alternativa funzionante e di gran lunga superiore tramite Single-Sign-On e Federated ID. Questa funzione offre maggiore controllo e sicurezza sull’esperienza di accesso degli utenti. Per ulteriori informazioni, consulta di seguito.

## In che modo la rimozione di questa funzione ti influisce?

Per tutti i clienti che hanno **[!UICONTROL Enforce IP login restrictions]** impostato, questa funzione verrà rimossa a gennaio 2021. A quel punto, le eventuali restrizioni di accesso IP ancora in vigore non verranno più applicate. Se devi ancora limitare l’accesso per indirizzo IP, devi rivedere e implementare la soluzione consigliata di Single-Sign-On e Federated ID (ulteriori informazioni e risorse di seguito).

Inoltre, l’impostazione **[!UICONTROL Enforce IP login restrictions]** verrà rimossa da **[!UICONTROL Admin]> [!UICONTROL All admin] > [!UICONTROL Company settings] >[!UICONTROL Security Manager]** nell’interfaccia utente di Analytics (come mostrato di seguito).

![](assets/sec-manager2.png)

## Quali sono le tue altre opzioni?

Come indicato in precedenza, questa funzione di Analytics terminerà. Per darti il tempo di implementare SSO e Federated ID, la data di fine del ciclo di vita è stata posticipata a gennaio 2021.

Gli SSO e i Federated ID sono soluzioni superiori alla funzione di restrizione dell’accesso IP attualmente in vigore e ti forniranno maggiore controllo, sicurezza e funzionalità. Per informazioni su come impostare SSO/Federated ID, è disponibile la seguente documentazione di aiuto. Si consiglia di leggerle a fondo e di collaborare con il reparto IT per implementarle:

* [Single Sign-On e l’Experience Cloud](https://spark.adobe.com/page/JeSB8EPEQIvjD/)
* [Admin Console - Documentazione dell’installazione di Identity](https://helpx.adobe.com/it/enterprise/using/set-up-identity.html)
* [Admin Console - Esercitazione sull’impostazione dell’identità (video)](https://helpx.adobe.com/enterprise/how-to/identity-directories-domains.html?playlist=/ccx/v1/collection/product/enterprise/topics/enterprise-identity/collection.ccx.js&amp;ref=helpx.adobe.com)
* [Esercitazione su come configurare il Federated ID (video)](https://helpx.adobe.com/enterprise/how-to/identity-configure-ids.html?playlist=/ccx/v1/collection/product/enterprise/topics/enterprise-identity/collection.ccx.js&amp;ref=helpx.adobe.com)
* [Single Sign-On - Domande comuni](https://helpx.adobe.com/enterprise/using/sso-faq.html)
* [Tipi di identità supportati da Adobe](https://helpx.adobe.com/enterprise/using/identity.html)

Se desideri continuare a esprimere il tuo supporto per le restrizioni di accesso IP e richiederne l’invio tramite l’Experience Cloud, puoi votare questa funzione nella nostra [pagina del forum](https://forums.adobe.com/ideas/11648).
