---
title: Implementazione di Analytics per gli assistenti digitali
description: Implementa  Adobe Analytics sugli assistenti digitali, ad esempio  Amazon  Alexa o Google Home.
translation-type: tm+mt
source-git-commit: 09b453c1b4cd8555c5d1718759003945f5c230c5
workflow-type: tm+mt
source-wordcount: '1266'
ht-degree: 1%

---


# Implementazione di Analytics per gli assistenti digitali

Con i recenti progressi nel cloud computing, nell&#39;apprendimento automatico e nell&#39;elaborazione del linguaggio naturale, gli assistenti digitali stanno diventando parte della vita quotidiana. I consumatori stanno iniziando a parlare con i loro dispositivi e si aspettano che capiscano e rispondano in modi simili a quelli umani. Man mano che queste piattaforme diventano più affermate, i marchi possono presentare i loro servizi ai consumatori in questi stessi modi realistici e realistici. Ad esempio, i consumatori possono chiedere cose come:

* &quot; Alexa, chiedi alla mia macchina quando ha bisogno di un cambio di olio.&quot;
* &quot;Cortana, qual è il saldo del mio conto corrente?&quot;
* &quot;Siri, manda John $20 per cena ieri sera dalla mia app bancaria.&quot;

Questa pagina fornisce una panoramica di come utilizzare al meglio  Adobe Analytics per misurare e ottimizzare questi tipi di esperienze.

## Panoramica sull&#39;architettura dell&#39;esperienza digitale

![Flusso di lavoro con Assistente digitale](assets/Digital-Assitants.png)

La maggior parte degli assistenti digitali segue oggi una simile architettura di alto livello:

1. **Dispositivo**: Esiste un dispositivo (come un Amazon Echo  o un telefono) con un microfono che consente all&#39;utente di porre una domanda.
1. **Assistente** digitale: Quel dispositivo interagisce con il servizio che alimenta l&#39;assistente digitale. È dove il discorso è convertito in intenti comprensibili a macchina e i dettagli della richiesta sono analizzati. Una volta compreso l&#39;intento dell&#39;utente, l&#39;assistente digitale trasmette l&#39;intento e i dettagli della richiesta all&#39;app che gestisce la richiesta.
1. **&quot;App&quot;**: L&#39;app può essere un&#39;app per telefono o un&#39;app per voce. L&#39;app risponde alla richiesta. Risponde all&#39;assistente digitale e l&#39;assistente digitale risponde all&#39;utente.

## Dove implementare Analytics

Uno dei punti migliori per implementare Analytics è l&#39;app. L&#39;app riceve l&#39;intento e i dettagli dall&#39;assistente digitale, quindi l&#39;app determina come rispondere.

Durante una richiesta sono presenti due volte che possono essere utili per inviare dati a  Adobe Analytics.

1. Quando la richiesta viene inviata all&#39;app.
1. Dopo che la risposta viene restituita dall&#39;app.

Se siete interessati a registrare ciò che è successo con il cliente per un&#39;ottimizzazione futura, inviate una richiesta a  Adobe Analytics dopo la restituzione della risposta. Il contesto completo della richiesta e della risposta del sistema.

## Nuove installazioni

Per alcuni assistenti digitali, si riceve una notifica quando un utente installa la capacità, soprattutto quando è coinvolta l&#39;autenticazione.  Adobe consiglia di inviare un evento Install impostando la variabile di dati di contesto `a.InstallEvent=1`. Questa funzione non è disponibile su tutti gli assistenti digitali, ma è utile quando è presente per guardare la conservazione. L’esempio di codice seguente invia i valori Install event, Install Date e AppID alle variabili di dati contestuali.

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

È probabile che l&#39;organizzazione desideri app per più piattaforme. La procedura ottimale consiste nell&#39;includere un ID app a ogni richiesta. Questa variabile può essere impostata nella variabile di dati di `a.AppID` contesto. Seguite il formato di `[AppName] [BundleVersion]`, ad esempio BigMac per  Alexa 1.2:

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

 Adobe Analytics utilizza [Adobe Experience Cloud Identity Service](https://docs.adobe.com/content/help/it-IT/id-service/using/home.html) per collegare le interazioni nel tempo alla stessa persona. La maggior parte degli assistenti digitali restituisce un `userID` valore che è possibile utilizzare per mantenere l&#39;attività per utenti diversi. Nella maggior parte dei casi, questo valore è quello che potete trasmettere come identificatore univoco. Alcune piattaforme restituiscono un identificatore che supera i 100 caratteri consentiti. In questi casi,  Adobe consiglia di applicare l’hash dell’identificatore univoco a un valore di lunghezza fissa utilizzando un algoritmo di hash standard, ad esempio MD5 o Sha1.

L’utilizzo del servizio ID fornisce il massimo valore quando si esegue la mappatura di ECID su diversi dispositivi (ad esempio, Web-assistente digitale). Se l’app è un’app mobile, usa gli SDK del Experience Platform  così com’è e invia l’ID utente utilizzando il `setCustomerID` metodo . Tuttavia, se l’app è un servizio, utilizzate l’ID utente fornito dal servizio come ECID, nonché impostatelo in `setCustomerID`.

```text
GET /b/ss/examplersid/1?vid=[UserID]&pageName=[intent]  HTTP/1.1
Host: example.data.adobedc.net
Cache-Control: no-cache
```

## Sessions

Poiché gli assistenti digitali sono conversazionali, spesso hanno il concetto di sessione. Ad esempio:

**Consumatore:** &quot;Ok Google, chiama un taxi per me&quot;

**Google:**: &quot;Certo, a che ora vuoi?&quot;

**Consumatore:** &quot;8:30 pm&quot;

**Google:** &quot;Suona bene, il driver sarà entro le 8:30 pm&quot;

Le sessioni sono importanti per mantenere il contesto e aiutare a raccogliere più dettagli per rendere più naturale l&#39;assistente digitale. Quando si implementa Analytics in una conversazione, all&#39;avvio di una nuova sessione è necessario eseguire due operazioni:

1. **Raggiungi  Audience Manager**: Ottenete i segmenti rilevanti di cui l’utente fa parte in modo da poter personalizzare la risposta. Ad esempio, questa persona attualmente si qualifica per lo sconto multicanale.
2. **Invia in una nuova sessione o in un nuovo evento** di avvio: Quando inviate la prima risposta ad Analytics, includete un evento di avvio. Solitamente, questo può essere inviato impostando i dati contestuali di `a.LaunchEvent=1`.

```text
GET /b/ss/examplersid/1?vid=[UserID]&c.a.LaunchEvent=1&c.Intent=[intent]&pageName=[intent]  HTTP/1.1
Host: example.data.adobedc.net
Cache-Control: no-cache
```

## Intenti

Ciascuno degli assistenti digitali dispone di algoritmi che rilevano gli intenti e quindi trasmettono l&#39;intento all&#39;&quot;App&quot; in modo che l&#39;app sappia cosa fare. Questi intenti sono una breve rappresentazione della richiesta.

Ad esempio, se un utente dice, &quot;Siri, Invia a John $20 per cena ieri sera dalla mia app bancaria,&quot; l&#39;intento potrebbe essere qualcosa come *sendMoney*.

Mediante l&#39;invio di ciascuna di queste richieste come eVar , puoi eseguire report di percorsi su ciascuno degli intenti per le app di conversazione. Assicurati che la tua app possa gestire le richieste anche senza un intento.  Adobe consiglia di passare &#39;Nessun intento specificato&#39; alla variabile di dati di contesto intento, anziché omettere la variabile.

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

Oltre all&#39;intento, gli assistenti digitali spesso dispongono di una serie di coppie chiave/valore che forniscono dettagli sull&#39;intento. Possono essere denominati slot, entità o parametri. Ad esempio, &quot;Siri, Send John $20 per cena ieri sera dalla mia app bancaria&quot; avrebbe i seguenti parametri:

* Who = John
* Importo = 20
* Perché = Cena

L&#39;app presenta in genere un numero limitato di questi valori. Per tenere traccia di questi valori in Analytics, inviali nelle variabili di dati di contesto e mappatura di ciascuno dei parametri su un eVar .

```text
GET /b/ss/examplersid/1?vid=[UserID]&c.a.AppID=Penmo1.0=1&c.a.LaunchEvent=1&c.Intent=SendPayment&c.Amount=20.00&c.Reason=Dinner&c.ReceivingPerson=John&c.Intent=SendPayment&pageName=[intent]  HTTP/1.1
Host: example.data.adobedc.net
Cache-Control: no-cache
```

## Stati di errore

A volte l&#39;assistente digitale fornisce all&#39;app input che non sa come gestire. Per esempio, &quot;Siri, Invia a John 20 sacchi di carbone per cena ieri sera dalla mia app bancaria&quot;

Quando questa situazione si verifica, chiedete chiarimenti alla vostra app. Inoltre, invia dati a  Adobe che indica che l&#39;app ha uno stato di errore insieme a un eVar  che specifica quale tipo di errore si è verificato. Assicuratevi di includere errori in cui gli input non sono corretti ed errori in cui l&#39;app ha avuto un problema.

```text
GET /b/ss/examplersid/1?vid=[UserID]&c.a.AppID=Penmo1.0&c.Error=1&c.ErrorName=InvalidCurrency&pageName=[intent]  HTTP/1.1
Host: example.data.adobedc.net
Cache-Control: no-cache
```

## Funzionalità del dispositivo

Anche se la maggior parte delle piattaforme non espone il dispositivo a cui l&#39;utente ha parlato, espone le capacità del dispositivo. Ad esempio, Audio, Schermo, Video, ecc. Questa informazione è utile perché definisce i tipi di contenuto che possono essere utilizzati per interagire con gli utenti. Per misurare le funzionalità dei dispositivi, è consigliabile concatenarle (in ordine alfabetico).

Esempio: `":Audio:Camera:Screen:Video:"`

I punti iniziali e finali sono utili per la creazione di segmenti. Ad esempio, mostra tutti gli hit con `:Audio:` funzionalità.

* [funzionalità](https://developer.amazon.com/public/solutions/alexa/alexa-skills-kit/docs/alexa-skills-kit-interface-reference) Amazon utilizzando  Amazon  Alexa
* [Google Capabilities](https://developers.google.com/actions/assistant/surface-capabilities) tramite le azioni su Google

## Esempi

| Persona | Risposta del dispositivo | Azione/Intento | GET richiesta |
|---|---|---|---|
| Installa spoofide | Nessuna risposta | Installazione | `GET /b/ss/examplersid/1?vid=[UserID]&c.a.InstallEvent=1&c.a.InstallDate=[currentDate]&c.a.AppID=Spoofify1.0&c.OSType=Alexa&c.Intent=Install&pageName=Install  HTTP/1.1`<br>`Host: example.data.adobedc.net`<br>`Cache-Control: no-cache` |
| Riproduci spoofide | &quot;Ok, giocare a Spoofify&quot; | Play | `GET /b/ss/examplersid/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.a.LaunchEvent=1&c.Intent=Play&pageName=PlayApp  HTTP/1.1`<br>`Host: example.data.adobedc.net`<br>`Cache-Control: no-cache` |
| Cambia canzone | &quot;Ok, che canzone vuoi?&quot; | ChangeSong | `GET /b/ss/examplersid/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.Intent=ChangeSong&pageName= Ask%20For%20Song  HTTP/1.1`<br>`Host: example.data.adobedc.net`<br>`Cache-Control: no-cache` |
| Gioca &quot;Baby Shark&quot; | &quot;Ok, suonando &#39;Baby Shark&#39; di PinkFong&quot; | ChangeSong | `GET /b/ss/examplersid/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.Intent=ChangeSong&pageName=Action%20Play%20Song&c.SongID=[012345]  HTTP/1.1`<br>`Host: example.data.adobedc.net`<br>`Cache-Control: no-cache` |
| Cambia playlist | &quot;Ok, quale playlist vuoi?&quot; | ChangePlaylist | `GET /b/ss/examplersid/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.Intent=ChangePlaylist&pageName=Ask%20For%20Playlist  HTTP/1.1`<br>`Host: example.data.adobedc.net`<br>`Cache-Control: no-cache` |
| Riproduci la playlist delle mie canzoni preferite | &quot;Ok, suonate la playlist dei vostri brani preferiti&quot; | ChangePlaylist | `GET /b/ss/examplersid/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.Intent=ChangePlaylist&pageName=Action%20Play%20Playlist&c.Playlist=My%20Favorite%20Songs  HTTP/1.1`<br>`Host: example.data.adobedc.net`<br>`Cache-Control: no-cache` |
| Disattivazione della musica | Nessuna risposta, la musica si spegne | Disattivato | `GET /b/ss/examplersid/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.Intent=Off&pageName=Music%20Off  HTTP/1.1`<br>`Host: example.data.adobedc.net`<br>`Cache-Control: no-cache` |
