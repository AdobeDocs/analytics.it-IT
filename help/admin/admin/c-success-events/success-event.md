---
description: Gli eventi di successo sono azioni che possono essere tracciate. È possibile determinare l'evento di successo. Ad esempio, se un visitatore acquista un elemento, l'evento di acquisto potrebbe essere considerato l'evento di successo.
keywords: prodView
seo-description: Gli eventi di successo sono azioni che possono essere tracciate. È possibile determinare l'evento di successo. Ad esempio, se un visitatore acquista un elemento, l'evento di acquisto potrebbe essere considerato l'evento di successo.
seo-title: Panoramica eventi di successo
solution: Analytics
title: Panoramica eventi di successo
topic: Strumenti di amministrazione
uuid: 410eee44-8960-462c-a9c3-07b44d0b1df0
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Panoramica eventi di successo

Gli eventi di successo sono azioni che possono essere tracciate. È possibile determinare l'evento di successo. Ad esempio, se un visitatore acquista un elemento, l'evento di acquisto potrebbe essere considerato l'evento di successo.

Esistono molti tipi di eventi di successo, a seconda del tipo di sito Web. Alcuni esempi:

* **Vendita al dettaglio**: Visualizzazione prodotto, estrazione, acquisto
* **File multimediali**: Iscrizione, iscrizione al concorso, visualizzazione pagina, visualizzazione video
* **Finanza**: Invio applicazione, login, utilizzo degli strumenti self-service
* **Viaggi**: Prenotazione (acquisto), campagna interna (click-through), ricerca (itinerario di determinazione prezzi)
* **Telecomunicazioni**: Acquisto, lead, utilizzo di strumenti self-service
* **High Tech**: Download white paper, RFP, completamento modulo, richieste di assistenza
* **Automotive**: Invio di lead, richiesta di preventivo, download di brochure

La variabile [s.events](https://marketing.adobe.com/resources/help/en_US/sc/implement/events.html) definisce un evento success.

## Pagina Eventi Di Successo - Descrizioni {#section_681ECEC981694CABBDBF00E18165B447}

**[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]** &gt; **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Conversion]** &gt; **[!UICONTROL Success Events]**

La pagina Eventi di successo consente di configurare le variabili Evento utilizzate sul sito. Potete aggiungere fino a 1.000 eventi di successo. Gli eventi 81-1.000 funzionano solo se con codice H22 o superiore.

| Elemento | Descrizione |
|--- |--- |
| Evento | Il nome originale dell’evento. |
| Nome | Assegna nomi significativi agli eventi di successo utilizzati sul sito. Ad esempio, se event1 viene utilizzato per tenere traccia delle registrazioni, modificate qui il nome in modo che event1 venga rappresentato come metrica "Registrazioni" in tutti i rapporti di conversione. |
| Type (Tipo) | Il tipo selezionato determina se l'evento è un contatore (standard), un evento numerico o un evento valutario. Gli eventi numerici e valutari consentono di incrementare le metriche di più di un elemento.  Gli eventi contatore vengono utilizzati per registrare un evento nel tempo, mentre gli eventi valuta registrano un numero decimale, come l'imposta o la spedizione. Il valore passato in eventi di valuta viene convertito dalla valuta della pagina alla valuta di base della suite di rapporti al momento dell'incasso. Per informazioni sull'utilizzo degli eventi relativi alla valuta, contattate un rappresentante Adobe. Gli eventi numerici vengono utilizzati per creare rapporti sui numeri non in valuta, ad esempio il numero di coupon utilizzati in un ordine. Gli eventi di valuta vengono utilizzati per tenere traccia delle spese di spedizione e di imposta. Gli eventi utilizzati nel tipo Standard di Origini dati devono essere eventi numerici o di valuta. |
| Polarità | La polarità della metrica consente di indicare se Adobe Analytics deve considerare positivo o negativo un determinato evento personalizzato (metrica). Consentirà ad Adobe Analytics di mostrare indicatori direzionali (frecce) per diverse metriche per aggiungere contesto (ad esempio, confronti tra settimane e settimane).  Esempi: se "Bug Inviati" va avanti di settimana in settimana, Adobe Analytics dovrebbe considerarlo buono o cattivo? Un aumento delle registrazioni per e-mail è probabilmente positivo. Tuttavia, un aumento degli errori di invio del modulo è probabilmente negativo.  In Analysis Workspace, la polarità è applicata a: Formattazione condizionale della tabella a forma libera, visualizzazioni Variazione di riepilogo e schema di colori positivo/negativo della visualizzazione Mappa. |
| Descrizione | Breve descrizione dello scopo e dell'utilizzo dell'evento. |
| Registrazione evento univoca | Vedi [Serializzazione degli eventi](/help/implement/js-implementation/event-serialization.md). |
| Partecipazione | Consulta Partecipazione alle [metriche](/help/components/c-variables/c-metrics/metrics-participation.md). |
| Avviso (evento valuta) | Quando si modificano i tipi di evento in o da un evento valuta, viene visualizzato un messaggio che indica che i dati storici non sono disponibili nel reporting.  Diversi tipi di evento utilizzano tabelle di dati separate e non possono essere utilizzati contemporaneamente. Alcuni dati storici possono essere ripristinati se l'utente ripristina il tipo di evento. Tuttavia, eventuali dati raccolti dopo la modifica iniziale non sono disponibili. Prestate attenzione quando modificate un tipo di evento. |

