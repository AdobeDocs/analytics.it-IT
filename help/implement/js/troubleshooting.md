---
title: Risoluzione dei problemi relativi all’implementazione di JavaScript
description: Scopri i problemi comuni e le best practice per la risoluzione dei problemi di implementazione di JavaScript.
feature: Implementation Basics
exl-id: e7181e78-65bf-446d-8d5c-b47323dbec1d
role: Developer
source-git-commit: a40f30bbe8fdbf98862c4c9a05341fb63962cdd1
workflow-type: tm+mt
source-wordcount: '688'
ht-degree: 1%

---

# Risoluzione dei problemi relativi all’implementazione di JavaScript

Di seguito sono riportati diversi motivi per cui la tua organizzazione potrebbe riscontrare problemi nel recupero corretto dei dati in Adobe Analytics.

## Utilizzo delle virgolette

La maggior parte delle variabili inviate ad Adobe sono stringhe. In JavaScript è possibile utilizzare le virgolette singole o doppie.

### Combinazione di virgolette per definire una variabile

Come best practice, accertati di essere coerente con i tipi di virgolette utilizzati. Se una virgoletta singola indica l&#39;inizio di una stringa, è necessario utilizzare una virgoletta singola per chiuderla.

Ad esempio, sia `s.eVar1 = 'Value'` che `s.eVar1 = "Value"` sono entrambi validi. `s.eVar1 = 'Value"` non è valido.

### Inclusione di virgolette singole o doppie in una stringa

A volte è consigliabile includere una virgoletta singola o doppia in una stringa. Ad esempio, si desidera includere il valore `Alex's sale` o `John the "Hunter"` nei report. Esistono due metodi per includere questi valori:

* **Utilizzare l&#39;altro tipo di virgolette**: ad esempio, `s.eVar1 = "Alex's sale"` e `s.eVar1 = 'John the "Hunter"'` sono entrambi validi.
* **Virgolette di escape**: utilizza una barra rovesciata per eliminare le virgolette. Ad esempio, `s.eVar1 = 'Alex\'s sale'` e `s.eVar1 = "John the \"Hunter\""` sono entrambi validi.

### Evita l&#39;uso di virgolette

Alcuni programmi convertono automaticamente le virgolette neutre (`"..."` e `'...'`) in virgolette (`"..."` e `'...'`). Evitare di utilizzare editor di documenti (come Microsoft Word) o di trasmettere frammenti di codice tramite e-mail. Non è possibile utilizzare le virgolette curve in JavaScript.

## Fare riferimento all&#39;oggetto Analytics

Tutte le variabili inviate ad Adobe utilizzano l’oggetto Analytics. La maggior parte delle implementazioni utilizza l&#39;oggetto `s`. Assicurati che quando fai riferimento a variabili includi l’oggetto Analytics nel tuo riferimento.

`s.eVar1 = 'Value'` ad esempio è valido, mentre `eVar1 = 'Value'` non lo è.

## Definisci ogni variabile una volta

Quando viene eseguita una funzione di traccia (`s.t()`), AppMeasurement prende tutte le variabili definite e le compila in una richiesta di immagine. Se definisci una variabile più di una volta nell’implementazione, viene utilizzato solo il valore più recente. Assicurati che tutti i valori delle variabili contengano il valore corretto quando la funzione di tracciamento viene eseguita.

## Correggi maiuscole/minuscole variabili

Alcune variabili utilizzano lettere maiuscole. Le variabili di JavaScript fanno distinzione tra maiuscole e minuscole. Assicurati di usare le maiuscole/minuscole corrette quando definisci le variabili. `s.eVar1 = 'Value'` ad esempio è valido, mentre `s.evar1 = 'Value'` non lo è.

## Plug-in

Alcune organizzazioni utilizzano i plug-in per migliorare la propria implementazione di Adobe Analytics. Durante l’aggiornamento delle versioni di AppMeasurement, non dimenticare di includere nuovamente i plug-in installati. Il codice creato in [!UICONTROL Code Manager] non contiene codice plug-in. Crea una copia del codice esistente nel caso sia necessario ripristinare una versione precedente di AppMeasurement.

## Spazio vuoto nei valori delle variabili

In HTML sono disponibili diversi caratteri che creano spazi vuoti. Questi includono uno spazio, una tabulazione e un ritorno a capo (o avanzamento riga). Prendi in considerazione l’esempio seguente:

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

In questo caso, `document.title` compila `s.pageName`, che riceve il valore &quot;Home Page&quot;. Tuttavia, alcuni browser possono interpretare gli spazi vuoti in modo diverso. Il risultato può essere uno dei due esempi seguenti:

```js
s.pageName = "Home Page";
```

```js
s.pageName = "        Home Page";
```

Questi due valori delle variabili sono considerati separati in Adobe Analytics. Tuttavia, lo spazio vuoto viene rimosso automaticamente a scopo di visualizzazione. Il risultato è un report che visualizza due elementi di riga &quot;Home Page&quot; apparentemente identici. Assicurati che i valori delle variabili non contengano spazi prima o dopo il valore desiderato.

## Richieste di immagini troncate

Le implementazioni che popolano molte variabili con valori lunghi a volte possono causare richieste di immagini troncate. Alcuni browser meno recenti, come Internet Explorer, impongono un limite di 2083 caratteri per gli URL di richiesta delle immagini. Se l’organizzazione deve far fronte a richieste di immagini molto lunghe, prova quanto segue:

* **Utilizza il servizio Experience Cloud ID**: le librerie AppMeasurement 1.4.1 e versioni successive inviano automaticamente le richieste di immagini tramite HTTP POST se sono troppo lunghe. I dati inviati con questo metodo non vengono troncati, a prescindere dalla lunghezza. Per ulteriori informazioni, consulta [Servizio Adobe Experience Cloud ID](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=it).
* **Usa regole di elaborazione**: [Le regole di elaborazione](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules.md) possono copiare i valori da una variabile a un&#39;altra. Questo metodo evita di impostare lo stesso valore in più variabili. Ad esempio:

  Esegui sempre:<br>
Sovrascrivi il valore di prop1 con eVar1<br>
Sovrascrivi il valore di eVar2 con eVar1<br>
Sovrascrivi il valore di prop2 con eVar1<br>

  Quindi imposta eVar1 nella tua implementazione:

  ```js
  s.eVar1 = "The quick brown fox jumps over the lazy dog";
  ```

* **Utilizza variabili dinamiche**: se l&#39;implementazione popola molte variabili con lo stesso valore, puoi utilizzare [variabili dinamiche](/help/implement/vars/page-vars/dynamic-variables.md) per ridurre l&#39;URL della richiesta:

  ```js
  s.eVar1 = "The quick brown fox jumps over the lazy dog";
  s.eVar2 = "D=v1";
  s.prop1 = "D=v1";
  s.prop2 = "D=v1";
  ```

* **Usa classificazioni**: se i nomi di prodotti o pagine sono insolitamente lunghi, puoi utilizzare un valore o un codice identificativo, quindi utilizzare [classificazioni](/help/components/classifications/classifications-overview.md) per visualizzare un nome più descrittivo.
