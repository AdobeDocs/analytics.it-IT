---
title: Risoluzione dei problemi di implementazione JavaScript
description: Scopri i problemi comuni e le best practice per la risoluzione dei problemi dell’implementazione JavaScript.
feature: Implementation Basics
exl-id: e7181e78-65bf-446d-8d5c-b47323dbec1d
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '690'
ht-degree: 2%

---

# Risoluzione dei problemi di implementazione JavaScript

Di seguito sono riportati diversi motivi per cui l’organizzazione potrebbe avere problemi nel ricevere correttamente i dati in Adobe Analytics.

## Utilizzo delle virgolette

La maggior parte delle variabili inviate all&#39;Adobe sono stringhe. In JavaScript è possibile utilizzare virgolette singole o doppie.

### Combinazione di virgolette per definire una variabile

Come best practice, accertati di essere coerente con i tipi di virgolette utilizzati. Se una virgoletta singola indica l&#39;inizio di una stringa, per chiuderla è necessario utilizzare una singola virgolette.

Ad esempio, entrambi `s.eVar1 = 'Value'` e `s.eVar1 = "Value"` sono entrambi validi. `s.eVar1 = 'Value"` non è valido.

### Inclusione di virgolette singole o doppie in una stringa

A volte è necessario includere una virgoletta singola o doppia in una stringa. Ad esempio, si desidera includere il valore `Alex's sale` o `John the "Hunter"` nei rapporti. Esistono due metodi per includere questi valori:

* **Utilizza l&#39;altro tipo di preventivo**: Ad esempio: `s.eVar1 = "Alex's sale"` e `s.eVar1 = 'John the "Hunter"'` sono entrambi validi.
* **Virgolette di escape**: Utilizza una barra rovesciata per evitare virgolette. Ad esempio: `s.eVar1 = 'Alex\'s sale'` e `s.eVar1 = "John the \"Hunter\""` sono entrambi validi.

### Evita di utilizzare virgolette curvi

Alcuni programmi convertono automaticamente le virgolette neutre (`"..."` e `'...'`) tra virgolette graffe (`“...”` e `‘...’`). Evita di utilizzare editor di documenti (come Microsoft Word) o di trasmettere frammenti di codice tramite e-mail. Non è possibile utilizzare virgolette curve in JavaScript.

## Riferimento all’oggetto Analytics

Tutte le variabili inviate ad Adobe utilizzano l’oggetto Analytics . La maggior parte delle implementazioni utilizza le `s` oggetto. Assicurati che quando fai riferimento alle variabili, l&#39;oggetto Analytics sia incluso nel riferimento.

Ad esempio: `s.eVar1 = 'Value'` è valido, mentre `eVar1 = 'Value'` non lo è.

## Definisci ogni variabile una volta

Quando una funzione di tracciamento (`s.t()`) viene eseguita, AppMeasurement prende tutte le variabili definite e le compila in una richiesta di immagine. Se definisci una variabile più di una volta nell’implementazione, viene utilizzato solo il valore più recente. Assicurati che tutti i valori delle variabili contengano il valore corretto durante l&#39;esecuzione della funzione di tracciamento.

## Correzione della capitalizzazione delle variabili

Alcune variabili utilizzano lettere maiuscole. Le variabili JavaScript sono sensibili all’uso di maiuscole e minuscole. Assicurati di utilizzare il caso corretto quando definisci le variabili. Ad esempio: `s.eVar1 = 'Value'` è valido, mentre `s.evar1 = 'Value'` non lo è.

## Plug-in

Alcune organizzazioni utilizzano i plug-in per migliorare la loro implementazione di Adobe Analytics. Durante l&#39;aggiornamento delle versioni AppMeasurement, non dimenticare di includere nuovamente eventuali plug-in installati. Il codice creato in [!UICONTROL Code Manager] non ha alcun codice plug-in con esso. Crea una copia del codice esistente nel caso sia necessario ripristinare una versione precedente di AppMeasurement.

## Spazio vuoto nei valori variabili

In HTML sono presenti diversi caratteri che creano spazi bianchi. tra cui uno spazio, una scheda e un ritorno a capo (o avanzamento linea). Prendi in considerazione l’esempio seguente:

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

In questo caso, `document.title` popolato `s.pageName`, che riceve il valore di &quot;Home page&quot;. Tuttavia, alcuni browser possono interpretare lo spazio vuoto in modo diverso. Il risultato può essere uno dei due seguenti esempi:

```js
s.pageName = "Home Page";
```

```js
s.pageName = "        Home Page";
```

Questi due valori variabili sono considerati separati in Adobe Analytics. Tuttavia, lo spazio vuoto viene rimosso automaticamente a scopo di visualizzazione. Il risultato è un rapporto che mostra due voci di riga apparentemente identiche &quot;Home Page&quot;. Assicurati che i valori delle variabili non contengano spazi prima o dopo il valore desiderato.

## Richieste di immagini troncate

Le implementazioni che popolano molte variabili con valori lunghi a volte possono incorrere in richieste di immagini troncate. Alcuni browser meno recenti, come Internet Explorer, impongono un limite di 2083 caratteri per gli URL delle richieste di immagini. Se l&#39;organizzazione deve affrontare richieste di immagini molto lunghe, prova quanto segue:

* **Utilizzare il servizio Experience Cloud ID**: Le librerie AppMeasurement 1.4.1 e versioni successive inviano automaticamente richieste di immagini utilizzando HTTP POST se sono troppo lunghe. I dati inviati con questo metodo non vengono troncati indipendentemente dalla lunghezza. Vedi [Servizio Adobe Experience Cloud ID](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=it) per ulteriori informazioni.
* **Utilizzare le regole di elaborazione**: [Regole di elaborazione](/help/admin/admin/c-processing-rules/processing-rules.md) può copiare i valori da una variabile a un&#39;altra. Questo metodo ti consente di evitare di impostare lo stesso valore in più variabili. Ad esempio:

   Esegui sempre:<br>
Sovrascrivi il valore di prop1 con eVar1<br>
Sovrascrivi valore di eVar2 con eVar1<br>
Sovrascrivi il valore di prop2 con eVar1<br>

   Quindi imposta eVar1 nella tua implementazione:

   ```js
   s.eVar1 = "The quick brown fox jumps over the lazy dog";
   ```

* **Usa variabili dinamiche**: Se l&#39;implementazione popola molte variabili con lo stesso valore, puoi utilizzare [variabili dinamiche](/help/implement/vars/page-vars/dynamic-variables.md) per ridurre l’URL della richiesta:

   ```js
   s.eVar1 = "The quick brown fox jumps over the lazy dog";
   s.eVar2 = "D=v1";
   s.prop1 = "D=v1";
   s.prop2 = "D=v1";
   ```

* **Utilizzare le classificazioni**: Se i nomi di prodotto o pagina sono insolitamente lunghi, puoi utilizzare un valore o un codice di identificazione, quindi utilizzare [classificazioni](/help/components/classifications/c-classifications.md) per visualizzare un nome più descrittivo.
