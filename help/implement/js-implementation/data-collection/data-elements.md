---
description: È possibile acquisire i valori degli elementi del modulo, come ad esempio gli elementi di un pulsante di scelta e di una casella di controllo, nei rapporti. Questo consente di analizzare le scelte più comuni nei moduli online.
keywords: Implementazione di Analytics
seo-description: È possibile acquisire i valori degli elementi del modulo, come ad esempio gli elementi di un pulsante di scelta e di una casella di controllo, nei rapporti. Questo consente di analizzare le scelte più comuni nei moduli online.
seo-title: Raccogliere dati dagli elementi modulo
solution: Analytics
title: Raccogliere dati dagli elementi modulo
topic: Sviluppatore e implementazione
uuid: e0c13b96-e1ca-4744-a912-60ca2b8f25c3
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Raccogliere dati dagli elementi modulo

È possibile acquisire i valori degli elementi del modulo, come ad esempio gli elementi di un pulsante di scelta e di una casella di controllo, nei rapporti. Questo consente di analizzare le scelte più comuni nei moduli online.

Ad esempio, se un pulsante di scelta consentiva all'utente di specificare il suo genere musicale preferito (come rock, rap, classico o jazz), potreste acquisire la risposta in una variabile per determinare le preferenze musicali complessive della base di utenti.

Il modo migliore per acquisire questi dati dipende dalla modalità di elaborazione dei moduli. Dipende anche dal fatto che le selezioni del modulo che si desidera acquisire siano disponibili nella stringa di query sulla pagina successiva all'invio del modulo. Esempi in questo articolo sono riportati in PHP. Tuttavia, è possibile adattare questi concetti a un'altra lingua, a seconda dell'ambiente del server.

Queste informazioni sono adatte agli utenti avanzati che hanno una buona conoscenza sia del reporting che dell'implementazione. Non tentare di apportare modifiche alla tua implementazione senza una conoscenza completa delle sue conseguenze. Se hai bisogno di modifiche all'implementazione, contatta l'Account Manager della tua organizzazione.

## GET, metodo {#section_7A2B35822BFF4F6EB57940B31AE6303A}

Se il modulo utilizza un [!UICONTROL GET] metodo per inviare i dati, è possibile accedere ai dati desiderati nella stringa di query dell'URL nella pagina che segue l'invio del modulo. È possibile utilizzare il [!UICONTROL getQueryParam] plug-in per acquisire automaticamente questi dati dalla stringa di query e inserirla nella variabile scelta.

## Metodo POST {#section_56715C30EF374BA7AA12B946B50E4A9A}

Se il modulo utilizza un [!UICONTROL POST] metodo di invio dei dati (più comune), i risultati per ciascun elemento modulo specifico sono disponibili nel modulo [!UICONTROL $_POST superglobal]. Per acquisire questo elemento in una variabile, è necessario determinare il nome dell’elemento del modulo in questione. Utilizzando l’esempio di genere musicale precedentemente menzionato, parte dell’elemento in questione ha l’aspetto seguente:

```
<input type="radio" name="music_genre" value="rock">
```

Questo pulsante di scelta appartiene all'elemento "music_genre". Potete quindi accedere al valore selezionato dall'utente utilizzando $_POST['music_genre']. Questa variabile può essere scritta sulla pagina dopo l’invio del modulo:

```js
s.eVar1="<?=$_POST['music_genre'];?>"
```

La [!UICONTROL eVar1] variabile riceve una copia del valore inviato al server tramite il modulo, come specificato nella proprietà value=.

Per ulteriori informazioni su questo metodo di implementazione personalizzato, contatta l’Account Manager della tua organizzazione. Possono organizzare una riunione con uno dei nostri Consulenti per l'implementazione per fornire l'aiuto necessario.
