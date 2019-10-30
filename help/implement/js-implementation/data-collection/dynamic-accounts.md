---
description: Il file .js può essere configurato per selezionare automaticamente un ID suite di rapporti.
keywords: Implementazione di Analytics
seo-description: Il file .js può essere configurato per selezionare automaticamente un ID suite di rapporti.
seo-title: 'ID suite di rapporti: account dinamici'
solution: Analytics
title: 'ID suite di rapporti: account dinamici'
topic: Sviluppatore e implementazione
uuid: 763a9741-309d-4795-8819-6543866047d5
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# ID suite di rapporti: account dinamici

Il file .js può essere configurato per selezionare automaticamente un ID suite di rapporti. Il file .js invia automaticamente la richiesta di immagine alla suite di rapporti in base all'URL. Ad esempio, se l’URL è `www.mysite.com`, la richiesta di immagine viene inviata automaticamente alla suite di rapporti A. Se l’URL è `www.mysite1.com`l’immagine, la richiesta viene inviata automaticamente alla suite di rapporti B.

Queste stringhe si trovano in uno dei seguenti elementi:

* Host/dominio (impostazione predefinita)
* Path (Percorso)
* Query Stringa
* Host/dominio e percorso
* Percorso e stringa query
* URL completo

Per ulteriori informazioni sulla configurazione [!DNL Analytics] per selezionare automaticamente un [!UICONTROL Report Suite ID], contattate il supporto Adobe Live.

## Definizione del segmento URL da associare {#section_8099162F75F641CFBE46FD814450EF36}

Dato il seguente URL di esempio, le parti dell’URL sono mostrate di seguito, insieme alla `s.dynamicAccountMatch` variabile da impostare. (L'impostazione predefinita, se non `s.dynamicAccountMatch` è definita, consiste nella ricerca solo dell'host o del nome di dominio).
URL di esempio: `https://www.client.com/directory1/directory2/filename.html?param1=1234&param2=4321`

| Porzione | Esempio (dall'alto) |
|---|---|
| Nome host/dominio | `www.client.com` |
| Path (Percorso) | `directory1/directory2/filename.html` |
| Query Stringa | `param1=1234&param2=4321` |
| Host/Dominio e Percorso | `www.client.com/directory1/directory2/filename.html` |
| Percorso e stringa query | `directory1/directory2/filename.html?param1=1234&param2=4321` |
| URL | `https://www.client.com/directory1/directory2/filename.html?param1=1234&param2=4321` |
| Porzione | `s.dynamicAccountmatch` |
| Nome host/dominio | Non definito |
| Path (Percorso) | `window.location.pathname` |
| Query Stringa | `(window.location.search?window.location.search:"?")` |
| Host/Dominio e Percorso | `window.location.host+window.location.pathname` |
| Percorso e stringa query | `window.location.pathname+(window.location.search?window.location.search:"?")` |
| URL | `window.location.href` |

Prendi in considerazione l'esempio seguente:

* `s.dynamicAccountSelection=true`
* `s.dynamicAccountList="devreportsuite1=qa.client.com;reportsuite2=clientdirectory;reportsuite1=client.com"`
* `s.dynamicAccountMatch=window.location.host+window.location.pathname`

## Regole multiple {#section_163FED1C1FA74C48BCB78B0D67EF36AE}

Se sono selezionate più regole (vedere l'esempio precedente), le regole vengono eseguite da sinistra a destra. Le regole si fermano non appena si effettua una corrispondenza, come mostrato di seguito (con il set di regole specificato).

* `s.dynamicAccountSelection=true`
* `s.dynamicAccountList="devreportsuite1=qa.client.com;reportsuite1=client.com"`

Il codice controlla innanzitutto se `qa.client.com` esiste all'interno del nome host/dominio. In tal caso, la suite di rapporti `devreportsuite1` è selezionata e la corrispondenza si interrompe. Separate più regole con punti e virgola.

## Suite di rapporti predefinita {#section_0360D724929348B0B211708B5BA15647}

La `s_account` variabile può essere impostata per prima e funge da valore predefinito nel caso in cui non sia possibile trovare una delle stringhe specificate. Di seguito è riportato un esempio:

```javascript
var s_account="defaultreportsuiteid" 
s.dynamicAccountSelection=true 
s.dynamicAccountList="devreportsuite1=qa.client.com;reportsuite1=client.com" 
```

Nel caso precedente, se il nome host/dominio non conteneva `qa.client.com` o `client.com`, verrà utilizzato *defaultreportsuite* di rapporti.
