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


# transactionID

[!UICONTROL Integration Data Sources] utilizzare [!UICONTROL transaction ID] per collegare i dati offline a una transazione online (come un lead o un acquisto generato online).

<!-- 

transactionID.xml

 -->

Ogni singolo *`transactionID`* inviato ad Adobe viene registrato in preparazione del [!UICONTROL Data Sources] caricamento di informazioni offline sulla transazione. Vedere [Origini](https://marketing.adobe.com/resources/help/en_US/sc/datasources/)dati.

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| 100 byte | esatto | n/d | "" |

**Abilita archiviazione** ID transazione {#section_3EA2C9DC9D4C4F0FBE4AB67981BCB52E}

Prima di registrare *`transactionID`* i valori, [!UICONTROL Transaction ID Storage] è necessario abilitare la suite di rapporti selezionata in Report Suite Manager. Questa impostazione si trova in

```
Analytics > Admin > Report Suites > Edit Settings > General > General Account Settings.
```

Per verificare se *`transactionID Storage`* è abilitata per una suite di rapporti, vai a

```
Analytics > Admin > Data Sources > Manage
```

**Sintassi e valori** possibili {#section_0C18329203DC45E989DBAE70C0FB4801}

```js
s.transactionID="unique_id"
```

I caratteri *`transactionID`* devono contenere solo caratteri alfanumerici. Se più [!UICONTROL transactionIDs] devono essere registrati in un singolo hit, è possibile utilizzare una virgola per delimitare più valori.

**Esempi** {#section_A4C1F0E54CB54AD7B86A22147E9B5FEF}

```js
s.transactionID="11123456"
```

```js
s.transactionID="lead_12345xyz"
```

```js
s.transactionID=s.purchaseID
```

**Insidie, domande e suggerimenti**{#section_4299BAD5D0154DBC88A9EF0E2C252BB4}

* Se *`transactionID`* la registrazione non è abilitata, *`transactionID`* i valori verranno scartati e non saranno utilizzabili con [!UICONTROL Integration Data Sources]. Assicurarsi di impostare una variabile di conversione o un evento (una eVar o la variabile eventi) sulla pagina in cui *`transactionID`* è impostata. In caso contrario, non viene registrato alcun dato per il *`transactionID`*.

* Se state registrando [!UICONTROL transactionIDs] per più sistemi, ad esempio acquisti e lead, accertatevi che il valore in *`transactionID`* sia sempre univoco. Questo può essere ottenuto aggiungendo un prefisso all’ID, ad esempio lead_1234 e purchase_1234. [!UICONTROL Integration Data Sources] non funzionano come previsto ( [!UICONTROL Data Source] i dati si collegano ai dati errati) se una univoca *`transactionID`* viene vista due volte.

* Per impostazione predefinita, *`transactionID`* i valori vengono conservati per 90 giorni. Se il processo di interazione offline supera i 90 giorni, contatta l'Assistenza clienti per richiedere la proroga del limite.

> [!NOTE] La *`transactionID`* variabile può contenere caratteri diversi da una virgola. Deve trovarsi nella stessa posizione in cui è specificato il limite di caratteri (100 byte). Se si utilizzano caratteri multibyte, è necessario abilitare il supporto dei caratteri multibyte per evitare problemi con i caratteri imprevisti nel *`transactionID`*.
