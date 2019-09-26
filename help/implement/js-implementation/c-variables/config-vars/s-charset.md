---
description: Le variabili dinamiche consentono di copiare i valori da una variabile all’altra senza digitare più volte i valori completi nelle richieste di immagini sul sito.
keywords: Implementazione di Analytics
seo-description: Le variabili dinamiche consentono di copiare i valori da una variabile all’altra senza digitare più volte i valori completi nelle richieste di immagini sul sito.
solution: null
title: Variabili dinamiche
translation-type: tm+mt
source-git-commit: 60dd1b300035e5149f53870239de85fb3174a77a

---


# s.charSet

La proprietà charSet, normalmente impostata nel file JavaScript, viene utilizzata da Analytics per convertire i dati in entrata in UTF-8 per l'archiviazione e il reporting da parte di Analytics.

>[!N] Nota: La proprietà charSet è obbligatoria quando si inviano dati a una suite di rapporti multibyte e non deve mai essere utilizzata con una suite di rapporti standard. L'impostazione della proprietà charSet con una suite di rapporti ISO standard può determinare il troncamento variabile o una conversione di caratteri imprevista.

Il valore della proprietà charSet deve corrispondere alla codifica della pagina Web nel tag META o nell'intestazione http, anche se la sintassi può variare leggermente. Anche se il tag META può utilizzare un alias per la codifica, il valore di charSet deve utilizzare il nome preferito (o ufficiale) della codifica.

Alcune delle codifiche più comuni con il nome e gli alias preferiti sono elencate nella tabella seguente.

| Preferred Name | Alias |
|--- |--- |
| ISO-8859-1 | ISO_8859-1, CP819, latin1 |
| ISO-8859-2 | ISO_8859-2, latin2 |
| ISO-8859-5 | ISO_8859-5, cicrilico |
| Big5 | Big-5 |
| Shift_JIS | SJIS |

Poiché esistono numerose codifiche e alias, contatta il tuo Consulente per l’implementazione o l’Assistenza clienti Adobe per confermare il valore corretto per charSet, se non viene visualizzato nella tabella precedente.

Se un sito dispone di codifiche Web diverse su pagine diverse, o se per più siti viene utilizzato un singolo file JavaScript, la proprietà charSet può essere impostata su un valore predefinito nel file JavaScript e quindi reimpostata su pagine specifiche, in base alle esigenze, per ignorare il valore predefinito; ad esempio `s.charSet="UTF-8"` o `s.charSet="SJIS"`.

Qualsiasi valore non vuoto del parametro charSet causerà la conversione dei dati in UTF-8 per l'archiviazione. Tutti i caratteri nell'intervallo 128-255 saranno convertiti nella sequenza UTF-8 a due byte corretta e memorizzati. Questi caratteri non verranno visualizzati correttamente in una suite di rapporti standard. Pertanto, la proprietà charSet non deve mai essere utilizzata con una suite di rapporti standard.

Likewise, a blank value of the charSet parameter will bypass the data conversion process, and any characters in the range 128-255 will be stored as a single byte. Questi caratteri non verranno visualizzati correttamente in una suite di rapporti multibyte, poiché i codici a byte singolo per questi caratteri non sono UTF-8 validi. Pertanto, il parametro charSet deve sempre essere utilizzato con una suite di rapporti multibyte. Additionally, the proper value should be used with respect to the web page encoding.

Se la *`charSet`* variabile contiene un valore non corretto, i dati di tutte le altre variabili vengono convertiti in modo non corretto. Se variabili JavaScript nelle pagine (ad esempio *`pageName`*, [!UICONTROL prop1]o *`channel`*) contengono solo caratteri ASCII, *`charSet`* non è necessario definirli. Tuttavia, se le variabili nelle pagine contengono caratteri non ASCII, la *`charSet`* variabile deve essere compilata.

## Parametri

| Dimensioni massime | Debugger Parameter | Reports Populated | Valore predefinito |
|--- |--- |--- |--- |
| N/D | CE | N/D | "" |

## Syntax and Possible Values

```js
s.charSet="character_set"
```

## Esempi

```js
s.charSet="ISO-8859-1"
```

```js
s.charSet="SJIS"
```
