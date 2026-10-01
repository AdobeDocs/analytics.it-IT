---
description: La variabile di conversione (o eVar) Custom Insight viene inserita nel codice di Adobe in specifiche pagine del sito web. Il suo scopo principale è segmentare le metriche di successo della conversione nei rapporti di marketing personalizzati. Un’eVar può essere basata su visite e funziona in modo simile ai cookie. I valori trasmessi nelle variabili eVar seguono l’utente per un periodo di tempo predeterminato.
keywords: eVar
title: Variabili di conversione (eVar)
feature: Admin Tools
role: Admin
exl-id: 822ecaff-a06c-42e1-aee8-ef4a43df4230
TQID: https://experienceleague.adobe.com/rYLxVYB1oDyfEk8gQyesTSRRPHid-6zJ8QaqFG2b0Kc
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
    internal-label: Admin Tools
subfeature_v2:
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
    internal-label: Events
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: ca917b867cd84b09b899ce7b72586f0b15003106
workflow-type: tm+mt
source-wordcount: '1613'
ht-degree: 47%
---
# Variabili di conversione (eVar)

La variabile di conversione (o eVar) Custom Insight viene inserita nel codice di Adobe in specifiche pagine del sito web. Il suo scopo principale è segmentare le metriche di successo della conversione nei rapporti di marketing personalizzati. Un’eVar può essere basata su visite e funziona in modo simile ai cookie. I valori trasmessi nelle variabili eVar seguono l’utente per un periodo di tempo predeterminato.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL Conversion]** > **[!UICONTROL Conversion Variables]**

## Panoramica sulle variabili di conversione (eVar)

Per una panoramica video delle variabili di conversione, vedi [Introduzione alle variabili di conversione](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/dimensions/introduction-to-conversion-variables-evars) nella guida delle esercitazioni di Analytics.

Quando un’eVar è impostata su un valore per un visitatore, Adobe ricorda automaticamente tale valore fino alla scadenza. Eventuali eventi di successo riscontrati da un visitatore mentre il valore eVar è attivo vengono conteggiati per il valore eVar.

Le eVar vengono utilizzate in particolare per misurare la causa e l’effetto, ad esempio:

* Quali campagne interne hanno influenzato i ricavi
* Quali banner pubblicitari hanno portato a una registrazione
* Quante volte in cui è stata utilizzata una ricerca interna prima di effettuare un ordine

Per misurare il traffico o tracciare un percorso, si consiglia invece di utilizzare le variabili di traffico.

>[!NOTE]
>
>Nell’eVar di una richiesta di immagine è possibile memorizzare un solo valore. Se si desidera inserire più valori in un valore eVar, utilizzare [Variabili elenco](/help/implement/vars/page-vars/page-variables.md).

### Variabili di conversione - Descrizioni {#section_7C317BB0287A4B8EB0A1A4ECC40627BF}

| Elemento | Descrizione |
| --- | --- |
| [!UICONTROL Status] | Determina se eVar è attivo:<ul><li>**[!UICONTROL Enabled]**: eVar è attivo.</li><li>**[!UICONTROL Disabled]**: disabilita eVar e la rimuove dall&#39;elenco delle variabili di conversione.</li></ul> |
| [!UICONTROL Description] | Descrizione facoltativa di eVar. Utilizzalo per documentare cosa acquisisce eVar e come viene implementato. |
| [!UICONTROL Name] | Il nome descrittivo della dimensione della variabile di conversione. È così che viene fatto riferimento ad eVar nei rapporti generali. |
| [!UICONTROL Allocation] | Determina il modo in cui Analytics attribuisce il merito di un evento di successo se una variabile riceve più valori prima dell’evento. I valori supportati includono:<ul><li>**[!UICONTROL Most Recent (Last)]**: all’ultimo valore eVar viene sempre attribuito il merito degli eventi di successo fino alla scadenza di tale eVar.</li><li>**[!UICONTROL Original Value (First)]**: al primo valore eVar viene sempre attribuito il merito per gli eventi di successo fino alla scadenza di tale eVar.</li><li>**[!UICONTROL Linear]**: gli eventi di successo vengono attribuiti in modo uniforme a tutti i valori eVar. Poiché l’allocazione lineare distribuisce i valori solo all’interno di una visita, utilizza l’allocazione lineare con scadenza eVar pari a Visita o inferiore. Questa opzione non è disponibile per le eVar di merchandising.</li></ul>**Importante**: Adobe consiglia di non passare all&#39;allocazione [!UICONTROL Linear] o viceversa, in quanto nasconde i dati storici nei rapporti fino a quando non si torna indietro. Per modificare l’allocazione su un eVar con cronologia significativa, Adobe consiglia di utilizzare un nuovo eVar. |
| [!UICONTROL Expire After] | Specifica quando scade il valore eVar (non riceve più crediti per eventi di successo). Se un evento di successo si verifica dopo la scadenza dell’eVar, il merito per l’evento viene attribuito al valore None (nessun eVar è attivo). I valori supportati includono:<ul><li>**[!UICONTROL Visit]**: il valore scade alla fine della visita.</li><li>**[!UICONTROL Hit]**: il valore si applica solo all&#39;hit su cui è impostato.</li><li>**[!UICONTROL Minute]**, **[!UICONTROL Hour]**, **[!UICONTROL Day]**, **[!UICONTROL Week]**, **[!UICONTROL Month]**, **[!UICONTROL Quarter]** o **[!UICONTROL Year]**: il valore scade dopo un periodo di tempo fisso, al secondo:<ul><li>Minuto = 60 secondi</li><li>Ora = 3.600 secondi (60 minuti)</li><li>Giorno = 86400 secondi (24 ore)</li><li>Settimana = 604800 secondi (7 giorni)</li><li>Mese = 2678400 secondi (31 giorni)</li><li>Trimestre = 8035200 secondi (93 giorni - 3 mesi di 31 giorni)</li><li>Anno = 31536000 secondi (365 giorni)</li></ul>Ad esempio, se un eVar è impostato alle 07:15 del lunedì, la scadenza [!UICONTROL Day] termina alle 07:15 del martedì, la scadenza [!UICONTROL Week] termina alle 07:15 del lunedì successivo e la scadenza [!UICONTROL Month] termina 31 giorni dopo alle 07:15.</li><li>**[!UICONTROL Custom]**: il valore scade dopo il numero di giorni immessi (86400 secondi al giorno).</li><li>**Un evento** ([!UICONTROL Purchase], [!UICONTROL Product View], [!UICONTROL Cart Open], [!UICONTROL Cart Checkout], [!UICONTROL Cart Add], [!UICONTROL Cart Remove], [!UICONTROL Cart View] o un evento personalizzato): il valore scade quando si verifica l&#39;evento selezionato. Se l’evento non si verifica, il valore non scade mai.</li><li>**[!UICONTROL Never]**: se un visitatore utilizza lo stesso identificatore, può trascorrere qualsiasi periodo di tempo tra l&#39;evento e eVar.</li></ul> |
| [!UICONTROL Type] | Il tipo di valore della variabile:<ul><li>**[!UICONTROL Text String]**: acquisisce i valori di testo. Si tratta del tipo più comune di eVar e dell’impostazione predefinita. Agisce in modo simile ad altre variabili, dove il valore al suo interno è una stringa di testo statica. Se tieni traccia di elementi quali campagne interne o parole chiave di ricerca interna, si consiglia questa impostazione.</li><li>**[!UICONTROL Counter]**: conta quante volte si verifica un’azioneprima dell’evento di successo. Ad esempio, puoi contare il numero di ricerche effettuate, indipendentemente dai termini di ricerca utilizzati, prima di un evento di successo.</li></ul> |
| [!UICONTROL Reset] | Al momento del salvataggio, scade immediatamente tutti i valori persistenti lato server per questa variabile in tutti i visitatori, incluse le associazioni dei prodotti di merchandising. Utilizza [!UICONTROL Reset] quando riutilizzi un eVar in modo da non combinare un valore precedente in un nuovo rapporto. **Il ripristino non cancella i dati storici.** |
| [!UICONTROL Enable Merchandising] | I valori supportati includono:<ul><li>**[!UICONTROL Disabled]**: eVar attribuisce gli eventi di successo al valore che persiste per il visitatore.</li><li>**[!UICONTROL Enabled]**: eVar diventa un&#39;eVar di merchandising che associa valori a singoli prodotti. Gli eventi di successo per ciascun prodotto vengono attribuiti al valore associato a tale prodotto. L&#39;abilitazione del merchandising mostra le impostazioni [!UICONTROL Merchandising] e [!UICONTROL Merchandising Binding Event] e rimuove l&#39;allocazione [!UICONTROL Linear].</li></ul>Abilita il merchandising solo per le eVar che descrivono come vengono trovati o acquistati i prodotti. Un’eVar di merchandising non attribuisce più crediti a eventi di successo che non sono legati a un prodotto. Consulta [eVar (Merchandising)](/help/components/dimensions/evar-merchandising.md). |
| [!UICONTROL Merchandising] | Determina da dove proviene il valore da associare ai prodotti:<ul><li>**[!UICONTROL Product Syntax]**: il valore è impostato su ciascun prodotto nella variabile `products` e si associa a tale prodotto in tale hit. Ogni prodotto può avere un valore diverso. Gli eventi di binding non sono utilizzati, pertanto [!UICONTROL Merchandising Binding Event] è disabilitato.</li><li>**[!UICONTROL Conversion Variable Syntax]**: il valore è impostato nell&#39;eVar stesso e persiste come valore di staging, riflettendo sempre il valore più recente inviato indipendentemente da [!UICONTROL Allocation]. Il valore si associa ai prodotti in un hit solo se l&#39;hit contiene un [!UICONTROL Merchandising Binding Event] selezionato. Ogni prodotto in tale hit riceve lo stesso valore.</li></ul>La modifica di questa impostazione senza aggiornare di conseguenza l’implementazione causa la perdita di dati. Per informazioni dettagliate sull&#39;implementazione, consulta [eVar (variabile merchandising)](/help/implement/vars/page-vars/evar-merchandising.md). |
| [!UICONTROL Merchandising Binding Event] | Disponibile solo quando [!UICONTROL Merchandising] è impostato su [!UICONTROL Conversion Variable Syntax]. Determina quali eventi o eVar associano il valore di staging di eVar ai prodotti sullo stesso hit. Se non si seleziona un evento di binding, verrà utilizzato [!UICONTROL All]. I valori supportati includono:<ul><li>**[!UICONTROL All]**: qualsiasi altro evento o eVar sull&#39;associazione dei trigger di hit. Questa è l&#39;impostazione predefinita.</li><li>**[!UICONTROL Purchase Event]**, **[!UICONTROL Product View Event]**, **[!UICONTROL Cart Open Event]**, **[!UICONTROL Cart Checkout Event]**, **[!UICONTROL Cart Add Event]**, **[!UICONTROL Cart Remove Event]** o **[!UICONTROL Cart View Event]**: l&#39;associazione si verifica sugli hit che contengono l&#39;evento selezionato.</li><li>**[!UICONTROL Campaign Event]**: l&#39;associazione si verifica negli hit che contengono un&#39;istanza della dimensione [Codice di tracciamento](/help/components/dimensions/tracking-code.md) ([`campaign`](/help/implement/vars/page-vars/campaign.md) variabile).</li><li>**Un evento personalizzato**: l&#39;associazione si verifica sugli hit che contengono l&#39;evento personalizzato selezionato.</li><li>**Un eVar personalizzato**: l&#39;associazione si verifica sugli hit che impostano l&#39;eVar selezionato.</li></ul>Le proprietà non possono attivare l&#39;associazione. Selezionare più valori tenendo premuto Ctrl (Windows) o Comando (Mac) e facendo clic su più elementi nell&#39;elenco. Quando un prodotto specifico già associato a un eVar riceve un&#39;altra associazione con lo stesso eVar, [!UICONTROL Allocation] determina quale valore viene mantenuto. |

### Scadenza

Le `eVars` scadono dopo un periodo di tempo specificato. Dopo la scadenza, all’eVar non viene più attribuito il merito degli eventi di successo. Le eVar possono anche essere configurate in modo da scadere in caso di eventi di successo. Ad esempio, se una promozione interna scade alla fine di una visita, le verrà attribuito il merito solo per gli acquisti o le registrazioni che si verificano durante la visita in cui sono stati attivati.

Ci sono due modi per far scadere un’eVar:

* Puoi impostare l’eVar in modo che scada dopo un determinato periodo di tempo o evento.
* Puoi forzare la scadenza di un’eVar reimpostandola, il che è utile quando si riutilizza una variabile.

Ad esempio, se modifichi la scadenza di un’eVar da 30 a 90 giorni, i valori eVar raccolti continueranno a persistere per la durata della nuova scadenza (in questo caso, 90 giorni). Per determinare la scadenza, il sistema controlla l’impostazione di scadenza corrente e l’ultima marca temporale impostata per il valore eVar raccolto. Solo l’opzione **[!UICONTROL Reset]** fa scadere i valori, immediatamente.

Un altro esempio: se un’eVar viene utilizzata a maggio per riflettere le promozioni interne e scade dopo 21 giorni, e a giugno viene utilizzata per acquisire le parole chiave di ricerca interna, il 1° giugno è necessario forzarne la scadenza o ripristinare la variabile. In questo modo potrai escludere i valori di promozioni interne dai rapporti di giugno.

### Distinzione tra maiuscole e minuscole

Le eVar non distinguono tra maiuscole e minuscole. La maiuscola o la minuscola utilizzata nei rapporti si basa sul primo valore registrato dal sistema backend. Questo valore potrebbe essere la prima istanza mai vista o variare su base temporale (ad esempio, mensile), a seconda della varietà e della quantità di dati associati alla suite di rapporti.

### Contatori

Sebbene le eVar siano utilizzate più spesso per valori stringa, possono anche essere configurate come contatori. Come contatori, le eVar sono utili se si vuole contare il numero di azioni eseguite da un utente prima di un evento. Ad esempio, puoi utilizzare un’eVar per acquisire il numero di ricerche interne eseguite prima dell’acquisto. Ogni volta che un visitatore esegue una ricerca, l’eVar deve contenere un valore &quot;+1&quot;. Se un visitatore esegue quattro ricerche prima di un acquisto, visualizzerai un’istanza per ciascun conteggio totale: 1.00, 2.00, 3.00 e 4.00. Tuttavia, solo al 4.00 viene attribuito il merito per l’evento di acquisto (metriche Ordini e Ricavi). I valori delle eVar di tipo contatore possono essere solo numeri positivi.

## Aggiungere o modificare le variabili di conversione

1. Fai clic su **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. Seleziona una suite di rapporti.
1. Fai clic su **[!UICONTROL Edit Settings]** > **[!UICONTROL Conversion]** > **[!UICONTROL Conversion Variables]**.
1. Sulla pagina [!UICONTROL Conversion Variables], fai clic su **[!UICONTROL Expand]** icona [+] accanto alla variabile di conversione da modificare.

   Oppure

   Fai clic su **[!UICONTROL Add New]** per aggiungere un eVar non utilizzato alla suite di rapporti.
1. Seleziona i campi della variabile di conversione da modificare.

   Consulta [Variabili di conversione - Descrizioni](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/conversion-var-admin.md#section_7C317BB0287A4B8EB0A1A4ECC40627BF). Alcuni campi consentono di digitare direttamente nel campo. Altri consentono di selezionare da un elenco a discesa di valori supportati.
1. Fai clic su **[!UICONTROL Save]**.
