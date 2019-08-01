---
description: Elenca le informazioni necessarie per fornire dall'account Selligent prima di poter distribuire l'integrazione.
seo-description: Elenca le informazioni necessarie per fornire dall'account Selligent prima di poter distribuire l'integrazione.
seo-title: Prerequisiti per Selligent
solution: Analytics
title: Prerequisiti per Selligent
uuid: 3 a 43 a 1 c 0-5 f 51-4 bc 8-b 6 b 9-0 c 46 aa 00 ba 9 f
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Prerequisites for Selligent{#prerequisites-for-selligent}

Elenca le informazioni necessarie per fornire dall'account Selligent prima di poter distribuire l'integrazione.

**Account Selligent valido**

Per utilizzare questa integrazione di Connettori dati, è necessario disporre di un account Selligent valido.

**Informazioni account**

Durante questa configurazione dell'integrazione dovrete disporre delle seguenti informazioni sull'account Selligent:

* **URL Adobe Service**:

   L'URL può essere derivato dall'URL utilizzato per accedere alla soluzione Marketing Selligent. Sostituite la parte «/simweb/login. aspx» dell'url con «/automation/omniture. asmx»

   Ad esempio: http://<client-specific install url>/automation/omniture.asmx

* **Parametri stringa query:** Questi vengono aggiunti nell'URL della pagina di destinazione per ID messaggio e ID destinatario (ID visitatore). Sono sempre MID e RID rispettivamente per ID messaggio e ID destinatario.

* **Token integrazione** Consente di avviare lo strumento Manager dall'interno di Simweb e passare **[!UICONTROL Configuration]** a &gt; **[!UICONTROL System Settings]****[!UICONTROL General]** &gt; scheda &gt; **[!UICONTROL System]**. Under **[!UICONTROL Security]**, you can find the Integration token.

   ![](assets/selligent-integration_token.png)

