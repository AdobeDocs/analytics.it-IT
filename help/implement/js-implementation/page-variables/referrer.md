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


# referrer

La variabile può essere utilizzata per ripristinare le informazioni di referente perse.

<!-- 

referrer.xml

 -->

I reindirizzamenti lato server e JavaScript sono spesso utilizzati per indirizzare i visitatori verso le posizioni corrette. Tuttavia, quando un browser viene reindirizzato, l'URL di provenienza originale viene perso.

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| 255 byte | R | Traffico &gt; Ricerca metodi Conversione &gt; Ricerca metodi | document.referrer |

Molte aziende utilizzano i reindirizzamenti in molti punti all'interno dei loro siti web. Ad esempio, un visitatore può essere inviato tramite un reindirizzamento da un motore di ricerca con risultati di ricerca a pagamento. Quando un browser viene reindirizzato, il referente viene spesso perso. La *`referrer`* variabile può essere utilizzata per ripristinare il *`referrer`* valore originale sulla prima pagina dopo un reindirizzamento. È *`referrer`* possibile compilare il file sul lato server o tramite JavaScript dalla stringa di query.

Affinché Analytics possa registrare un referente, deve essere "formato correttamente", ovvero deve seguire il formato URL standard, con un protocollo e una posizione appropriata.

**Sintassi e valori** possibili {#section_A0365D76789C4F4A959E81FE5A9D491D}

```js
s.referrer="URL"
```

Solo i valori compatibili con l’URL dovrebbero essere inclusi nel *`referrer`*. Verificate che la stringa sia codificata tramite URL (nessun spazio).

**Esempi** {#section_86FB1577670C4AA18BF3718F0832FCD4}

```js
s.referrer="https://www.google.com/search?q=search+string" 
s.referrer=<%=referrerVar%> // populated server-side  
if(s.getQueryParam('ref') 
s.referrer=s.getQueryParam('ref') 
```

**Impostazioni** di configurazione {#section_7AAEF28A7CBC446984F32C0659EFBF8D}

Nessuno

**Insidie, domande e suggerimenti**{#section_B42BF7FBA1094FF9805707FEA810CFE1}

Deve *`referrer`* avere l'aspetto di un URL standard e includere un protocollo.
