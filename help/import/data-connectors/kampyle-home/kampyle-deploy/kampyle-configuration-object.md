---
description: Dopo aver completato la procedura guidata di integrazione, dovete distribuire l'oggetto di configurazione dell'integrazione alla proprietà Web.
seo-description: Dopo aver completato la procedura guidata di integrazione, dovete distribuire l'oggetto di configurazione dell'integrazione alla proprietà Web.
seo-title: Implementare l'oggetto di configurazione dell'integrazione
solution: Analytics
title: Implementare l'oggetto di configurazione dell'integrazione
uuid: e 951 c 864-2914-4324-9 f 03-5069 d 4 f 75 d 99
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Implementare l'oggetto di configurazione dell'integrazione{#deploy-the-integration-configuration-object}

Dopo aver completato la procedura guidata di integrazione, dovete distribuire l'oggetto di configurazione dell'integrazione alla proprietà Web.

In molti casi, il modo più semplice per distribuire l'oggetto di configurazione dell'integrazione è includerlo con il codice di distribuzione Adobe Analytics.

>[!NOTE]
>
>Se utilizzate Adobe tagmanager o Gestione tag dinamica per implementare Adobe Analytics, potete aggiungere facilmente l'oggetto di configurazione all'integrazione tramite tale strumento.

1. Passate alla **[!UICONTROL Resources]** scheda &gt; **[!UICONTROL Support]** dell'integrazione.
1. Scaricate e salvate la **[!UICONTROL Kampyle Integration Code (JS)]** risorsa. Il codice è simile a quello riportato di seguito:

   ```
   /* Kampyle:  Integration configuration settings */
     window.k_sc_param = { "version":1.1 }
   ```

1. Distribuite il codice utilizzando uno dei seguenti metodi:

       | ** Utilizzate Adobe tagmanager o Gestione tag dinamica.** | Utilizzate l'interfaccia di gestione tag per aggiungere il codice. |
    |—|—|
    | ** In tutti gli altri casi** | Distribuite il codice alla risorsa aziendale responsabile dell'aggiornamento del codice di distribuzione Adobe Analytics. |
   
