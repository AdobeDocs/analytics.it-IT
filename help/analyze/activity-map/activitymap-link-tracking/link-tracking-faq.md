---
description: Domande frequenti sul tracciamento dei collegamenti in Activity Map.
title: Domande frequenti sul tracciamento dei collegamenti
uuid: 10172073-b98b-4950-8397-67a18b37b3b4
feature: Activity Map
role: Business Practitioner, Administrator
exl-id: b6ccdf91-98ce-413f-842d-c5423598ed49
translation-type: tm+mt
source-git-commit: af3e4fc64085e94ec5616b8b6851a823e4954b36
workflow-type: tm+mt
source-wordcount: '513'
ht-degree: 1%

---

# Domande frequenti sul tracciamento dei collegamenti

Domande frequenti sul tracciamento dei collegamenti in Activity Map.

>[!CAUTION]
>
>Attivando il tracciamento di Activity Map, **è possibile che tu stia raccogliendo dati personali identificabili (PII).** Questi dati possono essere utilizzati da soli o con altre informazioni per identificare, contattare o individuare una singola persona o per identificare un individuo nel contesto.

Di seguito sono riportati alcuni casi noti in cui i dati PII potrebbero essere raccolti utilizzando il tracciamento di Activity Map:

* `Mailto` link. Un collegamento mailto è un tipo di collegamento HTML che attiva il client di posta elettronica predefinito sul computer per l’invio di un messaggio di posta elettronica.
* `User ID` collegamenti che possono essere visualizzati nell’intestazione/piè di pagina di un sito web dopo l’accesso dell’utente.
* Per gli istituti finanziari, il numero del conto può essere indicato come collegamento. Facendo clic su di esso verrà raccolto il testo del collegamento.
* I siti web sanitari possono anche avere dati PII mostrati come link. Facendo clic su questi collegamenti si raccoglierà il testo del collegamento, raccogliendo quindi dati PII.

## Quando si verifica il tracciamento dei collegamenti?

L’identificazione del collegamento e dell’area geografica di Activity Map si verifica quando gli utenti fanno clic su una pagina.

## Cosa viene tracciato per impostazione predefinita?

Se si verifica un evento di clic su un elemento, l’elemento deve superare alcuni controlli per determinare se AppMeasurement lo tratterà come un collegamento. Questi sono i controlli:

* Si tratta di un tag `A` o `AREA` con una proprietà `href`?
* Esiste un attributo `onclick` che imposta una variabile `s_objectID`?
* Si tratta di un tag `INPUT` o di un pulsante `SUBMIT` con un valore o un testo secondario?
* Si tratta di un tag `INPUT` con tipo `IMAGE` e una proprietà `src`?
* Si tratta di un `BUTTON`?

Se la risposta è Sì a una delle domande precedenti, l’elemento viene trattato come un collegamento e verrà tracciato.

>[!IMPORTANT]
>
>I tag pulsante con l’attributo type=&quot;button&quot; non sono considerati collegamenti da AppMeasurement. Prendi in considerazione la rimozione di type=&quot;button&quot; sui tag pulsante e l’aggiunta di role=&quot;button&quot; o submit=&quot;button&quot;.

>[!IMPORTANT]
>
>Un tag di ancoraggio con un &quot;href&quot; che inizia con &quot;#&quot; viene considerato un percorso di destinazione interno da AppMeasurement, non un collegamento (in quanto non si esce dalla pagina). Per impostazione predefinita, Activity Map non tiene traccia di queste posizioni di destinazione interne. Traccia solo i collegamenti che navigano verso una nuova pagina.

## In che modo Activity Map tiene traccia degli altri elementi HTML visivi?

a) Tramite la funzione `s.tl()`.

Se il clic si è verificato tramite una chiamata `s.tl()`, anche Activity Map riceverà questo evento click e determinerà se è stata trovata una variabile di stringa `linkName`. Durante l’esecuzione di `s.tl()`, linkName verrà impostato come ID collegamento di Activity Map. L’elemento su cui è stato fatto clic per la chiamata `s.tl()` viene utilizzato per determinare l’area. Esempio:

```
<img onclick="s.tl(true,'o','abc')" src="someimageurl.png"/>
```

b) Tramite la variabile `s_objectID`. Esempio:

    &quot;
    
    &lt;a>&lt;img>&lt;/a>
    
    &lt;a>Testo collegamento qui&lt;/a>
    
    
    &quot;

>[!IMPORTANT]
>
>È necessario un punto e virgola finale (;) quando si utilizza `s_objectID` in Activity Map.

## Potete fornirmi alcuni esempi di collegamenti che verranno tracciati?

* `<a hef="/home?lang=en>Home</a>`
* `<input type="submit" value="Submit"/>`
* `<input type="image" src="submit-button.png"/>`
* 

```
    <p onclick="var s_objectID='custom link id';">
      <span class="title">Current Market Rates</span>
      <span class="subtitle">1.45USD</span>
    </p>
```

* 

```
    <div onclick="s.tl(true,'o','custom link id')">
      <span class="title">Current Market Rates</span>
      <span class="subtitle">1.45USD</span>
    </div>
```

## Puoi fornirmi alcuni esempi di collegamenti che NON verranno tracciati?

1. Motivo: Il tag di ancoraggio non ha un `href` valido:
   `<a name="innerAnchor">Section header</a>`

1. Motivo: Non sono presenti né `s_ObjectID` né `s.tl()`:

   ```
   <p onclick="showPanel('market rates')">
     <span class="title">Current Market Rates</span>
     <span class="subtitle">1.45USD</span>
   </p>
   ```

1. Motivo: Non sono presenti né `s_ObjectID` né `s.tl()`:

   ``` 
   <input type="radio" onclick="changeState(this)" name="group1" value="A"/>
   <input type="radio" onclick="changeState(this)" name="group1" value="B"/>
   <input type="radio" onclick="changeState(this)" name="group1" value="C"/>
   
   ```  
   
1. Motivo: Nella proprietà &quot;src&quot; manca un elemento di input del modulo:

   `<input type="image"/>`
