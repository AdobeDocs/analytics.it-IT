---
description: Gli eventi di successo sono azioni che possono essere tracciate. È possibile determinare la natura dell’evento di successo. Ad esempio, se un visitatore acquista un articolo, l’evento di acquisto potrebbe essere considerato l’evento di successo.
keywords: evento
title: Panoramica degli eventi di successo
feature: Metrics
role: Admin
exl-id: d52a691a-8124-4601-932f-d6d2d0a7842b
TQID: https://experienceleague.adobe.com/wOWG6t9fsrfkd4FE-BNkwIrPW6DEGxBKDc2XItyRaoc
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2: id: a544b409-2610-410d-a842-474ac1d0d54eid: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06id: b3a8b8a0-1cc2-48a8-ac82-ffd9c66ccab4id: dcae653e-62c6-4cc8-84e6-ee110b848296id: ef60b66e-5984-4336-ba72-6d978b1b6f87id: f1f1a2d4-0976-4881-b091-c2bb8de7ffacid: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d3cdead0-685a-4489-9250-4bb709942f66id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 949
ht-degree: 47%

---

# Eventi di successo

Gli eventi di successo (noti anche come eventi di conversione o eventi personalizzati) sono azioni che possono essere tracciate. È possibile determinare la natura dell’evento di successo. Ad esempio, se un visitatore acquista un articolo, l’evento di acquisto potrebbe essere considerato l’evento di successo.

Per una panoramica video degli eventi di successo, consulta [Introduzione agli eventi di conversione](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/metrics/introduction-to-conversion-events) nella guida delle esercitazioni di Analytics.

## Esempi di eventi di successo

Ci sono molti tipi di eventi di successo, a seconda del tipo di sito web. Alcuni esempi:

* **Retail**: visualizzazione prodotto, pagamento, acquisto
* **Media**: abbonamento, iscrizioni a concorsi, visualizzazione pagina, visualizzazione video
* **Finanza**: invio di richieste, accesso, utilizzo di strumenti self-service
* **Viaggi**: prenotazione (acquisto), campagna interna (click-through), ricerca (itinerario di determinazione prezzi)
* **Telecomunicazioni**: acquisto, lead, utilizzo di strumenti self-service
* **High Tech**: download di white paper, RFP, completamento di moduli, richieste di supporto
* **Automotive**: invio di lead, richiesta preventivo, download di brochure

La variabile [s.events](/help/implement/vars/page-vars/events/event-serialization.md) definisce un evento di successo.

## Configurare eventi di successo

Puoi configurare le variabili evento utilizzate sul tuo sito. Puoi aggiungere fino a 1.000 eventi di successo. Gli eventi da 81 a 1.000 funzionano solo se utilizzi il codice H22 o superiore.

Per configurare eventi di successo:

1. In Adobe Analytics, selezionare **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. Seleziona la suite di rapporti in cui desideri configurare gli eventi di successo.
1. Selezionare **[!UICONTROL Edit Settings]** > **[!UICONTROL Conversion]** > **[!UICONTROL Success Events]**.

   ![Risultato del passaggio](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/c-success-events/assets/success_event_page.png)

1. Nella colonna [!UICONTROL **Evento**] identificare il nome dell&#39;evento che si desidera utilizzare come evento di successo.

1. Nella colonna **[!UICONTROL Name]**, seleziona la casella di controllo accanto all&#39;elemento per abilitarne la modifica, quindi specifica il nome desiderato.

   Assegna nomi significativi agli eventi di successo utilizzati nel sito. Ad esempio, se event1 viene utilizzato per tenere traccia delle registrazioni, cambia il nome in modo che event1 venga rappresentato come metrica “Registrazioni” in tutti i rapporti di conversione.

1. Nella colonna **[!UICONTROL Type]** selezionare la casella di controllo accanto all&#39;elemento per abilitare l&#39;elenco a discesa, quindi selezionare il tipo desiderato.

   >[!IMPORTANT]
   >
   >Quando modifichi il tipo di evento, tieni presente quanto segue:<ul><li>È possibile modificare il tipo di evento tra contatore e numerico senza perdere l’accesso ai dati acquisiti in precedenza.</li><li>Quando si modificano i tipi di evento in o da un evento di valuta, viene visualizzato un messaggio che informa che i dati storici non sono disponibili nel reporting. I tipi di evento diversi utilizzano tabelle di dati separate e non possono essere utilizzati contemporaneamente. Alcuni dati storici possono essere ripristinati se l’utente ripristina il tipo di evento. Tuttavia, i dati raccolti dopo la modifica iniziale non sono disponibili.</li></ul>

   Il tipo selezionato determina se l&#39;evento è un evento contatore (standard), numerico o di valuta. <p>Gli eventi contatore vengono utilizzati per registrare un evento nel tempo.</p><p>Gli eventi numerici vengono utilizzati per generare rapporti sui numeri non in valuta, ad esempio il numero di coupon utilizzati in un ordine.</p> <p>Gli eventi di valuta registrano un numero decimale, ad esempio imposta o spedizione. Il valore passato negli eventi di valuta viene convertito dalla valuta della pagina alla valuta di base della suite di rapporti al momento della ricezione. Gli eventi di valuta vengono utilizzati per tenere traccia delle imposte e delle spese di spedizione. Per informazioni sull’utilizzo degli eventi relativi alla valuta, contatta un rappresentante di Adobe.<p>Gli eventi numerici e di valuta consentono di incrementare le metriche di più di uno.</p><p>Gli eventi utilizzati nel tipo Standard di Origini dati devono essere eventi numerici o di valuta.</p>

1. Nella colonna **[!UICONTROL Polarity]**, seleziona la casella di controllo, quindi scegli dal menu a discesa se una tendenza verso l’alto per questa metrica è buona o cattiva.

   questo consente di indicare se Adobe Analytics deve considerare positivo o negativo l’aumento di un dato evento personalizzato (metrica). Attiva indicatori direzionali (frecce) per varie metriche per aggiungere contesto (ad esempio, confronti settimana per settimana).  Esempi: se “Bug inviati” aumenta settimana dopo settimana, Adobe Analytics deve considerarlo positivo o negativo? Un aumento delle registrazioni e-mail è probabilmente positivo. Tuttavia, un aumento degli errori di invio del modulo è probabilmente negativo.  In Analysis Workspace, la polarità viene applicata a: Formattazione condizionale della tabella a forma libera, visualizzazioni Variazione di riepilogo e schema di colori positivo/negativo della visualizzazione Mappa.

1. Nella colonna **[!UICONTROL Visibility]**, seleziona la casella di controllo, quindi scegli dal menu a discesa se nascondere le metriche standard (integrate), gli eventi personalizzati e gli eventi incorporati in Menu, Selettori metriche, Generatore metriche calcolate e Generatore segmenti.

   Questa impostazione non influisce sulla raccolta di dati per quella metrica o evento; influisce solo sulla sua visibilità nell’interfaccia utente, come segue:

   Sono disponibili le seguenti impostazioni:

   | Impostazione | Visibile in | Non visibile in |
   |---------|----------|---------|
   | [!UICONTROL **Visibile ovunque**] | <ul><li>Analysis Workspace</li><li>Generatore di segmenti</li><li>Generatore di metrica calcolata</li></ul> | N/D |
   | [!UICONTROL **Generatori**] | <ul><li>Generatore di segmenti</li><li>Generatore di metrica calcolata</li><li>Analysis Workspace</li></ul> |  |
   | [!UICONTROL **Nascosto ovunque**] | N/D | <ul><li>Analysis Workspace</li><li>Generatore di segmenti</li><li>Generatore di metrica calcolata</li></ul> |

1. Nella colonna [!UICONTROL **Descrizione**], seleziona la casella di controllo, quindi fornisci una descrizione.
1. Nella colonna [!UICONTROL **Registrazione evento univoca**] selezionare la casella di controllo, quindi scegliere dal menu a discesa se registrare sempre l&#39;evento.

   Sono disponibili le seguenti opzioni:

   | Opzione | Funzione |
   |---------|----------|
   | [!UICONTROL **Registra una volta per visita**] | Associa l’evento specificato alla sessione del visitatore. I conteggi successivi per un dato evento durante la stessa visita vengono ignorati. Questo tipo di serializzazione dell’evento non richiede alcuna modifica dell’implementazione. |
   | [!UICONTROL **Usa ID evento**] | Associa l’evento specificato a un ID personalizzato. I conteggi successivi per un dato evento con lo stesso ID evento vengono ignorati. Questo tipo di serializzazione degli eventi richiede un ID personalizzato nei risultati per deduplicare i valori. Vedi [Serializzazione degli ID evento](/help/implement/vars/page-vars/events/event-serialization.md) nella Guida utente di implementazione. |

1. Nella colonna [!UICONTROL **Partecipazione**] selezionare la casella di controllo, quindi scegliere se attivare o disattivare la partecipazione. Quando è abilitato, attribuisce il merito di attribuzione completo a tutti gli elementi dimensionali nella visita.

   >[!NOTE]
   >
   >Puoi abilitare la partecipazione per un massimo di 100 eventi personalizzati. Inoltre, puoi creare metriche di partecipazione nel generatore [Metriche calcolate](/help/components/calculated-metrics/workflow/c-build-metrics/participation-metric.md).

1. Seleziona **[!UICONTROL Save]**.
