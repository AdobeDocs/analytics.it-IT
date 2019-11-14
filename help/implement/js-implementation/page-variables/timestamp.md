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


# timestamp

Questa variabile consente di personalizzare la marca temporale di un hit in modo simile alle librerie AppMeasurement per altre piattaforme.

<!-- 

timestamp.xml

 -->

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| 4 byte | Data/ora | Non segnalati direttamente. | Impostato dai server di raccolta dati. |

**Sintassi** {#section_1DF752B1202C4412A301AC7CC10874DF}

```js
s.timestamp="UNIX or ISO-8601 format timestamp"
```

La *`timestamp`* variabile deve essere nel formato descritto nella sezione successiva.

>[!IMPORTANT]
>
>Per poter usare la *`timestamp`* variabile, l'Assistenza clienti deve abilitare le marche temporali nella suite di rapporti. Una volta abilitato il supporto per le marche temporali, tutti gli hit inviati a questa suite di rapporti da JavaScript devono avere una marca temporale impostata manualmente (tramite *`s.timestamp`*), altrimenti gli hit non verranno registrati.
>
>Inoltre, se attivi il supporto delle marche temporali in una suite di rapporti per supportare il tracciamento offline, tutti gli hit inviati a questa suite di rapporti da JavaScript devono avere anche una marca temporale impostata manualmente (utilizzando *`s.timestamp`*). Non puoi inviare hit con marca temporale e non con marca temporale alla stessa suite di rapporti.
>
>Puoi anche utilizzare l’impostazione [Marca temporale](/help/implement/js-implementation/timestamps-overview.md)opzionale per combinare dati con marca temporale e senza marca nella stessa suite di rapporti globale, inviare dati con marca temporale da un’app mobile a una suite di rapporti globale e aggiornare le app per utilizzare marche temporali senza dover creare una nuova suite di rapporti.

**Formati** timestamp {#section_C12CBCECCD7047D38EF63A5800761CE9}

Le marche temporali devono essere in formato UNIX (in secondi dal 1° gennaio 1970) o ISO-8601, con le seguenti limitazioni al formato ISO-8601 accettato:

* Devono essere fornite sia la data che l'ora, separate da "T"
* La data deve essere una data di calendario con precisione completa (anno, mese e giorno). . Le date della settimana e quelle ordinali non sono supportate.
* La data può essere in formato standard o esteso ( `YYYY-MM-DD` o `YYYYMMDD`), ma deve includere l’ora e il minuto. I secondi sono facoltativi ( `HH:MM`, `HH:MM:SS`, `HHMM`o `HHMMSS`). È possibile trasmettere minuti e secondi frazionari, ma la parte frazionaria viene ignorata.

* Un fuso orario opzionale può essere specificato in formato standard o esteso ( `±HH`, `±HH:MM`, `±HH`, `±HHMM`o Z)

Le marche temporali UNIX continuano a essere supportate (secondi dal 1° gennaio 1970).

**Esempi** {#section_FA19C53D70DE4CF2AF259A5B968B84C3}

```js
s.timestamp=Math.round((new Date()).getTime()/1000);
```

```js
s.timestamp="2012-04-20T12:49:31-0700";
```

L'elenco seguente contiene esempi di marche temporali valide in formato ISO-8601:

```
2013-01-01T12:30:05+06:00 
2013-01-01T12:30:05Z 
2013-01-01T12:30:05 
2013-01-01T12:30
```

**Impostazioni** di configurazione {#section_5275D206F2CB4009B3681E8C4457124A}

Per poter utilizzare questa variabile, è necessario abilitare una suite di rapporti per accettare marche temporali personalizzate dall'Assistenza clienti. Una volta abilitate le marche temporali personalizzate, tutti gli hit inviati alla suite di rapporti devono contenere una marca temporale o vengono scartati.

**Insidie, domande e suggerimenti**{#section_EFDE8F67D13C4775A461E0B00D30AFD7}

* Le marche temporali sono utilizzate principalmente per tenere traccia dei dati offline sulle piattaforme mobili. Le marche temporali personalizzate sono generalmente disattivate, a meno che non raccogliiate sia dati app Web che offline nella stessa suite di rapporti.
* I dati vengono contrassegnati con marca temporale quando i dati offline sono abilitati nell’SDK per dispositivi mobili (impostazione predefinita) o quando una suite di rapporti è configurata per accettare i dati con marca temporale. I dati raccolti offline possono essere inviati ore o settimane dopo la data in cui si è verificato l'evento in origine. Questi hit possono essere messi in coda nella piattaforma Analytics per minuti o ore più a lungo degli hit senza marca temporale:

   * Per i dati con marca temporale inviati in tempi molto prossimi, il ritardo probabile è di 10-15 minuti.
   * Per i dati con marca temporale inviati da ieri, il probabile ritardo è di circa 2 ore.
   * Per i dati con marca temporale inviati in precedenza rispetto a ieri, ogni giorno aggiunge circa 2 ore di ritardo, fino a un massimo di 48 ore.

