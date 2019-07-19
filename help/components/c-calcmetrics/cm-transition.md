---
description: Queste modifiche al modo in cui le metriche calcolate funzionano in Analytics possono interessarvi.
seo-description: Queste modifiche al modo in cui le metriche calcolate funzionano in Analytics possono interessarvi.
seo-title: Domande frequenti
title: Domande frequenti
uuid: 9 b 7 f 1 cd 1-b 969-4 b 15-8 af 1-969 d 816 b 65 b 8
translation-type: tm+mt
source-git-commit: ecc762f73f9a303cebf48668b807fef9a2f055c5

---


# Domande frequenti

These changes to the way calculated metrics work in [!DNL Analytics] may impact you.

[Come si accede al Generatore di metriche calcolate?](../../components/c-calcmetrics/cm-transition.md#section_D9AE9A0ACF824BACB5D05F0C2F7E9CA1)

[Come si accede al Gestore metriche calcolate?](../../components/c-calcmetrics/cm-transition.md#section_DD0BD13E9EC940268EBE8BC88241A152)

[Perché trovo un numero di metriche calcolate con lo stesso nome?](../../components/c-calcmetrics/cm-transition.md#section_E15C5B6CCC58498CAEC3FBDA8988F0A1)

[Cosa succede alle metriche calcolate globali?](../../components/c-calcmetrics/cm-transition.md#section_7351D4C7361F4ABAA1B43F8E89AAD211)

[Cosa è accaduto a Metriche calcolate globali condivise tra le aziende di accesso?](../../components/c-calcmetrics/cm-transition.md#section_59E5CD948ED643AE9AD3D2E4277647F8)

[Cosa è accaduto a Metriche calcolate con classificazione numerico o numerico 2?](../../components/c-calcmetrics/cm-transition.md#section_71AFE6C4A7CD4AA19AB3A9D3C41D115B)

[Cosa è accaduto alle metriche del tempo reale?](../../components/c-calcmetrics/cm-transition.md#section_AEDB02EF24584DAD8731BED9DDCE4F48)

[Cosa devo sapere su Metriche calcolate basate sulle metriche giornaliere/settimanali/mensili/trimestrali/annuali?](../../components/c-calcmetrics/cm-transition.md#section_E9A77EBB41CE4881B196CC1C282B2DF3)

[What about Calculated Metrics created or managed with the old report suite API?](../../components/c-calcmetrics/cm-transition.md#section_13ED1BAD02634674BDAEB479B060A4B6)

[Dati correnti supporta tutti i tipi di metriche calcolate?](../../components/c-calcmetrics/cm-transition.md#section_1DAA718BB8DB4413BAF8AD4B4FAAFFA2)

[Cosa significa «No name provided» (Nessun nome fornito) insieme alle metriche calcolate migrate?](../../components/c-calcmetrics/cm-transition.md#section_C90CBB72A67644F38D583301981F8D03)

[Cosa succede alle metriche calcolate di un utente se quell'utente è stato eliminato?](../../components/c-calcmetrics/cm-transition.md#section_42ED4C15830540879C4A161423690E5A)

[Perché visualizzi metriche calcolate «Sconosciute» non valide per altre suite di rapporti, anche se possono essere create e applicate a tali suite di rapporti?](../../components/c-calcmetrics/cm-transition.md#section_6772818EFDED46E9B7095D64C3B77211)

[Perché sono state apportate modifiche alle metriche calcolate legacy non salvate?](../../components/c-calcmetrics/cm-transition.md#section_81CDEFCA1FD542579AF183DA1494EAF0)

[Perché le metriche calcolate non vengono visualizzate nel report Marketing Channels (Canali di marketing)?](../../components/c-calcmetrics/cm-transition.md#section_FC350359A775433AB5F43C7CAB304D62)

[Perché alcune metriche calcolate mostrano formule senza le parentesi che ho aggiunto?](../../components/c-calcmetrics/cm-transition.md#section_AC0D1E9714AD487F9A1C73359F518B5E)

[(Solo Analisi ad hoc) Le metriche calcolate con definizioni dei segmenti incorporate o in linea continuano a essere supportate?](../../components/c-calcmetrics/cm-transition.md#section_B25C924A282F49388AB604E3D826F44C)

[(Solo Generatore di report) Perché le metriche calcolate sono scomparse dalle mie richieste?](../../components/c-calcmetrics/cm-transition.md#section_DA4792FE5D7945218CD5E6328DE08E82)

[Come funzionano i totali delle metriche calcolate?](../../components/c-calcmetrics/cm-transition.md#section_57BA3A299C7948ABB82B0392A9B0F33E)

## How do I access the Calculated Metric Builder? {#section_D9AE9A0ACF824BACB5D05F0C2F7E9CA1}

* Click **[!UICONTROL + Add]** at the top of the Calculated Metric Manager, or
* In any Analytics report, click the Metrics icon  ![](assets/metrics_icon.png) to the left of a report to bring up the Metrics rail, then click **[!UICONTROL Add]**.

## How do I access the Calculated Metric Manager? {#section_DD0BD13E9EC940268EBE8BC88241A152}

* Go to  **[!UICONTROL Analytics]** &gt; **[!UICONTROL Components]** in the left navigation. Then click **[!UICONTROL Calculated Metrics]**.

* In any [!DNL Analytics] report, click the Metrics icon  ![](assets/metrics_icon.png) to the left of a report to bring up the Metrics rail, then click **[!UICONTROL Manage]**.

## Why do I see so many Calculated Metrics with the same name? {#section_E15C5B6CCC58498CAEC3FBDA8988F0A1}

(In precedenza, le metriche calcolate globali non erano di proprietà da parte di un utente amministratore specifico e erano visibili a tutti gli utenti della suite di rapporti. Le metriche venivano separate dalla suite di rapporti. Se una metrica in una suite di rapporti aveva lo stesso nome di una metrica in una suite di rapporti diversa, apparirebbe semplicemente agli utenti come la stessa metrica quando hanno cambiato suite di rapporti.

Adesso, le metriche non sono più separate dalle suite di rapporti. Se una metrica in una suite di rapporti ha lo stesso nome di una metrica in una suite di rapporti diversa, entrambe saranno visibili sia nel Generatore metriche calcolate che nel Selettore metriche, e potrebbero essere visualizzate come metriche duplicate, anche se possono avere la stessa definizione.

You would see a number of calculated metrics with the same name (but created in different report suites) only if you unchecked the (Only `<report suite>`) checkbox as shown here:

![](assets/report_suite.png)

**Cosa dovete fare**

Prendete in considerazione il consolidamento delle metriche calcolate con nomi e definizioni simili, ma con cautela nel farlo. Puoi controllare la suite di rapporti per una metrica calcolata nel Gestore metriche calcolate, per verificarne la suite originale. È inoltre necessario controllare le definizioni delle metriche durante l'eliminazione di potenziali duplicati per garantire il corretto consolidamento delle metriche.

> [!NOTE] Anche se le metriche calcolate non sono più associate a una suite di rapporti specifica e possono essere utilizzate in qualsiasi suite di rapporti che sia visibile per la società di accesso, la suite di rapporti in cui è stata creata la metrica calcolata o l'ultimo salvataggio è ancora visibile nel Gestore metriche calcolate.

> [!NOTE] Anche se una metrica calcolata viene eliminata, tutti i segnalibri o i rapporti dashboard che fanno riferimento a tale metrica continueranno a funzionare.

## What happened to my Global Calculated Metrics? {#section_7351D4C7361F4ABAA1B43F8E89AAD211}

(In precedenza, un amministratore poteva creare metriche calcolate (denominate metriche calcolate globali o «suite di rapporti calcolate») in una suite di rapporti tramite Strumenti di amministrazione.

Le metriche calcolate globali sono ora di proprietà del primo utente Admin nell'elenco di utenti Admin della società di accesso. Saranno condivisi con «Tutti» per impostazione predefinita. Questo pattern segue gli stessi piani di condivisione e di migrazione come segmenti.

**Cosa dovete fare**

Niente. Tuttavia, il nuovo proprietario amministratore deve prestare molta attenzione durante la modifica o l'eliminazione di queste metriche calcolate, che possono essere utilizzate in una serie di report con segnalibro e dashboard.

> [!NOTE] Anche se una metrica calcolata viene eliminata, tutti i segnalibri o i rapporti dashboard che fanno riferimento a tale metrica continueranno a funzionare.

## What happened to Global Calculated Metrics that were shared across Login Companies? {#section_59E5CD948ED643AE9AD3D2E4277647F8}

(In precedenza, un amministratore poteva creare metriche calcolate (denominate metriche calcolate globali o «suite di rapporti calcolate») in una suite di rapporti tramite Strumenti di amministrazione. Queste metriche possono essere "condivise" nelle società di accesso aggiungendo la suite di rapporti a più società di accesso.

Le metriche calcolate globali non possono più essere condivise tra le società di accesso. Non sono più associati o associati a una suite di rapporti specifica, ma sono collegati a una società di accesso specifica. Metriche calcolate condivise tra le società di accesso

* Sono state migrate a tutte le società di accesso con accesso a quella suite di rapporti.
* Impostazione predefinita: «Condiviso con tutti».
* Saranno copie indipendenti da tutte le altre società di accesso.

>[!NOTE]
>
>Se la metrica calcolata era utilizzata in un segnalibro, in una dashboard, in un avviso o in un rapporto pianificato, la modifica della nuova copia NON influirà sulla vecchia metrica calcolata persistente.

## What happened to Calculated Metrics with a Numeric or Numeric2 Classification? {#section_71AFE6C4A7CD4AA19AB3A9D3C41D115B}

(Previously, calculated metrics with a Numeric or Numeric2 classification were only visible in [!UICONTROL Reports & Analytics], [!UICONTROL Report Builder], and the APIs.)

Now, calculated metrics with a Numeric or Numeric2 classification will continue to be visible in [!UICONTROL Reports & Analytics], [!UICONTROL Report Builder], and the APIs. Tuttavia, non saranno supportati in alcun rapporto con un segmento applicato.

In addition, calculated metrics with a Numeric or Numeric2 classification will not be supported in the following components: [!UICONTROL Ad Hoc Analysis], [!UICONTROL Analysis Workspace], [!UICONTROL Real-Time] reports, [!UICONTROL Anomaly Detection], and [!UICONTROL Contribution Analysis]. Quando create o modificate una metrica calcolata con una classificazione numerico o numerico 2, viene visualizzato un avviso di compatibilità che informa che la metrica calcolata non è compatibile con determinate aree del prodotto.

**Cosa dovete fare**

Evitate di creare metriche calcolate con classificazioni numeriche 1 o numeriche 2 se la metrica è destinata a essere utilizzata con un segmento o con uno dei componenti non compatibili.

## What happened to Life-Time Metrics? {#section_AEDB02EF24584DAD8731BED9DDCE4F48}

Life-Time metrics (a.k.a. all-time metrics) are no longer supported and no longer visible in the [!UICONTROL Reports & Analytics] UI or any other UI. Non possono essere interrogati dall'API rapporto.

Tutti i segnalibri, i dashboard, i report pianificati o gli avvisi che contengono una metrica temporale continueranno a essere eseguiti senza quella metrica, purché nel report sia anche presente almeno un'altra metrica valida. Se l'unica metrica sul segnalibro, il dashboard, il rapporto pianificato o l'avviso è una metrica temporale, il report non verrà più eseguito.

## What do I need to know about Calculated Metrics based on Daily/Weekly/Monthly/Quarterly/Yearly Unique Visitor metrics? {#section_E9A77EBB41CE4881B196CC1C282B2DF3}

Calculated metrics based on Unique Visitor metrics will be visible in the following [!DNL Analytics] components: [!UICONTROL Reports & Analytics], [!UICONTROL Report Builder], and Reporting API.

However, these metrics will not be supported in the following components: [!UICONTROL Segments], [!UICONTROL Analysis Workspace], [!UICONTROL Real-Time] reports, [!UICONTROL Anomaly Detection], and [!UICONTROL Contribution Analysis]. Quando create o modificate una metrica calcolata basata sulle metriche Visitatori univoci, viene visualizzato un avviso di compatibilità che informa che la metrica non è compatibile con determinate aree del prodotto.

Puoi utilizzare una metrica Visitatore univoco su un rapporto con un segmento. Puoi creare una metrica calcolata basata su una metrica Visitatore univoco; Tuttavia, la metrica calcolata non può essere applicata a un report con un segmento, né può avere un segmento incorporato in esso.

## What happens to Calculated Metrics created or managed with the old report suite API methods? {#section_13ED1BAD02634674BDAEB479B060A4B6}

In precedenza, il salvataggio di una metrica calcolata con il metodo API (1.3 o 1.4) API reportsuite. savecalculatedmetrics corrispondeva alla creazione o all'aggiornamento di una metrica calcolata in Admin Console. Lo stesso applicato a reportsuite. deletecalculatedmetrics. Inoltre, l'elenco delle metriche calcolate visualizzate nell'Admin Console o durante la chiamata di reportsuite. getcalculatedmetrics era la stessa.

Ora, i metodi API calculatedmetrics (1.3 o 1.4) continueranno a salvare, eliminare e recuperare le metriche calcolate utilizzando il vecchio store. Le metriche calcolate esistenti verranno trasferite e saranno visibili nel nuovo Generatore di metriche calcolate. **Le nuove metriche calcolate create con i metodi API saranno visibili solo nell'API. They will still be usable in the Reporting API.**

**Cosa dovete fare**

Se devi utilizzare sia l'API che il Generatore di metriche calcolate, devi interrompere l'utilizzo dei metodi API calculatedmetrics di reportsuite e utilizzare i nuovi metodi API calculatedmetrics (Get, Save, Delete e getfunctions).

## Does Current Data support all types of Calculated Metrics? {#section_1DAA718BB8DB4413BAF8AD4B4FAAFFA2}

I dati correnti non supportano le metriche calcolate contenenti segmenti o funzioni statistiche. Le uniche funzioni supportate sono funzioni matematiche di base come aggiunta, eliminazione, moltiplicazione, divisione e negazione (-x).

## What does "No name provided" mean in conjunction with migrated calculated metrics? {#section_C90CBB72A67644F38D583301981F8D03}

" Nessun nome fornito "significa che non è associato alcun nome di metrica a questa metrica migrata (solo una formula senza nome descrittivo).

## What happens to a user's calculated metrics if that user was deleted? {#section_42ED4C15830540879C4A161423690E5A}

Vengono inoltre eliminate tutte le metriche calcolate create dall'utente. Tuttavia, le metriche calcolate eliminate continueranno a funzionare come parte di segnalibri salvati, dashboard o rapporti pianificati.

## Why do I see “Unknown" calculated metrics that aren't 'valid' for other report suites even though they can be created and applied to those report suites? {#section_6772818EFDED46E9B7095D64C3B77211}

L'interfaccia utente visualizza «unknown» se la metrica calcolata contiene metriche di base o dimensioni che non esistono per la suite di rapporti selezionata.

## Why were changes that I made to my legacy calculated metrics not saved? {#section_81CDEFCA1FD542579AF183DA1494EAF0}

Questo potrebbe dipendere dal tempo della migrazione al nuovo database delle metriche calcolate, verificatosi tra il 15 giugno e il 18 giugno 2015.

**Cosa dovete fare**

Dovrai ripristinare le modifiche apportate alle metriche legacy.

## Why don’t my calculated metrics show up in the Marketing Channels report? {#section_FC350359A775433AB5F43C7CAB304D62}

(In precedenza, tutte le metriche calcolate erano elencate nel selettore delle metriche sui report Canali di marketing con un'opzione Primo tocco e Ultimo tocco).

Adesso, nel selettore delle metriche sui report di Marketing Channels (Canali di marketing) sono disponibili solo quelle calcolate con tipo di allocazione specificatamente impostato su First Touch (Primo contatto) o Last Touch (Ultimo tocco). Eventuali metriche calcolate già applicate ai report Canale marketing continueranno a essere applicate e funzionano come prima. Per creare una metrica calcolata per Marketing Channels (Canali di marketing), fai clic sull'icona di configurazione nel generatore di metriche e seleziona First Touch (Primo tocco) o Last Touch (Ultimo contatto) come tipo di allocazione. Tieni presente che la metrica calcolata sarà compatibile solo con i rapporti Canale di marketing e non sarà utilizzabile in nessun altro rapporto.

## Why do some of the calculated metrics show formulas without the parentheses I added? {#section_AC0D1E9714AD487F9A1C73359F518B5E}

Durante la migrazione, Adobe estrae parentesi superflue da alcune formule. Sono state rimosse solo le parentesi che non influenzano il calcolo della metrica. Questo non modificherà i dati, semplificando semplicemente la formula.

## (Ad Hoc Analysis only) Are Calculated Metrics with embedded or inline segment definitions still supported? {#section_B25C924A282F49388AB604E3D826F44C}

Le metriche calcolate create in Analisi ad hoc possono in precedenza contenere definizioni dei segmenti in linea. Non è più possibile.

**Cosa dovete fare**

Devi salvare il segmento in modo esplicito. Le metriche calcolate esistenti con definizioni dei segmenti in linea continueranno a funzionare correttamente e possono essere visualizzate in Analisi ad hoc, ma non possono essere salvate senza salvare esplicitamente il segmento.

## (Report Builder only) Why have calculated metrics disappeared from my requests? {#section_DA4792FE5D7945218CD5E6328DE08E82}

Se la richiesta è stata creata in v 5.2 e contiene metriche calcolate, queste metriche non sono visibili nella release v 5.1 (o versioni precedenti). Questo perché le metriche calcolate ora utilizzano gli ID globali (ID non specifici per report).

**Cosa dovete fare**

Per visualizzare queste metriche, devi eseguire l'aggiornamento alla versione 5.2.

## How do Calculated Metrics Totals work? {#section_57BA3A299C7948ABB82B0392A9B0F33E}

When [!UICONTROL Reports & Analytics] shows a calculated metrics total in [!UICONTROL Reports & Analytics], it's just applying the formula to the total. Ad esempio, il totale per gli ordini/visita di metriche calcolate prende Ordini totali e li divide in Visite totali. In alcuni casi, tuttavia, il totale della metrica calcolata non è solo la somma degli elementi della linea, ma un totale per il sito.

Esempio 1: Visitatori per un termine di ricerca: lo stesso visitatore potrebbe aver cercato più termini. In questo caso, i visitatori totali non equivalgono alla somma degli elementi della riga.

Esempio 2: Visualizzazioni di pagina sui prodotti: nel carrello, possono essere presenti più prodotti, quindi sono disponibili più visualizzazioni di pagina per il carrello. For more information on comparing the sum of line items to report totals, see [this knowledge base article](https://helpx.adobe.com/analytics/kb/sum-line-items-different-from-total.html).
