---
description: Gli eventi di successo sono azioni che possono essere tracciate. È possibile determinare la natura dell’evento di successo. Ad esempio, se un visitatore acquista un articolo, l’evento di acquisto potrebbe essere considerato l’evento di successo.
keywords: evento
title: Panoramica degli eventi di successo
feature: Event
exl-id: d52a691a-8124-4601-932f-d6d2d0a7842b
source-git-commit: f659d1bde361550928528c7f2a70531e3ac88047
workflow-type: ht
source-wordcount: '699'
ht-degree: 100%

---

# Panoramica degli eventi di successo

Gli eventi di successo (noti anche come eventi di conversione o eventi personalizzati) sono azioni che possono essere tracciate. È possibile determinare la natura dell’evento di successo. Ad esempio, se un visitatore acquista un articolo, l’evento di acquisto potrebbe essere considerato l’evento di successo.

Panoramica video:

>[!VIDEO](https://video.tv.adobe.com/v/28764/?quality=12)

Accedi alla pagina degli eventi di successo nelle impostazioni della suite di rapporti:

1. Accedi a [experiencecloud.adobe.com](https://experiencecloud.adobe.com) utilizzando le credenziali Adobe ID.
2. Fai clic sul pulsante della griglia a 9 celle in alto, quindi fai clic su [!UICONTROL Analytics].
3. Passa a [!UICONTROL Admin] > [!UICONTROL Report Suites]
4. Seleziona la suite di rapporti desiderata, quindi passa a [!UICONTROL Edit Settings] > [!UICONTROL Conversion] > [!UICONTROL Success Events].
5. Individua l’evento desiderato e modifica l’elenco a discesa [!UICONTROL Unique Event Recording] in [!UICONTROL Record Once Per Visit] o [!UICONTROL Use Event ID].

Ci sono molti tipi di eventi di successo, a seconda del tipo di sito web. Alcuni esempi:

* **Retail**: visualizzazione prodotto, pagamento, acquisto
* **Media**: abbonamento, iscrizioni a concorsi, visualizzazione pagina, visualizzazione video
* **Finanza**: invio di richieste, accesso, utilizzo di strumenti self-service
* **Viaggi**: prenotazione (acquisto), campagna interna (click-through), ricerca (itinerario di determinazione prezzi)
* **Telecomunicazioni**: acquisto, lead, utilizzo di strumenti self-service
* **High Tech**: download di white paper, RFP, completamento di moduli, richieste di supporto
* **Automotive**: invio di lead, richiesta preventivo, download di brochure

La variabile [s.events](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/events/event-serialization.html?lang=it) definisce un evento di successo.

## Pagina Eventi di successo - Descrizioni {#section_681ECEC981694CABBDBF00E18165B447}

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL Conversion]** > **[!UICONTROL Success Events]**

La pagina Eventi di successo consente di configurare le variabili evento utilizzate nel sito. Puoi aggiungere fino a 1.000 eventi di successo. Gli eventi da 81 a 1.000 funzionano solo con codice H22 o superiore.

| Elemento | Descrizione |
|--- |--- |
| Evento | Nome originale dell’evento. |
| Nome | Assegna nomi significativi agli eventi di successo utilizzati nel sito. Ad esempio, se event1 viene utilizzato per tenere traccia delle registrazioni, cambia il nome in modo che event1 venga rappresentato come metrica “Registrazioni” in tutti i rapporti di conversione. |
| Tipo | Il tipo selezionato determina se l’evento è un evento contatore (standard), numerico o valuta. Gli eventi numerici e di valuta consentono di incrementare le metriche di più di uno.  Gli eventi contatore vengono utilizzati per registrare un evento nel tempo, mentre gli eventi di valuta registrano un numero decimale, ad esempio l’imposta o la spedizione. Il valore passato negli eventi di valuta viene convertito dalla valuta della pagina alla valuta di base della suite di rapporti al momento della ricezione. Per informazioni sull’utilizzo degli eventi relativi alla valuta, contatta un rappresentante di Adobe. Gli eventi numerici vengono utilizzati per generare rapporti sui numeri non in valuta, ad esempio il numero di coupon utilizzati in un ordine. Gli eventi di valuta vengono utilizzati per tenere traccia delle imposte e delle spese di spedizione. Gli eventi utilizzati nel tipo Standard di Origini dati devono essere eventi numerici o di valuta. |
| Polarità | La polarità delle metriche consente di indicare se Adobe Analytics debba considerare positivo o negativo l’aumento di un determinato evento personalizzato (metrica). Consentirà ad Adobe Analytics di visualizzare indicatori direzionali (frecce) per diverse metriche per aggiungere contesto (ad esempio, confronti settimana per settimana.  Esempi: se “Bug inviati” aumenta settimana dopo settimana, Adobe Analytics deve considerarlo positivo o negativo? Un aumento delle registrazioni e-mail è probabilmente positivo. Tuttavia, un aumento degli errori di invio del modulo è probabilmente negativo.  In Analysis Workspace, la polarità viene applicata a: Formattazione condizionale della tabella a forma libera, visualizzazioni Variazione di riepilogo e schema di colori positivo/negativo della visualizzazione Mappa. |
| Descrizione | Breve descrizione dello scopo e dell’utilizzo dell’evento. |
| Registrazione di eventi univoci | **Registra una volta per visita**: associa l’evento specificato alla sessione del visitatore. I conteggi successivi per un dato evento durante la stessa visita vengono ignorati. Questo tipo di serializzazione dell’evento non richiede alcuna modifica dell’implementazione.<br>**Usa ID evento**: lega l’evento specificato a un ID personalizzato. I conteggi successivi per un dato evento con lo stesso ID evento vengono ignorati. Questo tipo di serializzazione degli eventi richiede un ID personalizzato nei risultati per deduplicare i valori. Vedi [Serializzazione degli ID evento](../../../implement/vars/page-vars/events/event-serialization.md) nella Guida utente di implementazione. |
| Partecipazione | Attribuisce il merito di attribuzione completo a tutti gli elementi dimensionali nella visita. |
| Avviso (evento di valuta) | Quando si modificano i tipi di evento in o da un evento di valuta, un messaggio indica che i dati storici non sono disponibili nella reportistica.  I tipi di evento diversi utilizzano tabelle di dati separate e non possono essere utilizzati contemporaneamente. Alcuni dati storici possono essere ripristinati se l’utente ripristina il tipo di evento. Tuttavia, i dati raccolti dopo la modifica iniziale non sono disponibili. Presta attenzione quando modifichi un tipo di evento. |
