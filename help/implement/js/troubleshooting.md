---
title: Risoluzione dei problemi di implementazione JavaScript
description: Informazioni su problemi comuni e procedure ottimali per la risoluzione dei problemi relativi all'implementazione JavaScript.
translation-type: tm+mt
source-git-commit: b569f87dde3b9a8b323e0664d6c4d1578d410bb7
workflow-type: tm+mt
source-wordcount: '692'
ht-degree: 2%

---


# Risoluzione dei problemi di implementazione JavaScript

Di seguito sono riportati diversi motivi per cui l&#39;organizzazione potrebbe avere problemi con la corretta immissione dei dati in  Adobe Analytics.

## Utilizzo delle virgolette

La maggior parte delle variabili inviate al Adobe  sono stringhe. In JavaScript, è possibile utilizzare virgolette singole o doppie.

### Combinazione di virgolette per definire una variabile

Come procedura ottimale, accertatevi di essere coerenti con i tipi di virgolette utilizzati. Se una singola citazione indica l&#39;inizio di una stringa, per chiuderla è necessario utilizzare una singola citazione.

Ad esempio, entrambi `s.eVar1 = 'Value'` e `s.eVar1 = "Value"` sono validi. `s.eVar1 = 'Value"` non è valido.

### Inclusione di virgolette singole o doppie in una stringa

Talvolta è necessario includere una citazione singola o doppia in una stringa. Ad esempio, se desiderate includere il valore `Alex's sale` o `John the "Hunter"` nei rapporti. Esistono due metodi per includere i seguenti valori:

* **Utilizzare l&#39;altro tipo** di offerta: Ad esempio, `s.eVar1 = "Alex's sale"` e `s.eVar1 = 'John the "Hunter"'` sono entrambi validi.
* **Virgolette** di escape: Utilizzare una barra rovesciata per evitare le virgolette. Ad esempio, `s.eVar1 = 'Alex\'s sale'` e `s.eVar1 = "John the \"Hunter\""` sono entrambi validi.

### Evitate di usare virgolette inglesi

Alcuni programmi convertono automaticamente le virgolette (`"..."` e `'...'`) in virgolette`“...”` e `‘...’`). Evitate di utilizzare editor di documenti (come Microsoft Word) o di trasmettere snippet di codice tramite e-mail. Le virgolette inglesi non possono essere utilizzate in JavaScript.

## Riferimento all&#39;oggetto Analytics

Tutte le variabili inviate  Adobe utilizzano l&#39;oggetto Analytics. La maggior parte delle implementazioni utilizza l&#39; `s` oggetto. Accertatevi che, quando fate riferimento a variabili, l&#39;oggetto Analytics sia incluso nel riferimento.

Ad esempio, `s.eVar1 = 'Value'` è valido, mentre `eVar1 = 'Value'` non lo è.

## Definisci ogni variabile una volta

Quando viene eseguita una funzione di tracciamento (`s.t()`), AppMeasurement prende tutte le variabili definite e le compila in una richiesta di immagine. Se si definisce una variabile più di una volta nell&#39;implementazione, viene utilizzato solo il valore più recente. Assicurarsi che tutti i valori delle variabili contengano il valore corretto durante l&#39;esecuzione della funzione track.

## Correggere la maiuscola variabile

Alcune variabili utilizzano lettere maiuscole. Le variabili JavaScript fanno distinzione tra maiuscole e minuscole. Quando si definiscono le variabili, assicurarsi di utilizzare le maiuscole/minuscole corrette. Ad esempio, `s.eVar1 = 'Value'` è valido, mentre `s.evar1 = 'Value'` non lo è.

## Plug-in

Alcune organizzazioni utilizzano i plug-in per migliorare la propria implementazione di  Adobe Analytics. Durante l&#39;aggiornamento delle versioni di AppMeasurement, non dimenticare di includere nuovamente i plug-in installati. Il codice creato in [!UICONTROL Code Manager] non contiene alcun codice plug-in. Crea una copia del codice esistente nel caso sia necessario ripristinare una versione precedente di AppMeasurement.

## Spazio vuoto nei valori variabili

In HTML ci sono diversi caratteri che creano spazi bianchi. Questi includono uno spazio, una scheda e un ritorno a capo (o avanzamento linea). Prendi in considerazione l’esempio seguente:

```html
<head>
  <title>
    Home Page
  </title>
</head>
<body>
<script language="javascript">
  s.pageName = document.title;
</script>
</body>
```

In questo caso, `document.title` compila `s.pageName`, che riceve il valore &quot;Home Page&quot;. Tuttavia, alcuni browser possono interpretare lo spazio bianco in modo diverso. Il risultato può essere uno dei due seguenti esempi:

```js
s.pageName = "Home Page";
```

```js
s.pageName = "        Home Page";
```

Questi due valori di variabile sono considerati separati in  Adobe Analytics. Tuttavia, lo spazio vuoto viene rimosso automaticamente a scopo di visualizzazione. Il risultato è un rapporto che mostra due voci apparentemente identiche di &quot;Home Page&quot;. Accertatevi che i valori delle variabili non contengano spazi prima o dopo il valore desiderato.

## Richieste di immagini troncate

Le implementazioni che popolano molte variabili con valori lunghi possono a volte essere eseguite in richieste di immagini troncate. Alcuni browser meno recenti, come Internet Explorer, impongono un limite di 2083 caratteri per gli URL delle richieste di immagini. Se l’organizzazione deve far fronte a richieste di immagini molto lunghe, provate quanto segue:

* **Utilizzate il servizio** ID Experience Cloud : Le librerie AppMeasurement 1.4.1 e versioni successive inviano automaticamente le richieste di immagine utilizzando POST HTTP se sono troppo lunghe. I dati inviati con questo metodo non vengono troncati indipendentemente dalla lunghezza. Per ulteriori informazioni, consulta il servizio [ID](https://docs.adobe.com/content/help/it-IT/id-service/using/home.html) Adobe Experience Cloud.
* **Usa regole** di elaborazione: [Le regole](/help/admin/admin/c-processing-rules/processing-rules.md) di elaborazione possono copiare i valori da una variabile all&#39;altra. Questo metodo consente di evitare di impostare lo stesso valore in più variabili. Ad esempio:

   Esegui sempre:<br>
Sovrascrivi il valore di prop1 con  eVar1<br>Sovrascrivi il valore di  eVar2 con  eVar1<br>Sovrascrivi il valore di prop2 con  eVar1<br>

   Quindi imposta  eVar1 nella tua implementazione:

   ```js
   s.eVar1 = "The quick brown fox jumps over the lazy dog";
   ```

* **Usa variabili** dinamiche: Se l’implementazione completa molte variabili con lo stesso valore, potete utilizzare variabili [](/help/implement/vars/page-vars/dynamic-variables.md) dinamiche per ridurre l’URL della richiesta:

   ```js
   s.eVar1 = "The quick brown fox jumps over the lazy dog";
   s.eVar2 = "D=v1";
   s.prop1 = "D=v1";
   s.prop2 = "D=v1";
   ```

* **Usa classificazioni**: Se i nomi di prodotto o pagina sono insolitamente lunghi, puoi usare un valore o un codice identificativo, quindi utilizzare [le classificazioni](/help/components/classifications/c-classifications.md) per visualizzare un nome più descrittivo.
