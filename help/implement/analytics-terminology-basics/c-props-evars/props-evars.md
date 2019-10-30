---
description: Le variabili di traffico personalizzate, denominate anche variabili di proprietà (s.prop) o di proprietà, sono contatori che contano il numero di volte in cui ogni valore viene inviato in Analytics.
keywords: Implementazione di Analytics;Traffic prop;prop;conversion;evar;s.prop;custom conversion insider;Traffic variable
seo-description: Le variabili di traffico personalizzate, denominate anche variabili di proprietà (s.prop) o di proprietà, sono contatori che contano il numero di volte in cui ogni valore viene inviato in Analytics.
seo-title: Panoramica di prop ed eVar
solution: Analytics
title: Panoramica di prop ed eVar
topic: Sviluppatore e implementazione
uuid: 522CAB2b-1ef8-4f10-b216-c82b21431487
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Panoramica di prop ed eVar

Le variabili di traffico personalizzate, denominate anche variabili di proprietà (s.prop) o di proprietà, sono contatori che contano il numero di volte in cui ogni valore viene inviato in Analytics.

Per determinare quali variabili vengono assegnate dove, è importante comprendere le differenze tra le funzionalità Prop e eVar. Comprendere queste differenze consente all'organizzazione di decidere quale tipo di variabile è più adatto all'uso. Per informazioni dettagliate, consultate [Confronto tra proprietà ed eVar](../../../implement/analytics-terminology-basics/c-props-evars/props-vs-evars.md#concept_6E55483C1EC24566B5D3B2736E766EBC).

Le proprietà consentono inoltre di correlare dati personalizzati con eventi specifici relativi al traffico. Queste variabili sono incorporate nel [!DNL Analytics] codice presente in ciascuna pagina del sito Web. Attraverso [!UICONTROL s.prop] le variabili, [!DNL Analytics] puoi creare rapporti personalizzati, specifici per l'organizzazione, il settore e gli obiettivi aziendali.

Ad esempio, se sei un produttore di automobili, potresti essere interessato a vedere "Modello auto più popolare" per completare il tuo rapporto "Pagine". È possibile ottenere questo risultato assegnando una delle proprietà di traffico per rappresentare il modello auto. Quindi implementate il codice per passare in modello auto sulle pagine appropriate.

> [!NOTE] [!DNL Analytics] supporta fino a 75 [!UICONTROL s.prop] variabili.

Le proprietà vengono utilizzate nei rapporti di percorso o nei rapporti di correlazione. Ad esempio, [!UICONTROL property] le variabili possono essere utilizzate per mostrare il tipo di contenuto, la sottosezione o il nome del modello. I rapporti risultanti [!UICONTROL Custom Traffic] mostrano quale tipo di contenuto, sottosezione o modello viene visualizzato più spesso.

Ci sono innumerevoli domande aziendali cui è possibile rispondere tramite le variabili di traffico personalizzate, a seconda di ciò che si sta acquisendo dal sito Web. Il seguente elenco contiene alcuni obiettivi e obiettivi comuni:

* Navigazione degli utenti nel sito Web
* Comportamento della ricerca utente interna
* Segmentazione del traffico per navigazione o categoria
* Segmentazione del comportamento dei visitatori in base ai dati demografici

Le eVar (o [!UICONTROL Custom Conversion Insight] variabili) vengono utilizzate per identificare in che modo attributi o azioni specifici contribuiscono agli eventi di successo sul sito. Ad esempio, per un sito multimediale, le eVar possono essere utilizzate per identificare in che modo le promozioni interne portano i visitatori a registrarsi. Quando un visitatore fa clic sulla promozione interna, è possibile utilizzare un'eVar per memorizzare un identificatore univoco per tale promozione. Quando lo stesso visitatore completa la registrazione e viene attivato un evento di successo personalizzato, l’identificatore univoco originale riceve credito per l’evento di registrazione.

In un sito di conversione, le eVar possono essere utilizzate per monitorare il modo in cui i visitatori che hanno effettuato l'accesso si confrontano con i visitatori che non hanno effettuato l'accesso al completamento di un acquisto. Quando un visitatore effettua l'accesso, una eVar viene impostata su "connesso". Quando il visitatore raggiunge la pagina di estrazione, l'evento di checkout viene attribuito al valore "connesso". Quando un visitatore raggiunge la pagina di ringraziamento dopo l’acquisto, i prodotti e gli importi di acquisto vengono attribuiti al valore "registrato". Il [!UICONTROL Custom eVar] rapporto risultante mostra il numero totale di pagamenti e ordini per i visitatori "connessi" e "non connessi".

Per ulteriori informazioni, vedi Variabile [di](https://marketing.adobe.com/resources/help/en_US/reference/traffic_var.html) traffico nella guida e nei riferimenti di Analytics.

Per informazioni sulla configurazione delle proprietà in Gestione tag digitale, consultate [Creare proprietà](../../../implement/c-implement-with-dtm/t-create-web-property.md#task_960467FBB7A54499AC228CB3AA3C4123)Web.
