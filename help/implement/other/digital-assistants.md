---
title: Implementazione di Analytics per gli assistenti digitali
description: Implementare Adobe Analytics sugli assistenti digitali, ad esempio Amazon Alexa o Google Home.
feature: Implementation Basics
exl-id: ebe29bc7-db34-4526-a3a5-43ed8704cfe9
role: Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '1258'
ht-degree: 100%

---

# Implementazione di Analytics per gli assistenti digitali

Con i recenti progressi nel cloud computing, nell’apprendimento automatico e nell’elaborazione del linguaggio naturale, gli assistenti digitali stanno entrando a far parte della vita quotidiana. I consumatori stanno iniziando a parlare con i loro dispositivi e si aspettano che capiscano e rispondano come farebbe un essere umano. Man mano che queste piattaforme si consolidano, i marchi possono presentare i servizi ai consumatori in queste stesse modalità realistiche e verosimili. Ad esempio, i consumatori possono chiedere cose come:

* “Alexa, chiedi alla mia macchina quando serve un cambio d’olio.”
* “Cortana, qual è il saldo del mio conto corrente?”
* “Siri, manda 20 € a John per cena di ieri sera dall’app della banca.”

Questa pagina fornisce una panoramica su quale sia il modo migliore di utilizzare Adobe Analytics per misurare e ottimizzare questi tipi di esperienze.

## Panoramica dell’architettura dell’esperienza digitale

![Flusso di lavoro dell’Assistente digitale](assets/Digital-Assitants.png)

La maggior parte degli assistenti digitali segue oggi un’architettura di alto livello simile:

1. **Dispositivo**: un dispositivo (come Amazon Echo o un telefono) con un microfono che consente all’utente di porre una domanda.
1. **Assistente digitale**: tale dispositivo interagisce con il servizio che gestisce l’assistente digitale. È dove il discorso viene convertito in intenzioni comprensibili da parte della macchina e vengono analizzati i dati della richiesta. Una volta compresa l’intenzione dell’utente, l’assistente digitale la trasmette insieme ai dettagli della richiesta all’app che la gestisce.
1. **“App”**: l’app può essere un’app sul telefono oppure un’app vocale. L’app è responsabile della risposta alla richiesta. Risponde all’assistente digitale e l’assistente digitale risponde quindi all’utente.

## Dove implementare Analytics

Una delle zone migliori per implementare Analytics è all’interno dell’app. L’app riceve l’intenzione e i dettagli dall’assistente digitale e determina quindi come rispondere.

Nel corso di una richiesta, esistono due momenti che possono essere utili per inviare dati ad Adobe Analytics.

1. Quando la richiesta viene inviata all’app.
1. Dopo che la risposta viene restituita dall’app.

Se sei solo interessato a registrare l’evento con il cliente per un’ottimizzazione futura, invia una richiesta ad Adobe Analytics dopo che la risposta è stata restituita. Avrai il contesto completo della richiesta e della risposta del sistema.

## Nuove installazioni

Per alcuni assistenti digitali, ricevi una notifica quando qualcuno installa l’abilità, soprattutto quando è richiesta l’autenticazione. Adobe consiglia di inviare un Install event impostando la variabile di dati di contesto `a.InstallEvent=1`. Questa funzione non è disponibile per tutti gli assistenti digitali, ma è utile quando è presente per esaminare la fidelizzazione. Il codice di esempio seguente invia i valori Install event, Install Date e AppID nelle variabili di dati di contesto.

```text
GET
/b/ss/examplersid1,examplersid2/1?vid=[UserID]&c.a.InstallEvent=1&c.a.InstallDate=2017-04-24&c.a.AppID=Spoofify1.0&c.OSType=Alexa&pageName=install
HTTP/1.1
Host:
<xref href="https://example.data.adobedc.net">
  example.data.adobedc.net
 Cache-Control: no-cache
</xref href="https:>
```

## Diversi assistenti o app diverse

È probabile che la tua organizzazione desideri app per più piattaforme. La best practice prevede l’inclusione di un ID app a ogni richiesta. Questa variabile può essere impostata nella variabile di dati di contesto `a.AppID`. Segui il formato di `[AppName] [BundleVersion]`, ad esempio, BigMac per Alexa 1.2:

```text
GET /b/ss/examplersid1,examplersid2/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.a.Launches=1&c.Product=AmazonEcho&c.OSType=Alexa&pageName=install  HTTP/1.1
Host: example.data.adobedc.net
Cache-Control: no-cache
```

```text
GET /b/ss/examplersid1,examplersid2/1?vid=[UserID]&c.a.AppID=Spoofify2.0&c.a.Launches=1&c.Product=GoogleHome&c.OSType=Android&pageName=install  HTTP/1.1
Host: example.data.adobedc.net
Cache-Control: no-cache
```

## Identificazione utente/visitatore

Adobe Analytics utilizza il [servizio Adobe Experience Cloud Identity](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=it) per collegare le interazioni alla stessa persona nel tempo. La maggior parte degli assistenti digitali restituisce un `userID` che puoi utilizzare per mantenere l’attività per utenti diversi. In gran parte dei casi, questo valore è quello che puoi trasmettere come identificatore univoco. Alcune piattaforme restituiscono un identificatore che supera i 100 caratteri consentiti. In questi casi, Adobe consiglia di eseguire l’hashing dell’identificatore univoco a un valore a lunghezza fissa utilizzando un algoritmo di hashing standard, ad esempio MD5 o Sha1.

L’utilizzo del servizio ID fornisce il massimo valore quando mappi gli ECID su diversi dispositivi (ad esempio, da web ad assistente digitale). Se utilizzi un’app per dispositivo mobile, usa gli SDK di Experience Platform così come sono e invia l’ID utente utilizzando il metodo `setCustomerID`. Tuttavia, se la tua app invece è un servizio, usa l’ID utente fornito dal servizio come ECID, e impostalo in `setCustomerID`.

```text
GET /b/ss/examplersid1,examplersid2/1?vid=[UserID]&pageName=[intent]  HTTP/1.1
Host: example.data.adobedc.net
Cache-Control: no-cache
```

## Sessioni

Poiché gli assistenti digitali sono di tipo conversazionale, spesso hanno il concetto di sessione. Esempio:

**Consumatore:** “Ok Google, chiama un taxi per me”

**Google:** “Certo, a che ora lo vuoi?”

**Consumatore:** “20:30”

**Google:** “Va bene, il taxi arriverà alle 20:30”

Le sessioni sono importanti per mantenere il contesto e aiutare a raccogliere più dettagli per rendere più naturale l’assistente digitale. Quando si implementa Analytics su una conversazione, è necessario eseguire due operazioni all’avvio di una nuova sessione:

1. **Contattare Audience Manager**: ottieni i segmenti rilevanti di cui fa parte un utente in modo da poter personalizzare la risposta. (Ad esempio, questa persona attualmente può usufruire dello sconto multicanale).
2. **Inviare una nuova sessione o un nuovo evento di avvio**: quando invii la prima risposta ad Analytics, includi un evento di avvio. Di solito, questo può essere inviato impostando i dati contestuali di `a.LaunchEvent=1`.

```text
GET /b/ss/examplersid1,examplersid2/1?vid=[UserID]&c.a.LaunchEvent=1&c.Intent=[intent]&pageName=[intent]  HTTP/1.1
Host: example.data.adobedc.net
Cache-Control: no-cache
```

## Intenti

Ciascuno degli assistenti digitali dispone di algoritmi che rilevano gli intenti e quindi trasmettono l’intento all’app in modo che l’app sappia cosa fare. Questi intenti sono una breve rappresentazione della richiesta.

Per esempio, se un utente dice, “Siri, invia a John 20 $ per la cena di ieri sera dalla mia app bancaria”, l’intento potrebbe essere qualcosa come *InviaSoldi*.

Inviando ciascuna di queste richieste come eVar, puoi eseguire rapporti di percorsi su ciascuno degli intenti per le app conversazionali. Assicurati che la tua app possa gestire le richieste anche senza un intento. Adobe consiglia di passare “Nessun intento specificato” alla variabile di dati di contesto intento, anziché omettere la variabile.

```text
GET /b/ss/examplersid1,examplersid2/1?vid=[UserID]&c.a.AppID=Penmo1.0&c.a.LaunchEvent=1&c.Intent=SendPayment&pageName=[intent]  HTTP/1.1
Host: example.sc.adobedc.net
Cache-Control: no-cache
```

oppure

```text
GET /b/ss/examplersid1,examplersid2/1?vid=[UserID]&c.a.AppID=Penmo1.0&c.a.LaunchEvent=1&c.Intent=No_Intent_Specified&pageName=[intent]  HTTP/1.1
Host: example.data.adobedc.net
Cache-Control: no-cache
```

## Parametri/Slot/Entità

Oltre all’intento, gli assistenti digitali spesso dispongono di un set di coppie chiave/valore che forniscono dettagli sull’intento. Possono essere chiamati slot, entità o parametri. Ad esempio, “Siri, invia a John 20 $ per la cena di ieri sera dalla mia app bancaria” avrebbe i seguenti parametri:

* Chi = John
* Importo = 20
* Perché = Cena

L’app in genere contiene un numero finito di questi valori. Per tenere traccia di questi valori in Analytics, inviali nelle variabili di dati di contesto e quindi mappa ciascuno dei parametri su un eVar.

```text
GET /b/ss/examplersid1,examplersid2/1?vid=[UserID]&c.a.AppID=Penmo1.0=1&c.a.LaunchEvent=1&c.Intent=SendPayment&c.Amount=20.00&c.Reason=Dinner&c.ReceivingPerson=John&c.Intent=SendPayment&pageName=[intent]  HTTP/1.1
Host: example.data.adobedc.net
Cache-Control: no-cache
```

## Stati di errore

A volte l’assistente digitale fornisce all’app input che non sa come gestire. Per esempio, “Siri, invia a John 20 sacchi di carbone per la cena di ieri sera dalla mia app bancaria”

Quando si verifica questa situazione, chiedi chiarimenti alla tua app. Inoltre, invia i dati ad Adobe che indica che l’app ha uno stato di errore insieme a un eVar che specifica quale tipo di errore si è verificato. Assicurati di includere gli errori in cui gli input non sono corretti ed errori in cui l’app ha avuto un problema.

```text
GET /b/ss/examplersid1,examplersid2/1?vid=[UserID]&c.a.AppID=Penmo1.0&c.Error=1&c.ErrorName=InvalidCurrency&pageName=[intent]  HTTP/1.1
Host: example.data.adobedc.net
Cache-Control: no-cache
```

## Funzionalità del dispositivo

Anche se la maggior parte delle piattaforme non espongono il dispositivo a cui l’utente ha parlato, espongono le funzionalità del dispositivo. Ad esempio, Audio, Schermo, Video, ecc. Queste informazioni sono utili perché definiscono i tipi di contenuto che possono essere utilizzati durante l’interazione con gli utenti. Quando si misurano le funzionalità dei dispositivi, è consigliabile concatenarle (in ordine alfabetico).

Esempio: `":Audio:Camera:Screen:Video:"`

I due punti iniziali e finali sono utili per la creazione dei segmenti. Ad esempio, mostra tutti gli hit con funzionalità `:Audio:`.

* [Funzionalità di Amazon](https://developer.amazon.com/public/solutions/alexa/alexa-skills-kit/docs/alexa-skills-kit-interface-reference) utilizzando Amazon Alexa
* [Funzionalità Google](https://developers.google.com/actions/assistant/surface-capabilities) utilizzando Actions on Google

## Esempi

| Persona | Risposta del dispositivo | Azione/Intento | richiesta GET |
|---|---|---|---|
| Installa Spoofify | Nessuna risposta | Installa | `GET /b/ss/examplersid1,examplersid2/1?vid=[UserID]&c.a.InstallEvent=1&c.a.InstallDate=[currentDate]&c.a.AppID=Spoofify1.0&c.OSType=Alexa&c.Intent=Install&pageName=Install  HTTP/1.1`<br>`Host: example.data.adobedc.net`<br>`Cache-Control: no-cache` |
| Riproduci Spoofify | “Ok, riproduci Spoofify” | Play | `GET /b/ss/examplersid1,examplersid2/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.a.LaunchEvent=1&c.Intent=Play&pageName=PlayApp  HTTP/1.1`<br>`Host: example.data.adobedc.net`<br>`Cache-Control: no-cache` |
| Cambia canzone | “Ok, che canzone vuoi?” | ChangeSong | `GET /b/ss/examplersid1,examplersid2/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.Intent=ChangeSong&pageName= Ask%20For%20Song  HTTP/1.1`<br>`Host: example.data.adobedc.net`<br>`Cache-Control: no-cache` |
| Riproduci “Baby Shark” | “Ok, ‘Baby Shark’ di PinkFong in riproduzione” | ChangeSong | `GET /b/ss/examplersid1,examplersid2/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.Intent=ChangeSong&pageName=Action%20Play%20Song&c.SongID=[012345]  HTTP/1.1`<br>`Host: example.data.adobedc.net`<br>`Cache-Control: no-cache` |
| Modifica la playlist | “Ok, quale playlist vuoi?” | ChangePlaylist | `GET /b/ss/examplersid1,examplersid2/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.Intent=ChangePlaylist&pageName=Ask%20For%20Playlist  HTTP/1.1`<br>`Host: example.data.adobedc.net`<br>`Cache-Control: no-cache` |
| Riproduci la mia playlist di brani preferiti | “Ok, playlist dei tuoi brani preferiti in riproduzione” | ChangePlaylist | `GET /b/ss/examplersid1,examplersid2/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.Intent=ChangePlaylist&pageName=Action%20Play%20Playlist&c.Playlist=My%20Favorite%20Songs  HTTP/1.1`<br>`Host: example.data.adobedc.net`<br>`Cache-Control: no-cache` |
| Spegni musica | Nessuna risposta, la musica si spegne | Off | `GET /b/ss/examplersid1,examplersid2/1?vid=[UserID]&c.a.AppID=Spoofify1.0&c.Intent=Off&pageName=Music%20Off  HTTP/1.1`<br>`Host: example.data.adobedc.net`<br>`Cache-Control: no-cache` |
