---
description: Seguono istruzioni su come individuare gli ID account per Google e Bing.
title: Individuare gli ID account
feature: Advertising Analytics
exl-id: 2faccfd1-df7b-4b0c-a2f3-23138c39a838
source-git-commit: 0453f374e9027d1c539682212e880c4ebc81152f
workflow-type: tm+mt
source-wordcount: '240'
ht-degree: 3%

---

# Individuare gli ID account

Seguono istruzioni su come individuare gli ID account per Google e Bing.

## Google Ads (AdWords) {#section_2A62AD448BD949889DB77C2AF3E04C33}

>[!IMPORTANT]
>
>Google AdWords utilizza due tipi di account:
>
>- Account MCC (My Client Center) e
>- Account standard.
>
>Per questa integrazione con Adobe Analytics, **devi utilizzare un account di accesso standard**, non un account di accesso MCC. Il motivo è che un account MCC funge da account &quot;ombrello&quot; che può accedere a più account AdWords con un singolo accesso, mentre l’accesso all’account Standard può accedere a un solo account AdWords per ogni accesso. Google supporta il collegamento di un’e-mail per gestire 5 account, ma Advertising Analytics non supporta ancora questa funzione. Un’e-mail può essere collegata a un solo account Adwords.

Fai clic sull’icona Account in alto a destra per visualizzare il numero di account AdWords (ID cliente).

![Account Google Ads Manager](assets/google-account.png)

## Microsoft Advertising (Bing) {#section_F1B9C7E997444746936599732CD62665}

>[!NOTE]
>
>Se il tuo account Microsoft Advertising (precedentemente noto come Bing) utilizza la funzione di importazione Google, assicurati di aggiornare la stringa di tracciamento corretta. La stringa di tracciamento non viene aggiornata automaticamente dalla versione di Google alla stringa di tracciamento Bing corretta e potrebbe causare dati non specificati. Ulteriori dettagli sulla funzione sono disponibili [qui](https://help.ads.microsoft.com/apex/index/3/en/50851/).

**[!UICONTROL Account ID]** e **[!UICONTROL Account Number]** sono entrambi obbligatori. Sono elencati nella scheda **[!UICONTROL Accounts settings]** in **[!UICONTROL Settings]**.

>[!NOTE]
>
>Il numero di account non corrisponde all&#39;ID account.

![Microsoft Advertising](assets/bing-id.png)
