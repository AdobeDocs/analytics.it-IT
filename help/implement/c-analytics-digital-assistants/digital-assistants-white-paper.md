---
description: nulle
seo-description: nulle
seo-title: Implementazione di Analytics per gli assistenti digitali
title: Implementazione di Analytics per gli assistenti digitali
uuid: c61e6a1a-ec08-4936-9053-5f57223f57ff
translation-type: tm+mt
source-git-commit: b7a92c7b7305c5456e6764b4329c51ad13f2609e

---


# Implementazione di Analytics per gli assistenti digitali

<!-- 
https://wiki.corp.adobe.com/display/mobileanalytics/Analytics+for+Digital+Assistants+Whitepaper
https://marketing.adobe.com/resources/help/en_US/sc/implement/digital-assistants-white-paper.html
Ticket: https://jira.corp.adobe.com/browse/AN-157750
-->

Con i recenti progressi nel cloud computing, nell'apprendimento automatico e nell'elaborazione del linguaggio naturale, gli assistenti digitali stanno diventando parte della vita quotidiana. I consumatori stanno iniziando a parlare con i loro dispositivi e si aspettano che capiscano e rispondano in modi simili a quelli umani. Man mano che queste piattaforme diventano più affermate, i marchi possono presentare i loro servizi ai consumatori in questi stessi modi realistici e realistici. Ad esempio, i consumatori possono chiedere cose come:

* "Alexa, chiedi alla mia macchina quando ha bisogno di un cambio di petrolio."
* "Cortana, qual è il saldo del mio conto corrente?"
* "Siri, manda John $20 per cena ieri sera dalla mia app bancaria."

Questa pagina fornisce una panoramica di come utilizzare al meglio Adobe Analytics per misurare e ottimizzare questi tipi di esperienze.

## Panoramica sull'architettura dell'esperienza digitale

![](assets/Digital-Assitants.png)

La maggior parte degli assistenti digitali segue oggi una simile architettura di alto livello:

1. **** Dispositivo: Esiste un dispositivo (come Amazon Echo o un telefono) con un microfono che consente all'utente di porre una domanda.
1. **** Assistente digitale: Quel dispositivo interagisce con il servizio che alimenta l'assistente digitale. È dove il discorso è convertito in intenti comprensibili a macchina e i dettagli della richiesta sono analizzati. Una volta compreso l'intento dell'utente, l'assistente digitale trasmette l'intento e i dettagli della richiesta all'app che gestisce la richiesta.
1. **** "App": L'app può essere un'app per telefono o un'app per voce. L'app risponde alla richiesta. Risponde all'assistente digitale e l'assistente digitale risponde all'utente.

## Dove implementare Analytics

Uno dei punti migliori per implementare Analytics è l'app. L'app riceve l'intento e i dettagli dall'assistente digitale, quindi l'app determina come rispondere.

Durante una richiesta sono presenti due volte che possono essere utili per inviare dati ad Adobe Analytics.

1. Quando la richiesta viene inviata all'app.
1. Dopo che la risposta viene restituita dall'app.

Se sei interessato a registrare ciò che è successo al cliente per un'ottimizzazione futura, invia una richiesta ad Adobe Analytics dopo la restituzione della risposta. Il contesto completo della richiesta e della risposta del sistema.

## Nuove installazioni

Per alcuni assistenti digitali, si riceve una notifica quando un utente installa la capacità, soprattutto quando è coinvolta l'autenticazione. Adobe consiglia di inviare un evento Install impostando la variabile di dati contestuali `a.InstallEvent=1`. Questa funzione non è disponibile su tutti gli assistenti digitali, ma è utile quando è presente per guardare la conservazione. L’esempio di codice seguente invia i valori Install event, Install Date e AppID alle variabili di dati contestuali.

```text
GET
/b/ss/[rsid]/1?vid=[UserID]&c.a.InstallEvent=1&c.a.InstallDate=2017-04-24&c.a.AppID=Spoofify1.0&c.OSType=Alexa&pageName=install
HTTP/1.1
Host:
<xref href="https://sc.omtrdc.net">
  sc.omtrdc.net
 Cache-Control: no-cache
</xref href="https:>
```

## Più assistenti o più app

È probabile che l'organizzazione desideri app per più piattaforme. La procedura ottimale consiste nell'includere un ID app a ogni richiesta. Questa variabile può essere impostata nella variabile di dati di `a.AppID` contesto. Seguite il formato di `[AppName] [BundleVersion]`, ad esempio BigMac per Alexa 1.2:

```text
GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.a.Launches=1&c.Product=AmazonEcho&c.OSType=Alexa&pageName=install  HTTP/1.1
Host: example.sc.omtrdc.net
Cache-Control: no-cache
```

```text
GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Spoofify2.0&c.a.Launches=1&c.Product=GoogleHome&c.OSType=Android&pageName=install  HTTP/1.1
Host: example.sc.omtrdc.net
Cache-Control: no-cache
```

## Identificazione utente/visitatore

Adobe Analytics utilizza il servizio [](https://docs.adobe.com/content/help/en/id-service/using/home.html) Adobe Experience Cloud Identity per collegare le interazioni nel tempo alla stessa persona. La maggior parte degli assistenti digitali restituisce un `userID` valore che è possibile utilizzare per mantenere l'attività per utenti diversi. Nella maggior parte dei casi, questo valore è quello che potete trasmettere come identificatore univoco. Alcune piattaforme restituiscono un identificatore che supera i 100 caratteri consentiti. In questi casi, Adobe consiglia di applicare l’hash dell’identificatore univoco a un valore di lunghezza fissa utilizzando un algoritmo di hash standard, ad esempio MD5 o Sha1.

L’utilizzo del servizio ID fornisce il massimo valore quando si esegue la mappatura di ECID su diversi dispositivi (ad esempio, Web-assistente digitale). Se l’app è un’app mobile, usa gli SDK della piattaforma Experience così com’è e invia l’ID utente utilizzando il `setCustomerID` metodo . Tuttavia, se l’app è un servizio, utilizzate l’ID utente fornito dal servizio come ECID, nonché impostatelo in `setCustomerID`.

```text
GET /b/ss/[rsid]/1?vid=[UserID]&pageName=[intent]  HTTP/1.1
Host: example.sc.omtrdc.net
Cache-Control: no-cache
```

## Sessioni

Poiché gli assistenti digitali sono conversazionali, spesso hanno il concetto di sessione. Ad esempio:

**** Consumatore: "Ok Google, chiama un taxi per me"

**Google:**: "Certo, a che ora vuoi?"

**** Consumatore: "8:30 pm"

**** Google: "Suona bene, il driver sarà entro le 8:30 pm"

Le sessioni sono importanti per mantenere il contesto e aiutare a raccogliere più dettagli per rendere più naturale l'assistente digitale. Quando si implementa Analytics in una conversazione, all'avvio di una nuova sessione è necessario eseguire due operazioni:

1. **** Rivolgiti ad Audience Manager: Ottenete i segmenti rilevanti di cui l’utente fa parte per personalizzare la risposta. Ad esempio, questa persona attualmente si qualifica per lo sconto multicanale.
2. **** Invia in una nuova sessione o in un nuovo evento di avvio: Quando inviate la prima risposta ad Analytics, includete un evento di avvio. Solitamente, questo può essere inviato impostando i dati contestuali di `a.LaunchEvent=1`.

```text
GET /b/ss/[rsid]/1?vid=[UserID]&c.a.LaunchEvent=1&c.Intent=[intent]&pageName=[intent]  HTTP/1.1
Host: sc.omtrdc.net
Cache-Control: no-cache
```

## Intenti

Ciascuno degli assistenti digitali dispone di algoritmi che rilevano gli intenti e quindi trasmettono l'intento all'"App" in modo che l'app sappia cosa fare. Questi intenti sono una breve rappresentazione della richiesta.

Ad esempio, se un utente dice, "Siri, Invia a John $20 per cena ieri sera dalla mia app bancaria," l'intento potrebbe essere qualcosa come *sendMoney*.

Inviando ciascuna di queste richieste come eVar, puoi eseguire rapporti di percorsi su ogni intento per le app di conversazione. Assicurati che la tua app possa gestire le richieste anche senza un intento. Adobe consiglia di passare 'Nessun intento specificato' alla variabile di dati contestuali dell'intento, invece di omettere la variabile.

```text
GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Penmo1.0&c.a.LaunchEvent=1&c.Intent=SendPayment&pageName=[intent]  HTTP/1.1
Host: example.sc.omtrdc.net
Cache-Control: no-cache
```

 oppure 

```text
GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Penmo1.0&c.a.LaunchEvent=1&c.Intent=No_Intent_Specified&pageName=[intent]  HTTP/1.1
Host: sc.omtrdc.net
Cache-Control: no-cache
```

## Parametri/Slot/Entità

Oltre all'intento, gli assistenti digitali spesso dispongono di una serie di coppie chiave/valore che forniscono dettagli sull'intento. Possono essere denominati slot, entità o parametri. Ad esempio, "Siri, Send John $20 per cena ieri sera dalla mia app bancaria" avrebbe i seguenti parametri:

* Who = John
* Importo = 20
* Perché = Cena

L'app presenta in genere un numero limitato di questi valori. Per tenere traccia di questi valori in Analytics, inviali nelle variabili di dati di contesto e mappatura di ciascuno dei parametri su una eVar.

```text
GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Penmo1.0=1&c.a.LaunchEvent=1&c.Intent=SendPayment&c.Amount=20.00&c.Reason=Dinner&c.ReceivingPerson=John&c.Intent=SendPayment&pageName=[intent]  HTTP/1.1
Host: example.sc.omtrdc.net
Cache-Control: no-cache
```

## Stati di errore

A volte l'assistente digitale fornisce all'app input che non sa come gestire. Per esempio, "Siri, Invia a John 20 sacchi di carbone per cena ieri sera dalla mia app bancaria"

Quando questa situazione si verifica, chiedete chiarimenti alla vostra app. Inoltre, invia dati ad Adobe che indicano che l'app ha uno stato di errore insieme a una eVar che specifica quale tipo di errore si è verificato. Assicuratevi di includere errori in cui gli input non sono corretti ed errori in cui l'app ha avuto un problema.

```text
GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Penmo1.0&c.Error=1&c.ErrorName=InvalidCurrency&pageName=[intent]  HTTP/1.1
Host: example.sc.omtrdc.net
Cache-Control: no-cache
```

## Funzionalità dispositivo

Anche se la maggior parte delle piattaforme non espone il dispositivo a cui l'utente ha parlato, espone le capacità del dispositivo. Ad esempio, Audio, Schermo, Video, ecc. Questa informazione è utile perché definisce i tipi di contenuto che possono essere utilizzati per interagire con gli utenti. Per misurare le funzionalità dei dispositivi, è consigliabile concatenarle (in ordine alfabetico).

Esempio: `":Audio:Camera:Screen:Video:"`

I punti iniziali e finali sono utili per la creazione di segmenti. Ad esempio, mostra tutti gli hit con `:Audio:` funzionalità.

* [Funzionalità](https://developer.amazon.com/public/solutions/alexa/alexa-skills-kit/docs/alexa-skills-kit-interface-reference) Amazon con Amazon Alexa
* [Google Capabilities](https://developers.google.com/actions/assistant/surface-capabilities) tramite le azioni su Google

## Esempi

| Persona | Risposta del dispositivo | Azione/Intento | GET, richiesta |
| --- | --- | --- | --- | ---|
| Installa spoofide | Nessuna risposta | Installazione | `GET /b/ss/[rsid]/1?vid=[UserID]&c.a.InstallEvent=1&c.a.InstallDate=[currentDate]&c.a.AppID=Spoofify1.0&c.OSType=Alexa&c.Intent=Install&pageName=Install  HTTP/1.1`<br>`Host: example.sc.omtrdc.net`<br>`Cache-Control: no-cache` |
| Riproduci spoofide | "Ok, giocare a Spoofify" | Play | `GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.a.LaunchEvent=1&c.Intent=Play&pageName=PlayApp  HTTP/1.1`<br>`Host: example.sc.omtrdc.net`<br>`Cache-Control: no-cache` |
| Cambia canzone | "Ok, che canzone vuoi?" | ChangeSong | `GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.Intent=ChangeSong&pageName= Ask%20For%20Song  HTTP/1.1`<br>`Host: example.sc.omtrdc.net`<br>`Cache-Control: no-cache` |
| Gioca "Baby Shark" | "Ok, giocando 'Baby Shark' di PinkFong" | ChangeSong | `GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.Intent=ChangeSong&pageName=Action%20Play%20Song&c.SongID=[012345]  HTTP/1.1`<br>`Host: example.sc.omtrdc.net`<br>`Cache-Control: no-cache` |
| Cambia playlist | "Ok, quale playlist vuoi?" | ChangePlaylist | `GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.Intent=ChangePlaylist&pageName=Ask%20For%20Playlist  HTTP/1.1`<br>`Host: example.sc.omtrdc.net`<br>`Cache-Control: no-cache` |
| Riproduci la playlist delle mie canzoni preferite | "Ok, suonate la playlist dei vostri brani preferiti" | ChangePlaylist | `GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.Intent=ChangePlaylist&pageName=Action%20Play%20Playlist&c.Playlist=My%20Favorite%20Songs  HTTP/1.1`<br>`Host: example.sc.omtrdc.net`<br>`Cache-Control: no-cache` |
| Spegni musica | Nessuna risposta, la musica si spegne | Disattivato | `GET /b/ss/[rsid]/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.Intent=Off&pageName=Music%20Off  HTTP/1.1`<br>`Host: example.sc.omtrdc.net`<br>`Cache-Control: no-cache` |
