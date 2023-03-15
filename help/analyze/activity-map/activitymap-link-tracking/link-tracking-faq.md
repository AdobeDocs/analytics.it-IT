---
description: Domande frequenti sul tracciamento dei collegamenti in Activity Map.
title: Domande frequenti sul tracciamento dei collegamenti
uuid: 10172073-b98b-4950-8397-67a18b37b3b4
feature: Activity Map
role: User, Admin
exl-id: b6ccdf91-98ce-413f-842d-c5423598ed49
source-git-commit: ac9e4934cee0178fb00e4201cc3444d333a74052
workflow-type: tm+mt
source-wordcount: '516'
ht-degree: 1%

---

# Domande frequenti sul tracciamento dei collegamenti

Domande frequenti sul tracciamento dei collegamenti in Activity Map.

>[!CAUTION]
>
>Attivando il tracciamento Activity Map, **è possibile che tu stia raccogliendo dati personali (PII).** Questi dati possono essere utilizzati da soli o con altre informazioni per identificare, contattare o individuare una singola persona o per identificare un individuo nel contesto.

Di seguito sono riportati alcuni casi noti in cui i dati PII potrebbero essere raccolti utilizzando il tracciamento Activity Map:

* `Mailto` collegamenti. Un collegamento mailto è un tipo di collegamento HTML che attiva il client di posta predefinito nel computer per l&#39;invio di un messaggio di posta elettronica.
* `User ID` collegamenti che possono essere visualizzati nell’intestazione/piè di pagina di un sito web dopo l’accesso dell’utente.
* Per gli istituti finanziari, il numero di conto può essere indicato come collegamento. Facendo clic su di esso verrà raccolto il testo del collegamento.
* I siti web dedicati al settore sanitario possono anche presentare dati PII sotto forma di collegamenti. Facendo clic su questi collegamenti verrà raccolto il testo del collegamento, con conseguente raccolta di dati PII.

## Quando si verifica il tracciamento dei collegamenti?

L’identificazione del collegamento Activity Map e dell’area geografica si verifica quando gli utenti fanno clic su una pagina.

## Cosa viene tracciato per impostazione predefinita?

Se si verifica un evento clic su un elemento, l’elemento deve superare alcuni controlli per determinare se AppMeasurement lo considererà come un collegamento. Questi sono i controlli:

* È un `A` o `AREA` tag con un `href` proprietà?
* Esiste un `onclick` attributo che imposta un `s_objectID` variabile?
* È un `INPUT` tag o `SUBMIT` con un valore o un testo figlio?
* È un `INPUT` tag con tipo `IMAGE` e un `src` proprietà?
* Si tratta di un `BUTTON`?

Se la risposta è Sì a una delle domande precedenti, l’elemento viene trattato come un collegamento e verrà tracciato.

>[!IMPORTANT]
>
>I tag di pulsanti con l’attributo type=&quot;button&quot; non sono considerati collegamenti da AppMeasurement. È consigliabile rimuovere type=&quot;button&quot; sui tag button e aggiungere role=&quot;button&quot; o submit=&quot;button&quot;.

>[!IMPORTANT]
>
>Un tag di ancoraggio con un &quot;href&quot; che inizia con &quot;#&quot; viene considerato da AppMeasurement come una posizione di destinazione interna, non come un collegamento (in quanto non si esce dalla pagina). Per impostazione predefinita, Activity Map non tiene traccia di queste posizioni di destinazione interne. Tiene traccia solo dei collegamenti che consentono di passare a una nuova pagina.

## In che modo l’Activity Map tiene traccia degli altri elementi di HTML visivi?

a. Tramite il `s.tl()` funzione.

Se il clic si è verificato tramite un `s.tl()` , l&#39;Activity Map riceverà anche questo evento di clic e determinerà se `linkName` variabile stringa trovata. Durante `s.tl()` esecuzione, il linkName verrà impostato come ID collegamento Activity Map. L’elemento su cui è stato fatto clic ha dato origine al `s.tl()` Per determinare la regione verrà utilizzata una chiamata. Esempio:

```
<img onclick="s.tl(true,'o','abc')" src="someimageurl.png"/>
```

b. Tramite il `s_objectID` variabile. Esempio:

    &quot; 
    
    &lt;img onclick=&quot;s_objectID=&amp;#39;abc&amp;#39;;&quot; src=&quot;someimageurl.png&quot; />
    &lt;a href=&quot;some-url.html&quot; onclick=&quot;s_objectID=&amp;#39;abc&amp;#39;;&quot;>
    Collega testo qui
    &lt;/a>
    
    &quot;

>[!IMPORTANT]
>
>È necessario un punto e virgola finale (;) quando si utilizza `s_objectID` in Activity Map.

## Puoi fornirmi alcuni esempi di collegamenti che verranno tracciati?

### Esempio 1

```
  <a hef="/home>Home</a>
```

### Esempio 2

```
 <input type="submit" value="Submit"/>
```

### Esempio 3

```
  <input type="image" src="submit-button.png"/>
```

### Esempio 4

```
    <p onclick="var s_objectID='custom link id';">
      <span class="title">Current Market Rates</span>
      <span class="subtitle">1.45USD</span>
    </p>
```

### Esempio 5

```
    <div onclick="s.tl(true,'o','custom link id')">
      <span class="title">Current Market Rates</span>
      <span class="subtitle">1.45USD</span>
    </div>
```

## Puoi fornirmi alcuni esempi di collegamenti che NON saranno tracciati?

1. Motivo: il tag di ancoraggio non ha un valore valido `href`:
   `<a name="innerAnchor">Section header</a>`

1. Motivo: nessuno `s_ObjectID` né `s.tl()` presente:

   ```
   <p onclick="showPanel('market rates')">
     <span class="title">Current Market Rates</span>
     <span class="subtitle">1.45USD</span>
   </p>
   ```

1. Motivo: nessuno `s_ObjectID` né `s.tl()` presente:

   ``` 
   <input type="radio" onclick="changeState(this)" name="group1" value="A"/>
   <input type="radio" onclick="changeState(this)" name="group1" value="B"/>
   <input type="radio" onclick="changeState(this)" name="group1" value="C"/>
   
   ```  
   
1. Motivo: nella proprietà &quot;src&quot; manca un elemento di input del modulo:

   `<input type="image"/>`

