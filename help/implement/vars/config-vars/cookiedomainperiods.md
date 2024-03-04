---
title: cookieDomainPeriods
description: AppMeasurement di aiuto per capire quale dominio memorizzare i cookie se nel dominio è presente un punto nel suffisso.
feature: Variables
exl-id: c426d6a7-4521-4d50-bb7d-1664920618d8
role: Admin, Developer
source-git-commit: fe33da47c109adacb8162c7165ad4c63bd65c08d
workflow-type: tm+mt
source-wordcount: '659'
ht-degree: 7%

---


# cookieDomainPeriods

AppMeasurement determina la posizione del cookie osservando il dominio e il suffisso di dominio. Per domini come `example.com`, AppMeasurement imposta i cookie nella posizione corretta. Tuttavia, per altri domini come `example.co.uk`, AppMeasurement può erroneamente impostare i cookie su `co.uk`. La maggior parte dei browser rifiuta i cookie impostati su questo dominio non valido, causando problemi con l’identificazione dei visitatori.

Il `cookieDomainPeriods` La variabile aiuta AppMeasurement a determinare dove vengono impostati i cookie di Analytics richiamando l’attenzione sul fatto che il suffisso di dominio contiene un punto aggiuntivo. Questa variabile consente ad AppMeasurement di inserire il periodo aggiuntivo nel suffisso di dominio e impostare i cookie nella posizione giusta.

* Per domini come `example.com` o `www.example.com`, non è necessario impostare questa variabile. Se necessario, puoi impostare questa variabile su `"2"`.
* Per domini come `example.co.uk` o `www.example.co.jp`, imposta questa variabile su `"3"`.


>[!IMPORTANT]
>
>Non prendere in considerazione i sottodomini per questa variabile. Ad esempio, non impostare `cookieDomainPeriods` sull’URL di esempio `store.toys.example.com`. L’AppMeasurement per impostazione predefinita riconosce che i cookie devono essere memorizzati su `example.com`, anche su URL con molti sottodomini.


## Periodi di dominio dei cookie, cookie di terze parti e identificazione dei visitatori legacy

Solo quando utilizzi l’identificazione dei visitatori legacy di Adobe Analytics (invece del servizio consigliato di Experience Cloud Identity), la configurazione implicita o esplicita di `cookieDomainPeriods` può avere implicazioni sul modo in cui i visitatori vengono identificati, a seconda che i cookie di terze parti siano bloccati o meno.

La tabella seguente illustra quattro possibili scenari.

| Scenario | `cookieDomainPeriods` configurazione: ... | I cookie di terze parti sono bloccati? | Risultato quando si utilizza il servizio legacy di identificazione dei visitatori di Adobe Analytics |
|:---:|---|---|---|
| 1 | <span style="color:green">Corretto</span> | No | I visitatori sono identificati con un `s_vi` cookie, imposta lato server. |
| 2 | <span style="color:green">Corretto</span> | Sì | I visitatori sono identificati con un fallback `s_fid` cookie, imposta lato client (dominio pagina di prime parti). |
| 3 | <span style="color:red">Errato</span> | No | I visitatori vengono identificati con l’identificatore di fallback in base alla combinazione di agente utente e indirizzo IP. <br/>AppMeasurement è costretto a impostare i cookie come cookie di terze parti.<br/> Il `s_vi` il cookie può essere impostato quando `cookieDomainPeriods` non viene trasmesso correttamente. |
| 4 | <span style="color:red">Errato</span> | Sì | I visitatori vengono identificati con l’identificatore di fallback in base alla combinazione di agente utente e indirizzo IP.<br/>AppMeasurement è costretto a impostare i cookie come cookie di terze parti che sono bloccati, quindi non vengono impostati cookie. |

>[!CAUTION]
>
>Potresti aver configurato inavvertitamente `cookieDomainPeriods` <span style="color:red">errato</span> (lasciando invariato il valore predefinito di `"2"`) durante l&#39;utilizzo di domini come `example.co.uk`. Questa configurazione implicita non corretta porta all’identificazione dei visitatori secondo lo scenario 3 o 4.
>
>Configurazioni AppMeasurement versione 2.26.x o successive `cookieDomainPeriods` automaticamente con il valore corretto, in modo che siano possibili solo gli scenari 1 o 2. Quando esegui l’aggiornamento alla versione 2.26.x o successiva di AppMeasurement, identificando al momento i visitatori in modo errato (scenario 3 o 4), l’aggiornamento ha implicazioni principali.
>
>* Gli identificatori dei visitatori vengono reimpostati e i visitatori verranno visualizzati come nuovi visitatori. Non sarà possibile collegare la nuova attività all’identificatore visitatore precedente.
>* I cookie sono impostati (ad esempio per il tracciamento dei collegamenti o la mappa delle attività, ad esempio`s_sq` cookie), con conseguenti differenze improvvise nella generazione dei rapporti.
>
>Durante la configurazione corretta `cookieDomainPeriods` migliorerà le funzionalità di AppMeasurement e Analytics; si consiglia di valutare se le modifiche derivanti dall’aggiornamento della libreria di AppMeasurement influiscono sulle modifiche.
>
> Consulta [Cookie di Analytics](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/cookies-analytics.html?lang=it) per ulteriori informazioni sui cookie, l’AppMeasurement utilizza.

## Periodi del dominio dei cookie tramite Web SDK

L’SDK per web può determinare il dominio di archiviazione dei cookie corretto senza questa variabile.

## Periodi del dominio dei cookie tramite l’estensione Adobe Analytics

Periodi di dominio è un campo sotto [!UICONTROL Cookies] Pannello a soffietto durante la configurazione dell’estensione Adobe Analytics.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà del tag desiderata.
1. Vai alla scheda [!UICONTROL Extensions], quindi fai clic sul pulsante **[!UICONTROL Configure]** in Adobe Analytics.
1. Espandi il pannello a soffietto [!UICONTROL Cookies], che mostra il campo [!UICONTROL Domain Periods].

Imposta questo campo su `3` solo sui domini contenenti un punto nel relativo suffisso. In caso contrario, questo campo può essere lasciato vuoto.

## Periodi di dominio dei cookie nell’AppMeasurement di codice e nell’editor di codice personalizzato dell’estensione Analytics

È possibile impostare `cookieDomainPeriods` nella libreria JavaScript di AppMeasurement o nell’editor di codice personalizzato dell’estensione Analytics.

Il `cookieDomainPeriods` variabile è una stringa in genere impostata su `"3"`, solo sui domini che contengono un punto nel relativo suffisso. Il valore predefinito è `"2"`, che ospita la maggior parte dei domini.

```js
// Manually set cookieDomainPeriods for domains with a period in its suffix, such as www.example.co.uk
s.cookieDomainPeriods = "3";

// Detect if a URL has a domain suffix with an extra period, and set s.cookieDomainPeriods automatically
document.URL.indexOf(".co.") > 0 ? s.cookieDomainPeriods = "3" : s.cookieDomainPeriods = "2";
```
