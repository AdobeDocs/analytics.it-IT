---
description: Istruzioni per individuare gli ID account per Google Ads e Microsoft Advertising.
title: Individuare gli ID account
feature: Advertising Analytics
exl-id: 2faccfd1-df7b-4b0c-a2f3-23138c39a838
source-git-commit: 586459d99674f01a3b18f84f975a3365ddf2fcd9
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 22%

---

# Individuare gli ID account {#locate-your-account-ids}

Scopri come individuare gli ID account per Google Ads e Microsoft Advertising.

## Google Ads (AdWords) {#google}

>[!IMPORTANT]
>
>Google Ads utilizza due tipi di account:
>
>- Account MCC (My Client Center) e
>- Account standard.
>
>Per questa integrazione con Adobe Analytics, **devi utilizzare un account di accesso standard**, non un account di accesso MCC. Il motivo è che un account MCC funge da account &quot;ombrello&quot; in grado di accedere a più account Google Ads con un singolo accesso, mentre l’accesso all’account Standard può accedere a un solo account per ogni accesso. Google supporta il collegamento di un’e-mail per gestire 5 account, ma Advertising Analytics non supporta ancora questa funzione. È possibile collegare un’e-mail a un solo account Google Ads.

Fai clic sull’icona Account in alto a destra per visualizzare il numero di account Google Ads (ID cliente).

![Account Google Ads Manager](assets/google-account.png)

## Microsoft Advertising (Bing) {#microsoft}

>[!NOTE]
>
>Se il tuo account Microsoft Advertising (precedentemente noto come Bing) utilizza la funzione di importazione di Google, assicurati di aggiornare la stringa di tracciamento corretta. La stringa di tracciamento non viene aggiornata automaticamente dalla versione di Google alla stringa di tracciamento di Microsoft Advertising corretta e può causare dati non specificati. Per ulteriori informazioni, vedi [Cosa viene importato da Google Ads](https://help.ads.microsoft.com/apex/index/3/en/50851/) nella guida di Microsoft Advertising.

**[!UICONTROL Account ID]** e **[!UICONTROL Manager account ID]** sono entrambi obbligatori.

- **[!UICONTROL Account ID]** si trova in **[!UICONTROL Settings]** > **[!UICONTROL Account settings]** > **[!UICONTROL Account ID]**. Assicurarsi di utilizzare [!UICONTROL Account ID] e NON [!UICONTROL Account number].
- **[!UICONTROL Manager account ID]** si trova in **[!UICONTROL Settings]** > **[!UICONTROL Manager account settings]** > **[!UICONTROL Manager account ID]**. Assicurarsi di utilizzare [!UICONTROL Manager account ID] e NON [!UICONTROL Manager account number].

![Navigazione Microsoft Advertising](assets/bing-id.png)

>[!CONTEXTUALHELP]
>id="adanalytics_ma_account_id"
>title="ID account"
>abstract="L’“ID account” è un valore numerico che si trova nell’interfaccia di Microsoft Advertising. Puoi individuarlo passando a Impostazioni > Impostazioni account > ID account."

>[!CONTEXTUALHELP]
>id="adanalytics_ma_manager_account_id"
>title="ID account manager"
>abstract="L’“ID account manager” è un valore numerico che si trova nell’interfaccia di Microsoft Advertising. Puoi individuarlo passando a Impostazioni > Impostazioni account manager > ID account manager."
