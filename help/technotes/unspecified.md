---
description: Vari rapporti in Adobe Analytics possono mostrare Non specificato, Nessuno, Altro o Sconosciuto, a seconda del rapporto specifico visualizzato. In genere, questo elemento di riga indica che la variabile non è stata definita o altrimenti non disponibile.
title: Non specificato, Nessuno, Altro e Sconosciuto nella generazione rapporti
feature: Analytics Basics
exl-id: 35451239-91f3-400a-981e-8c3fbc0e4185
source-git-commit: d3d5b01fe17f88d07a748fac814d2161682837c2
workflow-type: tm+mt
source-wordcount: '515'
ht-degree: 100%

---

# “Non specificato”, “Nessuno”, “Altro” e “Sconosciuto” nella generazione rapporti

Vari rapporti in Adobe Analytics possono mostrare “Non specificato”, “Altro” o “Sconosciuto”, a seconda del rapporto specifico visualizzato. In genere, questo elemento di riga indica che la variabile non è stata definita o altrimenti non disponibile. Di seguito viene fornito un elenco completo di come ciascun rapporto può avere uno di questi elementi di riga.

## “Non specificato” (o “Nessuno”) nei rapporti {#reporting}

“Non specificato” è un elemento di riga abbastanza comune nei rapporti. Viene spesso indicato anche come “Nessuno”.

* **Un evento si attiva senza una variabile di conversione:** ad esempio, un utente arriva sul tuo sito ed effettua un acquisto senza alcun valore eVar1. Se visualizzi gli ordini utilizzando la dimensione eVar1, non esiste alcun valore a cui attribuire questo ordine. Pertanto viene automaticamente attribuito a “Non specificato”.
* **Dati non classificati nei rapporti di classificazione:** quando si visualizzano i dati di classificazione, qualsiasi valore a cui non sono associati dati con quella particolare classificazione restituisce “Non specificato”. Per risolvere questo problema, classifica il valore della variabile principale.
* **Rapporti con raggruppamenti in cui è stata attivata solo una variabile:** quando si applica un raggruppamento a una variabile, è necessario tenere conto di ogni istanza di tale variabile. Se la seconda variabile non è stata vista o se persiste da un hit precedente, l’elemento dimensione è “Non specificato”.
* **Hit non mobili nei rapporti mobili:** qualsiasi hit non mobile nei rapporti mobili viene elencato come “Non specificato” (“Non mobile” in rapporti e analisi).

## “Altro” nella generazione rapporti {#other}

Sebbene sia piuttosto raro nella generazione rapporti, il termine “Altro” può verificarsi in diverse circostanze:

* **Le pagine si attivano al di fuori dei filtri URL interni:** questo valore serve a proteggerti dalle frodi dei dati, ad esempio se un’altra organizzazione ruba il tuo codice sorgente e lo implementa sul proprio sito. Per correggere questo problema, assicurati che tutti gli URL su cui è implementato il tuo codice corrispondano ai filtri URL interni nelle impostazioni della suite di rapporti.
* **Visitatori che utilizzano un browser utilizzato raramente:** nel rapporto Tipi di browser, “Altro” viene visualizzato come un raggruppamento se i visitatori utilizzano un browser che non è un tipo di browser popolare. Esistono molte organizzazioni che producono browser. Tutti i browser non creati dalle organizzazioni più grandi vengono inseriti nel bucket “Altro” per evitare confusione nel rapporto.

## “Sconosciuto” nella generazione rapporti {#unknown}

“Sconosciuto” può verificarsi in diverse circostanze:

* **Hit non del browser durante la visualizzazione dei rapporti sulla tecnologia:** se una libreria AppMeasurement non è in grado di determinare se una funzionalità è supportata, nei rapporti viene visualizzato “Sconosciuto”.
* **Utilizzo di segmenti in cui i componenti non sono accessibili:** assicurati che le variabili utilizzate in un segmento siano abilitate e che gli utenti possano accedervi. Se un utente non ha accesso a un componente del segmento o se una variabile è disabilitata, viene visualizzato “Sconosciuto”.

## Filtraggio di questi valori nei rapporti {#filter}

Nella maggior parte dei casi, è sicuro ignorare questi elementi di riga. Se lo si desidera, è possibile utilizzare il filtro di ricerca per rimuoverli.

Alcune variabili di dati di backend utilizzano il valore `::unspecified::` nei rapporti, sebbene non sia mostrato nell’interfaccia. Se un filtro di ricerca non riesce a escludere i dati, prova a utilizzare questo valore (inclusi i due punti).
