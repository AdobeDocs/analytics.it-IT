---
description: Questa sezione contiene le linee guida per testare le regole di elaborazione e un elenco di errori comuni da evitare.
seo-description: Questa sezione contiene le linee guida per testare le regole di elaborazione e un elenco di errori comuni da evitare.
seo-title: Suggerimenti e trucchi per le regole di elaborazione
solution: Analytics
subtopic: Regole di elaborazione
title: Suggerimenti e trucchi per le regole di elaborazione
topic: Strumenti di amministrazione
uuid: e 3 a 9 ff 8 a-b 81 a -41 c 9-9 f 61-e 40 cb 4 bf 7 d 99
translation-type: tm+mt
source-git-commit: 5a30ea6ac47ddd8612728e488afda868491a1ddc

---


# Suggerimenti e trucchi per le regole di elaborazione

Questa sezione contiene le linee guida per testare le regole di elaborazione e un elenco di errori comuni da evitare.

## Testing Processing Rules {#section_F092D2FECDE24082AE9FC6F8BE87F29F}

Questa sezione contiene alcune linee guida per testare le regole di elaborazione prima di essere distribuite in produzione.

**Regole di test che leggono Termini di ricerca**

Per qualsiasi criterio basato su una ricerca, ad esempio se prop 1 contiene «news», andate al rapporto prop 1 e cercate «news» e verificate che vi siano delle corrispondenze non previste.

**Regole di test che leggono variabili**

Create a blank HTML page on your desktop, include the s_code from your site, and set the `s.account` variable to a dev report suite. If your rules are based on referrer, referring domain, and so on, take some sample URLs from the live referrers report, set the `s.referrer` variable with one of those values and load the page. Likewise, if the rule is based on the page URL value, you can set `s.pageURL`. Lo stesso processo può essere utilizzato per qualsiasi variabile.

**Utilizzo di una suite di rapporti**

Consigliamo di configurare le regole di elaborazione in una suite di rapporti per accertarti che funzionino correttamente. Se possibile, consigliamo di copiare le regole in una piccola suite di rapporti di produzione prima dell'ampia distribuzione.

## Check for Empty Values {#section_EE84A5525E26415787930723B0CAAE0F}

Quando create una regola, prendete in considerazione il caso in cui un valore sia vuoto. Se non si aggiunge una condizione che verifica un valore vuoto, è possibile sovrascrivere involontariamente le variabili con valori vuoti.

![](assets/tips-set-value-acquisition-code.png)

È inoltre importante tenere in considerazione l'ordine di elaborazione. Nell'esempio seguente, l'evar personalizzato Nome pagina precedente sarà impostato sull'URL se il nome pagina non è presente. Tuttavia, l'URL viene inserito nel nome della pagina dopo l'applicazione delle regole di elaborazione; in questo caso, il nome pagina è vuoto se non è impostato sulla pagina.

![](assets/tips-copy-page-name-to-evar.png)

## Avoid Overwriting Values {#section_49FCCA31E31A433EA2EF5EAF91443DAF}

Nell'esempio seguente, sul sito sono utilizzate due variabili di dati di contesto per acquisire termini di ricerca: search_ keyword e search_ term. Tuttavia, in base alla configurazione, il valore di ricerca_ keyword viene sempre sovrascritto, anche se search_ term è vuoto.

Questa regola deve essere riconfigurata per testare ogni variabile di dati di contesto per un valore prima di compilare il termine di ricerca interno ed eventualmente, concatenare i due valori se esiste un caso d'uso per mantenerli entrambi.

![](assets/tips-search-keyword.png)

## Encode Search Terms to UTF-8 or Unicode {#section_3BBBE1FB8FEA48589362452DE51DB575}

I termini di ricerca prelevati da una stringa query devono essere codificati correttamente oppure non verranno associati dalle regole di elaborazione.

![](assets/tips-multibyte.png)

## Starts With, Contains, and Ends With {#section_80CE853244FC435B844A09EA51868D8D}

Selezionare la condizione di corrispondenza corretta per trovare la condizione più restrittiva che corrisponda correttamente. Potete cercare i valori in un rapporto prima di creare una regola per assicurarvi che non siano presenti corrispondenze indesiderate. Ad esempio, è necessario cercare il rapporto Prop 2 per trovare tutte le posizioni in cui questa condizione corrisponde prima di abilitare questa regola.

![](assets/tips-startswith.png)

