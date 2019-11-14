---
description: Le variabili di pagina popolano direttamente un report, ad esempio pageName, List Props, List Variables e così via.
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: Variabili di pagina
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 45642bdbe18627caa20b1def6443f1e596a41f52

---



# Eventi

La variabile viene utilizzata per registrare eventi di successo comuni del carrello e eventi di successo personalizzati.

<!-- 

events.xml

 -->

<table id="table_9EB9D08C80544CD68C4B1A2012440472"> 
 <thead> 
  <tr> 
   <th class="entry"> Dimensioni massime </th> 
   <th class="entry"> Parametro debugger </th> 
   <th class="entry"> Report compilati </th> 
   <th class="entry"> Valore predefinito </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> Nessun limite </td> 
   <td> events </td> 
   <td> <p>Eventi carrello acquisti </p> <p>Eventi personalizzati </p> </td> 
   <td> N/D </td> 
  </tr> 
 </tbody> 
</table>

Un sito [!UICONTROL event] deve essere considerato una pietra miliare. Gli eventi di successo sono popolati più comunemente nella pagina finale di conferma di un processo, ad esempio un processo di registrazione o di registrazione alla newsletter. Gli eventi personalizzati sono definiti compilando la variabile degli eventi con i valori letterali definiti nella sezione Valori possibili riportata di seguito.

Per impostazione predefinita, gli eventi di successo sono configurati come eventi *contatore* . Gli eventi contatore contano il numero di volte in cui un evento di successo viene impostato (x+1). Gli eventi possono essere configurati anche come eventi *numerici* . Gli eventi numerici consentono di specificare il numero da incrementare (come potrebbe essere necessario quando si contano valori dinamici o arbitrari, ad esempio il numero di risultati restituiti da una ricerca interna).

Un tipo di evento finale, *valuta*, consente di definire l'importo da aggiungere (simile agli eventi numerici), ma viene visualizzato come valuta nei rapporti ed è soggetto a conversioni valutarie basate su s. valore *`currencyCode`* e impostazione della valuta predefinita per la suite di rapporti. Per ulteriori informazioni sull'utilizzo di eventi numerici e valutari, vedere [Prodotti](/help/implement/js-implementation/c-variables/page-variables.md).

**Configurazione della variabile**{#section_9195286C34C54B02B2598E2B856492C3}

La [!UICONTROL s.events] variabile è abilitata per impostazione predefinita per tutte le implementazioni. I sette eventi di conversione preconfigurati vengono automaticamente attivati per tutte le nuove suite di rapporti. I nuovi eventi personalizzati (event1- [event100 o event1000](/help/implement/js-implementation/c-variables/page-variables.md)) possono essere attivati da qualsiasi utente a livello di amministratore tramite Admin Console.

**Valori possibili**{#section_18395A3BEFEB4E9F8D7B2ED0001FBE4E}

Di seguito è riportato un elenco di valori possibili per la variabile event:

| Evento | Descrizione | Rapporti Popolato |
|---|---|---|
| all'evento | Visualizzazioni prodotto | Prodotti |
| scOpen | Aprire / Inizializzare un nuovo carrello | Carrelli |
| scAdd | Aggiungere elementi al carrello | Aggiunte carrello |
| scRemove | Rimuovere elementi dal carrello | Rimozioni carrello |
| scView | Visualizza carrello | Visualizzazioni carrello |
| scCheckout | Inizio del processo di estrazione | Pagamenti |
| purchase | Completamento di un acquisto (ordine) | Ordini |
| event1 - event1000 (event100 per il prodotto principale) | Eventi personalizzati | Eventi personalizzati |

**Sintassi ed esempi**{#section_45A159DF00114066B8551DDEB15E084C}

Gli eventi contatore vengono impostati posizionando gli eventi desiderati nella [!UICONTROL s.events] variabile, in un elenco separato da virgole (se devono essere passati più eventi).

```js
s.events="scAdd"
```

```js
s.events="scAdd,event1,event7"
```

```js
s.events="event5"
```

```js
s.events="purchase,event10"
```

Se nel codice H23 o superiore, agli eventi contatore possono essere assegnati numeri interi maggiori di uno.

```js
s.events="event1=10"
```

```js
s.events="scRemove=3,event6,event2=4"
```

Gli eventi contatore di implementazione con valori interi assegnati gestiscono l’evento come se fosse stato attivato più volte all’interno della richiesta di immagine. Gli eventi contatore non consentono i decimali. È consigliabile utilizzare gli eventi numerici invece se questa funzionalità è necessaria.
Gli eventi numerici e valutari devono essere inclusi nella [!UICONTROL s.events] variabile, anche se in genere ricevono il valore numerico (ad esempio, 24,99) nella [!UICONTROL s.products] variabile. Questo consente di collegare valori numerici e valutari specifici a singole voci di prodotto.

**Serializzazione degli eventi** {#section_A89488EF4471405AAFC4D6DD05E77621}

Per impostazione predefinita, un evento viene conteggiato ogni volta che l’evento viene impostato sul sito.

Per ulteriori informazioni, consultate Serializzazione [degli](/help/implement/js-implementation/event-serialization.md) eventi.

**Sintassi** {#section_8559D42D3F344AF3BB3C0125F78C4989}

```js
s.events="event1:3167fhjkah"
```

**Esempi** {#section_7B5B5728A59648ADB3E2548CDAD2C9D4}

```js
s.events="scAdd:003717174"
```

```js
s.events="scAdd:user228197,event1:577247280,event7:P7fhF8571"
```
