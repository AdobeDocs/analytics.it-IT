---
description: Informazioni sui tre modi in cui accedere al Report Builder.
title: Accesso di Report Builder
topic: Report builder
uuid: 9a21b791-e323-46d2-b850-2d67babe964b
translation-type: tm+mt
source-git-commit: 5b130de23d7826a266f34ed1830540c8c0865560
workflow-type: tm+mt
source-wordcount: '485'
ht-degree: 4%

---


# Accesso di Report Builder

>[!IMPORTANT]
>
>La versione di Report Builder 5.6.47 e versioni successive supporta solo  login di Experience Cloud e non supporta accessi legacy quali Site Catalyst Single Sign-On o Accesso standard. Entro il 30 aprile 2021, tutti gli utenti del Report Builder devono aggiornare il componente aggiuntivo di Report Builder alla versione 5.6.47 o successiva, che include un aggiornamento critico del processo di accesso.

Per accedere al Report Builder, usate il vostro account di accesso  Experience Cloud.

## Experience Cloud {#section_1FA230F35AB54021A874A7A28DE4C850}

L&#39;accesso al Experience Cloud  consente di utilizzare l&#39;Enterprise ID  (e-mail e password) per accedere all&#39;Adobe Experience Cloud. Fare clic su **[!UICONTROL Sign In]** > **[!UICONTROL Sign in with an Enterprise ID]** per essere reindirizzato alla pagina di accesso singolo della società. Per ulteriori informazioni sull&#39;Enterprise ID , fare clic su [qui](https://helpx.adobe.com/enterprise/kb/enterprise-id-faq.html#whatis).

![](assets/adobe_id_login.png)

>[!NOTE]
>
>L&#39;accesso al Experience Cloud  è basato sulla sessione e il token scade dopo 30 giorni.

## Accedere a Report Builder

Per accedere al Report Builder

1. In Excel, fare clic su **[!UICONTROL Add-Ins]**.
1. Fai clic su **[!UICONTROL Sign In]**. Altre azioni che consentono di effettuare l’accesso:

   * Fai clic su **[!UICONTROL Create]**.
   * [Selezionate una richiesta in Gestore](/help/analyze/report-builder/manage-requests/r-arb-manage-requests.md) richieste, quindi fate clic su  **[!UICONTROL Add]** o  **[!UICONTROL Manage]**.
   * Fate doppio clic su una richiesta in Excel.

1. Completare i campi nella pagina [!UICONTROL Login], quindi fare clic su **[!UICONTROL OK]**.

## Tipi di accesso legacy

>[!IMPORTANT]
>
>Entro il 30 aprile 2021, i tipi di accesso legacy non funzioneranno. Tutti gli utenti di Report Builder devono aggiornare il componente aggiuntivo di Report Builder alla versione 5.6.47 o successiva, che include un aggiornamento critico del processo di accesso. **La versione di Report Builder 5.6.47 e versioni successive supporta solo  login di Experience Cloud e non supporta accessi legacy quali Accesso standard o Accesso singolo a Site Catalyst.**

<!-- ![](assets/login_screen.png) -->

* [Standard](/help/analyze/report-builder/setup/login.md#section_6D54B8ADAE7F416BB83F5082B3771CFA)
* [SiteCatalyst Single Sign-On](/help/analyze/report-builder/setup/login.md#section_6970A5F926774976B85FFE576610E85F)

## Standard {#section_6D54B8ADAE7F416BB83F5082B3771CFA}

Utilizzate questo login se desiderate accedere al Report Builder utilizzando le vostre credenziali Adobe Analytics .

**Login Report Builder - definizioni dei campi**

| Campo | Definizione |
|--- |--- |
| Azienda | La credenziale di accesso della società utilizzata per  Adobe Analytics. |
| Nome utente | L’accesso al nome utente utilizzato per  Adobe Analytics. Le attività pianificate per un utente sono collegate al nome utente. È possibile visualizzare le attività pianificate da qualsiasi computer se si accede al generatore di report con le stesse credenziali di accesso. |
| Password | La password di Analytics. |
| Ricorda utente | Le informazioni di login vengono crittografate e memorizzate in un file di profilo utente nel computer in cui è installato il Report Builder. Poiché le informazioni di login vengono salvate, chiunque utilizzi lo stesso PC del creatore di report che apre un foglio di calcolo contenente un report può aggiornare e modificare i dati. Se condividete il computer con altri utenti e desiderate mantenere privati i dati del foglio di calcolo, non attivate questa opzione.  Per disattivare l&#39;impostazione di accesso automatico, fare clic su **[!UICONTROL Log in With Different Credentials]** nella barra degli strumenti e disabilitare **[!UICONTROL Remember Me]**. |
| Utilizzo di un server proxy | Abilitate questa opzione se state effettuando l&#39;accesso a Internet tramite un server proxy e dovete fornire un nome utente e una password proxy. |

## Single Sign-On {#section_6970A5F926774976B85FFE576610E85F}

Questo single sign-on (legacy) consente di accedere solo a  Adobe Analytics, non all’intero Experience Cloud .

Puoi anche digitare un dominio e il sistema riconoscerà il dominio e ti reindirizzerà alla pagina di accesso della tua società per accedere a  Adobe Analytics.
