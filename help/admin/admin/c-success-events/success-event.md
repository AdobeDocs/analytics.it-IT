---
description: Gli eventi di successo sono azioni che possono essere tracciate. È possibile determinare l'evento di successo. Ad esempio, se un visitatore acquista un elemento, l'evento di acquisto potrebbe essere considerato l'evento di successo.
keywords: event
title: Panoramica eventi di successo
topic: Admin tools
uuid: 410eee44-8960-462c-a9c3-07b44d0b1df0
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '687'
ht-degree: 5%

---


# Panoramica eventi di successo

Gli eventi di successo sono azioni che possono essere tracciate. È possibile determinare l&#39;evento di successo. Ad esempio, se un visitatore acquista un elemento, l&#39;evento di acquisto potrebbe essere considerato l&#39;evento di successo.

Accedi alla pagina Eventi di successo nelle impostazioni della suite di rapporti:

1. Log in to [experiencecloud.adobe.com](https://experiencecloud.adobe.com) using your AdobeID credentials.
2. Fate clic sul pulsante a 9 griglie nella parte superiore, quindi fate clic [!UICONTROL Analytics].
3. Passa a [!UICONTROL Admin] > [!UICONTROL Report Suites]
4. Selezionate la suite di rapporti desiderata, quindi andate a [!UICONTROL Edit Settings] > [!UICONTROL Conversion] > [!UICONTROL Success Events].
5. Individuate l’evento desiderato e modificate il menu a discesa [!UICONTROL Unique Event Recording] in [!UICONTROL Record Once Per Visit] o [!UICONTROL Use Event ID].

Esistono molti tipi di eventi di successo, a seconda del tipo di sito Web. Alcuni esempi:

* **Vendita al dettaglio**: Visualizzazione prodotto, estrazione, acquisto
* **File multimediali**: Iscrizione, iscrizione al concorso, visualizzazione pagina, visualizzazione video
* **Finanza**: Invio applicazione, login, utilizzo degli strumenti self-service
* **Viaggi**: Prenotazione (acquisto), campagna interna (click-through), ricerca (itinerario di determinazione prezzi)
* **Telecomunicazioni**: Acquisto, lead, utilizzo di strumenti self-service
* **High Tech**: Download white paper, RFP, completamento del modulo, richieste di assistenza
* **Automotive**: Invio di lead, richiesta di preventivo, download di brochure

La variabile [s.events](https://docs.adobe.com/content/help/it-IT/analytics/implementation/vars/page-vars/events/event-serialization.html) definisce un evento success.

## Pagina Eventi Di Successo - Descrizioni {#section_681ECEC981694CABBDBF00E18165B447}

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL Conversion]** > **[!UICONTROL Success Events]**

La pagina Eventi di successo consente di configurare le variabili Evento utilizzate sul sito. Potete aggiungere fino a 1.000 eventi di successo. Gli eventi 81-1.000 funzionano solo se con codice H22 o superiore.

| Elemento | Descrizione |
|--- |--- |
| Evento | Il nome originale dell’evento. |
| Nome | Assegna nomi significativi agli eventi di successo utilizzati sul sito. Ad esempio, se event1 viene utilizzato per tenere traccia delle registrazioni, modificate qui il nome in modo che event1 venga rappresentato come metrica &quot;Registrazioni&quot; in tutti i rapporti di conversione. |
| Tipo | Il tipo selezionato determina se l&#39;evento è un contatore (standard), un evento numerico o un evento valutario. Gli eventi numerici e valutari consentono di incrementare le metriche di più di un elemento.  Gli eventi contatore vengono utilizzati per registrare un evento nel tempo, mentre gli eventi della valuta registrano un numero decimale, come l&#39;imposta o la spedizione. Il valore passato in eventi di valuta viene convertito dalla valuta della pagina alla valuta di base della suite di rapporti al momento dell&#39;incasso. Per informazioni sull&#39;utilizzo degli eventi relativi alla valuta, contattate un rappresentante Adobe. Gli eventi numerici vengono utilizzati per creare rapporti sui numeri non in valuta, ad esempio il numero di coupon utilizzati in un ordine. Gli eventi di valuta vengono utilizzati per tenere traccia delle spese di spedizione e di imposta. Gli eventi utilizzati nel tipo Standard di Origini dati devono essere eventi numerici o di valuta. |
| Polarità | La polarità della metrica consente di indicare se Adobe  Analytics deve considerare positivo o negativo un determinato evento personalizzato (metrica). Consente ad Adobe  Analytics di visualizzare indicatori direzionali (frecce) per diverse metriche per aggiungere contesto (ad esempio, confronti tra settimane e settimane).  Esempi: se &quot;Bugs Subsent&quot; va su settimana, Adobe  Analytics dovrebbe considerarlo buono o cattivo? Un aumento delle registrazioni per e-mail è probabilmente positivo. Tuttavia, un aumento degli errori di invio del modulo è probabilmente negativo.  In  Analysis Workspace, la polarità è applicata a: Formattazione condizionale della tabella a forma libera, visualizzazioni Variazione di riepilogo e schema di colori positivo/negativo della visualizzazione Mappa. |
| Descrizione | Breve descrizione dello scopo e dell&#39;utilizzo dell&#39;evento. |
| Registrazione evento univoca | **Registra una volta per visita**: Collega l&#39;evento specificato alla sessione del visitatore. I conteggi successivi per un dato evento nella stessa visita vengono ignorati. Questo tipo di serializzazione dell&#39;evento non richiede alcuna modifica nell&#39;implementazione.<br>**Usa ID **evento: Collega l&#39;evento specificato a un ID personalizzato. I conteggi successivi per un dato evento con lo stesso ID evento vengono ignorati. Questo tipo di serializzazione degli eventi richiede un ID personalizzato negli hit per deduplicare i valori. Consultate Serializzazione degli ID[evento](../../../implement/vars/page-vars/events/event-serialization.md)nella guida per l’utente Implementa. |
| Partecipazione | Attribuisce credito di attribuzione completo a tutti gli elementi di dimensione della visita. |
| Avviso (evento valuta) | Quando si modificano i tipi di evento in o da un evento valuta, viene visualizzato un messaggio che indica che i dati storici non sono disponibili nel reporting.  Diversi tipi di evento utilizzano tabelle di dati separate e non possono essere utilizzati contemporaneamente. Alcuni dati storici possono essere ripristinati se l&#39;utente ripristina il tipo di evento. Tuttavia, eventuali dati raccolti dopo la modifica iniziale non sono disponibili. Prestate attenzione quando modificate un tipo di evento. |

