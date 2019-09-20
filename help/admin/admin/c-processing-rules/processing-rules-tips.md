---
description: Questa sezione contiene le linee guida per testare le regole di elaborazione e un elenco di errori comuni da evitare.
seo-description: Questa sezione contiene le linee guida per testare le regole di elaborazione e un elenco di errori comuni da evitare.
seo-title: Suggerimenti e trucchi per le regole di elaborazione
solution: Analytics
subtopic: Regole di elaborazione
title: Suggerimenti e trucchi per le regole di elaborazione
topic: Strumenti di amministrazione
uuid: e3a9ff8a-b81a-41c9-9f61-e40cb4bf7d99
translation-type: tm+mt
source-git-commit: f087c9255281023baa791cc181126046cfb94dc1

---


# Suggerimenti e trucchi per le regole di elaborazione

Questa sezione contiene le linee guida per testare le regole di elaborazione e un elenco di errori comuni da evitare.

## Regole di elaborazione dei test {#section_F092D2FECDE24082AE9FC6F8BE87F29F}

Questa sezione contiene alcune linee guida per il test delle regole di elaborazione prima che vengano distribuite in produzione.

**Verifica Di Regole Che Leggono I Termini Di Ricerca**

Per qualsiasi criterio basato su una ricerca, ad esempio se prop1 contiene "news", andate al report prop 1 e cercate "news" e verificate se ci sono delle partite che non vi aspettavate.

**Verifica delle regole per la lettura delle variabili**

Create una pagina HTML vuota sul desktop, includete il codice s_code dal sito e impostate la `s.account` variabile su una suite di rapporti dev. Se le regole sono basate su referente, dominio di riferimento e così via, prelevate alcuni URL di esempio dal rapporto referenti live, impostate la `s.referrer` variabile con uno di questi valori e caricate la pagina. Analogamente, se la regola è basata sul valore dell’URL della pagina, potete impostare `s.pageURL`. Lo stesso processo può essere utilizzato per qualsiasi variabile.

**Utilizzo di una suite di rapporti per sviluppatori**

Consigliamo di configurare le regole di elaborazione su una suite di rapporti dev per essere certi che funzionino correttamente. Se possibile, si consiglia di copiare le regole in una suite di rapporti per la produzione di piccole dimensioni prima dell'implementazione più ampia.

## Verifica valori vuoti {#section_EE84A5525E26415787930723B0CAAE0F}

Quando create una regola, considerate il caso in cui un valore è vuoto. Se non si aggiunge una condizione per la ricerca di un valore vuoto, è possibile sovrascrivere involontariamente le variabili con valori vuoti.

![](assets/tips-set-value-acquisition-code.png)

È inoltre importante considerare l'ordine di elaborazione. Nell'esempio seguente, se il Nome pagina non è presente, l'eVar personalizzato Nome pagina precedente viene impostato sull'URL. Tuttavia, l’URL viene inserito nel nome della pagina dopo l’applicazione delle regole di elaborazione; in questo caso, il nome pagina è vuoto se non è impostato sulla pagina.

![](assets/tips-copy-page-name-to-evar.png)

## Evita sovrascrittura Dei Valori {#section_49FCCA31E31A433EA2EF5EAF91443DAF}

Nell'esempio seguente, due variabili di dati contestuali vengono utilizzate sul sito per acquisire i termini di ricerca: search_keyword e search_term. Tuttavia, in base alla configurazione, il valore search_keyword viene sempre sovrascritto, anche se search_term è vuoto.

Questa regola deve essere riconfigurata per sottoporre a test ogni variabile di dati di contesto per un valore prima di compilare il Termine di ricerca interna e, facoltativamente, per concatenare i due valori, in caso di utilizzo per mantenerli entrambi.

![](assets/tips-search-keyword.png)

## Codifica i termini di ricerca in UTF-8 o Unicode {#section_3BBBE1FB8FEA48589362452DE51DB575}

I termini di ricerca estratti da una stringa di query devono essere codificati correttamente oppure non devono essere associati da regole di elaborazione.

![](assets/tips-multibyte.png)

## Inizia con, Contiene e termina con {#section_80CE853244FC435B844A09EA51868D8D}

Selezionare la condizione di corrispondenza corretta per trovare la condizione più restrittiva che corrisponde correttamente. È possibile cercare valori in un rapporto prima di creare una regola per essere sicuri che non ci siano corrispondenze non desiderate. Ad esempio, è necessario eseguire una ricerca nel report Prop2 per individuare tutte le posizioni in cui questa condizione corrisponde prima di abilitare questa regola.

![](assets/tips-startswith.png)

