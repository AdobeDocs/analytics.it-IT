---
description: Le variabili dinamiche consentono di copiare i valori da una variabile all’altra senza digitare più volte i valori completi nelle richieste di immagini sul sito.
keywords: Implementazione di Analytics
solution: null
title: Variabili dinamiche
translation-type: tm+mt
source-git-commit: 8c06a54ccd652f3f915af3af040e9cc69f01d0c1

---


# s.useForcedLinkTracking

Questo flag viene utilizzato per disabilitare il tracciamento forzato dei collegamenti per alcuni browser. Il tracciamento forzato dei collegamenti è abilitato per impostazione predefinita per i browser FireFox 20+ e WebKit.

Quando `useForcedLinkTracking` è attivato, il file AppMeasurement ha la precedenza sul comportamento predefinito dei collegamenti in alcuni browser per impedire che la chiamata di tracciamento dei collegamenti venga annullata quando si apre la nuova pagina. Il file AppMeasurement esegue la chiamata di tracciamento del collegamento e gestisce l’evento di navigazione manualmente, invece di utilizzare l’azione browser predefinita.

In JavaScript H.25.4 (rilasciato a febbraio 2013), le seguenti limitazioni dell'ambito sono state aggiunte ai collegamenti tracciati quando `useForcedLinkTracking` è attivato. Il tracciamento automatico dei collegamenti forzati si applica solo a:

* `<A>` e `<AREA>` tag.
* Il tag deve avere un `HREF` attributo.
* Non `HREF` può iniziare con `#`, `about:`, o `javascript:`.
* L' `TARGET` attributo non deve essere impostato, o `TARGET` deve fare riferimento alla finestra corrente ( `_self`, `_top`, o al valore di `window.name`).

Valore predefinito = true

## Esempio 

`s.useForcedLinkTracking = false`

