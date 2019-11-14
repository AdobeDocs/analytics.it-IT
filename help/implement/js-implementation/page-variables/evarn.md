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


# eVarN

Le [!UICONTROL eVar] variabili vengono utilizzate per creare rapporti personalizzati.

<!-- 

eVarN.xml

 -->

Quando un eVar viene impostato su un valore per un visitatore, il valore viene memorizzato fino alla scadenza. Eventuali eventi di successo riscontrati da un visitatore mentre il valore eVar è attivo vengono conteggiati per il valore eVar.

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| 255 byte | V1-v75 ( [o v100 o v250](/help/implement/js-implementation/c-variables/page-variables.md)) | Conversione personalizzata | "" |

**Scadenza**{#section_6DB5882B960D4660AE248B91B76883C4}

[!UICONTROL eVars] scade dopo un periodo di tempo specificato. Dopo la scadenza dell'eVar, non riceve più credito per gli eventi di successo. Le eVar possono anche essere configurate per scadere in caso di eventi di successo. Ad esempio, se si dispone di una promozione interna che scade al termine di una visita, la promozione interna riceve credito solo per gli acquisti o le registrazioni che si verificano durante la visita in cui sono stati attivati.

Esistono due modi per scadere di un'eVar:

* Potete impostare la scadenza dell'eVar dopo un periodo di tempo o un evento specificato.
* È possibile utilizzare Forza scadenza di un'eVar, utile per riproporre una variabile.

Se un eVar viene utilizzato in maggio per riflettere le promozioni interne e scade dopo 21 giorni, e in giugno viene utilizzato per acquisire le parole chiave di ricerca interna, il 1 giugno è necessario forzare la scadenza o reimpostare la variabile. In questo modo, i rapporti di giugno consentiranno di mantenere i valori di promozione interni.

**Sensibilità** caso {#section_6E9145B7FCC2438E95BB35AAE3857412}

Le eVar non fanno distinzione tra maiuscole e minuscole, ma vengono visualizzate nelle maiuscole della prima occorrenza. Ad esempio, se la prima istanza di eVar1 è impostata su "Accesso", ma tutte le istanze successive vengono passate come "Accesso", i rapporti mostrano sempre "Accesso" come valore dell'eVar.

**Contatori**{#section_D8403F0C175E4BC9BE4F2E794B1F4D33}

Sebbene le eVar siano utilizzate più spesso per contenere valori stringa, possono anche essere configurate per fungere da contatori. Le eVar sono utili come contatori quando si tenta di contare il numero di azioni eseguite da un utente prima di un evento. Ad esempio, potete utilizzare un'eVar per acquisire il numero di ricerche interne prima dell'acquisto. Ogni volta che un visitatore effettua una ricerca, l'eVar deve contenere il valore '+1.' Se un visitatore effettua una ricerca quattro volte prima di un acquisto, verrà visualizzata un’istanza per ciascun conteggio totale: 1,00, 2,00, 3,00 e 4,00. Tuttavia, solo la versione 4.00 riceve credito per l'evento di acquisto (Metriche Ordini e Entrate). Solo i numeri positivi sono consentiti come valori di un contatore eVar.

**Sottorelazioni** {#section_2BEABBBC735241F4BA42E74D19B5AEE0}

Un requisito comune per un [!UICONTROL Custom eVar] rapporto è la possibilità di suddividere un [!UICONTROL Custom eVar] rapporto per un altro. Ad esempio, se una eVar contiene il genere e un'altra contiene lo stipendio, è possibile porre la seguente domanda: delle donne che hanno visitato il mio sito, quante entrate sono state generate dalle donne che guadagnano più di 50.000 dollari l'anno. Qualsiasi eVar completamente correlata consente questo tipo di suddivisione nei rapporti. Ad esempio, se per l'eVar per genere sono abilitate le sottorelazioni complete, tutti gli altri rapporti eVar personalizzati possono essere suddivisi per genere e il genere può essere suddiviso per tutti gli altri. Per visualizzare la relazione tra due rapporti, è necessario abilitare solo una delle due sottorelazioni complete. Per impostazione predefinita, [!UICONTROL Campaigns], [!UICONTROL Products]e [!UICONTROL Category] i rapporti sono completamente correlati sotto-livello (qualsiasi eVar può essere suddiviso per campagna o prodotti).

**Sintassi e valori** possibili {#section_BD46438B14F3488FB9AC42994C317B06}

Anche se le eVar possono essere rinominate, devono sempre essere indicate nel file JavaScript da eVarX, dove X è un numero compreso tra 1 e 75 ( [o 100 o 250](/help/implement/js-implementation/c-variables/page-variables.md)).

```js
s.eVarX="value"
```

Se non viene utilizzato come contatore, le eVar hanno le stesse limitazioni di tutte le altre variabili. Se l'eVar è un "contatore", si prevede che riceva valori numerici come "1" o "2.5". Se vengono date più di due posizioni decimali, il contatore eVar arrotonda a due posizioni decimali. Un contatore eVar non può contenere numeri negativi.

**Esempi** {#section_B37F4B0D56734DA3AB02BB218825BA4E}

```js
s.eVar1="logged in"
```

```js
s.eVar23="internal spring promo 4"
```

**Impostazioni** di configurazione {#section_BD1FE63001C84D3DB69F3DEE243960B6}

Le eVar possono essere configurate in [!UICONTROL Analytics > Admin > Report Suites > Edit Settings > Conversion > Conversion Variables]. Tutte le eVar possono essere configurate con un [!UICONTROL Name], [!UICONTROL Type], [!UICONTROL Allocation], [!UICONTROL Expire After Setting]o [!UICONTROL Reset]. Ogni impostazione di configurazione è indirizzata separatamente.

<table id="table_5C524B71520849FA8A9A6B79A3EE77C9"> 
 <thead> 
  <tr> 
   <th class="entry"> Impostazione </th> 
   <th class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> Nome </td> 
   <td> Consente di modificare il nome del rapporto eVar in <span class="keyword"> Analytics </span>. <p>Nel codice JavaScript deve essere sempre fatto riferimento all'eVarX come s.eVarX, indipendentemente dal nome assegnato al report in <span class="keyword"> Analytics </span>. </p> </td> 
  </tr> 
  <tr> 
   <td> Type (Tipo) </td> 
   <td> Consente di mostrare se l'eVar è una stringa di testo o un contatore. </td> 
  </tr> 
  <tr> 
   <td> Allocazione </td> 
   <td> Utilizzato per configurare quale valore dell'eVar riceve il credito per gli eventi di successo. <p>Se l'allocazione è impostata su "Most Recent (Last)", allora B riceve credito. </p> <p>Se l'opzione Allocazione è impostata su "Valore originale (primo)", A riceve credito. </p> <p>Se l'opzione Allocazione è impostata su "Lineare", sia A che B ricevono credito per metà del valore di acquisto. </p> </td> 
  </tr> 
  <tr> 
   <td> Scade dopo </td> 
   <td> Consente di determinare se un eVar scade in un evento specifico, come l'acquisto, o dopo un periodo di tempo personalizzato o predefinito. </td> 
  </tr> 
  <tr> 
   <td> Reset </td> 
   <td> Selezionando la <span class="wintitle"> casella di controllo Ripristina </span> per una eVar e facendo clic su <span class="wintitle"> Salva </span> nella parte inferiore della pagina, tutti i valori di tale eVar sono immediatamente scaduti. In seguito, solo i nuovi valori dell'eVar ricevono credito per gli eventi di successo. </td> 
  </tr> 
 </tbody> 
</table>

**Insidie, domande e suggerimenti**{#section_DA6912C802E445F986C6DE4234C6C737}

* A differenza delle [!UICONTROL prop] variabili, le variabili eVar non possono essere elenchi di valori delimitati. Se si compila un eVar con un elenco di valori, ad esempio "uno,due,tre", la stringa esatta verrà visualizzata nei report.
* I contatori eVar non possono contenere numeri negativi.
