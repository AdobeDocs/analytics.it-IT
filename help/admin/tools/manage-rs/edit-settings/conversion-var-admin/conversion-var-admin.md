---
description: La variabile di conversione (o eVar) Custom Insight viene inserita nel codice di Adobe in specifiche pagine del sito web. Il suo scopo principale è segmentare le metriche di successo della conversione nei rapporti di marketing personalizzati. Un’eVar può essere basata su visite e funziona in modo simile ai cookie. I valori trasmessi nelle variabili eVar seguono l’utente per un periodo di tempo predeterminato.
keywords: eVar
title: Variabili di conversione (eVar)
feature: Admin Tools
role: Admin
exl-id: 822ecaff-a06c-42e1-aee8-ef4a43df4230
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '1639'
ht-degree: 94%

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
>Nell’eVar di una richiesta di immagine è possibile memorizzare un solo valore. Per poter usare più valori in un valore eVar, consigliamo di implementare [variabili elenco (list var)](/help/implement/vars/page-vars/page-variables.md).

### Variabili di conversione - Descrizioni {#section_7C317BB0287A4B8EB0A1A4ECC40627BF}

Descrizione dei campi utilizzati nella [modifica delle variabili di conversione](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/conversion-var-admin.md).

| Elemento | Descrizione |
| --- | --- |
| [!UICONTROL Name] | Nome descrittivo della variabile di conversione. Questo nome rappresenta il modo in cui l’eVar viene indicata nei rapporti e sarà usato come nome rapporto/dimensione nel menu a sinistra. |
| [!UICONTROL Type] (solo eVar) | Il tipo di valore della variabile:<ul><li>**[!UICONTROL Text String]**: acquisisce i valori di testo utilizzati sul sito. Si tratta del tipo di eVar più comune ed è usato per impostazione predefinita. Agisce in modo simile ad altre variabili, dove il valore al suo interno è una stringa di testo statica. Se tieni traccia di elementi quali campagne interne o parole chiave di ricerca interna, questa è l’impostazione consigliata.</li><li>**[!UICONTROL Counter]**: conta quante volte si verifica un’azioneprima dell’evento di successo. Ad esempio, se utilizzi un’eVar per tenere traccia delle ricerche interne sul sito, imposta questo valore su [!UICONTROL Text String] per tenere traccia dell’uso dei termini di ricerca. Imposta questo valore su [!UICONTROL Counter] per contare il numero di ricerche effettuate, indipendentemente dai termini di ricerca utilizzati. Ad esempio, puoi utilizzare un’eVar contatore per tenere traccia di quante volte un utente ha utilizzato la ricerca interna prima di effettuare un acquisto.</li></ul> |
| [!UICONTROL Allocation] | Determina il modo in cui Analytics attribuisce il merito di un evento di successo se una variabile riceve più valori prima dell’evento. I valori supportati includono:<ul><li>**[!UICONTROL Most Recent]**: all’ultimo valore eVar viene sempre attribuito il merito degli eventi di successo fino alla scadenza di tale eVar.</li><li>**[!UICONTROL Original Value]**: al primo valore eVar viene sempre attribuito il merito per gli eventi di successo fino alla scadenza di tale eVar.</li><li>**[!UICONTROL Linear]**: gli eventi di successo vengono attribuiti in modo uniforme a tutti i valori eVar. Poiché l’allocazione lineare distribuisce accuratamente i valori solo all’interno di una visita, utilizza l’allocazione lineare insieme a una scadenza eVar di tipo Visita.</li></ul> **Nota**: il passaggio dell’allocazione a o da Lineare impedisce la visualizzazione dei dati storici. La combinazione di tipi di allocazione nell’interfaccia di reporting può portare a dati errati nei rapporti. Ad esempio, l’allocazione lineare potrebbe dividere i ricavi in diversi valori di eVar. Dopo aver ripristinato l’allocazione più recente, il 100% di tali entrate sarebbe associato al singolo valore più recente. Questa associazione può portare a conclusioni errate da parte degli utenti.<br><br>Per evitare possibile confusione nei rapporti, i dati storici non sono disponibili nell’interfaccia di Adobe Analytics. Possono essere visualizzati se si ripristina l’impostazione di allocazione iniziale dell’eVar specificata.Tuttavia si consiglia di non modificare le impostazioni di allocazione eVar con l’unico scopo di poter accedere ai dati storici. Se si desidera impostare nuove impostazioni di allocazione per i dati già registrati, Adobe consiglia di utilizzare una nuova eVar anziché modificare le impostazioni di allocazione su un’eVar per la quale sono già stati accumulati molti dati storici. |
| [!UICONTROL Expire After] | Specifica un periodo di tempo, o un evento, dopo il quale scadrà il valore eVar (non gli verrà più attribuito il merito per eventi di successo). Se un evento di successo si verifica dopo la scadenza dell’eVar, il merito per l’evento viene attribuito al valore None (nessun eVar è attivo). Se selezioni un evento come valore di scadenza, la variabile scade solo se si verifica l’evento. Se l’evento non si verifica, la variabile non scade.  Le opzioni di scadenza disponibili possono essere classificate in quattro categorie principali:<ul><li>**A livello di visualizzazione pagina o di visita.** Gli eventi di conversione che non rientrano nella visualizzazione pagina o visita non vengono associati all’eVar.</li><li>**In base a un periodo di tempo, ad esempio giorno, settimana, mese o anno.** Gli eventi di conversione che non rientrano nel periodo di tempo specificato non vengono associati all’eVar. Il periodo di scadenza inizia quando la variabile viene impostata. Le eVar scadono in base al tempo impostato, al secondo (minuto, ora, giorno, mese, ecc.): <ul><li>MINUTO=60 secondi</li><li>ORA=3.600 secondi (60 minuti)</li><li>GIORNO=86.400 secondi (24 ore)</li><li>SETTIMANA=604.800 secondi (7 giorni)</li><li>MESE=2.678.400 secondi (31 giorni)</li><li>TRIMESTRE=8.035.200 secondi (93 giorni - 3 mesi di 31 giorni)</li><li>ANNO=31.536.000 secondi (365 giorni)</li><br>Se una visita inizia alle ore 7:00 di lunedì e un eVar è impostato per tale visita, alle ore 07:15, la scadenza avviene come indicato di seguito:<li>Scadenza giorno: eVar scade alle ore 7:15 di martedì.</li><li>Scadenza settimana: eVar scade il lunedì successivo alle ore 07:00.:15</li><li>Scadenza mese: eVar scade 31 giorni a partire da lunedì alle ore 07:00.:15</li></ul><li>**Eventi di conversione specifici.** Qualsiasi altro evento di conversione che si attiva dopo l’evento specifico designato viene associato all’eVar.</li><li>**Mai.** Finché il cookie visitorID è intatto, può trascorrere qualsiasi periodo di tempo tra eVar ed evento.</li></ul> |
| [!UICONTROL Status] (Solo eVar) | Definisce lo stato [!UICONTROL eVar]:<ul><li>**Disabilitato**: disattiva l’[!UICONTROL eVar]. Rimuove l’[!UICONTROL eVar] dall’elenco delle variabili di conversione.</li><li>**Nessuna relazione secondaria**: impedisce la suddivisione dell’[!UICONTROL eVar] per una dimensione.</li><li>**Relazioni secondarie di base**: consente di suddividere un’eVar per qualsiasi dimensione intera (ad esempio, Prodotti o Campagna).</li></ul> |
| [!UICONTROL Reset] | Ripristina eventuali valori esistenti nell’eVar. Utilizza questa impostazione quando assegni una nuova destinazione a un eVar in modo da non combinare un valore precedente in un nuovo rapporto. Il ripristino non cancella i dati storici. |
| [!UICONTROL Merchandising] (solo eVar) | Le variabili di merchandising possono seguire una delle due sintassi seguenti:<ul><li>**[!UICONTROL Products Syntax]**: associa il valore eVar a un prodotto. **Nota**: se [!UICONTROL Products Syntax] è selezionato, la sezione [!UICONTROL Merchandising Binding Event] è disabilitata e non è possibile selezionarla per la modifica. Per questa sintassi, [!UICONTROL Binding Events] non sono applicabili.</li><li>**[!UICONTROL Conversion Variable Syntax]**: associa l’eVar a un prodotto solo se si verifica un [!UICONTROL Binding Event]. In questo caso, seleziona gli eventi che agiscono da [!UICONTROL Binding Events].  Se si modifica questa impostazione senza aggiornare di conseguenza il codice JavaScript, si verificherà una perdita di dati. Vedi [Variabili di merchandising](/help/components/dimensions/evar-merchandising.md).</li></ul> |
| [!UICONTROL Merchandising Binding Event] (solo eVar) | Se Merchandising è impostato su [!UICONTROL Conversion Variable Syntax], gli eventi selezionati associano il valore eVar corrente a un prodotto. Per utilizzare un [!UICONTROL Binding Event], imposta [!UICONTROL Allocation] su [!UICONTROL Most Recent]. Se [!UICONTROL Allocation] è impostato su [!UICONTROL Original Value], la prima associazione del prodotto eVar rimane fino alla scadenza dell’eVar. Per selezionare più eventi, tieni premuto Ctrl (Windows) o Comando (Mac) e fai clic su più elementi nell’elenco. Puoi selezionare un evento solo quando è selezionato [!UICONTROL Conversion Variable Syntax]. |

### Scadenza

Le `eVars` scadono dopo un periodo di tempo specificato. Dopo la scadenza, all’eVar non viene più attribuito il merito degli eventi di successo. Le eVar possono anche essere configurate in modo da scadere in caso di eventi di successo. Ad esempio, se una promozione interna scade alla fine di una visita, le verrà attribuito il merito solo per gli acquisti o le registrazioni che si verificano durante la visita in cui sono stati attivati.

Ci sono due modi per far scadere un’eVar:

* Puoi impostare l’eVar in modo che scada dopo un determinato periodo di tempo o evento.
* Puoi forzare la scadenza di un’eVar ripristinandolo; questo metodo è utile se si vuole riutilizzare una variabile.

Ad esempio, se modifichi la scadenza di un’eVar da 30 a 90 giorni, i valori eVar raccolti continueranno a persistere per la durata della nuova scadenza (in questo caso, 90 giorni). Per determinare la scadenza, il sistema controlla l’impostazione di scadenza corrente e l’ultima marca temporale impostata per il valore eVar raccolto. Solo l’opzione **[!UICONTROL Reset]** fa scadere i valori, immediatamente.

Un altro esempio: se un’eVar viene utilizzata a maggio per riflettere le promozioni interne e scade dopo 21 giorni, e a giugno viene utilizzata per acquisire le parole chiave di ricerca interna, il 1° giugno è necessario forzarne la scadenza o ripristinare la variabile. In questo modo potrai escludere i valori di promozioni interne dai rapporti di giugno.

### Distinzione tra maiuscole e minuscole

Le eVar non distinguono tra maiuscole e minuscole. La maiuscola o la minuscola utilizzata nei rapporti si basa sul primo valore registrato dal sistema backend. Questo valore potrebbe essere la prima istanza mai vista o variare su base temporale (ad esempio, mensile), a seconda della varietà e della quantità di dati associati alla suite di rapporti.

### Contatori

Sebbene le eVar siano utilizzate più spesso per valori stringa, possono anche essere configurate come contatori. Come contatori, le eVar sono utili se si vuole contare il numero di azioni eseguite da un utente prima di un evento. Ad esempio, puoi utilizzare un’eVar per acquisire il numero di ricerche interne eseguite prima dell’acquisto. Ogni volta che un visitatore esegue una ricerca, l’eVar deve contenere un valore “+1”. Se un visitatore esegue quattro ricerche prima di un acquisto, troverai un’istanza per ogni conteggio totale: 1.00, 2.00, 3.00 e 4.00. Tuttavia, solo al 4.00 viene attribuito il merito per l’evento di acquisto (metriche Ordini e Ricavi). I valori delle eVar di tipo contatore possono essere solo numeri positivi.

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
