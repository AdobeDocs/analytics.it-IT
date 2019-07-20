---
description: Le variabili di traffico personalizzate, denominate anche proprietà (proprietà s. prop) o variabili di proprietà, sono contatori che contano quante volte ogni valore viene inviato in Analytics.
keywords: Implementazione di Analytics; prop Traffico; prop; conversione; evar; s. prop; informazioni di conversione personalizzate; variabile traffico
seo-description: Le variabili di traffico personalizzate, denominate anche proprietà (proprietà s. prop) o variabili di proprietà, sono contatori che contano quante volte ogni valore viene inviato in Analytics.
seo-title: Panoramica di prop ed evar
solution: Analytics
title: Panoramica di prop ed evar
topic: Sviluppatore e implementazione
uuid: 522 cab 2 b -1 ef 8-4 f 10-b 216-c 82 b 21431487
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Panoramica di prop ed evar

Le variabili di traffico personalizzate, denominate anche proprietà (proprietà s. prop) o variabili di proprietà, sono contatori che contano quante volte ogni valore viene inviato in Analytics.

Per determinare quali variabili vengono assegnate dove, è importante comprendere le differenze tra le funzionalità Prop e evar. Comprendere queste differenze consente all'organizzazione di stabilire quale tipo di variabile è più efficace. For detailed information, see [Comparing Props and eVars](../../../implement/analytics-terminology-basics/c-props-evars/props-vs-evars.md#concept_6E55483C1EC24566B5D3B2736E766EBC).

Prop consente inoltre di correlare dati personalizzati con eventi specifici relativi al traffico. These variables are embedded in the [!DNL Analytics] code on each page of your website. Through [!UICONTROL s.prop] variables, [!DNL Analytics] lets you create custom reports, unique to your organization, industry, and business objectives.

Ad esempio, se sei un produttore automobilistico, potresti essere interessato a visualizzare «Most Popular Car Model» (Modello auto più popolare) per completare il rapporto «Pagine». Per farlo, allocate una delle proprietà del traffico per rappresentare il modello dell'automobile. Quindi implementate il codice per passare il modello di automobile nelle pagine appropriate.

>[!NOTE]
>
>[!DNL Analytics] supporta fino a 75 [!UICONTROL s.prop] variabili.

I prop sono utilizzati nei rapporti percorsi o nei rapporti di correlazione. For example, [!UICONTROL property] variables can be used to show content type, sub-section, or template name. The resulting [!UICONTROL Custom Traffic] reports show which content type, sub-section, or template is viewed most often.

Esistono infinite domande di business a cui puoi rispondere tramite le variabili di traffico personalizzate, a seconda di cosa stai acquisendo dal tuo sito Web. L'elenco seguente contiene alcuni obiettivi e obiettivi comuni:

* Informazioni sulla navigazione attraverso il sito Web
* Funzionamento del comportamento interno della ricerca utente
* Segmentazione del traffico tramite navigazione o categoria
* Segmentazione del comportamento dei visitatori per demografia

eVars (or [!UICONTROL Custom Conversion Insight] variables) are used to identify how well specific attributes or actions contribute to success events on your site. Ad esempio, per un sito multimediale, le evar possono essere utilizzate per identificare il modo in cui le promozioni interne invitano i visitatori a registrarsi. Quando un visitatore fa clic sulla promozione interna, è possibile utilizzare un evar per memorizzare un identificatore univoco per tale promozione. Quando lo stesso visitatore completa la registrazione e viene attivato un evento di successo personalizzato, l'identificatore univoco originale riceve credito per l'evento di registrazione.

In un sito di conversione, le evar possono essere utilizzate per tenere traccia del modo in cui i visitatori registrati confrontano i visitatori non registrati durante la compilazione di un acquisto. Quando un visitatore accede, una evar è impostata su «accesso». Quando il visitatore raggiunge la pagina di pagamento, l'evento checkout viene attribuito al valore "accesso". Quando un visitatore raggiunge la pagina di ringraziamento dopo l'acquisto, i prodotti e gli importi di acquisto vengono attribuiti al valore "accesso". The resulting [!UICONTROL Custom eVar] report shows the total number of checkouts and orders for "logged in" and "non-logged in" visitors.

For additional information, see [Traffic Variable](https://marketing.adobe.com/resources/help/en_US/reference/traffic_var.html) in the Analytics Help and Reference.

For information about setting up properties in Digital Tag Management, see [Create Web Property](../../../implement/c-implement-with-dtm/t-create-web-property.md#task_960467FBB7A54499AC228CB3AA3C4123).
