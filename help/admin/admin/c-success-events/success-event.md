---
description: Gli eventi di successo sono azioni che possono essere tracciate. È possibile determinare l'evento di successo. Ad esempio, se un visitatore acquista un articolo, l’evento di acquisto potrebbe essere considerato l’evento di successo.
keywords: prodView
title: Panoramica eventi di successo
feature: Admin Tools
exl-id: d52a691a-8124-4601-932f-d6d2d0a7842b
source-git-commit: ee56267979979f8e03b1c6a0d849ccf994599024
workflow-type: tm+mt
source-wordcount: '699'
ht-degree: 6%

---

# Panoramica eventi di successo

Gli eventi di successo (noti anche come eventi di conversione o eventi personalizzati) sono azioni che possono essere tracciati. È possibile determinare l&#39;evento di successo. Ad esempio, se un visitatore acquista un articolo, l’evento di acquisto potrebbe essere considerato l’evento di successo.

Panoramica video:

>[!VIDEO](https://video.tv.adobe.com/v/28764/?quality=12)

Accedi alla pagina Eventi di successo nelle impostazioni della suite di rapporti:

1. Accedi a [experiencecloud.adobe.com](https://experiencecloud.adobe.com) utilizzo delle credenziali AdobeID.
2. Fai clic sul pulsante a 9 griglia in alto, quindi fai clic su [!UICONTROL Analytics].
3. Passa a [!UICONTROL Admin] > [!UICONTROL Report Suites]
4. Seleziona la suite di rapporti desiderata, quindi passa a [!UICONTROL Edit Settings] > [!UICONTROL Conversion] > [!UICONTROL Success Events].
5. Individua l’evento desiderato e modifica [!UICONTROL Unique Event Recording] a discesa [!UICONTROL Record Once Per Visit] o [!UICONTROL Use Event ID].

Ci sono molti tipi di eventi di successo, a seconda del tipo di sito web. Alcuni esempi:

* **Retail**: Visualizzazione prodotto, pagamento, acquisto
* **Media**: Iscrizione, iscrizioni al concorso, visualizzazione pagina, visualizzazione video
* **Finanza**: Invio di applicazioni, accesso, utilizzo di strumenti self-service
* **Viaggi**: Prenotazione (acquisto), campagna interna (click-through), ricerca (itinerario di determinazione prezzi)
* **Telecomunicazioni**: Acquisto, lead, utilizzo di strumenti self-service
* **High Tech**: Download white paper, RFP, completamento del modulo, richieste di supporto
* **Automotive**: Invio di lead, richiesta preventivo, download di brochure

La [s.events](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/events/event-serialization.html?lang=it) definisce un evento riuscito.

## Pagina Eventi di successo - Descrizioni {#section_681ECEC981694CABBDBF00E18165B447}

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL Conversion]** > **[!UICONTROL Success Events]**

La pagina Eventi di successo consente di configurare le variabili evento utilizzate sul sito. Puoi aggiungere fino a 1.000 eventi di successo. Gli eventi 81-1.000 funzionano solo con codice H22 o superiore.

| Elemento | Descrizione |
|--- |--- |
| Evento | Nome originale dell&#39;evento. |
| Nome | Assegna nomi significativi agli eventi di successo utilizzati sul sito. Ad esempio, se l’evento1 viene utilizzato per tenere traccia delle registrazioni, cambia il nome in modo che l’evento1 venga rappresentato come metrica &quot;Registrazioni&quot; in tutti i rapporti di conversione. |
| Tipo | Il tipo selezionato determina se l&#39;evento è un evento contatore (standard), numerico o valuta. Gli eventi numerici e valutari consentono di incrementare le metriche di più di uno.  Gli eventi contatore vengono utilizzati per registrare un evento in tempo, mentre gli eventi valuta registrano un numero decimale, come l&#39;imposta o la spedizione. Il valore passato in eventi di valuta viene convertito dalla valuta della pagina alla valuta di base della suite di rapporti al momento della ricezione. Per informazioni sull&#39;utilizzo degli eventi relativi alla valuta, contattare un rappresentante di Adobe. Gli eventi numerici vengono utilizzati per generare rapporti sui numeri non in valuta, ad esempio il numero di coupon utilizzati in un ordine. Gli eventi di valuta vengono utilizzati per tenere traccia delle imposte e delle spese di spedizione. Gli eventi utilizzati nel tipo Standard di Origini dati devono essere eventi numerici o valutari. |
| Polarità | La polarità delle metriche consente di indicare se Adobe Analytics deve considerare positivo o negativo l’aumento di un dato evento personalizzato (metrica). Consentirà ad Adobe Analytics di mostrare indicatori direzionali (frecce) per diverse metriche per aggiungere contesto (ad esempio, confronti settimana per settimana).  Esempi: se &quot;Bug inviati&quot; aumenta settimana dopo settimana, Adobe Analytics dovrebbe considerarlo buono, o cattivo? Un aumento delle registrazioni e-mail è probabilmente positivo. Tuttavia, un aumento degli errori di invio del modulo è probabilmente negativo.  In Analysis Workspace, la polarità viene applicata a: Formattazione condizionale della tabella a forma libera, visualizzazioni Variazione di riepilogo e schema di colori positivo/negativo della visualizzazione Mappa. |
| Descrizione | Breve descrizione dello scopo e dell’utilizzo dell’evento. |
| Registrazione di eventi unica | **Registra una volta per visita**: lega l’evento specificato alla sessione del visitatore. I conteggi successivi per un dato evento nella stessa visita vengono ignorati. Questo tipo di serializzazione dell&#39;evento non richiede alcuna modifica dell&#39;implementazione.<br>**Usa ID evento**: lega l&#39;evento specificato a un ID personalizzato. I conteggi successivi per un dato evento con lo stesso ID evento vengono ignorati. Questo tipo di serializzazione degli eventi richiede un ID personalizzato nei risultati per deduplicare i valori. Vedi [Serializzazione degli ID evento](../../../implement/vars/page-vars/events/event-serialization.md) nella guida utente Implementa . |
| Partecipazione | Attribuisce un credito di attribuzione completo a tutti gli elementi dimensionali nella visita. |
| Avviso (evento valuta) | Quando si modificano i tipi di evento in o da un evento valuta, viene visualizzato un messaggio che indica che i dati storici non sono disponibili nel reporting.  I tipi di evento diversi utilizzano tabelle di dati separate e non possono essere utilizzati contemporaneamente. Alcuni dati storici possono essere ripristinati se l’utente ripristina il tipo di evento. Tuttavia, i dati raccolti dopo la modifica iniziale non sono disponibili. Presta attenzione quando modifichi un tipo di evento. |
