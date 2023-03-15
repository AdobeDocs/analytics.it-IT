---
description: In Adobe Analytics, in vari rapporti è possibile visualizzare i valori Unspecified (Non specificato), None (Nessuno), Other (Altro) o Unknown (Sconosciuto), a seconda del rapporto specifico visualizzato. In genere, questo elemento di riga indica che la variabile non è stata definita o non è altrimenti disponibile.
title: Non specificato, Nessuno, Altro e Sconosciuto nel reporting
feature: Analytics Basics
exl-id: 35451239-91f3-400a-981e-8c3fbc0e4185
source-git-commit: c8faf29262b9b04fc426f4a26efaa8e51293f0ec
workflow-type: tm+mt
source-wordcount: '515'
ht-degree: 0%

---

# &quot;Unspecified&quot;, &quot;None&quot;, &quot;Other&quot;, and &quot;Unknown&quot; in reporting (Non specificato, &quot;Nessuno&quot;, &quot;Altro&quot; e &quot;Sconosciuto&quot; nel reporting)

In vari rapporti di Adobe Analytics è possibile visualizzare i valori &quot;Non specificato&quot;, &quot;Altro&quot; o &quot;Sconosciuto&quot;, a seconda del rapporto specifico visualizzato. In genere, questo elemento di riga indica che la variabile non è stata definita o non è altrimenti disponibile. Di seguito viene fornito un elenco completo di come ogni rapporto può avere una di queste voci.

## &quot;Non specificato&quot; (o &quot;Nessuno&quot;) nel reporting

&quot;Non specificato&quot; è una voce abbastanza comune nei rapporti. Viene spesso indicato anche come &quot;Nessuno&quot;.

* **Un evento viene attivato senza una variabile di conversione:** Ad esempio, un utente accede al sito e effettua un acquisto senza alcun valore eVar1. Se visualizzi gli ordini utilizzando la dimensione eVar1, non esiste un valore a cui attribuire questo ordine. Pertanto, viene automaticamente attribuito a &quot;Non specificato&quot;.
* **Dati non classificati nei rapporti di classificazione:** Quando si visualizzano i dati di classificazione, qualsiasi valore senza dati associati a tale classificazione restituisce &quot;Non specificato&quot;. Per risolvere questo problema, classifica il valore della variabile padre.
* **Rapporti di suddivisione in cui veniva generata una sola variabile:** Quando applichi un raggruppamento a una variabile, ogni istanza di tale variabile deve essere considerata. Se la seconda variabile non è stata visualizzata o se è persistita da un hit precedente, l’elemento dimensionale è &quot;Non specificato&quot;.
* **Hit non per dispositivi mobili nei rapporti sui dispositivi mobili:** Qualsiasi hit non mobile nei rapporti sui dispositivi mobili è elencato come &quot;Non specificato&quot; (&quot;Non mobile&quot; in Reports and Analytics).

## &quot;Altro&quot; nel reporting

Sebbene sia piuttosto raro nei rapporti, &quot;Altro&quot; può verificarsi in diverse circostanze:

* **Le pagine si attivano all’esterno dei filtri URL interni:** Questo valore ha lo scopo di prevenire le frodi dei dati, ad esempio se un’altra organizzazione ruba il codice sorgente e lo implementa sul proprio sito. Per risolvere questo problema, assicurati che tutti gli URL in cui viene implementato il codice corrispondano ai filtri URL interni nelle impostazioni della suite di rapporti.
* **Visitatori che utilizzano un browser poco utilizzato:** Nel rapporto Tipi di browser, &quot;Altro&quot; viene visualizzato come raggruppamento se i visitatori utilizzano un browser che non è un tipo di browser comune. Ci sono molte organizzazioni che producono browser. Tutti i browser che le organizzazioni più grandi non hanno creato sono inseriti nel bucket &quot;Altro&quot; per evitare elementi superflui dei rapporti.

## &quot;Sconosciuto&quot; nel reporting

&quot;Sconosciuto&quot; può verificarsi in diverse circostanze:

* **Hit non del browser durante la visualizzazione dei rapporti Tecnologia:** Se una libreria AppMeasurement non è in grado di determinare se una funzione è supportata, nel reporting viene visualizzato &quot;Sconosciuto&quot;.
* **Utilizzo di segmenti in cui i componenti non sono accessibili:** Assicurati che le variabili utilizzate in un segmento siano abilitate e che gli utenti possano accedervi. Se un utente non ha accesso a un componente del segmento o se una variabile è disabilitata, viene visualizzato &quot;Sconosciuto&quot;.

## Filtrare questi valori nel reporting {#section_5536E2B419D445D39C932E8F12C0070C}

Nella maggior parte dei casi, è sicuro ignorare queste righe. Se necessario, puoi utilizzare il filtro di ricerca per rimuoverli.

Alcune variabili di dati di back-end utilizzano il valore `::unspecified::` nel reporting, anche se non viene visualizzato nell’interfaccia. Se un filtro di ricerca non esclude i dati, prova a utilizzare questo valore (compresi i due punti).
