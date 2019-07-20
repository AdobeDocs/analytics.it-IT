---
description: Gli eventi di successo sono azioni che possono essere tracciate. Determinare l'evento di successo. Ad esempio, se un visitatore acquista un elemento, l'evento di acquisto potrebbe essere considerato come evento di successo.
keywords: prodView
seo-description: Gli eventi di successo sono azioni che possono essere tracciate. Determinare l'evento di successo. Ad esempio, se un visitatore acquista un elemento, l'evento di acquisto potrebbe essere considerato come evento di successo.
seo-title: Panoramica eventi di successo
solution: Analytics
title: Panoramica eventi di successo
topic: Strumenti di amministrazione
uuid: 410 eee 44-8960-462 c-a 9 c 3-07 b 44 d 0 b 1 df 0
translation-type: tm+mt
source-git-commit: a1213919de61a72c06ec5518e72a714c76c6859f

---


# Panoramica eventi di successo

Gli eventi di successo sono azioni che possono essere tracciate. Determinare l'evento di successo. Ad esempio, se un visitatore acquista un elemento, l'evento di acquisto potrebbe essere considerato come evento di successo.

Esistono molti tipi di eventi di successo, a seconda del tipo di sito Web. Alcuni esempi includono:

* **Vendita al dettaglio**: Visualizzazione prodotto, pagamento, acquisto
* **File multimediali**: Iscrizione, registrazione di concorsi, visualizzazione pagina, visualizzazione video
* **Finanza**: Invio applicazione, accesso, utilizzo degli strumenti self-service
* **Viaggi**: Prenotazione (acquisto), campagna interna (click-through), ricerca (itinerario di tariffazione)
* **Telecomunicazioni**: Acquisto, lead, utilizzo degli strumenti self-service
* **High Tech**: Download white paper, RFP, completamento del modulo, richieste di assistenza
* **Automobili**: Invio lead, richiesta di preventivo, download della brochure

The [s.events](https://marketing.adobe.com/resources/help/en_US/sc/implement/events.html) variable defines a success event.

## Success Events Page - Descriptions {#section_681ECEC981694CABBDBF00E18165B447}

**[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]** &gt; **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Conversion]** &gt; **[!UICONTROL Success Events]**

La pagina Eventi di successo consente di configurare le variabili Evento utilizzate sul sito. Potete aggiungere fino a 1,000 eventi di successo. Gli eventi 81-1,000 funzionano solo se sul codice H 22 o superiore.

| Elemento | Descrizione |
|--- |--- |
| Evento | Nome originale dell'evento. |
| Nome | Assegna nomi significativi agli eventi di successo utilizzati sul sito. Ad esempio, se l'evento 1 è utilizzato per monitorare le registrazioni, modificare il nome in questa posizione in modo che l'evento 1 venga rappresentato come metrica "Registrazioni" in tutti i report Conversione. |
| Type (Tipo) | Il tipo selezionato determina se l'evento è un contatore (standard), numerico o di valuta. Gli eventi numerici e valutari consentono di incrementare le metriche in base a più di una. Gli eventi contatore vengono utilizzati per registrare un evento nel tempo, mentre gli eventi valuta registrano un numero decimale, come l'imposta o la spedizione. Il valore passato negli eventi valuta viene convertito dalla valuta di pagina alla valuta di base della suite di rapporti, alla ricezione. Per informazioni dettagliate sull'utilizzo degli eventi di valuta, contattate un rappresentante Adobe. Gli eventi numerici vengono utilizzati per generare rapporti sui numeri non provenienti dalla valuta, ad esempio il numero di coupon utilizzati in un ordine. Gli eventi di valuta sono utilizzati per tenere traccia delle tasse e delle spese di spedizione. Gli eventi utilizzati nel tipo Standard di Origini dati devono essere eventi numerici o di valuta. |
| Polarità | La polarità delle metriche consente di indicare se Adobe Analytics deve considerarlo buono o cattivo se viene rilasciato un determinato evento personalizzato (metrica). Consente ad Adobe Analytics di mostrare indicatori direzionali (frecce) per diverse metriche per aggiungere contesto (ad esempio, settimana nel confronto della settimana. Esempi: Se i «Bug inviati» si spostano settimana su settimana, Adobe Analytics potrebbe essere considerato buono o cattivo? Un aumento delle registrazioni e-mail è probabilmente buono. Tuttavia, un aumento degli errori di invio del modulo potrebbe non essere corretto. In Analysis Workspace, la polarità viene applicata a: Formattazione condizionale Tabella a forma libera, visualizzazioni Variazione riepilogo e Schema colori positivo/negativo della visualizzazione Mappa. |
| Descrizione | Breve descrizione dello scopo e dell'utilizzo dell'evento. |
| Registrazione evento univoca | Vedi [Serializzazione degli eventi](/help/implement/js-implementation/event-serialization.md). |
| Partecipazione | See [Metrics Participation](/help/components/c-variables/c-metrics/metrics-participation.md). |
| Avviso (evento valuta) | Quando si modificano i tipi di evento in o da un evento di valuta, viene visualizzato un messaggio che indica che i dati storici non sono disponibili nei rapporti. Diversi tipi di eventi utilizzano tabelle di dati separate e non possono essere utilizzati contemporaneamente. Alcuni dati storici possono essere ripristinati se l'utente ripristina il tipo di evento. Tuttavia, tutti i dati raccolti dopo la modifica iniziale non sono disponibili. Utilizzate cautela quando si modifica un tipo di evento. |

