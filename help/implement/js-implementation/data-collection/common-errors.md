---
description: Gli errori comuni negli account dinamici sono descritti nelle sezioni seguenti.
keywords: Analytics Implementation
solution: Analytics
subtopic: Troubleshooting
title: Errori comuni
topic: Developer and implementation
uuid: 04345355-60cc-4678-81c3-390c86752df1
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Errori comuni

Gli errori comuni negli account dinamici sono descritti nelle sezioni seguenti.

## Account codificato {#section_FB6F89BF317F45D387C00986ACA690BC}

Se si desidera inviare sempre i dati a una suite di rapporti specifica, impostare [!UICONTROL s_dynamicAccountSelection] su false (alternativamente, le variabili possono essere rimosse del tutto:

```js
var s_account="defaultreportsuiteid" 
REMOVE: s.dynamicAccountSelection=true 
REMOVE: s.dynamicAccountList="devreportsuite1=qa.client.com;reportsuite1=client.com" 
```

Nel caso precedente, defaultreportvaligeid viene sempre utilizzato dopo la rimozione delle altre due righe.

## Posizionamento del codice {#section_05375CB2EF5A414794BC8209C906AEEB}

La definizione *`s_account`* dopo le righe di codice non esclude la selezione dinamica dei conti, come illustrato di seguito.

```js
var s_account="defaultreportsuiteid" 
s.dynamicAccountSelection=true 
s.dynamicAccountList="devreportsuite1=qa.client.com;reportsuite1=client.com" 
s_account="anotherreportsuiteid" 
```

Nell'esempio precedente, l'account "altroreportvaligeid" ha la precedenza su "defaultreportsuite eid", ma non esclude alcuna corrispondenza che si verifichi in [!UICONTROL s.dynamicAccountList]. La funzione che valuta [!UICONTROL s.dynamicAccountList] viene in realtà eseguita molto più tardi nel file JS.

## Multi-Suite Tagging {#section_6C014FA9B87D4622B483BCDE4281D2A9}

I tag per più suite possono essere utilizzati insieme alla selezione account dinamica, come illustrato di seguito.

```js
s.dynamicAccountSelection=true 
s.dynamicAccountList="suiteid1,suiteid2=client.com" 
```

## Corrispondenza account dinamica {#section_647AB47B38D640D6BCC853FDA4E4342D}

Non inserire le [!UICONTROL dynamic account match] variabili tra virgolette. Le opzioni sono visualizzate di seguito.

| Nome host/dominio | Nessuno |
|---|---|
| Stringa di query | s.dynamicAccountMatch=(window.location.search?window.location.search:"?") |
| Host/Dominio e Percorso | s.dynamicAccountMatch=window.location.host+window.location.pathname |
| Percorso e stringa query | s.dynamicAccountMatch=window.location.pathname+(window.location.search?window.location.search""?") |
| URL completo | s.dynamicAccountMatch=window.location.href |

