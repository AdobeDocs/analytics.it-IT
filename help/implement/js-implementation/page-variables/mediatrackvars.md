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


# Media.trackVars

La variabile identifica le variabili da inviare con un hit per file multimediali.

<!-- 

media_trackVars.xml

 -->

È applicabile solo con JavaScript e [!UICONTROL ActionSource].

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| N/D | N/D | N/D | s.Media.trackVars="None" |

**Sintassi e valori** possibili {#section_7374684A7EB34AE685E8C40A66CFD289}

Nomi di variabili quali [!UICONTROL propN], *`eVarN`*, *`events`*, *`channel`* e così via.

**Esempi** {#section_48653222ABA14AB0A3C4471659971FAA}

```js
s.Media.trackVars="prop2,events,eVar3"
```

**Insidie, domande e suggerimenti**{#section_615AE1B696124B00B78F651B03813EAB}

* Anche se eVar3 è specificato in [!UICONTROL trackVars], viene inviato con l’hit del supporto.

## dispositivi mobili {#concept_0CEE045F57B444138C0EAA015FC7EA70}

La variabile controlla l’ordine in cui i cookie e gli ID utente iscritto vengono utilizzati per identificare i visitatori.

<!-- 

mobile.xml

 -->

See [Mobile network protocols](/help/implement/js-implementation/c-additional-libraries/network-protocols.md).

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| N/D | /5/ o /1/ nel percorso dell'URL dell'immagine | N/D | Nessuno |

**Sintassi e valori** possibili {#section_7F1C58090C454882BA9D3D66C9263A76}

```js
s.mobile="any_string" //subscriber id used first, produces /5/ in path of image url 
s.mobile=""  // if set to an empty string or not set at all, cookies used first, produces /1/ in path of image url 
```

**Insidie, domande e suggerimenti**{#section_06CD5CB4EF1E4B9FBE3B9D1F18AAFA30}

Utilizzate l'identificazione cross-visitor per attenuare i possibili picchi nel traffico dei visitatori quando utilizzate la *`s.mobile`* variabile con l'implementazione dei cookie JavaScript.
