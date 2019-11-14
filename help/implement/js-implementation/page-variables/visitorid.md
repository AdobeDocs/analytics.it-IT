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


# visitorID

I visitatori possono essere identificati dalla variabile o dall'indirizzo IP/Agente utente.

<!-- 

visitorID.xml

 -->

I caratteri alfanumerici possono *`visitorID`* essere fino a 100 e non devono contenere un trattino.

Se imposti esplicitamente un ID personalizzato, verrà sempre utilizzato prima degli altri metodi ID.

Ordine di utilizzo: s.visitorID &gt; s_vi &gt; s_fid &gt; IP/UA.

| ** Dimensione massima* | ** Parametro debugger** | ** Report compilati** | ** Valore predefinito** |
|---|---|---|---|
| 100 byte | vid | n/d | "" |

**Sintassi e valori** possibili {#section_5F768C7AE6824557997E92B295C09280}

```js
s.visitorID="visitor_id"
```

> [!NOTE] La *`visitorID`* variabile non deve contenere un trattino.

**Esempi** {#section_F7F07FEFAC3644A5A084D166ACE1315E}

```js
s.visitorID="abc123"
```

**Impostazioni** di configurazione {#section_582B376FE55C4BCA8F978E0F62B5DB54}

Nessuno
