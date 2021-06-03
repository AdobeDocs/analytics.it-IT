---
description: Gli eventi di successo sono azioni che possono essere tracciate. È possibile determinare l'evento di successo. Ad esempio, se un visitatore acquista un articolo, l’evento di acquisto potrebbe essere considerato l’evento di successo.
keywords: prodView
title: Panoramica eventi di successo
feature: Strumenti di amministrazione
uuid: 410eee44-8960-462c-a9c3-07b44d0b1df0
exl-id: d52a691a-8124-4601-932f-d6d2d0a7842b
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '688'
ht-degree: 4%

---

# Panoramica eventi di successo

Gli eventi di successo sono azioni che possono essere tracciate. È possibile determinare l&#39;evento di successo. Ad esempio, se un visitatore acquista un articolo, l’evento di acquisto potrebbe essere considerato l’evento di successo.

Accedi alla pagina Eventi di successo nelle impostazioni della suite di rapporti:

1. Accedi a [experiencecloud.adobe.com](https://experiencecloud.adobe.com) utilizzando le credenziali AdobeID.
2. Fai clic sul pulsante a 9 griglia in alto, quindi fai clic su [!UICONTROL Analytics].
3. Passa a [!UICONTROL Admin] > [!UICONTROL Report Suites]
4. Seleziona la suite di rapporti desiderata, quindi passa a [!UICONTROL Edit Settings] > [!UICONTROL Conversion] > [!UICONTROL Success Events].
5. Individua l’evento desiderato e modifica il menu a discesa [!UICONTROL Unique Event Recording] in [!UICONTROL Record Once Per Visit] o [!UICONTROL Use Event ID].

Ci sono molti tipi di eventi di successo, a seconda del tipo di sito web. Alcuni esempi:

* **Retail**: Visualizzazione prodotto, pagamento, acquisto
* **Media**: Iscrizione, iscrizioni al concorso, visualizzazione pagina, visualizzazione video
* **Finanza**: Invio di applicazioni, accesso, utilizzo di strumenti self-service
* **Viaggi**: Prenotazione (acquisto), campagna interna (click-through), ricerca (itinerario di determinazione prezzi)
* **Telecomunicazioni**: Acquisto, lead, utilizzo di strumenti self-service
* **High Tech**: Download white paper, RFP, completamento del modulo, richieste di supporto
* **Automotive**: Invio di lead, richiesta preventivo, download di brochure

La variabile [s.events](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/events/event-serialization.html) definisce un evento riuscito.

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
| Registrazione di eventi unica | **Record Una Volta Per Visita**: lega l’evento specificato alla sessione del visitatore. I conteggi successivi per un dato evento nella stessa visita vengono ignorati. Questo tipo di serializzazione dell&#39;evento non richiede alcuna modifica dell&#39;implementazione.<br>**Usa ID** evento: lega l&#39;evento specificato a un ID personalizzato. I conteggi successivi per un dato evento con lo stesso ID evento vengono ignorati. Questo tipo di serializzazione degli eventi richiede un ID personalizzato nei risultati per deduplicare i valori. Consulta [Serializzazione degli ID evento](../../../implement/vars/page-vars/events/event-serialization.md) nella guida utente Implementa. |
| Partecipazione | Attribuisce un credito di attribuzione completo a tutti gli elementi dimensionali nella visita. |
| Avviso (evento valuta) | Quando si modificano i tipi di evento in o da un evento valuta, viene visualizzato un messaggio che indica che i dati storici non sono disponibili nel reporting.  I tipi di evento diversi utilizzano tabelle di dati separate e non possono essere utilizzati contemporaneamente. Alcuni dati storici possono essere ripristinati se l’utente ripristina il tipo di evento. Tuttavia, i dati raccolti dopo la modifica iniziale non sono disponibili. Presta attenzione quando modifichi un tipo di evento. |
