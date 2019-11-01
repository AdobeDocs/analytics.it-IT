---
description: Crea regole di elaborazione del canale di marketing, che determinano se un hit di visitatore soddisfa i criteri assegnati a un canale.
seo-description: Crea regole di elaborazione del canale di marketing, che determinano se un hit di visitatore soddisfa i criteri assegnati a un canale.
seo-title: Creare regole di elaborazione per il canale di marketing
solution: Analytics
subtopic: Canali di marketing
title: Creare regole di elaborazione per il canale di marketing
topic: Reports and Analytics
uuid: 0e47634f-3c69-46db-8af4-8d0b3d15f7a8
translation-type: tm+mt
source-git-commit: ed22e0520bf1c7427ead039fb1d0391f2f1e567f

---


# Creare regole di elaborazione per il canale di marketing

Crea regole di elaborazione del canale di marketing, che determinano se un hit di visitatore soddisfa i criteri assegnati a un canale.

Questa procedura utilizza una regola e-mail come esempio. L'esempio presuppone che sia stato aggiunto un canale e-mail all'elenco dei canali nella pagina Marketing Channel Manager.

1. Clic **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]**.
1. Seleziona una suite di rapporti.

   Se nella suite di rapporti non sono definiti canali, viene visualizzata la [!UICONTROL Marketing Channels: Auto Setup] pagina.

   Consultate [Eseguire la configurazione](/help/components/c-marketing-channels/c-channel-autosetup.md)automatica.

1. Clic **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Marketing Channels]** &gt; **[!UICONTROL Marketing Channel Processing Rules]**.

   ![Risultato passaggio](assets/marketing_channel_rules.png)

1. Dal **[!UICONTROL Add New Rule Set]** menu, selezionare **[!UICONTROL Email]**.

   Qui non selezionate il canale, ma un modello che completa la regola con alcuni dei parametri necessari.

   ![Risultato passaggio](assets/example_email.png)

   Utilizzare la logica booleana (istruzioni if / then) per configurare una regola. Ad esempio, in una regola del canale di posta elettronica, fornire le impostazioni o le informazioni enfatizzate nella seguente istruzione di regola:

   `"If **[!UICONTROL All]** or **[!UICONTROL Any]** of the following are true:  **[!UICONTROL Query String Parameter]** *<value>* **[!UICONTROL exists]**...`

   `"Then identify the channel as **[!UICONTROL Email]**...`

   `"Then set the channel's value to **[!UICONTROL Query String Parameter]** *<value>*."`

   In questo esempio *`<value>`* è il parametro della stringa di query utilizzato per la campagna e-mail, ad esempio *`eml`*.
1. Per continuare a creare le regole, fare clic su **[!UICONTROL Add Rule]**.
1. Per assegnare priorità alle regole, trascinatele fino alla posizione desiderata.
1. Fai clic su **[!UICONTROL Save.]**

>[!MORELIKETHIS]
>
>* [Domande frequenti ed esempi](/help/components/c-marketing-channels/c-faq.md)

