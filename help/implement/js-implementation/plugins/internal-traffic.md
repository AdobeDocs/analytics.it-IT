---
title: Traffico interno
description: Il plug-plugin Traffico interno identifica dinamicamente i visitatori provenienti da una rete interna.
seo-description: Plug-plugin Traffico interno
seo-title: Plug-plugin Traffico interno
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# Traffico interno

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
1. Modify doPlugins and set the eVar: The plugin can then be initialized by including this line of code within the doPlugins section of your AppMeasurement library code, using the eVar defined in step one: `s.eVarXX = s.intCheck();`
The variable value will be set to “internal” or “external”.
1. Aggiungete il codice sorgente plug-in: Includi il codice plug-plugin sotto la sezione doplugins del file appmeasurement.

## Codice sorgente plug-in

Aggiungi questo codice sotto la sezione doplugins della libreria appmeasurement.

```s.intCheck=new Function("",""
+"var s=this;if(document.cookie.indexOf('intChk=')==-1){try{document."
+"cookie='intChk=1';var x=new XMLHttpRequest(),y;x.open('GET',s.intUr"
+"l,false);x.send();if(x.status===200&&x.statusText==='OK'){y='intern"
+"al';}}catch(e){y='external'}finally{return y}}");```

## Other Notes

* Always test plug-in installations to ensure that data collection happens as expected before deploying them in a production environment.
* Your implementation might be using a different object name than the default Adobe Analytics "s" object. If so, please update the object name accordingly.
* If you employ a Tag Management System, please follow its steps to update doPlugins and the other custom plugins.

