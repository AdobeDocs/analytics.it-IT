---
description: Diversi rapporti in Adobe  Analytics possono mostrare Non specificato, Altro o Sconosciuto, a seconda del rapporto specifico visualizzato. In genere, questo elemento di riga indica che la variabile non era definita o altrimenti non disponibile.
title: Non specificato, Altro e Sconosciuto nel reporting
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '502'
ht-degree: 0%

---


# &quot;Non specificato&quot;, &quot;Altro&quot; e &quot;Sconosciuto&quot; nei rapporti

Diversi rapporti in Adobe  Analytics possono mostrare &quot;Non specificato&quot;, &quot;Altro&quot; o &quot;Sconosciuto&quot;, a seconda del rapporto specifico visualizzato. In genere, questo elemento di riga indica che la variabile non era definita o altrimenti non disponibile. Di seguito viene fornito un elenco completo di come ogni rapporto può contenere una di queste voci.

## &quot;Non specificato&quot; nel reporting

&quot;Non specificato&quot; è un elemento di riga piuttosto comune nei report.

* **Un evento viene attivato senza una variabile di conversione:** Ad esempio, un utente accede al sito e effettua un acquisto senza alcun valore eVar1. Se visualizzate gli ordini utilizzando la dimensione eVar1, non è presente alcun valore a cui attribuire l&#39;ordine. Pertanto, viene automaticamente attribuito a &quot;Non specificato&quot;.
* **Dati non classificati nei rapporti sulla classificazione:** Quando si visualizzano i dati di classificazione, qualsiasi valore a cui non siano associati dati a quella particolare classificazione restituisce &quot;Non specificato&quot;. Per risolvere questo problema, classificare il valore della variabile padre.
* **Report di suddivisione in cui è stata attivata una sola variabile:** Quando si applica una suddivisione a una variabile, ogni istanza di tale variabile deve essere contabilizzata. Se la seconda variabile non è stata visualizzata o se è persistente da un hit precedente, l’elemento dimensione è &quot;Non specificato&quot;.
* **hit non mobili nei rapporti sui dispositivi mobili:** Gli hit non mobili nei rapporti sui dispositivi mobili sono elencati come &quot;Non specificato&quot; (&quot;Non mobile&quot; in Report e  Analytics).

## &quot;Altro&quot; nella segnalazione

Anche se alquanto raro nel reportage, &quot;Altro&quot; può verificarsi in diverse circostanze:

* **Le pagine vengono attivate al di fuori dei filtri URL interni:** Questo valore è attivo per proteggere contro le frodi relative ai dati, ad esempio se un&#39;altra organizzazione ruba il codice sorgente e lo implementa sul proprio sito. Per correggere questo problema, accertatevi che tutti gli URL per i quali il codice è implementato corrispondano ai filtri URL interni nelle impostazioni della suite di rapporti.
* **Visitatori che utilizzano un browser di uso raro:** Nel rapporto Tipi browser, se i visitatori utilizzano un browser che non è un tipo di browser popolare, viene visualizzato &quot;Altro&quot; come suddivisione. Ci sono molte organizzazioni che producono browser. Tutti i browser che le organizzazioni più grandi non hanno creato vengono inseriti in &quot;Altro&quot; per evitare il disordine dei report.

## &quot;Sconosciuto&quot; nel report

&quot;Unknown&quot; può verificarsi in diverse circostanze:

* **Non riscontri browser quando si visualizzano i report Tecnologia:** Se una libreria AppMeasurement non è in grado di determinare se una funzione è supportata, nei rapporti viene visualizzato &quot;Sconosciuto&quot;.
* **Utilizzo di segmenti in cui i componenti non sono accessibili:** Assicurati che le variabili utilizzate in un segmento siano abilitate e che gli utenti possano accedervi. Se un utente non ha accesso a un componente segmento o se una variabile è disabilitata, viene visualizzato &quot;Sconosciuto&quot;.

## Applicazione di filtri a questi valori nel reporting {#section_5536E2B419D445D39C932E8F12C0070C}

Nella maggior parte dei casi, è sicuro ignorare questi elementi. Il filtro di ricerca può essere usato per rimuoverli, se necessario.

Alcune variabili di dati di back-end utilizzano il valore `::unspecified::` nel reporting, anche se non viene visualizzato nell&#39;interfaccia. Se un filtro di ricerca non riesce ad escludere i dati, provate a utilizzare questo valore (inclusi i due punti).
