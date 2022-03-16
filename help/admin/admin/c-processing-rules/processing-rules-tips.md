---
description: Questa sezione contiene le linee guida per testare le regole di elaborazione e un elenco di errori comuni da evitare.
subtopic: Processing rules
title: Suggerimenti e trucchi per le regole di elaborazione
feature: Processing Rules
exl-id: e663d98b-dcfd-4420-84ac-07ddfe55a3f2
source-git-commit: 71b3b1937e7fa272f0497008e8e510204bbb4418
workflow-type: ht
source-wordcount: '490'
ht-degree: 100%

---

# Suggerimenti e trucchi per le regole di elaborazione

Questa sezione contiene le linee guida per testare le regole di elaborazione e un elenco di errori comuni da evitare.

## Regole di elaborazione del test {#section_F092D2FECDE24082AE9FC6F8BE87F29F}

Questa sezione contiene alcune linee guida utili per testare le regole di elaborazione prima che vengano distribuite in produzione.

**Verifica delle regole che leggono i termini di ricerca**

Per qualsiasi criterio basato su una ricerca, ad esempio se prop1 contiene “news”, vai al rapporto prop 1, cerca “news” e vedi se ci sono corrispondenze che non ti aspettavi.

**Verifica delle regole per la lettura delle variabili**

Crea una pagina HTML vuota sul desktop, includi l’s_code dal sito e imposta la variabile `s.account` su una suite di rapporti per lo sviluppo. Se le tue regole sono basate su referrer, dominio di riferimento e così via, prendi alcuni URL di esempio dal rapporto sui referrer live, imposta la variabile `s.referrer` con uno di questi valori e carica la pagina. Allo stesso modo, se la regola si basa sul valore dell’URL della pagina, puoi impostare `s.pageURL`. Questo processo può essere utilizzato per qualsiasi variabile.

**Utilizzo di una suite di rapporti per lo sviluppo**

Ti consigliamo di configurare le regole di elaborazione per una suite di rapporti per lo sviluppo per assicurarti che funzionino correttamente. Se possibile, è consigliabile copiare le regole in una piccola suite di rapporti di produzione prima di una distribuzione ampia.

## Verificare la presenza di valori vuoti {#section_EE84A5525E26415787930723B0CAAE0F}

Quando crei una regola, considera il caso in cui un valore è vuoto. Se non aggiungi una condizione che verifica la presenza di un valore vuoto, puoi sovrascrivere involontariamente le variabili con valori vuoti.

![](assets/tips-set-value-acquisition-code.png)

È inoltre importante considerare l’ordine di elaborazione. Nell’esempio seguente risulta che l’eVar personalizzata Previous pageName verrà impostata sull’URL se il nome pagina non è presente. Tuttavia, l’URL viene inserito nel nome della pagina dopo l’applicazione delle regole di elaborazione. In questo caso, il nome pagina è vuoto se non è impostato sulla pagina.

![](assets/tips-copy-page-name-to-evar.png)

## Evitare la sovrascrittura dei valori {#section_49FCCA31E31A433EA2EF5EAF91443DAF}

Nell’esempio seguente, sul sito vengono utilizzate due variabili di dati di contesto per acquisire i termini di ricerca: search_keyword e search_term. Tuttavia, in base alla configurazione, il valore search_keyword viene sempre sovrascritto, anche se search_term è vuoto.

Questa regola deve essere riconfigurata per testare ogni variabile di dati di contesto per un valore prima di popolare il termine di ricerca interna e, facoltativamente, concatenare i due valori, in caso si mantengano entrambi.

![](assets/tips-search-keyword.png)

## Codificare i termini di ricerca in UTF-8 o Unicode {#section_3BBBE1FB8FEA48589362452DE51DB575}

I termini di ricerca estratti da una stringa di query devono essere codificati correttamente o non verranno abbinati dalle regole di elaborazione.

![](assets/tips-multibyte.png)

## Inizia con, Contiene e Termina con {#section_80CE853244FC435B844A09EA51868D8D}

Seleziona la condizione di corrispondenza corretta per trovare la condizione più restrittiva che crei correttamente la corrispondenza. Puoi cercare i valori in un rapporto prima di creare una regola per assicurarti che non vi siano corrispondenze non desiderate. Ad esempio, è necessario cercare nel rapporto Prop2 tutte le posizioni in cui questa condizione corrisponde prima di abilitare questa regola.

![](assets/tips-startswith.png)
