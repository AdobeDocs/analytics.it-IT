---
title: Internal Traffic
description: Il plug-plugin Traffico interno identifica dinamicamente i visitatori provenienti da una rete interna.
seo-description: Plug-plugin Traffico interno
seo-title: Plug-plugin Traffico interno
translation-type: tm+mt
source-git-commit: 8c2b28ee1ca2e9448b9dec99a0505d0fae525e94

---


# Internal Traffic

Il plug-plugin Traffico interno identifica dinamicamente i visitatori provenienti da una rete interna.

L'identificazione del traffico interno e esterno favorisce una maggiore precisione in tutti i tipi di reporting, fornendo un meccanismo di raccolta dei filtri e dei dati dei segmenti. Implementato correttamente, elimina anche la necessità di una regola VISTA o di regole di elaborazione che rappresentano approcci tipici per identificare tale traffico.

## Come funziona il plug-plugin Traffico interno?

Il plug-in tenta di caricare un file che sarà disponibile solo all'interno della rete/intranet interna, ad es. un pixel trasparente da 1 x 1. Se viene caricato correttamente, il traffico per quel visitatore viene identificato come interno. Qualsiasi altro elemento sarebbe il traffico esterno.

## Considerazioni

* L'unico lato negativo di questo approccio è rappresentato dal fatto che nella console del browser per i visitatori esterni viene visualizzato un errore 404 nella prima pagina della visita. Questo non influirà sull'esperienza dell'utente.
* Consigliamo vivamente di ottenere l'approvazione dal team Rete o infosec prima di tentare di caricare un pixel internamente.
* Anche se il plug-plugin non sposta il traffico in un'altra suite di rapporti o la escluderà dal reporting (come avviene con una regola VISTA), la logica personalizzata può essere inclusa con la sua implementazione, in modo che questa funzionalità possa avere luogo sul lato client.

## Implementazione

1. Aggiungete il pixel Intranet: Potete aggiungere qualsiasi tipo di file nella rete intranet che il plug-in tenta di accedere. È consigliabile un pixel trasparente da 1 x 1. Deve essere collocato in una posizione sulla rete Intranet accessibile dall'interno delle reti interne.
1. Configura una evar: Un evar deve essere aggiunto all'interno della suite di rapporti di destinazione. Deve avere una scadenza di «Visita» e allocazione di «Valore originale (primo)».
1. Definite l'URL interno: Nelle variabili di configurazione appmeasurement e prima che venga creata l'istanza di doplugins, definite la variabile URL interna (s. inturl) per il pixel o altro file per il controllo del traffico. Ad esempio: `s.intURL = "https://www.yourdomainhere.com/trafficCheck.gif"`
1. Modificate doplugins e impostate la evar: Il plug-plugin può essere inizializzato includendo questa riga di codice nella sezione doplugins del codice della libreria appmeasurement, utilizzando l'evar definito al punto uno: `s.eVarXX = s.intCheck();`
Il valore della variabile sarà impostato su «interno» o «esterno».
1. Aggiungete il codice sorgente plug-in: Includi il codice plug-plugin sotto la sezione doplugins del file appmeasurement.

## Codice sorgente plug-in

Aggiungi questo codice sotto la sezione doplugins della libreria appmeasurement.

```JavaScript
s.intCheck=new Function("",""
+"var s=this;if(document.cookie.indexOf('intChk=')==-1){try{document."
+"cookie='intChk=1';var x=new XMLHttpRequest(),y;x.open('GET',s.intUr"
+"l,false);x.send();if(x.status===200&&x.statusText==='OK'){y='intern"
+"al';}}catch(e){y='external'}finally{return y}}");
```

## Altre note

* Verifica sempre le installazioni dei plug-in per garantire che la raccolta dati avvenga come previsto prima di distribuirla in un ambiente di produzione.
* L'implementazione potrebbe utilizzare un nome oggetto diverso da quello predefinito di Adobe Analytics. In tal caso, aggiornare il nome dell'oggetto di conseguenza.
* Se utilizzate un sistema di gestione tag, attenetevi alla relativa procedura per aggiornare doplugins e gli altri plug-in personalizzati.
