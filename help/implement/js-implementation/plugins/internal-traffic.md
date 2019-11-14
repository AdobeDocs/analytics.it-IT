---
title: Internal Traffic
description: Il plug-in Traffico interno identifica dinamicamente i visitatori provenienti da una rete interna.
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Internal Traffic

Il plug-in Traffico interno identifica dinamicamente i visitatori provenienti da una rete interna.

Identificare il traffico interno ed esterno favorisce una maggiore precisione in tutti i tipi di reporting, fornendo un meccanismo che filtra e segmenta i dati raccolti. Implementata correttamente, eliminerebbe anche la necessità di una regola VISTA o di una regola di elaborazione che siano approcci tipici per identificare tale traffico.

## Come funziona il plugin Traffico interno?

Il plug-in tenta di caricare un file che sarebbe disponibile solo all’interno della rete interna o della rete Intranet, ovvero un pixel trasparente da 1x1. Se viene caricato correttamente, il traffico per quel visitatore viene identificato come interno. Qualsiasi altra cosa sarebbe il traffico esterno.

## Considerazioni

* L’unico aspetto negativo di questo approccio è che nella console del browser viene visualizzato un errore 404 per i visitatori esterni sulla prima pagina della visita. Ciò non influirà sull'esperienza utente.
* È consigliabile ottenere l'approvazione dalla rete o dal team InfoSec prima di tentare di caricare un pixel ospitato internamente.
* Anche se il plug-in non sposterà il traffico in un'altra suite di rapporti o non lo escluderà dal reporting (come potrebbe essere fatto con una regola VISTA), la logica personalizzata può essere inclusa nella relativa implementazione, in modo che questa funzionalità possa avvenire lato client.

## Implementazione

1. Aggiungi il tuo Pixel Intranet: Potete aggiungere qualsiasi tipo di file sulla rete Intranet a cui il plug-in tenta di accedere. Si consiglia un pixel trasparente 1x1. Dovrebbe essere collocato in una posizione sulla rete Intranet ampiamente accessibile dalle reti interne.
1. Configurare una eVar: Nella suite di rapporti di destinazione sarà necessario aggiungere un'eVar. Deve avere una scadenza di "Visita" e l'allocazione di "Valore originale (Primo)".
1. Definite l’URL interno: Nelle variabili di configurazione AppMeasurement e prima che venga creata un'istanza doPlugins, definite la variabile URL interna (s.intURL) per il pixel o altro file da usare per il controllo del traffico. Ad esempio: `s.intURL = "https://www.yourdomainhere.com/trafficCheck.gif"`
1. Modificare i doPlugins e impostare l'eVar: Il plug-in può quindi essere inizializzato includendo questa riga di codice nella sezione doPlugins del codice libreria AppMeasurement, utilizzando l'eVar definita al punto uno: `s.eVarXX = s.intCheck();`Il valore della variabile viene impostato su "internal" o "external".
1. Aggiungi il codice sorgente del plug-in: Includi il codice del plug-in sotto la sezione doPlugins del file AppMeasurement.

## Codice sorgente plug-in

Aggiungi questo codice sotto la sezione doPlugins della libreria AppMeasurement.

```JavaScript
s.intCheck=new Function("",""
+"var s=this;if(document.cookie.indexOf('intChk=')==-1){try{document."
+"cookie='intChk=1';var x=new XMLHttpRequest(),y;x.open('GET',s.intUr"
+"l,false);x.send();if(x.status===200&&x.statusText==='OK'){y='intern"
+"al';}}catch(e){y='external'}finally{return y}}");
```

## Altre note

* Verificate sempre le installazioni dei plug-in per garantire che la raccolta dei dati avvenga come previsto prima di distribuirli in un ambiente di produzione.
* L'implementazione potrebbe utilizzare un nome oggetto diverso dall'oggetto "s" di Adobe Analytics predefinito. In tal caso, aggiornare di conseguenza il nome dell'oggetto.
* Se utilizzi un sistema di gestione dei tag, esegui i passaggi per aggiornare doPlugins e gli altri plug-in personalizzati.
