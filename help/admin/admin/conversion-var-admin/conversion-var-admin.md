---
description: La variabile di conversione Custom Insight (o eVar) viene inserita nel codice di Adobe nelle pagine Web selezionate del sito. Il suo scopo principale è segmentare le metriche di successo della conversione nei rapporti di marketing personalizzati. Un eVar può essere basato su visite e funziona in modo simile ai cookie. I valori trasmessi nelle variabili eVar seguono l'utente per un periodo di tempo predeterminato.
keywords: eVar
title: Variabili di conversione (eVar)
feature: Strumenti di amministrazione
uuid: 1eed0cb1-0735-4142-be21-43f264216b50
exl-id: 822ecaff-a06c-42e1-aee8-ef4a43df4230
source-git-commit: eda2a34d2431d01d4301d47e547b4aa9955f12a5
workflow-type: tm+mt
source-wordcount: '1522'
ht-degree: 5%

---

# Conversion Variables (Variabili di conversione) (eVars)

La variabile di conversione Custom Insight (o eVar) viene inserita nel codice di Adobe nelle pagine Web selezionate del sito. Il suo scopo principale è segmentare le metriche di successo della conversione nei rapporti di marketing personalizzati. Un eVar può essere basato su visite e funziona in modo simile ai cookie. I valori trasmessi nelle variabili eVar seguono l&#39;utente per un periodo di tempo predeterminato.

Quando un eVar è impostato su un valore per un visitatore, Adobe ricorda automaticamente tale valore fino alla scadenza. Eventuali eventi di successo riscontrati da un visitatore mentre il valore eVar è attivo vengono conteggiati per il valore eVar.

Le eVar vengono utilizzate in modo più efficace per misurare la causa e l’effetto, ad esempio:

* Quali campagne interne hanno influenzato i ricavi
* Quali banner pubblicitari sono stati alla fine il risultato di una registrazione
* Numero di volte in cui è stata utilizzata una ricerca interna prima di effettuare un ordine

Se desideri misurare il traffico o tracciare un percorso, si consiglia di utilizzare le variabili di traffico.

>[!NOTE]
>
>In una richiesta di immagine è possibile memorizzare un solo valore in un eVar. Se in un valore eVar desideri valori multipli, ti consigliamo di implementare [Variabili elenco (variabili elenco)](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/page-variables.html?lang=it).

## Variabili di conversione - Descrizioni {#section_7C317BB0287A4B8EB0A1A4ECC40627BF}

Descrizioni dei campi utilizzati durante la [modifica delle variabili di conversione](/help/admin/admin/conversion-var-admin/t-conversion-variables-admin.md).

| Elemento | Descrizione |
| --- | --- |
| [!UICONTROL Name] | Nome descrittivo della variabile di conversione. Questo nome è il modo in cui l’eVar viene indicato nel reporting generale e sarà il nome del report/dimensione nel menu a sinistra. |
| [!UICONTROL Type]  (Solo eVar) | Il tipo di valore della variabile:<ul><li>**[!UICONTROL Text String]**: Acquisisce i valori di testo utilizzati sul sito. Si tratta del tipo di eVar più comune e dell’impostazione predefinita. Agisce in modo simile ad altre variabili, dove il valore al suo interno è una stringa di testo statica. Se tieni traccia di elementi quali campagne interne o parole chiave di ricerca interne, questa è l’impostazione consigliata.</li><li>**[!UICONTROL Counter]**: Conta il numero di volte in cui un’azione si verifica prima dell’evento di successo. Ad esempio, se utilizzi un eVar per tenere traccia delle ricerche interne sul sito, imposta questo valore su [!UICONTROL Text String] per tenere traccia dell’utilizzo dei termini di ricerca. Imposta questo valore su [!UICONTROL Counter] per contare il numero di ricerche effettuate, indipendentemente dai termini di ricerca utilizzati. Ad esempio, è possibile utilizzare un eVar contatore per tenere traccia del numero di volte in cui un utente ha utilizzato la ricerca interna prima di effettuare un acquisto.</li></ul> |
| [!UICONTROL Allocation] | Determina il modo in cui Analytics assegna il credito per un evento di successo se una variabile riceve valori multipli prima dell’evento. I valori supportati includono:<ul><li>**[!UICONTROL Most Recent]**: L’ultimo valore di eVar riceve sempre crediti per eventi di successo fino alla scadenza di tale eVar.</li><li>**[!UICONTROL Original Value]**: Il primo eVar riceve sempre crediti per eventi di successo fino alla scadenza di tale eVar.</li><li>**[!UICONTROL Linear]**: Alloca gli eventi di successo in modo uniforme in tutti i valori eVar. Poiché l’allocazione lineare distribuisce accuratamente i valori solo all’interno di una visita, utilizza l’allocazione lineare con una scadenza eVar della visita.</li></ul> **Nota**: Il passaggio dell’allocazione a o da Lineare impedisce la visualizzazione dei dati storici. La combinazione di tipi di allocazione nell’interfaccia di reporting può portare a dati errati nei rapporti. Ad esempio, l’allocazione lineare potrebbe dividere i ricavi in diversi valori di eVar. Dopo aver ripristinato l&#39;allocazione più recente, il 100% di tali entrate sarebbe associato al valore singolo più recente. Questa associazione può portare a conclusioni errate da parte degli utenti.<br><br>Per evitare la probabilità di confusione nei rapporti, Adobe Analytics rende i dati storici non disponibili nell’interfaccia. Può essere visualizzato se si decide di ripristinare l&#39;eVar specificato all&#39;impostazione di allocazione iniziale, anche se non è necessario modificare le impostazioni di allocazione eVar semplicemente per accedere ai dati storici. L’Adobe consiglia di utilizzare un nuovo eVar quando si desidera impostare nuove impostazioni di allocazione per i dati già registrati, anziché modificare le impostazioni di allocazione su un eVar che dispone già di una quantità significativa di dati storici. |
| [!UICONTROL Expire After] | Specifica un periodo di tempo, o un evento, dopo la scadenza del valore eVar (non riceve più crediti per eventi di successo). Se un evento di successo si verifica dopo la scadenza eVar, il valore None non riceve credito per l’evento (nessun eVar è attivo).  Se selezioni un evento come valore di scadenza, la variabile scade solo se si verifica l’evento. Se l’evento non si verifica, la variabile non scade.  Le opzioni di scadenza disponibili possono essere classificate in quattro categorie principali:<ul><li>**A livello di visualizzazione della pagina o di visita.** Gli eventi di conversione che vanno oltre la visualizzazione della pagina o la visita non si associano all’eVar.</li><li>**In base a un periodo di tempo, ad esempio giorno, settimana, mese o anno.** Gli eventi di conversione oltre il periodo di tempo specificato non si associano all&#39;eVar. Il periodo di scadenza inizia quando la variabile viene impostata. Le eVar scadono in base al tempo impostato, al secondo (minuto, ora, giorno, mese, ecc.): <ul><li>MINUTO=60 secondi</li><li>ORA=3600 secondi (60 minuti)</li><li>DAY=86400 secondi (24 ore)</li><li>WEEK=604800 secondi (7 giorni)</li><li>MESE=2678400 secondi (31 giorni)</li><li>TRIMESTRE=8035200 secondi (93 giorni - 3 mesi di 31 giorni)</li><li>ANNO=31536000 secondi (365 giorni)</li><br>Se una visita inizia alle 7:00 del lunedì e un eVar è impostato entro tale visita alle 7:15 del mattino, la scadenza è come illustrato di seguito:<li>Scadenza del giorno: L&#39;eVar scade alle 7:15 del mattino di martedì.</li><li>Scadenza settimana: L&#39;eVar scade il lunedì successivo alle 7:15.</li><li>Scadenza mese: L&#39;eVar scade 31 giorni a partire da lunedì alle 7:15.</li></ul><li>**Eventi di conversione specifici.** Qualsiasi altro evento di conversione che si attiva dopo l’evento specifico designato viene associato all’eVar.</li><li>**Mai.** Finché il cookie visitorID è intatto, può trascorrere qualsiasi periodo di tempo tra eVar ed evento.</li></ul> |
| [!UICONTROL Status]  (Solo eVar) | Definisce lo stato [!UICONTROL eVar]:<ul><li>**Disabilitato**: Disattiva  [!UICONTROL eVar]. Rimuove il [!UICONTROL eVar] dall’elenco delle variabili di conversione.</li><li>**Nessuna sottorelazione**: Impedisce la suddivisione del  [!UICONTROL eVar] per una dimensione.</li><li>**Sottorelazioni** di base: Consente di suddividere un eVar per qualsiasi dimensione completa (ad esempio, Prodotti o Campaign).</li></ul> |
| [!UICONTROL Reset] | Reimposta eventuali valori esistenti nell&#39;eVar. Utilizza questa impostazione quando riutilizzi un eVar in modo da combinare un valore precedente in un nuovo rapporto. La reimpostazione non cancella i dati storici. |
| [!UICONTROL Merchandising]  (Solo eVar) | Le variabili merchandising possono seguire una delle due sintassi:<ul><li>**[!UICONTROL Products Syntax]**: Associa il valore eVar a un prodotto. **Nota**: Se  [!UICONTROL Products Syntax] è selezionata, la  [!UICONTROL Merchandising Binding Event] sezione è disabilitata e non selezionabile per la modifica. Per questa sintassi, [!UICONTROL Binding Events] non sono applicabili.</li><li>**[!UICONTROL Conversion Variable Syntax]**: Associa l’eVar a un prodotto solo se  [!UICONTROL Binding Event] si verifica un evento . In questo caso, selezioni gli eventi che agiscono come [!UICONTROL Binding Events].  La modifica di questa impostazione senza aggiornare di conseguenza il codice JavaScript causa la perdita di dati. Consulta [Variabili di merchandising](/help/components/dimensions/evar-merchandising.md).</li></ul> |
| [!UICONTROL Merchandising Binding Event] (Solo eVar) | Se Merchandising è impostato su [!UICONTROL Conversion Variable Syntax], gli eventi selezionati associano il valore di eVar corrente a un prodotto. Per utilizzare un [!UICONTROL Binding Event], impostare [!UICONTROL Allocation] su [!UICONTROL Most Recent]. Se [!UICONTROL Allocation] è impostato su [!UICONTROL Original Value], il primo binding del prodotto eVar rimane fino alla scadenza dell’eVar. Per selezionare più eventi, tenete premuto Ctrl (Windows) o Comando (Mac) e fate clic su più elementi nell’elenco. È possibile selezionare un evento solo quando è selezionato [!UICONTROL Conversion Variable Syntax]. |

### Scadenza

`eVars` scadono dopo un periodo di tempo specificato. Dopo la scadenza dell’eVar, non riceve più crediti per eventi di successo. Le eVar possono anche essere configurate in modo da scadere in caso di eventi di successo. Ad esempio, se hai una promozione interna che scade alla fine di una visita, la promozione interna riceve credito solo per gli acquisti o le registrazioni che si verificano durante la visita in cui sono stati attivati.

Ci sono due modi per scadere un eVar:

* Puoi impostare l’eVar in modo che scada dopo un determinato periodo di tempo o evento.
* È possibile utilizzare la forza della scadenza di un eVar reimpostandolo, utile quando si ripropone una variabile.

Ad esempio, se modifichi la scadenza di un eVar da 30 a 90 giorni, i valori eVar raccolti continueranno a persistere per la durata del nuovo set di scadenza (in questo caso, 90 giorni). Il sistema controlla semplicemente l&#39;impostazione di scadenza corrente e l&#39;ultima marca temporale impostata del valore eVar raccolto per determinare la scadenza. Solo l’opzione **[!UICONTROL Reset]** scade i valori e lo fa immediatamente.

Un altro esempio: Se un eVar viene utilizzato a maggio per riflettere le promozioni interne e scade dopo 21 giorni, e a giugno viene utilizzato per acquisire le parole chiave di ricerca interne, il 1° giugno è necessario forzare la scadenza o reimpostare la variabile. In questo modo sarà possibile mantenere i valori di promozione interni al di fuori dei rapporti di giugno.

### Sensibilità ai casi

Le eVar non distinguono tra maiuscole e minuscole. La maiuscola o minuscola utilizzata nei rapporti si basa sul primo valore registrato dal sistema backend. Questo valore potrebbe essere la prima istanza mai vista o variare a seconda di un determinato periodo di tempo (ad esempio, mensile), a seconda della varietà e della quantità di dati associati alla suite di rapporti.

### Contatori

Sebbene le eVar siano utilizzate più spesso per contenere valori stringa, possono anche essere configurate per fungere da contatori. Le eVar sono utili come contatori quando si tenta di contare il numero di azioni eseguite da un utente prima di un evento. Ad esempio, puoi utilizzare un eVar per acquisire il numero di ricerche interne prima dell’acquisto. Ogni volta che un visitatore esegue una ricerca, l’eVar deve contenere un valore di &quot;+1.&quot; Se un visitatore esegue ricerche quattro volte prima di un acquisto, visualizzerai un’istanza per ogni conteggio totale: 1.00, 2.00, 3.00 e 4.00. Tuttavia, solo il 4.00 riceve credito per l’evento di acquisto (Metriche Ordini e Entrate). Solo i numeri positivi sono consentiti come valori di un contatore eVar.
