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


# purchaseID

Viene utilizzato per impedire che un ordine venga conteggiato più volte nel reporting.

<!-- 

purchaseID.xml

 -->

Ogni volta che l’ [!UICONTROL purchase] evento viene utilizzato sul sito, dovreste utilizzare la *`purchaseID`* variabile.

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| 20 byte | purchaseID | Conversione &gt; Acquisti &gt; Conversione ricavi | "" |

Quando un visitatore acquista un elemento dal sito, *`purchaseID`* viene popolato sulla pagina "Grazie" nello stesso punto in cui viene attivato l’ [!UICONTROL purchase] evento. Se *`purchaseID`* viene compilato, i prodotti nella pagina "Grazie" vengono conteggiati una sola volta *`purchaseID`*. Questo è importante perché molti visitatori del sito salveranno la pagina di ringraziamento o di conferma per i propri scopi. Gli acquisti *`purchaseID`* vengono conteggiati ogni volta che viene visualizzata la pagina.

Oltre a impedire che i dati di acquisto vengano conteggiati due volte, *`purchaseID`* quando vengono utilizzati, tutti i dati di conversione vengono conteggiati due volte nei rapporti.

**Sintassi e valori** possibili {#section_E352CE2370D54BA69A368E1F63A9C32D}

```js
s.purchaseID="unique_id"
```

Deve *`purchaseID`* contenere un massimo di 20 caratteri ed essere in formato ASCII standard.

**Esempi** {#section_60A5C1EAF42F4611898CD6A4F4CF5A28}

```js
s.purchaseID="11223344" 
s.purchaseID="a8g784hjq1mnp3"
```

**Impostazioni** di configurazione {#section_1808631C96674380BF9C4A6D9A2C568E}

Nessuno

**Insidie, domande e suggerimenti**{#section_F5D010F234ED43F19AD1FCD2CD64E060}

La *`purchaseID`* variabile consente di contare tutte le variabili di conversione sulla pagina solo una volta nei rapporti.
