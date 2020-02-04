---
title: Risoluzione dei problemi di implementazione JavaScript
description: Informazioni su problemi comuni e procedure ottimali per la risoluzione dei problemi relativi all'implementazione JavaScript.
translation-type: tm+mt
source-git-commit: 8aa6932dcbb6dad88c27ba1cd4f5aad3bafcfc52

---


# Risoluzione dei problemi di implementazione JavaScript

Di seguito sono riportati diversi motivi per cui la tua organizzazione potrebbe avere problemi a ricevere correttamente i dati in Adobe Analytics.

## Utilizzo delle virgolette

La maggior parte delle variabili inviate ad Adobe sono stringhe. In JavaScript, è possibile utilizzare virgolette singole o doppie.

### Combinazione di virgolette per definire una variabile

Come procedura ottimale, accertatevi di essere coerenti con i tipi di virgolette utilizzati. Se una singola citazione indica l&#39;inizio di una stringa, per chiuderla è necessario utilizzare una singola citazione.

Ad esempio, entrambi `s.eVar1 = 'Value'` e `s.eVar1 = "Value"` sono validi. `s.eVar1 = 'Value"` non è valido.

### Inclusione di virgolette singole o doppie in una stringa

Talvolta è necessario includere una citazione singola o doppia in una stringa. Ad esempio, se desiderate includere il valore `Alex's sale` o `John the "Hunter"` nei rapporti. Esistono due metodi per includere i seguenti valori:

* **Utilizzare l&#39;altro tipo** di offerta:Ad esempio, `s.eVar1 = "Alex's sale"` e `s.eVar1 = 'John the "Hunter"'` sono entrambi validi.
* **Virgolette** di escape: Utilizzare una barra rovesciata per evitare le virgolette. Ad esempio, `s.eVar1 = 'Alex\'s sale'` e `s.eVar1 = "John the \"Hunter\""` sono entrambi validi.

### Evitate di usare virgolette inglesi

Alcuni programmi convertono automaticamente le virgolette (`"..."` e `'...'`) in virgolette`“...”` e `‘...’`). Evitate di utilizzare editor di documenti (come Microsoft Word) o di trasmettere snippet di codice tramite e-mail. Le virgolette inglesi non possono essere utilizzate in JavaScript.

## Riferimento all&#39;oggetto Analytics

Tutte le variabili inviate ad Adobe utilizzano l&#39;oggetto Analytics. La maggior parte delle implementazioni utilizza l&#39; `s` oggetto. Accertatevi che, quando fate riferimento a variabili, l&#39;oggetto Analytics sia incluso nel riferimento.

Ad esempio, `s.eVar1 = 'Value'` è valido, mentre `eVar1 = 'Value'` non lo è.

## Definisci ogni variabile una volta

Quando viene eseguita una funzione di tracciamento (`s.t()`), AppMeasurement prende tutte le variabili definite e le compila in una richiesta di immagine. Se si definisce una variabile più volte nell&#39;implementazione, viene utilizzato solo il valore più recente. Assicurarsi che tutti i valori delle variabili contengano il valore corretto durante l&#39;esecuzione della funzione track.

## Correggere la maiuscola variabile

Alcune variabili utilizzano lettere maiuscole. Le variabili JavaScript fanno distinzione tra maiuscole e minuscole. Quando si definiscono le variabili, assicurarsi di utilizzare le maiuscole/minuscole corrette. Ad esempio, `s.eVar1 = 'Value'` è valido, mentre `s.evar1 = 'Value'` non lo è.

## Plug-in

Alcune organizzazioni utilizzano i plug-in per migliorare la propria implementazione di Adobe Analytics. Durante l&#39;aggiornamento delle versioni di AppMeasurement, non dimenticare di includere nuovamente i plug-in installati. Il codice creato in [!UICONTROL Code Manager] non contiene alcun codice plug-in. Crea una copia del codice esistente nel caso sia necessario ripristinare una versione precedente di AppMeasurement.

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

Questi due valori di variabile vengono considerati separati in Adobe Analytics. Tuttavia, lo spazio vuoto viene rimosso automaticamente a scopo di visualizzazione. Il risultato è un rapporto che mostra due voci apparentemente identiche di &quot;Home Page&quot;. Accertatevi che i valori delle variabili non contengano spazi prima o dopo il valore desiderato.
