---
description: Diversi rapporti in Adobe Analytics possono mostrare Non specificato, Nessuno, Altro o Sconosciuto, a seconda del rapporto specifico visualizzato. In genere, questa riga indica che la variabile non è stata definita o non è altrimenti disponibile.
title: Non specificato, nessuno, altro e sconosciuto nel reporting
feature: Analytics Basics
exl-id: 35451239-91f3-400a-981e-8c3fbc0e4185
source-git-commit: c8faf29262b9b04fc426f4a26efaa8e51293f0ec
workflow-type: tm+mt
source-wordcount: '515'
ht-degree: 0%

---

# &quot;Non specificato&quot;, &quot;Nessuno&quot;, &quot;Altro&quot; e &quot;Sconosciuto&quot; nel rapporto

Diversi rapporti in Adobe Analytics possono mostrare &quot;Non specificato&quot;, &quot;Altro&quot; o &quot;Sconosciuto&quot;, a seconda del rapporto specifico visualizzato. In genere, questa riga indica che la variabile non è stata definita o non è altrimenti disponibile. Di seguito è riportato un elenco completo delle possibili voci di un rapporto.

## &quot;Non specificato&quot; (o &quot;Nessuno&quot;) nel reporting

&quot;Non specificato&quot; è una voce di riga abbastanza comune nei rapporti. Viene anche spesso indicato come &quot;Nessuno&quot;.

* **Un evento viene attivato senza una variabile di conversione:** Ad esempio, un utente accede al tuo sito ed effettua un acquisto senza alcun valore eVar1. Se si visualizzano gli ordini utilizzando la dimensione eVar1, non esiste alcun valore a cui attribuire l&#39;ordine. Pertanto, viene automaticamente attribuito a &quot;Non specificato&quot;.
* **Dati non classificati nei rapporti di classificazione:** Quando visualizzi i dati di classificazione, qualsiasi valore a cui non sono associati dati di una particolare classificazione restituisce &quot;Non specificato&quot;. Per risolvere questo problema, classifica il valore della variabile padre.
* **Rapporti di suddivisione in cui è stata attivata una sola variabile:** Quando applichi un raggruppamento a una variabile, ogni istanza di tale variabile deve essere contabilizzata. Se la seconda variabile non è stata visualizzata o se è persistente da un hit precedente, l’elemento dimensione è &quot;Non specificato&quot;.
* **Risultati non mobili nei rapporti per dispositivi mobili:** Gli hit non mobili nei rapporti sui dispositivi mobili sono elencati come &quot;Non specificato&quot; (&quot;Non mobile&quot; in Reports and Analytics).

## &quot;Altro&quot; nella segnalazione

Anche se alquanto raro nel riportare, &quot;Altro&quot; può verificarsi in diverse circostanze:

* **Le pagine vengono attivate all’esterno dei filtri URL interni:** Questo valore è attivo per proteggere da frodi nei dati, ad esempio se un’altra organizzazione ruba il codice sorgente e lo implementa sul proprio sito. Per correggere questo problema, accertati che tutti gli URL in cui viene implementato il codice corrispondano ai filtri URL interni nelle impostazioni della suite di rapporti.
* **Visitatori che utilizzano un browser poco utilizzato:** Nel rapporto Tipi di browser , &quot;Altro&quot; viene visualizzato come suddivisione se i visitatori utilizzano un browser che non è un tipo di browser comune. Ci sono molte organizzazioni che producono browser. Tutti i browser che le organizzazioni più grandi non hanno creato vengono inseriti in &quot;Altro&quot; per evitare il disordine dei report.

## &quot;Sconosciuto&quot; nel reporting

&quot;Sconosciuto&quot; può verificarsi in diverse circostanze:

* **Risultati non relativi al browser quando visualizzi i rapporti sulla tecnologia:** Se una libreria AppMeasurement non è in grado di determinare se una funzione è supportata, nel rapporto viene visualizzato &quot;Sconosciuto&quot;.
* **Utilizzo di segmenti in cui i componenti non sono accessibili:** Assicurati che le variabili utilizzate in un segmento siano abilitate e che gli utenti possano accedervi. Se un utente non ha accesso a un componente segmento o se una variabile è disabilitata, viene visualizzato &quot;Sconosciuto&quot;.

## Filtrare questi valori nel reporting {#section_5536E2B419D445D39C932E8F12C0070C}

Nella maggior parte dei casi, è sicuro ignorare questi elementi di riga. Il filtro di ricerca può essere utilizzato per rimuoverli, se necessario.

Alcune variabili di dati di backend utilizzano il valore `::unspecified::` nel reporting, anche se non viene visualizzato nell’interfaccia di . Se un filtro di ricerca non riesce ad escludere i dati, prova a utilizzare questo valore (inclusi i due punti).
