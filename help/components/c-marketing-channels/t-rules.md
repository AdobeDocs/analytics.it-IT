---
description: Crea regole di elaborazione Canale marketing, che determinano se un hit visitatore soddisfa i criteri assegnati a un canale.
seo-description: Crea regole di elaborazione Canale marketing, che determinano se un hit visitatore soddisfa i criteri assegnati a un canale.
seo-title: Creare regole di elaborazione Canale marketing
solution: Analytics
subtopic: Canali di marketing
title: Creare regole di elaborazione Canale marketing
topic: Reports & Analytics
uuid: 0 e 47634 f -3 c 69-46 db -8 af 4-8 d 0 b 3 d 15 f 7 a 8
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Creare regole di elaborazione Canale marketing

Crea regole di elaborazione Canale marketing, che determinano se un hit visitatore soddisfa i criteri assegnati a un canale.

Questa procedura utilizza come esempio una regola e-mail. L'esempio presuppone che sia stato aggiunto un canale e-mail all'elenco dei canali nella pagina di Marketing Channel Manager.

1. Click **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]**.
1. Seleziona una suite di rapporti.

   If your report suite does not have channels defined, the [!UICONTROL Marketing Channels: Auto Setup] page displays.

   See [Run the Automatic Setup](/help/components/c-marketing-channels/c-channel-autosetup.md).

1. Click **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Marketing Channels]** &gt; **[!UICONTROL Marketing Channel Processing Rules]**.

   ![Risultato passaggio](assets/marketing_channel_rules.png)

1. From the **[!UICONTROL Add New Rule Set]** menu, select **[!UICONTROL Email]**.

   Qui non selezionate il canale, ma un modello che popola la regola con alcuni dei parametri necessari.

   ![Risultato passaggio](assets/example_email.png)

   Utilizzare logica booleana (istruzione if/then) per configurare una regola. Ad esempio, in una regola di canale e-mail, fornire le impostazioni o informazioni enfatizzate nella seguente istruzione regola:

   `"If **[!UICONTROL All]** or **[!UICONTROL Any]** of the following are true:  **[!UICONTROL Query String Parameter]** *<value>* **[!UICONTROL exists]**...`

   `"Then identify the channel as **[!UICONTROL Email]**...`

   `"Then set the channel's value to **[!UICONTROL Query String Parameter]** *<value>*."`

   In this example, *`<value>`* is the query string parameter that you use for your email campaign, such as *`eml`*.
1. To continue creating rules, click **[!UICONTROL Add Rule]**.
1. Per assegnare priorità alle regole, trascinatele nella posizione desiderata.
1. Fai clic su **[!UICONTROL Save.]**

>[!MORE_ LIKE_ THIS]
>
>* [Domande frequenti ed esempi](/help/components/c-marketing-channels/c-faq.md)

