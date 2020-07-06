---
description: Queste modifiche al modo in cui le metriche calcolate funzionano in  Analytics possono avere un impatto sull'utente.
title: Domande frequenti
uuid: 9b7f1cd1-b969-4b15-8af1-969d816b65b8
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '2105'
ht-degree: 0%

---


# Domande frequenti

Queste modifiche al modo in cui funzionano le metriche calcolate [!DNL Analytics] possono avere un impatto sull&#39;utente.

[Come posso accedere al Generatore metriche calcolate?](/help/components/c-calcmetrics/cm-transition.md#section_D9AE9A0ACF824BACB5D05F0C2F7E9CA1)

[Come posso accedere al Gestore della metrica calcolata?](/help/components/c-calcmetrics/cm-transition.md#section_DD0BD13E9EC940268EBE8BC88241A152)

[Perché vedo così tante metriche calcolate con lo stesso nome?](/help/components/c-calcmetrics/cm-transition.md#section_E15C5B6CCC58498CAEC3FBDA8988F0A1)

[Cos&#39;è successo alle mie metriche calcolate globali?](/help/components/c-calcmetrics/cm-transition.md#section_7351D4C7361F4ABAA1B43F8E89AAD211)

[Cos&#39;è successo alle metriche calcolate globali che sono state condivise tra le società di accesso?](/help/components/c-calcmetrics/cm-transition.md#section_59E5CD948ED643AE9AD3D2E4277647F8)

[Cos&#39;è successo alle metriche calcolate con una classificazione numerica o numerica2?](/help/components/c-calcmetrics/cm-transition.md#section_71AFE6C4A7CD4AA19AB3A9D3C41D115B)

[Cos&#39;è successo alle Metriche Life-Time?](/help/components/c-calcmetrics/cm-transition.md#section_AEDB02EF24584DAD8731BED9DDCE4F48)

[Cosa devo sapere sulle metriche calcolate in base alle metriche Visitatore unico giornaliero/settimanale/mensile/trimestrale/annuale?](/help/components/c-calcmetrics/cm-transition.md#section_E9A77EBB41CE4881B196CC1C282B2DF3)

[E per le metriche calcolate create o gestite con i metodi API della suite di rapporti precedente?](/help/components/c-calcmetrics/cm-transition.md#section_13ED1BAD02634674BDAEB479B060A4B6)

[I dati correnti supportano tutti i tipi di metriche calcolate?](/help/components/c-calcmetrics/cm-transition.md#section_1DAA718BB8DB4413BAF8AD4B4FAAFFA2)

[Cosa significa &quot;Nessun nome fornito&quot; insieme alle metriche calcolate migrate?](/help/components/c-calcmetrics/cm-transition.md#section_C90CBB72A67644F38D583301981F8D03)

[Cosa succede alle metriche calcolate di un utente se tale utente è stato eliminato?](/help/components/c-calcmetrics/cm-transition.md#section_42ED4C15830540879C4A161423690E5A)

[Perché vedo metriche calcolate &quot;sconosciute&quot; che non sono &quot;valide&quot; per altre suite di rapporti anche se possono essere create e applicate a tali suite di rapporti?](/help/components/c-calcmetrics/cm-transition.md#section_6772818EFDED46E9B7095D64C3B77211)

[Perché le modifiche apportate alle metriche calcolate legacy non sono state salvate?](/help/components/c-calcmetrics/cm-transition.md#section_81CDEFCA1FD542579AF183DA1494EAF0)

[Perché le metriche calcolate non vengono visualizzate nel report Marketing Channels (Canali di marketing)?](/help/components/c-calcmetrics/cm-transition.md#section_FC350359A775433AB5F43C7CAB304D62)

[Perché alcune delle metriche calcolate mostrano formule senza le parentesi aggiunte?](/help/components/c-calcmetrics/cm-transition.md#section_AC0D1E9714AD487F9A1C73359F518B5E)

[( solo Ad hoc analysis) Le metriche calcolate con le definizioni di segmento incorporate o in linea sono ancora supportate?](/help/components/c-calcmetrics/cm-transition.md#section_B25C924A282F49388AB604E3D826F44C)

[(Solo Generatore di report) Perché le metriche calcolate sono scomparse dalle mie richieste?](/help/components/c-calcmetrics/cm-transition.md#section_DA4792FE5D7945218CD5E6328DE08E82)

[Come funzionano i totali delle metriche calcolate?](/help/components/c-calcmetrics/cm-transition.md#section_57BA3A299C7948ABB82B0392A9B0F33E)

## Come posso accedere al Generatore metriche calcolate? {#section_D9AE9A0ACF824BACB5D05F0C2F7E9CA1}

* Fare clic **[!UICONTROL + Add]** nella parte superiore del Gestore della metrica calcolata oppure
* In un  rapporto Analytics, fai clic sull’icona Metriche ![](assets/metrics_icon.png) a sinistra di un rapporto per visualizzare la barra Metriche, quindi fai clic su **[!UICONTROL Add]**.

## Come posso accedere al Gestore della metrica calcolata? {#section_DD0BD13E9EC940268EBE8BC88241A152}

* Vai a **[!UICONTROL Analytics]** > **[!UICONTROL Components]** nel menu di navigazione a sinistra. Quindi fai clic su **[!UICONTROL Calculated Metrics]**.

* In qualsiasi [!DNL Analytics] rapporto, fai clic sull’icona Metriche ![](assets/metrics_icon.png) a sinistra di un rapporto per visualizzare la barra Metriche, quindi fai clic su **[!UICONTROL Manage]**.

## Perché vedo così tante metriche calcolate con lo stesso nome? {#section_E15C5B6CCC58498CAEC3FBDA8988F0A1}

(In precedenza, le metriche calcolate globali non erano di proprietà di alcun utente Amministratore specifico e erano visibili a tutti gli utenti di tale suite di rapporti. Le metriche sono state separate per suite di rapporti. Se una metrica in una suite di rapporti aveva lo stesso nome di una metrica in una suite di rapporti diversa, gli utenti venivano visualizzati semplicemente come la stessa metrica quando cambiavano suite di rapporti.

Ora, le metriche non vengono più separate per suite di rapporti. Se una metrica in una suite di rapporti ha lo stesso nome di una metrica in una suite di rapporti diversa, sarà visibile sia nel Generatore metriche calcolate che nel Selettore metrica e potrebbe essere visualizzata come metrica duplicata anche se potrebbe avere o meno la stessa definizione.

Vedreste una serie di metriche calcolate con lo stesso nome (ma create in suite di rapporti diverse) solo se avete deselezionato la casella di controllo (Solo `<report suite>`) come illustrato di seguito:

![](assets/report_suite.png)

**Cosa devi fare**

Considerate l&#39;opportunità di consolidare le metriche calcolate con nomi e definizioni simili, ma prestate attenzione nel farlo. Puoi controllare la suite di rapporti per verificare la metrica calcolata nel Gestore della metrica calcolata per verificare la suite di rapporti originale. È inoltre necessario verificare le definizioni delle metriche quando si eliminano potenziali duplicati per garantire il corretto consolidamento delle metriche.

>[!NOTE]
>
>Anche se le metriche calcolate non sono più associate a una suite di rapporti specifica e possono essere utilizzate in qualsiasi suite di rapporti visibile per la società di accesso, la suite di rapporti in cui è stata creata o salvata la metrica calcolata è ancora visibile in Gestione metriche calcolate.

>[!NOTE]
>
>Anche se viene eliminata una metrica calcolata, tutti i segnalibri o i report dashboard che fanno riferimento a tale metrica continueranno a funzionare.

## Cos&#39;è successo alle mie metriche calcolate globali? {#section_7351D4C7361F4ABAA1B43F8E89AAD211}

(In precedenza, un amministratore poteva creare metriche calcolate (note come &quot;metriche calcolate globali&quot; o &quot;metriche calcolate della suite di rapporti&quot;) in una suite di rapporti tramite Strumenti di amministrazione.

Le metriche calcolate globali ora sono di proprietà del primo utente Admin nell&#39;elenco degli utenti Admin della società di accesso. Per impostazione predefinita verranno condivisi con &quot;Tutti&quot;. Questo pattern segue lo stesso modello di condivisione e gli stessi piani di migrazione dei segmenti.

**Cosa devi fare**

Niente. Tuttavia, il nuovo amministratore deve prestare attenzione quando modifica o elimina queste metriche calcolate, che possono essere utilizzate in numerosi report e dashboard con segnalibro.

>[!NOTE]
>
>Anche se viene eliminata una metrica calcolata, tutti i segnalibri o i report dashboard che fanno riferimento a tale metrica continueranno a funzionare.

## Cos&#39;è successo alle metriche calcolate globali che sono state condivise tra le società di accesso? {#section_59E5CD948ED643AE9AD3D2E4277647F8}

(In precedenza, un amministratore poteva creare metriche calcolate (note come &quot;metriche calcolate globali&quot; o &quot;metriche calcolate della suite di rapporti&quot;) in una suite di rapporti tramite Strumenti di amministrazione. Queste metriche possono essere &quot;condivise&quot; tra le società di accesso aggiungendo la suite di rapporti a più società di accesso.

Le metriche calcolate globali non possono più essere condivise tra le società di accesso. Non sono più associati o associati a una suite di rapporti specifica, ma sono invece legati a una specifica società di accesso. Metriche calcolate condivise tra le società di accesso

* Sono stati migrati a tutte le società di accesso con accesso a tale suite di rapporti.
* Il valore predefinito è &quot;shared with Everyone&quot; (Condividi con tutti).
* Saranno copie indipendenti da tutte le altre società di accesso.

>[!NOTE]
>
>Se la metrica calcolata è stata utilizzata in un segnalibro, dashboard, avvisi o report pianificati, la modifica della nuova copia NON influirà sulla metrica calcolata persistente precedente.

## Cos&#39;è successo alle metriche calcolate con una classificazione numerica o numerica2? {#section_71AFE6C4A7CD4AA19AB3A9D3C41D115B}

(In precedenza, le metriche calcolate con una classificazione Numeric o Numeric2 erano visibili solo nelle [!UICONTROL Reports & Analytics], [!UICONTROL Report Builder]e nelle API.)

A questo punto, le metriche calcolate con una classificazione Numeric o Numeric2 continueranno a essere visibili nelle API [!UICONTROL Reports & Analytics]e [!UICONTROL Report Builder]. Tuttavia, non saranno supportati in alcun rapporto con un segmento applicato.

Inoltre, le metriche calcolate con una classificazione Numeric o Numeric2 non saranno supportate nei seguenti componenti: [!UICONTROL Ad Hoc Analysis], [!UICONTROL Analysis Workspace], [!UICONTROL Real-Time] report [!UICONTROL Anomaly Detection]e [!UICONTROL Contribution Analysis]. Quando create o modificate una metrica calcolata con una classificazione Numeric o Numeric2, viene visualizzato un avviso di compatibilità per avvisare che la metrica calcolata non è compatibile con determinate aree del prodotto.

**Cosa devi fare**

Evitare di creare metriche calcolate con classificazioni Numeric1 o Numeric2 se la metrica è destinata ad essere utilizzata con un segmento o con uno dei componenti non compatibili.

## Cos&#39;è successo alle Metriche Life-Time? {#section_AEDB02EF24584DAD8731BED9DDCE4F48}

Metriche Life-Time (ad esempio metriche aggiornate) non sono più supportate e non sono più visibili nell&#39; [!UICONTROL Reports & Analytics] interfaccia utente o in qualsiasi altra interfaccia. Non possono essere interrogati dall&#39;API di report.

Eventuali segnalibri, dashboard, report pianificati o avvisi che contenevano una metrica tutto il tempo continueranno a essere eseguiti senza tale metrica, purché nel rapporto sia presente almeno un&#39;altra metrica valida. Se l&#39;unica metrica presente nel segnalibro, nel dashboard, nel report pianificato o nell&#39;avviso è una metrica tutto il tempo, il report non verrà più eseguito.

## Cosa devo sapere sulle metriche calcolate in base alle metriche Visitatore unico giornaliero/settimanale/mensile/trimestrale/annuale? {#section_E9A77EBB41CE4881B196CC1C282B2DF3}

Le metriche calcolate in base alle metriche Visitatore univoco saranno visibili nei seguenti [!DNL Analytics] componenti: [!UICONTROL Reports & Analytics], [!UICONTROL Report Builder]e API di reporting.

Tuttavia, queste metriche non saranno supportate nei seguenti componenti: [!UICONTROL Segments], [!UICONTROL Analysis Workspace], [!UICONTROL Real-Time] report [!UICONTROL Anomaly Detection]e [!UICONTROL Contribution Analysis]. Quando create o modificate una metrica calcolata basata sulle metriche Visitatori unici, viene visualizzato un avviso di compatibilità per avvisare che la metrica non è compatibile con determinate aree del prodotto.

Puoi usare una metrica Visitatore univoco di base su un report con un segmento. Puoi creare una metrica calcolata basata su una metrica Visitatore unico; tuttavia, tale metrica calcolata non può essere applicata a un report con un segmento, né può avere un segmento incorporato in esso.

## Cosa succede alle metriche calcolate create o gestite con i metodi API della suite di rapporti precedente? {#section_13ED1BAD02634674BDAEB479B060A4B6}

In precedenza, il salvataggio di una metrica calcolata con il metodo (1.3 o 1.4) API ReportSuite.SaveCalculatedMetrics era lo stesso della creazione o dell&#39;aggiornamento di una metrica calcolata nell&#39;Admin Console . Lo stesso vale per ReportSuite.DeleteCalculatedMetrics. Inoltre, l&#39;elenco delle metriche calcolate visualizzate nell&#39;Admin Console  o durante la chiamata a ReportSuite.GetCalculatedMetrics era lo stesso.

Ora, i metodi API CalculatedMetrics di ReportSuite (1.3 o 1.4) continueranno a salvare, eliminare e recuperare le metriche calcolate utilizzando il vecchio store. Le metriche calcolate esistenti verranno migrate e saranno visibili nel nuovo Generatore di metriche calcolate. **Le nuove metriche calcolate create con i metodi API saranno visibili solo nell&#39;API. Saranno comunque utilizzabili nell&#39;API di reporting.**

**Cosa devi fare**

Se è necessario utilizzare sia l&#39;API che il Generatore di metriche calcolate, è necessario interrompere l&#39;utilizzo dei metodi API ReportSuite CalculatedMetrics e utilizzare invece i nuovi metodi API CalculatedMetrics (Get, Save, Delete e GetFunctions).

## I dati correnti supportano tutti i tipi di metriche calcolate? {#section_1DAA718BB8DB4413BAF8AD4B4FAAFFA2}

I dati correnti non supportano le metriche calcolate contenenti segmenti o funzioni statistiche. Le uniche funzioni supportate sono funzioni matematiche di base come addizione, eliminazione, moltiplicazione, divisione e negazione (-x).

## Cosa significa &quot;Nessun nome fornito&quot; insieme alle metriche calcolate migrate? {#section_C90CBB72A67644F38D583301981F8D03}

&quot;Nessun nome fornito&quot; significa che nessun nome di metrica è associato a questa metrica migrata (solo una formula senza un nome descrittivo).

## Cosa succede alle metriche calcolate di un utente se tale utente è stato eliminato? {#section_42ED4C15830540879C4A161423690E5A}

Vengono anche eliminate tutte le metriche calcolate create dall&#39;utente. Tuttavia, le metriche calcolate eliminate continueranno a funzionare come parte di segnalibri, dashboard o rapporti pianificati salvati.

## Perché vedo metriche calcolate &quot;sconosciute&quot; che non sono &quot;valide&quot; per altre suite di rapporti anche se possono essere create e applicate a tali suite di rapporti? {#section_6772818EFDED46E9B7095D64C3B77211}

L&#39;interfaccia utente visualizza &quot;unknown&quot; se la metrica calcolata contiene metriche di base o dimensioni che non esistono per la suite di rapporti selezionata.

## Perché le modifiche apportate alle metriche calcolate legacy non sono state salvate? {#section_81CDEFCA1FD542579AF183DA1494EAF0}

Ciò potrebbe essere dovuto alla tempistica della migrazione alla nuova banca dati delle metriche calcolate, avvenuta tra il 15 giugno e il 18 giugno 2015.

**Cosa devi fare**

Sarà necessario ripristinare le modifiche apportate alle metriche legacy.

## Perché le metriche calcolate non vengono visualizzate nel report Marketing Channels (Canali di marketing)? {#section_FC350359A775433AB5F43C7CAB304D62}

(In precedenza, tutte le metriche calcolate venivano elencate nel selettore delle metriche nei report Canali di marketing con l&#39;opzione Primo contatto e ultimo tocco.)

Ora, solo le metriche calcolate con il tipo di allocazione impostato specificatamente su Primo contatto o Ultimo contatto nel generatore Metriche calcolate saranno disponibili nel selettore delle metriche nei report Canali di marketing. Eventuali metriche calcolate già applicate ai report Marketing Channel continueranno ad essere applicate e funzioneranno come prima. Per creare una metrica calcolata per Marketing Channels (Canali di marketing), fai clic sull’icona di configurazione nel generatore di metriche e seleziona Primo tocco o Ultimo tocco come tipo di allocazione. Tieni presente che in questo modo la metrica calcolata sarà compatibile solo con i report Marketing Channel e non sarà utilizzabile su nessun altro report.

## Perché alcune delle metriche calcolate mostrano formule senza le parentesi aggiunte? {#section_AC0D1E9714AD487F9A1C73359F518B5E}

Durante la migrazione, Adobe ha eliminato alcune parentesi superflue da alcune formule. Sono state rimosse solo le parentesi che non influiscono sulla modalità di calcolo della metrica. Questo non cambierà i dati, ma semplicemente semplifica la formula.

## ( solo Ad hoc analysis) Le metriche calcolate con definizioni di segmento incorporate o inline sono ancora supportate? {#section_B25C924A282F49388AB604E3D826F44C}

Le metriche calcolate create in  Ad hoc analysis potevano in precedenza contenere definizioni di segmenti in linea. Questo non è più possibile.

**Cosa devi fare**

È necessario salvare esplicitamente il segmento. Le metriche calcolate esistenti con definizioni di segmenti in linea continueranno a essere eseguite correttamente e potranno essere visualizzate  Ad hoc analysis, ma non potranno essere salvate senza aver salvato esplicitamente il segmento.

## (Solo Generatore di report) Perché le metriche calcolate sono scomparse dalle mie richieste? {#section_DA4792FE5D7945218CD5E6328DE08E82}

Se la richiesta è stata creata in v5.2 e contiene metriche calcolate, tali metriche non sono visibili in v5.1 (o versioni precedenti). Questo perché le metriche calcolate ora utilizzano gli ID globali (ID non specifici delle suite di rapporti).

**Cosa devi fare**

Per visualizzare queste metriche è necessario eseguire l&#39;aggiornamento alla versione 5.2.

## Come funzionano i totali delle metriche calcolate? {#section_57BA3A299C7948ABB82B0392A9B0F33E}

Quando [!UICONTROL Reports & Analytics] mostra un totale di metriche calcolate in [!UICONTROL Reports & Analytics], si tratta solo di applicare la formula al totale. Ad esempio, il totale della metrica calcolata Ordini/Visita prende gli Ordini totali e li divide per Visite totali. In alcuni casi, tuttavia, il totale della metrica calcolata non è solo la somma degli elementi di riga, ma un totale per il sito.

Esempio 1: Visitatori per un termine di ricerca: lo stesso visitatore potrebbe aver cercato più termini, pertanto in questo caso il totale dei visitatori non corrisponde alla somma degli elementi della riga.

Esempio 2: Visualizzazioni di pagina sui prodotti: nel carrello, possono essere presenti più prodotti, di conseguenza, esistono più visualizzazioni di pagina per il carrello. Per ulteriori informazioni sul confronto tra la somma degli elementi di riga e i totali dei rapporti, consulta [questo articolo](https://helpx.adobe.com/analytics/kb/sum-line-items-different-from-total.html)della knowledge base.
