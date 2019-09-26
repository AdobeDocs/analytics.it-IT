---
description: Le variabili dinamiche consentono di copiare i valori da una variabile all’altra senza digitare più volte i valori completi nelle richieste di immagini sul sito.
keywords: Implementazione di Analytics
seo-description: Le variabili dinamiche consentono di copiare i valori da una variabile all’altra senza digitare più volte i valori completi nelle richieste di immagini sul sito.
solution: null
title: Variabili dinamiche
translation-type: tm+mt
source-git-commit: b38ba4222951d957c607cd764224028527835c7e

---


# s.cookieDomainPeriods

The  variable determines the domain on which the [!DNL Analytics] cookies `s_cc` and `s_sq` are set by determining the number of periods in the domain of the page URL. Questa variabile viene utilizzata anche da alcuni plug-in per determinare il dominio corretto per impostare il cookie del plug-in.

Il valore predefinito per *`cookieDomainPeriods`* è "2". Questo è il valore utilizzato se *`cookieDomainPeriods`* viene omesso. Ad esempio, utilizzando il dominio `www.mysite.com`, *`cookieDomainPeriods`* dovrebbe essere "2". Ad `www.mysite.co.jp`esempio, *`cookieDomainPeriods`* dovrebbe essere "3".

Se *`cookieDomainPeriods`* è impostato su "2" ma il dominio contiene tre punti, il file JavaScript tenta di impostare i cookie sul suffisso del dominio.

Ad esempio, se si imposta *`cookieDomainPeriods`* "2" sul dominio `www.mysite.co.jp`, i `s_cc` cookie e `s_sq` i cookie vengono creati sul dominio `co.jp`. Poiché `co.jp` è un dominio non valido, quasi tutti i browser rifiutano questi cookie. Di conseguenza, i dati delle mappe dei clic dei visitatori vengono persi e il rapporto [!UICONTROL Visitor Profile] &gt; [!UICONTROL Technology] &gt; [!UICONTROL Cookies] indica che quasi il 100% dei visitatori rifiuta i cookie.

Se *`cookieDomainPeriods`* è impostato su "3" ma il dominio contiene solo due punti, il file JavaScript imposta i cookie sul sottodominio del sito. Ad esempio, se si imposta *`cookieDomainPeriods`* "3" sul dominio `www2.mysite.com`, i `s_cc` cookie e `s_sq` i cookie vengono creati sul dominio `www2.mysite.com`. Quando un visitatore accede a un altro sottodominio del sito (ad esempio `www4.mysite.com`), non `www2.mysite.com` è possibile leggere tutti i cookie impostati con.

>[!NOTE]
>
>Non includete sottodomini aggiuntivi come parte di *`cookieDomainPeriods`*. Ad esempio, `store.toys.mysite.com` avrebbe comunque *`cookieDomainPeriods`* impostato su "2". Questa definizione di variabile imposta correttamente i cookie sul dominio principale [!DNL mysite.com]. L'impostazione *`cookieDomainPeriods`* su "3" in questo esempio imposta i cookie sul dominio [!DNL toys.mysite.com], con le stesse implicazioni dell'esempio precedente.

Vedere anche [s.fpCookieDomainPeriods](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html).

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| N/D | CDP | Interessa più rapporti in quanto controlla il modo in cui l’ID visitatore viene memorizzato e gestito. | "2" |

>[!NOTE]
>
>Alcuni servizi di cloud computing sono considerati Domini di primo livello, che non consentono la scrittura di cookie. (ad esempio `compute.amazonaws.com`, `*.herokuapp.com`, `*.googlecode.com`ecc.) Se implementi questi servizi, potresti essere potenzialmente influenzato dall'impostazione della privacy di Analytics che rimuove gli utenti che hanno bloccato tutti i cookie se non hai impostato il tuo dominio (ad esempio, se stai testando la tua implementazione). In questo caso, qualsiasi hit in cui il sistema ha determinato che i cookie sono disattivati, non funzionali o inaccessibili viene escluso e quindi escluso dalla segnalazione.

## Esempi

Impostazione manuale della variabile:

```js
s.cookieDomainPeriods = "3";
```

Diversi esempi per impostare in modo dinamico la variabile se il file JavaScript di base contiene entrambi i tipi:

```js
document.URL.indexOf(".co.") > 0 ? s.cookieDomainPeriods = "3" : s.cookieDomainPeriods = "2";
```

```js
s.cookieDomainPeriods = "2"; 
var d=window.location.hostname; 
if(d.indexOf(".co.uk") > 0 || d.indexOf(".com.au") > 0) 
    {s.cookieDomainPeriods = "3";}
```

```js
s.cookieDomainPeriods = "2"; 
if(window.location.indexOf(".co.jp") > 0 || window.location.indexOf(".com.au") > 0) 
    {s.cookieDomainPeriods = "3";}
```

## Insidie, domande e suggerimenti

* Se noti che i dati della mappa del clic del visitatore sono assenti o che il rapporto [!UICONTROL Traffic] &gt; [!UICONTROL Technology] &gt; [!UICONTROL Cookies] mostra una grande percentuale di visitatori che rifiutano i cookie, verifica che il valore di *`cookieDomainPeriods`* sia corretto.

* Se *`cookieDomainPeriods`* è superiore al numero di sezioni del dominio, i cookie verranno impostati con l'intero dominio. Ciò può causare la perdita di dati quando i visitatori passano da un sottodominio all'altro.
* La *`cookieDomainPeriods`* variabile è stata utilizzata nelle implementazioni obsolete prima di *`trackingServer`* impostare il cookie ID visitatore. Anche se presente solo in codice obsoleto, la mancata definizione corretta *`cookieDomainPeriods`* in questa circostanza mette la vostra implementazione a rischio di perdita di dati.