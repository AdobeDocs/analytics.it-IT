---
description: Questa sezione contiene le linee guida per testare le regole di elaborazione e un elenco di errori comuni da evitare.
subtopic: Processing rules
title: Suggerimenti e trucchi per le regole di elaborazione
feature: Strumenti di amministrazione
uuid: e3a9ff8a-b81a-41c9-9f61-e40cb4bf7d99
exl-id: e663d98b-dcfd-4420-84ac-07ddfe55a3f2
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '492'
ht-degree: 8%

---

# Suggerimenti e trucchi per le regole di elaborazione

Questa sezione contiene le linee guida per testare le regole di elaborazione e un elenco di errori comuni da evitare.

## Regole di elaborazione dei test {#section_F092D2FECDE24082AE9FC6F8BE87F29F}

Questa sezione contiene alcune linee guida utili per testare le regole di elaborazione prima che vengano distribuite in produzione.

**Verifica delle regole che leggono i termini di ricerca**

Per qualsiasi criterio basato su una ricerca, ad esempio se prop1 contiene &quot;news&quot;, vai al report prop 1 e cerca &quot;news&quot; e vedi se ci sono corrispondenze che non ti aspettavi.

**Verifica delle regole per la lettura delle variabili**

Crea una pagina HTML vuota sul desktop, includi s_code dal sito e imposta la variabile `s.account` su una suite di rapporti per sviluppo. Se le tue regole sono basate su un referente, un dominio di riferimento e così via, preleva alcuni URL di esempio dal rapporto referenti live, imposta la variabile `s.referrer` con uno di questi valori e carica la pagina. Allo stesso modo, se la regola si basa sul valore dell&#39;URL della pagina, puoi impostare `s.pageURL`. Lo stesso processo può essere utilizzato per qualsiasi variabile.

**Utilizzo di una suite di rapporti per sviluppatori**

È consigliabile configurare le regole di elaborazione su una suite di rapporti per sviluppo per assicurarci che funzionino correttamente. Se possibile, è consigliabile copiare le regole in una suite di rapporti di produzione di piccole dimensioni prima di una distribuzione estesa.

## Verifica valori vuoti {#section_EE84A5525E26415787930723B0CAAE0F}

Quando crei una regola, considera il caso in cui un valore è vuoto. Se non aggiungi una condizione che verifica la presenza di un valore vuoto, puoi sovrascrivere involontariamente le variabili con valori vuoti.

![](assets/tips-set-value-acquisition-code.png)

È inoltre importante considerare l&#39;ordine di elaborazione. Nell’esempio seguente, l’eVar personalizzato Nome pagina precedente verrà impostato sull’URL se il Nome pagina non è presente. Tuttavia, l’URL viene inserito nel nome della pagina dopo l’applicazione delle regole di elaborazione; in questo caso, il nome pagina è vuoto se non è impostato sulla pagina.

![](assets/tips-copy-page-name-to-evar.png)

## Evita sovrascrittura dei valori {#section_49FCCA31E31A433EA2EF5EAF91443DAF}

Nell’esempio seguente, sul sito vengono utilizzate due variabili di dati di contesto per acquisire i termini di ricerca: search_keyword e search_term. Tuttavia, in base alla configurazione, il valore search_keyword viene sempre sovrascritto, anche se search_term è vuoto.

Questa regola deve essere riconfigurata per testare ogni variabile di dati di contesto per un valore prima di popolare il termine di ricerca interna e, facoltativamente, per concatenare i due valori, in caso di utilizzo per mantenerli entrambi.

![](assets/tips-search-keyword.png)

## Codifica dei termini di ricerca in UTF-8 o Unicode {#section_3BBBE1FB8FEA48589362452DE51DB575}

I termini di ricerca estratti da una stringa di query devono essere codificati correttamente o non devono essere associati da regole di elaborazione.

![](assets/tips-multibyte.png)

## Inizia con, contiene e termina con {#section_80CE853244FC435B844A09EA51868D8D}

Seleziona la condizione di corrispondenza corretta per trovare la condizione più restrittiva che corrisponde correttamente. È possibile cercare i valori in un rapporto prima di creare una regola per assicurarsi che non vi siano corrispondenze non desiderate. Ad esempio, è necessario cercare nel rapporto Prop2 tutte le posizioni in cui questa condizione corrisponde prima di abilitare questa regola.

![](assets/tips-startswith.png)
