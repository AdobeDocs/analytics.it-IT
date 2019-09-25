---
description: Le variabili dinamiche consentono di copiare i valori da una variabile all’altra senza digitare più volte i valori completi nelle richieste di immagini sul sito.
keywords: Implementazione di Analytics
seo-description: Le variabili dinamiche consentono di copiare i valori da una variabile all’altra senza digitare più volte i valori completi nelle richieste di immagini sul sito.
solution: null
title: Variabili dinamiche
translation-type: tm+mt
source-git-commit: 4a6bac589d1d6d6caaf34dc5363c60bbfbb952d5

---


# s.account

La variabile determina la suite di rapporti in cui i dati vengono memorizzati e segnalati.

Se si inviano a più suite di rapporti (tag con più suite), `s.account` può trattarsi di un elenco di valori separati da virgola. L'ID suite di rapporti è determinato da Adobe.

## Parametri

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|--- |--- |--- |--- |
| 40 byte | Nel percorso URL | N/D | N/D |

Ogni ID suite di rapporti deve corrispondere al valore creato nel [!DNL Admin Console]. Ogni ID suite di rapporti deve essere di 40 byte o inferiore, ma l'aggregazione di tutte le suite di rapporti (l'intero elenco separato da virgole) non ha limiti.

La suite per report è il livello di segmentazione più fondamentale nei report. Puoi impostare un numero illimitato di suite di rapporti. Ogni suite di rapporti fa riferimento a un set dedicato di tabelle popolate nei server di raccolta di Adobe. Una suite di rapporti è identificata dalla `s_account` variabile nel codice JavaScript.

All'interno [!DNL Analytics]della casella a discesa del sito in alto a sinistra dei rapporti viene visualizzata la suite di rapporti corrente. Ciascuna suite di rapporti ha un identificatore univoco denominato ID suite di rapporti. La `s_account` variabile contiene uno o più ID suite di rapporti a cui vengono inviati i dati. Il valore ID suite di rapporti, invisibile agli [!DNL Analytics] utenti, deve essere fornito o approvato da Adobe prima di utilizzarlo. A ogni suite di rapporti è associato un "nome descrittivo" che può essere modificato nella sezione suite di rapporti di [!DNL Admin Console].

La `s_account` variabile viene normalmente dichiarata all'interno del file JavaScript (s_code.js). È possibile dichiarare la `s_account` variabile sulla pagina HTML, una pratica comune quando il valore di `s_account` può cambiare da una pagina all’altra. Poiché la `s_account` variabile ha un ambito globale, deve essere dichiarata immediatamente prima di includere il file JavaScript di Adobe. Se `s_account` non è presente un valore quando il file JavaScript viene caricato, non viene inviato alcun dato a [!DNL Analytics].

Adobe [!DNL DigitalPulse Debugger] visualizza il valore di `s_account` nel percorso dell'URL che appare appena sotto la parola "Immagine", subito dopo /b/ss/. In alcuni casi, il valore di `s_account` viene visualizzato anche nel dominio, prima di 112.2o7.net. Il valore nel percorso è l'unico valore che determina la suite di rapporti di destinazione. Il testo in grassetto riportato di seguito mostra le suite di rapporti a cui vengono inviati i dati, così come appaiono nel debugger. Vedere [Digital Pulse Debugger](/help/implement/impl-testing/debugger.md).

```js
https://mycompany.112.207.net/b/ss/ 
<b>mycompanycom,mycompanysection</b>/1/H.1-pdv-2/s21553246810948?[AQB]
```

## Sintassi e valori possibili

L'ID suite di rapporti è una stringa alfanumerica di caratteri ASCII, con una lunghezza massima di 40 byte. L'unico carattere non alfanumerico consentito è un trattino. Spazi, punti, virgole e altre punteggiature non consentiti. La `s_account` variabile può contenere più suite di rapporti, tutte le quali ricevono dati da quella pagina.

```js
var s_account="reportsuitecom[,reportsuite2[,reportsuite3]]"
```

Tutti i valori di `s_account` devono essere forniti o approvati da Adobe.

## Esempi

```js
var s_account="mycompanycom"
```

```js
var s_account="mycompanycom,mycompanysection"
```

## Configurazione della variabile in Analytics

Il nome descrittivo associato a ciascun ID suite di rapporti può essere modificato da Adobe [!DNL Customer Care]. Il nome descrittivo è visibile [!DNL Analytics] nella casella a discesa del sito, nella sezione superiore sinistra della schermata.

## Insidie, domande e suggerimenti

* Se `s_account` è vuoto, non dichiarato o contiene un valore imprevisto, non viene raccolto alcun dato.
* Se la `s_account` variabile è un elenco separato da virgole (tag per più suite), non inserite spazi tra gli ID delle suite di rapporti.
* Se [!UICONTROL s.dynamicAccountSelection] è impostato su *True* , l'URL viene utilizzato per determinare la suite di rapporti di destinazione. Utilizzate l'icona [!DNL DigitalPulse Debugger] per determinare le suite di rapporti di destinazione.

* In alcuni casi, [!DNL VISTA] può essere utilizzato per modificare la suite di rapporti di destinazione. Quando si utilizzano cookie di prime parti, o se il sito include più di 20 suite di rapporti attive, si consiglia [!DNL VISTA] di utilizzare per il reindirizzamento o la copia dei dati in un'altra suite di rapporti.

* Dichiarare sempre `s_account` all'interno del file JS o subito prima che venga incluso.
