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


# server

La variabile viene utilizzata per mostrare il dominio di una pagina Web (per mostrare i domini a cui arrivano gli utenti) o il server che distribuisce la pagina (per un riferimento rapido per il bilanciamento del carico).

<!-- 

server.xml

 -->

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| 100 byte | server | Server | "" |

Se il sito contiene più domini che gestiscono lo stesso contenuto, la *`server`* variabile può essere utilizzata per tenere traccia dei domini che i visitatori utilizzano. Il seguente JavaScript comporrà il dominio della pagina nella variabile server.

```js
s.server=window.location.hostname
```

Se si utilizza la variabile server per fornire una guida rapida al bilanciamento del carico, è possibile inserire un nome o un numero di server nella variabile server. Vedere l'esempio seguente:

```js
s.server="server 14"
```

Anche se il [!UICONTROL Most Popular Servers] rapporto può essere utilizzato come riferimento rapido per il bilanciamento del carico, non è una misura precisa del carico del server. Ad esempio, il traffico del pulsante Indietro non aumenta il carico del server, ma viene mostrato nei rapporti. Il rapporto non mostra quali server trasmettono immagini o grandi download.

**Sintassi e valori** possibili {#section_48E4B9BFEBFF4409A246D86EC0C0FB13}

```js
s.server="server_name"
```

Non esistono limitazioni alla *`server`* variabile al di fuori delle limitazioni standard.

**Esempi** {#section_78B9EE3C27FB491384869E3D0BD503D6}

```js
s.server="server 18" 
s.server=window.location.hostname 
```

**Impostazioni** di configurazione {#section_969DB379D5BD469FBEE8D505D3000E49}

Nessuno

**Insidie, domande e suggerimenti**{#section_42A28F9B01574F38891D9D54B411D8FE}

La *`server`* variabile può essere utilizzata per mostrare quali domini sono più popolari o quali server servono più pagine.

