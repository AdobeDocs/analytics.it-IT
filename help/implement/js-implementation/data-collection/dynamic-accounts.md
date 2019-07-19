---
description: Il file. js può essere configurato per selezionare automaticamente un ID suite di rapporti.
keywords: Implementazione di Analytics
seo-description: Il file. js può essere configurato per selezionare automaticamente un ID suite di rapporti.
seo-title: ID suite di rapporti - account dinamici
solution: Analytics
title: ID suite di rapporti - account dinamici
topic: Sviluppatore e implementazione
uuid: 763 a 9741-309 d -4795-8819-6543866047 d 5
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# ID suite di rapporti - account dinamici

Il file. js può essere configurato per selezionare automaticamente un ID suite di rapporti. Il file. js invia automaticamente la richiesta di immagine alla suite di rapporti in base all'URL. For example, if the URL is `www.mysite.com`, the image request is automatically sent to report suite A. If the URL is `www.mysite1.com`, the image request is automatically sent to report suite B.

Queste stringhe si trovano in una delle seguenti operazioni:

* Host/dominio (impostazione predefinita)
* Path (Percorso)
* Query Stringa
* Ospitante/dominio e percorso
* Percorso e stringa query
* URL completo

For more information on configuring [!DNL Analytics] to automatically select a [!UICONTROL Report Suite ID], contact Adobe Live Support.

## Defining the URL Segment to Match {#section_8099162F75F641CFBE46FD814450EF36}

Given the following sample URL, the portions of the URL are shown below, along with the `s.dynamicAccountMatch` variable that must be set. (The default - if `s.dynamicAccountMatch` is not defined - is to search the Host/Domain Name only).
URL di esempio: `https://www.client.com/directory1/directory2/filename.html?param1=1234&param2=4321`

| Parte | Esempio (da sopra) |
|---|---|
| Nome host/nome dominio | `www.client.com` |
| Path (Percorso) | `directory1/directory2/filename.html` |
| Query Stringa | `param1=1234&param2=4321` |
| Host/Dominio e percorso | `www.client.com/directory1/directory2/filename.html` |
| Percorso e stringa query | `directory1/directory2/filename.html?param1=1234&param2=4321` |
| URL | `https://www.client.com/directory1/directory2/filename.html?param1=1234&param2=4321` |
| Parte | `s.dynamicAccountmatch` |
| Nome host/nome dominio | Non definito |
| Path (Percorso) | `window.location.pathname` |
| Query Stringa | `(window.location.search?window.location.search:"?")` |
| Host/Dominio e percorso | `window.location.host+window.location.pathname` |
| Percorso e stringa query | `window.location.pathname+(window.location.search?window.location.search:"?")` |
| URL | `window.location.href` |

Prendi in considerazione l'esempio seguente:

* `s.dynamicAccountSelection=true`
* `s.dynamicAccountList="devreportsuite1=qa.client.com;reportsuite2=clientdirectory;reportsuite1=client.com"`
* `s.dynamicAccountMatch=window.location.host+window.location.pathname`

## Multiple Rules {#section_163FED1C1FA74C48BCB78B0D67EF36AE}

Se sono selezionate più regole (vedete l'esempio precedente), le regole vengono eseguite da sinistra a destra. Le regole si interrompono non appena viene effettuata una corrispondenza, come mostrato di seguito (con l'insieme di regole specificato).

* `s.dynamicAccountSelection=true`
* `s.dynamicAccountList="devreportsuite1=qa.client.com;reportsuite1=client.com"`

The code first checks to determine if `qa.client.com` exists within the Host/Domain Name. If so, the report suite `devreportsuite1` is selected, and the match stops. Separate più regole con punti e virgola.

## Default Report Suite {#section_0360D724929348B0B211708B5BA15647}

The `s_account` variable can be set first, and acts as a default value in case any of the specified strings cannot be found. Di seguito è riportato un esempio:

```javascript
var s_account="defaultreportsuiteid" 
s.dynamicAccountSelection=true 
s.dynamicAccountList="devreportsuite1=qa.client.com;reportsuite1=client.com" 
```

In the case above, if the host/domain name did not contain either `qa.client.com` or `client.com`, the report suite *defaultreportsuiteid* would be used.
