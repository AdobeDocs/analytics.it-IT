---
title: Domande frequenti su Activity Map
description: Domande frequenti sull’Activity Map.
feature: Activity Map
role: User, Admin
exl-id: 6b2767cb-6c2c-4bf3-b9a9-a23418624650
source-git-commit: f242ec6613cf046224f76f7edc7813a34c65fff8
workflow-type: tm+mt
source-wordcount: '1054'
ht-degree: 16%

---

# Domande frequenti su Activity Map

Domande frequenti sull’Activity Map.

+++Come posso concedere le autorizzazioni all’Activity Map?

Le autorizzazioni per l&#39;utilizzo di Activity Map e delle dimensioni associate vengono gestite in [Adobe Admin Console](/help/admin/admin-console/home.md).

I [elementi di autorizzazione](/help/admin/admin-console/permissions/product-profile.md) richiesti per Activity Map includono:

* **[!UICONTROL Analytics Tools]** > **[!UICONTROL Activity Map]**
* **[!UICONTROL Analytics Tools]** > **[!UICONTROL Segment Publishing]**
* **[!UICONTROL Dimensions]** > **[!UICONTROL Activity Map Scroll Reach]**
* **[!UICONTROL Dimensions]** > **[!UICONTROL Activity Map Link By Region]**
* **[!UICONTROL Dimensions]** > **[!UICONTROL Activity Map Region]**
* **[!UICONTROL Dimensions]** > **[!UICONTROL Activity Map Link]**
* **[!UICONTROL Dimensions]** > **[!UICONTROL Activity Map Page]**

Per ulteriori informazioni, consulta [Autorizzazioni del profilo di prodotto per gli strumenti Analytics](/help/admin/admin-console/permissions/analytics-tools.md).

+++

+++Tutti i clienti Analytics hanno accesso all’Activity Map?

Le organizzazioni con un contratto per Adobe Analytics Standard, Premium e Ultimate hanno accesso ad Activity Map. Questi tipi di contratto rappresentano la maggior parte dei clienti Adobe Analytics.

+++

+++In che modo Activity Map supporta le applicazioni a pagina singola (SPA)?

Ogni pochi secondi, Activity Map analizza la pagina web alla ricerca di modifiche. L’Activity Map trova nuovi contenuti nella pagina senza ricaricarli, ma questi sono sempre attribuiti al primo valore di dimensione della pagina.

* Activity Map controlla se la visibilità dei collegamenti di cui è a conoscenza è cambiata. Se viene rilevata una modifica nella visibilità, la colonna Link On Page della tabella Links On Page presente per quel collegamento si aggiorna con [!UICONTROL Displayed] o [!UICONTROL Hidden].

* Quando l&#39;interazione dell&#39;utente crea un nuovo contenuto, tutti i nuovi elementi che AppMeasurement determina come collegamento vengono aggiunti alla tabella [!UICONTROL Links On Page]. Activity Map invia una nuova richiesta di dati che include questi nuovi collegamenti. I nuovi collegamenti vengono visualizzati nella tabella [!UICONTROL Links On Page] quando viene restituita la richiesta di dati.

+++

+++L’Activity Map fornisce dati sui collegamenti visualizzati ma non selezionati?

No, Adobe non tiene traccia automaticamente dei collegamenti che sono stati visualizzati solo.

+++

+++Quali browser e versioni sono supportate da Activity Map?

Activity Map supporta la versione più recente della maggior parte dei browser moderni.

+++

+++L’Activity Map aumenta le chiamate server?

Activity Map non invia chiamate server da sola. Al contrario, le variabili di dati di contesto Activity Map sono incluse nelle chiamate di visualizzazione della pagina di Analytics nella pagina successiva. Tuttavia, alcune versioni precedenti di Activity Map sul Web SDK inviano una chiamata separata per i dati Activity Map. Se utilizzi la versione più recente del Web SDK, i dati Activity Map vengono uniti all’evento seguente.

+++

+++Perché mancano alcuni numeri di classifica dalla sovrapposizione?

Alcuni collegamenti, ad esempio quelli contenuti nei menu, sono nascosti dalla pagina. Di conseguenza, le sovrapposizioni di collegamento corrispondenti non vengono visualizzate. La classificazione viene calcolata per tutti i collegamenti sulla pagina, compresi quelli nascosti.

+++

+++Come viene determinata la classificazione dei collegamenti nel rapporto Tutti i collegamenti?

* **In modalità Sfumatura e bolla**: la colonna della metrica determina la classificazione. Per i collegamenti con lo stesso valore di metrica, la classificazione è ulteriormente basata sull’ordine alfabetico degli ID collegamento.
* **In modalità Gainer &amp; Loser**: la colonna della percentuale guadagnata determina la classificazione. Per i collegamenti con lo stesso guadagno, la classificazione è ulteriormente basato sull’ordine alfabetico dell’ID collegamento.

+++

+++Come funziona Activity Map con le pagine che utilizzano più suite di rapporti?

Per impostazione predefinita, Activity Map utilizza la suite di rapporti associata al primo tag nella pagina. Puoi selezionare una suite di rapporti diversa tramite la scheda **[!UICONTROL Activity Map Settings]** > **[!UICONTROL Others]**.

+++

+++Per quanto tempo Activity Map esegue la scansione di Adobe Analytics nella pagina?

Activity Map cerca la presenza di Adobe Analytics per un massimo di 20 secondi dopo un evento di completamento della pagina.

+++

+++In che modo Activity Map gestisce il contenuto dinamico?

Activity Map controlla ogni 2 secondi per verificare se sono state rilevate modifiche allo stato della pagina web, ad esempio:

* Contenuto HTML diventato visibile
* Contenuto HTML nascosto
* Nuovo contenuto HTML inserito

Se il contenuto è nascosto o visualizzato, lo stato dei collegamenti interessati (e quindi le sovrapposizioni) viene modificato automaticamente da nascosto a mostrato o da mostrato a nascosto. Se viene inserito un nuovo contenuto, l’applicazione recupera i collegamenti associati, estrae i dati di analisi relativi e aggiunge sovrapposizioni per tali collegamenti.

+++

+++Su quale metrica si basa il rapporto Flusso di pagina?

Tutti i dati visualizzati si basano sulle visualizzazioni di pagina.

+++

+++Posso esportare dati Activity Map tramite feed di dati?

Sì. Le [colonne feed dati](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md) utilizzate da Activity Map sono:

* Collegamento Activity Map: `clickmaplink`
* Pagina Activity Map: `clickmappage`
* Area geografica Activity Map: `clickmapregion`
* Collegamento Activity Map per area geografica: `clickmaplinkbyregion`

+++

+++I segmenti funzionano in modalità Live?

No, i segmenti non funzionano in modalità Live.

+++

+++L’Activity Map è compatibile con le suite di rapporti virtuali?

Sì. Tuttavia, a causa delle limitazioni della suite di rapporti virtuali, la modalità Live dell’Activity Map non è compatibile con le suite di rapporti virtuali.

+++

+++Come posso disabilitare l’Activity Map?

Il metodo per disabilitare l’Activity Map dipende dal tipo di implementazione:

* **Estensione Web SDK**: nelle impostazioni di configurazione dell&#39;estensione, deselezionare le caselle **[!UICONTROL Collect internal link clicks]**, **[!UICONTROL Collect external link clicks]** e **[!UICONTROL Collect download link clicks]**.
* **Libreria Web SDK JavaScript**: impostare [`clickCollectionEnabled`](https://experienceleague.adobe.com/it/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled) su `false`.
* **Estensione Analytics**: nelle impostazioni di configurazione dell&#39;estensione, deselezionare la casella con etichetta **[!UICONTROL Use Activity Map]**.
* **AppMeasurement**: rimuovere o commentare il modulo Activity Map in `AppMeasurement.js` oppure sovrascrivere la chiamata alla funzione del modulo con un corpo vuoto:

  ```js
  function AppMeasurement_Module_ActivityMap() {}
  ```

+++

+++Quali sono i requisiti di sistema per utilizzare la sovrapposizione Activity Map?

Puoi utilizzare la versione più recente di Chrome, Edge o Firefox con l’estensione Activity Map.

+++

+++Cosa devo considerare quando utilizzo l’Activity Map per informazioni personali?

Considera i seguenti scenari in cui è possibile raccogliere dati personali utilizzando l’Activity Map:

* **Collegamenti e-mail**: se è possibile fare clic su un indirizzo e-mail per aprire il client di posta dell&#39;utente, l&#39;Activity Map può raccogliere l&#39;indirizzo e-mail su cui è stato fatto clic.
* **Collegamenti ID utente**: dopo che un visitatore ha effettuato l&#39;accesso, l&#39;Activity Map può registrare tutti i collegamenti che contengono l&#39;ID utente del visitatore.
* **Collegamenti per informazioni riservate**: per le istituzioni finanziarie, è possibile tenere traccia di informazioni riservate come il numero di account, se si tratta di un collegamento su cui i visitatori fanno clic.
* **Collegamenti contenenti informazioni personali**: per i siti Web sanitari, i collegamenti possono contenere informazioni personali. Se un visitatore fa clic su questi collegamenti, Activity Map ne raccoglie il testo.

+++

+++Quali dati tiene traccia di Activity Map per impostazione predefinita?

Activity Map tiene traccia dei seguenti elementi:

* Tag `<a>` o `<area>` con proprietà `href`. I collegamenti dei tag di ancoraggio (`#`) non sono tracciati per impostazione predefinita.
* Attributo `onclick` che imposta una variabile `s_objectID`
* Un tag `<input>` o un pulsante `submit` con un valore o un testo figlio
* Un tag `<input>` con tipo `image` e una proprietà `src`
* Un tag `<button>` senza l&#39;attributo `type="button"`. Se desideri tenere traccia di `<button>` tag, puoi utilizzare attributi come `role="button"` o `submit="button"`.

+++

+++Quali sono alcuni esempi di collegamenti tracciati automaticamente da Activity Map?

Di seguito sono riportati alcuni esempi in cui Activity Map dispone di tutte le informazioni necessarie per tenere traccia di un collegamento.

```html
<a href="home.html">Home</a>

<input type="submit" value="Submit"/>

<input type="image" src="submit-button.png"/>

<p onclick="var s_objectID='Market rates';">
  <span class="title">Current Market Rates</span>
  <span class="subtitle">1.45 USD</span>
</p>

<div onclick="s.tl(true,'o','Chat button')">
  <span class="title">Chat with an agent now</span>
  <span class="subtitle">Current wait: 0 minutes</span>
</div>
```

+++

+++Quali sono alcuni esempi di collegamenti che Activity Map NON tiene traccia automaticamente?

* Il tag di ancoraggio non ha un `href` valido
* Metodo [`s_objectID`](/help/implement/vars/page-vars/s-objectid.md) o [`tl()`](/help/implement/vars/functions/tl-method.md) non presente
* Proprietà `src` mancante in un elemento di input del modulo

Di seguito sono riportati alcuni esempi in cui Activity Map non tiene traccia dei clic:

```html
<!-- Anchor tag does not have a valid href -->
<a name="innerAnchor">Section header</a>

<!-- Neither s_objectID or tl() method present -->
<p onclick="showPanel('stock price')">
  <span class="title">Current company stock price</span>
  <span class="subtitle">987.65 USD</span>
</p>

<!-- Neither s_objectID or tl() method present -->
<input type="radio" onclick="changeState(this)" name="group1" value="A"/>
<input type="radio" onclick="changeState(this)" name="group1" value="B"/>
<input type="radio" onclick="changeState(this)" name="group1" value="C"/>

<!-- src property missing on a form input element -->
<input type="image"/>
```

+++
