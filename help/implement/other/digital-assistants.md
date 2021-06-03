---
title: Implementazione di Analytics per gli assistenti digitali
description: Implementa Adobe Analytics sugli assistenti digitali, ad esempio Amazon Alexa o Google Home.
exl-id: ebe29bc7-db34-4526-a3a5-43ed8704cfe9
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '1264'
ht-degree: 1%

---

# Implementazione di Analytics per gli assistenti digitali

Con i recenti progressi nel cloud computing, nell&#39;apprendimento automatico e nell&#39;elaborazione del linguaggio naturale, gli assistenti digitali stanno diventando parte della vita quotidiana. I consumatori cominciano a parlare con i loro dispositivi e si aspettano che capiscano e rispondano in modo simile all&#39;uomo. Man mano che queste piattaforme si rafforzano, i marchi possono presentare i loro servizi ai consumatori in questi stessi modi realistici e realistici. Ad esempio, i consumatori possono chiedere cose come:

* &quot;Alexa, chiedi alla mia macchina quando ha bisogno di un cambio di petrolio.&quot;
* &quot;Cortana, qual è il saldo del mio conto corrente?&quot;
* &quot;Siri, manda John $20 per cena ieri sera dalla mia app bancaria.&quot;

Questa pagina fornisce una panoramica del modo migliore di utilizzare Adobe Analytics per misurare e ottimizzare questi tipi di esperienze.

## Panoramica dell’architettura digitale

![Flusso di lavoro per l’Assistente digitale](assets/Digital-Assitants.png)

La maggior parte degli assistenti digitali segue oggi un&#39;architettura di alto livello simile:

1. **Dispositivo**: Esiste un dispositivo (come un Amazon Echo o un telefono) con un microfono che consente all&#39;utente di fare una domanda.
1. **Assistente** digitale: Quel dispositivo interagisce con il servizio che alimenta l&#39;assistente digitale. È lì che il discorso viene convertito in intenti comprensibili a macchina e i dettagli della richiesta vengono analizzati. Una volta compreso l’intento dell’utente, l’assistente digitale trasmette l’intento e i dettagli della richiesta all’app che gestisce la richiesta.
1. **&quot;App&quot;**: L’app può essere un’app sul telefono o un’app per voce. L’app risponde alla richiesta. Risponde all&#39;assistente digitale e l&#39;assistente digitale risponde quindi all&#39;utente.

## Dove implementare Analytics

Una delle posizioni migliori per implementare Analytics è nell’app. L’app riceve l’intento e i dettagli dall’assistente digitale, quindi l’app determina come rispondere.

Ci sono due volte durante una richiesta che possono essere utili per inviare dati ad Adobe Analytics.

1. Quando la richiesta viene inviata all’app.
1. Dopo che la risposta viene restituita dall&#39;app.

Se sei interessato a registrare l’evento con il cliente per un’ottimizzazione futura, invia una richiesta ad Adobe Analytics dopo la restituzione della risposta. Il contesto completo della richiesta e della risposta del sistema.

## Nuove installazioni

Per alcuni assistenti digitali, ottieni una notifica quando qualcuno installa la capacità, specialmente quando si tratta di autenticazione. Adobe consiglia di inviare un evento Install impostando la variabile di dati di contesto `a.InstallEvent=1`. Questa funzione non è disponibile per tutti gli assistenti digitali, ma è utile quando è presente per guardare la conservazione. Il codice di esempio seguente invia i valori Install event, Install Date e AppID nelle variabili di dati di contesto.

```text
GET
/b/ss/examplersid/1?vid=[UserID]&c.a.InstallEvent=1&c.a.InstallDate=2017-04-24&c.a.AppID=Spoofify1.0&c.OSType=Alexa&pageName=install
HTTP/1.1
Host:
<xref href="https://example.data.adobedc.net">
  example.data.adobedc.net
 Cache-Control: no-cache
</xref href="https:>
```

## Più assistenti o più app

È probabile che la tua organizzazione desideri app per più piattaforme. La best practice prevede l’inclusione di un ID app a ogni richiesta. Questa variabile può essere impostata nella variabile di dati di contesto `a.AppID` . Segui il formato di `[AppName] [BundleVersion]`, ad esempio, BigMac per Alexa 1.2:

```text
GET /b/ss/examplersid/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.a.Launches=1&c.Product=AmazonEcho&c.OSType=Alexa&pageName=install  HTTP/1.1
Host: example.data.adobedc.net
Cache-Control: no-cache
```

```text
GET /b/ss/examplersid/1?vid=[UserID]&c.a.AppID=Spoofify2.0&c.a.Launches=1&c.Product=GoogleHome&c.OSType=Android&pageName=install  HTTP/1.1
Host: example.data.adobedc.net
Cache-Control: no-cache
```

## Identificazione utente/visitatore

Adobe Analytics utilizza il [servizio Adobe Experience Cloud Identity](https://experienceleague.adobe.com/docs/id-service/using/home.html) per collegare le interazioni nel tempo alla stessa persona. La maggior parte degli assistenti digitali restituisce un valore `userID` che è possibile utilizzare per mantenere l’attività per utenti diversi. Nella maggior parte dei casi, questo valore è quello che puoi passare come identificatore univoco. Alcune piattaforme restituiscono un identificatore più lungo dei 100 caratteri consentiti. In questi casi, l’Adobe consiglia di aggiungere l’identificatore univoco a un valore a lunghezza fissa utilizzando un algoritmo di hash standard, ad esempio MD5 o Sha1.

L&#39;utilizzo del servizio ID fornisce il massimo valore quando mappi ECID su diversi dispositivi (ad esempio, da web a digitale). Se l&#39;app è un&#39;app mobile, usa gli SDK di Experience Platform così com&#39;è e invia l&#39;ID utente utilizzando il metodo `setCustomerID` . Tuttavia, se la tua app è un servizio, usa l’ID utente fornito dal servizio come ECID, nonché impostalo in `setCustomerID`.

```text
GET /b/ss/examplersid/1?vid=[UserID]&pageName=[intent]  HTTP/1.1
Host: example.data.adobedc.net
Cache-Control: no-cache
```

## Sessions

Poiché gli assistenti digitali sono conversazionali, spesso hanno il concetto di sessione. Ad esempio:

**Consumatore:**  &quot;Ok Google, chiama un taxi per me&quot;

**Google:**: &quot;Certo, a che ora vuoi?&quot;

**Consumatore:**  &quot;20:30&quot;

**Google:** &quot;Suona bene, il conducente sarà alle 8:30pm&quot;

Le sessioni sono importanti per mantenere il contesto e aiutare a raccogliere più dettagli per rendere più naturale l&#39;assistente digitale. Quando si implementa Analytics su una conversazione, è necessario eseguire due operazioni all’avvio di una nuova sessione:

1. **Consulta l’Audience Manager**: Ottieni i segmenti rilevanti di cui fa parte un utente in modo da poter personalizzare la risposta. (Ad esempio, questa persona attualmente può usufruire dello sconto multicanale).
2. **Invia una nuova sessione o un nuovo evento** di avvio: Quando invii la prima risposta ad Analytics, includi un evento di avvio. Di solito, questo può essere inviato impostando i dati contestuali di `a.LaunchEvent=1`.

```text
GET /b/ss/examplersid/1?vid=[UserID]&c.a.LaunchEvent=1&c.Intent=[intent]&pageName=[intent]  HTTP/1.1
Host: example.data.adobedc.net
Cache-Control: no-cache
```

## Intenti

Ciascuno degli assistenti digitali dispone di algoritmi che rilevano gli intenti e quindi trasmettono l’intento all’app in modo che l’app sappia cosa fare. Questi intenti sono una breve rappresentazione della richiesta.

Ad esempio, se un utente dice, &quot;Siri, invia John $20 per la cena ieri sera dalla mia app bancaria&quot;, l&#39;intento potrebbe essere qualcosa come *sendMoney*.

Inviando ciascuna di queste richieste come eVar, puoi eseguire rapporti di percorsi su ciascuno degli intenti per le app conversazionali. Assicurati che la tua app possa gestire le richieste anche senza un intento. L&#39;Adobe consiglia di passare &#39;Nessun intento specificato&#39; alla variabile di dati di contesto intento, anziché omettere la variabile .

```text
GET /b/ss/examplersid/1?vid=[UserID]&c.a.AppID=Penmo1.0&c.a.LaunchEvent=1&c.Intent=SendPayment&pageName=[intent]  HTTP/1.1
Host: example.sc.adobedc.net
Cache-Control: no-cache
```

oppure

```text
GET /b/ss/examplersid/1?vid=[UserID]&c.a.AppID=Penmo1.0&c.a.LaunchEvent=1&c.Intent=No_Intent_Specified&pageName=[intent]  HTTP/1.1
Host: example.data.adobedc.net
Cache-Control: no-cache
```

## Parametri/Slot/Entità

Oltre all’intento, gli assistenti digitali spesso dispongono di un set di coppie chiave/valore che forniscono dettagli sull’intento. Possono essere chiamati slot, entità o parametri. Ad esempio, &quot;Siri, Invia John $20 per cena ieri sera dalla mia app bancaria&quot; avrebbe i seguenti parametri:

* Who = John
* Importo = 20
* Perché = Cena

L’app in genere contiene un numero finito di questi valori. Per tenere traccia di questi valori in Analytics, inviali nelle variabili di dati di contesto e quindi mappare ciascuno dei parametri su un eVar.

```text
GET /b/ss/examplersid/1?vid=[UserID]&c.a.AppID=Penmo1.0=1&c.a.LaunchEvent=1&c.Intent=SendPayment&c.Amount=20.00&c.Reason=Dinner&c.ReceivingPerson=John&c.Intent=SendPayment&pageName=[intent]  HTTP/1.1
Host: example.data.adobedc.net
Cache-Control: no-cache
```

## Stati di errore

A volte l’assistente digitale fornisce all’app input che non sa come gestire. Per esempio, &quot;Siri, Invia a John 20 sacchi di carbone per cena ieri sera dalla mia app bancaria&quot;

Quando si verifica questa situazione, chiedi chiarimenti alla tua app. Inoltre, invia i dati ad Adobe che indica che l’app ha uno stato di errore insieme a un eVar che specifica quale tipo di errore si è verificato. Assicurati di includere gli errori in cui gli input non sono corretti ed errori in cui l&#39;app ha avuto un problema.

```text
GET /b/ss/examplersid/1?vid=[UserID]&c.a.AppID=Penmo1.0&c.Error=1&c.ErrorName=InvalidCurrency&pageName=[intent]  HTTP/1.1
Host: example.data.adobedc.net
Cache-Control: no-cache
```

## Funzionalità del dispositivo

Anche se la maggior parte delle piattaforme non espongono il dispositivo a cui l&#39;utente ha parlato, espongono le funzionalità del dispositivo. Ad esempio, Audio, Schermo, Video, ecc. Queste informazioni sono utili perché definiscono i tipi di contenuto che possono essere utilizzati durante l’interazione con gli utenti. Quando si misurano le funzionalità dei dispositivi, è consigliabile concatenarle (in ordine alfabetico).

Esempio: `":Audio:Camera:Screen:Video:"`

I due punti iniziali e finali sono utili per la creazione dei segmenti. Ad esempio, mostra tutti gli hit con funzionalità `:Audio:`.

* [Funzionalità ](https://developer.amazon.com/public/solutions/alexa/alexa-skills-kit/docs/alexa-skills-kit-interface-reference) di Amazon con Amazon Alexa
* [Funzionalità ](https://developers.google.com/actions/assistant/surface-capabilities) di Google tramite azioni su Google

## Esempi

| Persona | Risposta del dispositivo | Azione/Intento | richiesta GET |
|---|---|---|---|
| Installa Spoofide | Nessuna risposta | Installa | `GET /b/ss/examplersid/1?vid=[UserID]&c.a.InstallEvent=1&c.a.InstallDate=[currentDate]&c.a.AppID=Spoofify1.0&c.OSType=Alexa&c.Intent=Install&pageName=Install  HTTP/1.1`<br>`Host: example.data.adobedc.net`<br>`Cache-Control: no-cache` |
| Riproduci Spoofide | &quot;Ok, giocare a Spoofify&quot; | Play | `GET /b/ss/examplersid/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.a.LaunchEvent=1&c.Intent=Play&pageName=PlayApp  HTTP/1.1`<br>`Host: example.data.adobedc.net`<br>`Cache-Control: no-cache` |
| Cambia canzone | &quot;Ok, che canzone vuoi?&quot; | ChangeSong | `GET /b/ss/examplersid/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.Intent=ChangeSong&pageName= Ask%20For%20Song  HTTP/1.1`<br>`Host: example.data.adobedc.net`<br>`Cache-Control: no-cache` |
| Gioca &quot;Baby Shark&quot; | &quot;Ok, giocando a &#39;Baby Shark&#39; di PinkFong&quot; | ChangeSong | `GET /b/ss/examplersid/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.Intent=ChangeSong&pageName=Action%20Play%20Song&c.SongID=[012345]  HTTP/1.1`<br>`Host: example.data.adobedc.net`<br>`Cache-Control: no-cache` |
| Modificare la playlist | &quot;Ok, quale playlist vuoi?&quot; | ChangePlaylist | `GET /b/ss/examplersid/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.Intent=ChangePlaylist&pageName=Ask%20For%20Playlist  HTTP/1.1`<br>`Host: example.data.adobedc.net`<br>`Cache-Control: no-cache` |
| Riproduci la mia playlist di brani preferiti | &quot;Ok, riproduzione della playlist dei tuoi brani preferiti&quot; | ChangePlaylist | `GET /b/ss/examplersid/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.Intent=ChangePlaylist&pageName=Action%20Play%20Playlist&c.Playlist=My%20Favorite%20Songs  HTTP/1.1`<br>`Host: example.data.adobedc.net`<br>`Cache-Control: no-cache` |
| Disattiva musica | Nessuna risposta, la musica si spegne | Disattivato | `GET /b/ss/examplersid/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.Intent=Off&pageName=Music%20Off  HTTP/1.1`<br>`Host: example.data.adobedc.net`<br>`Cache-Control: no-cache` |
