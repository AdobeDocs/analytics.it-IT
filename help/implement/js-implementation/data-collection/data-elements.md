---
description: È possibile acquisire i valori degli elementi modulo, ad esempio pulsanti di scelta e caselle di controllo, nei rapporti. Questo consente di analizzare le opzioni più comuni nei moduli online.
keywords: Implementazione di Analytics
seo-description: È possibile acquisire i valori degli elementi modulo, ad esempio pulsanti di scelta e caselle di controllo, nei rapporti. Questo consente di analizzare le opzioni più comuni nei moduli online.
seo-title: Raccogliere dati dagli elementi modulo
solution: Analytics
title: Raccogliere dati dagli elementi modulo
topic: Sviluppatore e implementazione
uuid: e 0 c 13 b 96-e 1 ca -4744-a 912-60 ca 2 b 8 f 25 c 3
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Raccogliere dati dagli elementi modulo

È possibile acquisire i valori degli elementi modulo, ad esempio pulsanti di scelta e caselle di controllo, nei rapporti. Questo consente di analizzare le opzioni più comuni nei moduli online.

Ad esempio, se disponete di un pulsante di scelta che consente all'utente di specificare il genere preferito di musica (come rock, rap, classic o jazz), potreste acquisire questa risposta in una variabile per determinare le preferenze musicali generali della base utente.

Il modo migliore per acquisire questi dati dipende dalla modalità di elaborazione dei moduli. Dipende inoltre dal fatto che le selezioni del modulo da acquisire siano disponibili nella stringa query sulla pagina dopo l'invio del modulo. Esempi in questo articolo sono forniti in PHP. Tuttavia, potete adattare questi concetti a un'altra lingua, a seconda dell'ambiente server.

Queste informazioni sono adatte agli utenti avanzati che sono ben orientati sia in reporting che nell'implementazione. Non tentare di apportare modifiche alla vostra implementazione senza conoscerne le conseguenze. Se avete bisogno di modifiche di implementazione, contattate l'Account Manager della vostra organizzazione.

## GET Method {#section_7A2B35822BFF4F6EB57940B31AE6303A}

If your form uses a [!UICONTROL GET] method to submit data, you have access to the desired data in the query string of the URL on the page following form submission. You can use the [!UICONTROL getQueryParam] plug-in to capture this data out of the query string automatically and place it into the variable of your choosing.

## POST Method {#section_56715C30EF374BA7AA12B946B50E4A9A}

If your form uses a [!UICONTROL POST] method to submit data (which is more common), you have the results for each specific form element available to you in the [!UICONTROL $_POST superglobal]. Per acquisirlo in una variabile, determinare il nome dell'elemento modulo in questione. Utilizzando l'esempio musicale citato prima, parte dell'elemento modulo in questione sarà simile a quella dell'esempio:

```
<input type="radio" name="music_genre" value="rock">
```

Questo pulsante di scelta appartiene all'elemento "music_ genre". You then have access to the user's selected value by using $_POST['music_genre']. Questo può essere scritto in una variabile sulla pagina dopo l'invio del modulo:

```js
s.eVar1="<?=$_POST['music_genre'];?>"
```

The [!UICONTROL eVar1] variable receives a copy of whatever value was submitted to your server through the form, as specified in the value= property.

Se ti servono ulteriori informazioni su questo metodo di implementazione personalizzato, contatta l'Account Manager della tua organizzazione. Possono disporre di una riunione con uno dei nostri consulenti di implementazione per fornire l'aiuto desiderato.
