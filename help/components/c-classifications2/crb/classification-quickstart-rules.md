---
description: Le regole di classificazione ricercano regolarmente i termini non classificati. Se viene trovata una corrispondenza di regole, le regole aggiungono automaticamente i termini alle tabelle di dati di classificazione. Potete inoltre utilizzare le regole di classificazione per sovrascrivere le chiavi esistenti.
seo-description: Le regole di classificazione ricercano regolarmente i termini non classificati. Se viene trovata una corrispondenza di regole, le regole aggiungono automaticamente i termini alle tabelle di dati di classificazione. Potete inoltre utilizzare le regole di classificazione per sovrascrivere le chiavi esistenti.
seo-title: Regole di classificazione
solution: Analytics
subtopic: Classificazioni
title: Regole di classificazione
topic: Strumenti di amministrazione
uuid: 08685919-216 d -448 b-b 886-3 adf 5 ff 5405 e
translation-type: tm+mt
source-git-commit: ecc762f73f9a303cebf48668b807fef9a2f055c5

---


# Regole di classificazione

Le regole di classificazione ricercano regolarmente i termini non classificati. Se viene trovata una corrispondenza di regole, le regole aggiungono automaticamente i termini alle tabelle di dati di classificazione. Potete inoltre utilizzare le regole di classificazione per sovrascrivere le chiavi esistenti.

## Classification rules {#concept_CF2F64BD96454FBFAA84638FC7DEA263}

Le regole di classificazione ricercano regolarmente i termini non classificati. Se viene trovata una corrispondenza di regole, le regole aggiungono automaticamente i termini alle tabelle di dati di classificazione. Potete inoltre utilizzare le regole di classificazione per sovrascrivere le chiavi esistenti.

**[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Classification Rule Builder]**

The Rule Builder lets you create a *`classification rule set`*, which is a list of *`classification rules`*. Una regola corrisponde ai criteri specificati, quindi esegue un'azione.

Le regole di classificazione sono utili per:

* **Annunci e-mail** e **display**: Create regole di classificazione per raggruppare singole campagne pubblicitarie di visualizzazione, in modo da poter ottenere le prestazioni delle campagne di visualizzazione rispetto alle campagne e-mail.

* **Codici di tracciamento**: Create regole di classificazione per categorizzare i valori chiave derivati dalle stringhe nei codici di tracciamento e associarli a criteri specifici definiti dall'utente.
* **Termini di ricerca**: Utilizzate [espressioni regolari](../../../components/c-classifications2/crb/classification-quickstart-rules.md#concept_8A63F9BCF9484963962E14E6286D312D) e caratteri jolly per semplificare la classificazione dei termini di ricerca. For example if a search term contains *`baseball`*, you can set a *`Sports League`* classification to *`MLB`*.

Ad esempio, supponiamo che un codice di tracciamento per un ID campagna e-mail sia:

`em:Summer:2013:Sale`.

Potete impostare tre regole in un set di regole che identifichi le parti della stringa e quindi classificare i valori:

| Seleziona tipo di regola | Inserire criteri di corrispondenza | Imposta classificazione | A |
|---|---|---|---|
| Inizia con | em: | Canale | E-mail |
| Termina con | Vendita | Type (Tipo) | Vendita |
| Contiene | 2013 | Anno | 2013 |

## How Rules Are Processed {#concept_A67A23F523844D37898583C632DB9D25}

Informazioni importanti sull'elaborazione delle regole di classificazione.

<!-- 

about_classification_rules.xml

 -->

* [Informazioni importanti sulle regole](/help/components/c-classifications2/crb/classification-rule-builder.md)
* [Quando Regole non classifica le chiavi?](/help/components/c-classifications2/crb/classification-rule-builder.md)
* [Informazioni sulla priorità regola](../../../components/c-classifications2/crb/classification-quickstart-rules.md#concept_93527FEB3C9B48FB96FB7DF857E5F980)

>[!NOTE]
>
>The [!UICONTROL Rule Builder] does not support Numeric 2 classifications.

## Important Information about Rules {#section_0BD46702FBEC4D98A4DD2EA0BD428046}

* Specify [group permissions](https://marketing.adobe.com/resources/help/en_US/reference/?f=groups) for classifications in [!UICONTROL Admin Tools].

* **Espressioni regolari**: La Guida è disponibile in [Espressioni regolari in Regole di classificazione](../../../components/c-classifications2/crb/classification-quickstart-rules.md#concept_8A63F9BCF9484963962E14E6286D312D).

* **Suite di rapporti**: Non è possibile scegliere una classificazione finché non viene selezionata almeno una suite di rapporti. Non potete applicare la suite di rapporti finché non avete creato il set di regole e assegnato una variabile.

   Quando sottoponete a test il set di regole, utilizzate le chiavi (la variabile in corso di classificazione) dal report per vedere come verranno influenzate dal set di regole. [(La chiave](../../../components/c-classifications2/c-classifications-importer/c-saint-data-files.md#concept_0B77B3079B5C414F9956058688990443) è la variabile in fase di classificazione o la prima colonna nella tabella di caricamento della classificazione.)

* **Priorità regola**: Se una chiave corrisponde a più regole che impostano la stessa classificazione (nella [!UICONTROL Set Classification] colonna), viene utilizzata l'ultima regola che corrisponde alla classificazione. See [About Rule Priority](../../../components/c-classifications2/crb/classification-quickstart-rules.md#concept_93527FEB3C9B48FB96FB7DF857E5F980).

* **Limiti per il numero di regole**: Non esiste alcun limite impostato per il numero di regole che puoi creare. Tuttavia, un numero elevato di regole può influire sulle prestazioni del browser.
* **Elaborazione**: Le regole vengono elaborate a intervalli frequenti, a seconda del volume di traffico correlato.

   Processo di regole attive ogni quattro ore, analizzando i dati di classificazione in genere un mese. Le regole verificano automaticamente nuovi valori e caricano le classificazioni utilizzando l'importazione.

* **Sovrascrivere le classificazioni esistenti**: Vedi [Quando regole non classifica chiavi?](../../../components/c-classifications2/crb/classification-quickstart-rules.md#section_4481E88CA28246B6B19EA16E2D83A3A8) Se necessario, potete eliminare o rimuovere le classificazioni esistenti utilizzando l'importazione.

## When Do Rules Not Classify Keys? {#section_4481E88CA28246B6B19EA16E2D83A3A8}

Quando attivate le regole, potete sovrascrivere le classificazioni esistenti. In the following situations, a classification rule does not classify a [key](../../../components/c-classifications2/c-classifications-importer/c-saint-data-files.md#concept_0B77B3079B5C414F9956058688990443)(variable) if:

* The key is already classified and you do not select [Overwrite Classifications](../../../components/c-classifications2/crb/classification-rule-definitions.md#overwrite_classifications).

   You can overwrite classifications when [adding and activating](../../../components/c-classifications2/crb/classification-quickstart-rules.md#task_86F216DFD2534FA181E64ABDF306782B) a rule, and when activating a data connectors integration. (For data connectors, rules are created by partners in the Dev Center and displayed in the [!UICONTROL Classification Rule Builder].)

* A classified key has not appeared in the data after a time frame specified when overwriting a key, even after you enable [Overwrite Classifications](../../../components/c-classifications2/crb/classification-rule-definitions.md#overwrite_classifications).
* The key is not classified and the key is never passed into [!DNL Adobe Analytics] after the time frame beginning about one month ago.

   >[!NOTE]
   >
   >Nei rapporti, le classificazioni si applicano a qualsiasi intervallo di tempo specificato, ogni volta che esiste una chiave. L'intervallo di date di un rapporto non influisce sui rapporti.

![](assets/overwrite_keys.png)

## Regular Expressions in Classification Rules {#concept_8A63F9BCF9484963962E14E6286D312D}

Utilizzate espressioni regolari per associare con una classificazione valori stringa formattati in modo coerente. Ad esempio, è possibile creare una classificazione da caratteri specifici in un codice di tracciamento. È possibile associare caratteri, parole o pattern particolari di caratteri.

<!-- 

regex_classification_rules.xml

 -->

* [Espressione regolare - Esempio di codice di tracciamento](../../../components/c-classifications2/crb/classification-quickstart-rules.md#section_2EF7951398EB4C2F8E52CEFAB4032669)
* [Espressione regolare - Classificazione di un carattere specifico](../../../components/c-classifications2/crb/classification-quickstart-rules.md#section_5D300C03FA484BADACBFCA983E738ACF)
* [Espressioni regolari - Codici di tracciamento corrispondenti di lunghezza variabile](../../../components/c-classifications2/crb/classification-quickstart-rules.md#section_E86F5BF5C2F44ABC8FFCE3EA67EE3BB2)
* [Espressioni regolari - «Non contiene» Esempio](../../../components/c-classifications2/crb/classification-quickstart-rules.md#section_FCA88A612A4E4B099458E3EF7B60B59C)
* [Espressioni regolari - Tabella di riferimento](../../../components/c-classifications2/crb/classification-quickstart-rules.md#section_0211DCB1760042099CCD3ED7A665D716)

>[!NOTE]
>
>Come procedura ottimale, le espressioni regolari sono particolarmente indicate per i codici di tracciamento che utilizzano i delimitatori.

## Regular Expression - Tracking Code Example {#section_2EF7951398EB4C2F8E52CEFAB4032669}

>[!NOTE]
>
>If the tracking code is URL encoded, it will **not** be classified by the Rules Builder.

In questo esempio, supponete di voler classificare il seguente ID campagna:

[!UICONTROL Sample Key]: `em:JuneSale:20130601`

Le parti del codice di tracciamento da classificare sono:

* `em` = e-mail
* `JuneSale` = nome campagna
* `20130601` = date

[!UICONTROL Regular Expression]: `^(.+)\:(.+)\:(.+)$`

Il modo in cui l'espressione regolare si riferisce all'ID della campagna:

![](assets/regex.png)

[!UICONTROL Match Groups]: Mostra come l'espressione regolare corrisponde ai caratteri ID campagna, in modo da poter classificare una posizione nell'ID della campagna.

![](assets/regex_tracking_code.png)

This example tells the rule that the campaign date `20140601` is at the third group `(.+)`, identified by `$3`.

** [!UICONTROL Rule Builder] **

In the [!UICONTROL Rule Builder], configure the rule as follows:

| Seleziona tipo di regola | Inserire criteri di corrispondenza | Imposta classificazione | A |
|---|---|---|---|
| Espressione regolare | &amp; amp; Cappello; (.+)\:(.+)\:(.+)$ | Data campagna | $3 |

**Sintassi**

| Espressione regolare | Stringa o Risultato corrispondenza | Corrispondenti gruppi corrispondenti |
|--- |--- |--- |
| `^(.+)\:(.+)\:(.+)$` | em: Junesale: 20130601 | `$0`: em: Junesale: 20130601 `$1`: em `$2`: Junesale `$3`: 20130601 |
| Creazione della sintassi | `^` = avvia la riga () = dei caratteri e consente di estrarre caratteri corrispondenti tra parentesi. `(.+)` = acquisisce uno (. ) e (+) qualsiasi altro valore\ = inizio di una stringa. `$` = indica che il carattere o il gruppo di caratteri precedente è l'ultimo nella riga. |

See [Regular Expressions - Reference Table](../../../components/c-classifications2/crb/classification-quickstart-rules.md#section_0211DCB1760042099CCD3ED7A665D716) for information about what the characters in a regular expression mean.

## Regular Expression - Classifying a Specific Character {#section_5D300C03FA484BADACBFCA983E738ACF}

Un modo per utilizzare un'espressione regolare consiste nel classificare un carattere specifico in una stringa di caratteri. Ad esempio, supponiamo che il seguente codice di tracciamento contenga due caratteri importanti:

[!UICONTROL Sample Key]: `4s3234`

* `4` = brand name
* `s` = identifica un motore di ricerca, ad esempio Google

![](assets/regex_char_position.png)

** [!UICONTROL Rule Builder] **

In the [!UICONTROL Rule Builder], configure the rule as follows:

| Seleziona tipo di regola | Inserire criteri di corrispondenza | Imposta classificazione | A |
|--- |--- |--- |--- |
| Espressione regolare | `^.(s).*$` | Marchio e motore | `$0` (acquisisce i primi due caratteri per il nome del marchio e il motore di ricerca.) |
| Espressione regolare | `^.(s).*$` | Motore di ricerca | `$1` (acquisisce il secondo carattere per Google.) |

## Regular Expressions - Matching Tracking Codes of Varying Length {#section_E86F5BF5C2F44ABC8FFCE3EA67EE3BB2}

Questo esempio mostra come identificare caratteri specifici tra i delimitatori di due punti quando si hanno codici di monitoraggio di lunghezze variabili. Adobe consiglia di utilizzare un'espressione regolare per ciascun codice di tracciamento.

Chiavi campione:

* `a:b`
* `a:b:c`
* `a:b:c:d`

**Sintassi**

![](assets/regex_b.png)

![](assets/regex_varying_length.png)

** [!UICONTROL Rule Builder] **

In the [!UICONTROL Rule Builder], configure the rule as follows:

| Seleziona tipo di regola | Inserire criteri di corrispondenza | Imposta classificazione | A |
|--- |--- |--- |--- |
| Espressione regolare Per la stringa di corrispondenza a: b | `^([^\:]+)\:([^\:]+)$` | a | `$1` |
| Espressione regolare Per la stringa di corrispondenza a: b | `^([^\:]+)\:([^\:]+)$` | b | `$2` |
| Espressione regolare Per la stringa di corrispondenza a: b: c | `^([^\:]+)\:([^\:]+)\:([^\:]+)$` | a | `$1` |
| Espressione regolare Per la stringa di corrispondenza a: b: c | `^([^\:]+)\:([^\:]+)\:([^\:]+)$` | b | `$2` |
| Espressione regolare Per la stringa di corrispondenza a: b: c | `^([^\:]+)\:([^\:]+)\:([^\:]+)$` | c | `$3` |
| Espressione regolare Per la stringa di corrispondenza a: b: c: d | `^([^\:]+)\:([^\:]+)\:([^\:]+)\:([^\:])$` | d | `$4` |

## Regular Expressions - "Does Not Contain" Example {#section_FCA88A612A4E4B099458E3EF7B60B59C}

This example provides a regular expression that matches any string that does not contain specific characters, in this case `13`.

Espressione regolare:

`^(?!.*13.*).*$`

Stringhe di test:

```
a:b:
a:b:1313
c:d:xoxo
c:d:yoyo
```

Risultati corrispondenza:

```
a:b:
c:d:xoxo
c:d:yoyo
```

In this result, `a:b:1313` does not indicate a match.

## Regular Expressions - Reference Table {#section_0211DCB1760042099CCD3ED7A665D716}

| Espressione | Descrizione |
|---|---|
| `(?ms)` | Fa corrispondere l'intera espressione regolare rispetto a un input multiriga, consentendo all'utente. carattere jolly per corrispondenza con i caratteri newline |
| (`?i`) | Non fa distinzione tra maiuscole e minuscole intere |
| [`abc`] | Un singolo carattere di: a, b o c |
| [`^abc`] | Qualsiasi carattere singolo tranne: a, b o c |
| [`a-z`] | Qualsiasi carattere singolo nell'intervallo a-z |
| [`a-zA-Z`] | Qualsiasi singolo carattere nell'intervallo a-z o A-Z |
| `^` | Inizio della riga (corrisponde all'inizio della riga) |
| `$` | Corrispondenza della fine della riga (o prima della nuova riga alla fine) |
| `\A` | Inizio della stringa |
| `\z` | Fine della stringa |
| `.` | Corrispondenza di qualsiasi carattere (tranne una nuova riga) |
| `\s` | Qualsiasi carattere whitespace |
| `\S` | Qualsiasi carattere non whitespace |
| `\d` | Qualsiasi cifra |
| `\D` | Qualsiasi non cifra |
| `\w` | Qualsiasi carattere parola (lettera, numero, carattere di sottolineatura) |
| `\W` | Qualsiasi carattere non Word |
| `\b` | Qualsiasi limite parola |
| `(...)` | Acquisisci tutto ciò che è incluso |
| `(a|b)` | a o b |
| `a?` | Zero o uno di uno |
| `a*` | Zero o più di un |
| `a+` | Uno o più di uno |
| `a{3}` | Esattamente il 3 di un |
| `a{3,}` | 3 o più di un |
| `a{3,6}` | Tra 3 e 6 di un |

Una buona risorsa per verificare la validità delle espressioni regolari è https://rubular.com/.

## About Rule Priority {#concept_93527FEB3C9B48FB96FB7DF857E5F980}

If a key is matched to multiple rules, and it sets the same classification column shown in the [!UICONTROL Set Classification] column, the last rule is used. Di conseguenza, potrebbe essere utile classificare l'ultimo importante nel set di regole.

<!-- 

rule_priority.xml

 -->

Se create più regole che non condividono la stessa classificazione, l'ordine di elaborazione non ha importanza.

Che cosa segue un esempio di regole di termine ricerca che classifica i tipi di ricerca per un atlgono:

| Numero regola | Tipo di regola | Corrispondenza | Imposta classificazione | A |
|---|---|---|---|---|
| 1 | Contiene | Cowboys | Tipo di ricerca | Team |
| 2 | Contiene | Fantasy | Tipo di ricerca | Fantasy |
| 3 | Contiene | Romo | Tipo di ricerca | Lettore |

If a user searches for *`Cowboys fantasy Tony Romo`*, the term *`Player`* is classified, because it matches the last given classification shown in the Set Classification column.

Analogamente, supponete di configurare due regole in un set per i seguenti termini di ricerca:

| Numero regola | Tipo di regola | Corrispondenza | Imposta classificazione | A |
|---|---|---|---|---|
| 1 | Contiene | Cowboys | Città | Dallas |
| 2 | Contiene | Broncos | Città | Denver |

A user searches for *`Cowboys vs. Broncos`*. Se il generatore di regole rileva un conflitto nella corrispondenza delle regole, la classificazione della seconda regola (Denver) viene applicata a questa ricerca.

## Add a Classification Rule to a Rule Set {#task_86F216DFD2534FA181E64ABDF306782B}

<!-- 

t_classification_rule.xml

 -->

Procedura che descrive come aggiungere o modificare una regola di classificazione.

Aggiungere regole facendo corrispondere una condizione a una classificazione e specificando l'azione.

>[!NOTE]
>
>In questa procedura, devi applicare le regole a una o più suite di rapporti. Il numero consigliato di regole per set di regole è compreso tra 500 e 1000, anche se non vi sono limiti. If you have over 100 rules, consider simplifying your rule set by using [sub-classifications](../../../components/c-classifications2/c-sub-classifications.md#concept_19EE5513A7DC43C38CC396E96F306CFE).

1. [Creare un set di regole di classificazione](../../../components/c-classifications2/crb/classification-rule-set.md#task_86F216DFD2534FA181E64ABDF306782B) .
1. On the rule set page, click **[!UICONTROL Add Rule]**.

   ![](assets/add_rule.png)

1. Next to **[!UICONTROL Report Suites]**, click **[!UICONTROL Add Suites]** to specify one or more report suites to assign to this rule set.

   The **[!UICONTROL Select Report Suites]** page displays.

   >[!NOTE]
   Report suites display on this page *`only`* when the following conditions are met:        &gt;

   * The report suites have at least one classification defined for that variable in [!UICONTROL Admin Tools].
   (See *`Variable`* in [Classification Rule Sets](../../../components/c-classifications2/crb/classification-rule-set.md#concept_CD3D510F5070486584F3BB535AE41524) for an explanation about this prerequisite.)

   * You selected the report suite on the **[!UICONTROL Available Report Suites]** page, which displays after you click [Add Rule Set](/help/components/c-classifications2/crb/classification-rule-set.md) to create the rule set.


1. Specificate se sovrascrivere i valori esistenti:

   | **Le regole sovrascrivono eventuali valori esistenti** | (Impostazione predefinita) Sovrascrive sempre le chiavi di classificazione esistenti, incluse le classificazioni caricate mediante l'importazione (SAINT). |
   |---|---|
   | **Le regole sovrascrivono solo i valori non impostati** | Riempire solo le celle vuote (non impostate). Le classificazioni esistenti non saranno modificate. |

1. [Definire la regola o le regole](../../../components/c-classifications2/crb/classification-rule-definitions.md#section_4A5BF384EEEE4994B6DC888339833529).

   ![Risultato passaggio](assets/classification_rules_page.png)

   For examples of building rules, see [Classifications Rule Builder](/help/components/c-classifications2/crb/classification-rule-builder.md) and [Regular Expressions in Classification Rules](../../../components/c-classifications2/crb/classification-quickstart-rules.md#concept_8A63F9BCF9484963962E14E6286D312D).

   >[!NOTE]
   >
   >Se una chiave corrisponde a più regole che impostano la stessa classificazione (nella colonna Imposta classificazione), viene utilizzata l'ultima regola che corrisponde alla classificazione. See **About Rule Priority** above for more information about sorting rules.

1. [Verificate il set di regole](../../../components/c-classifications2/crb/classification-quickstart-rules.md#task_618A1E7CC8664E728F312250E8367158).
1. After testing, click **[!UICONTROL Active]** to validate and activate the rule.

   L'attivazione di una regola crea automaticamente il file e lo carica automaticamente.

   Field definitions: See [Classification Rule Builder](../../../components/c-classifications2/crb/classification-rule-definitions.md#concept_6CAEFB1CA4564E2CA5808097C11EF468) for complete definitions of interface options on this page.

## Test a Classification Rule Set {#task_618A1E7CC8664E728F312250E8367158}

<!-- 

t_classifications_test_rule.xml

 -->

Procedura che descrive come sottoporre a test una regola di classificazione o un set di regole. L'esecuzione di un test verifica tutte le regole in un set.

1. [Creare un set di regole di classificazione](../../../components/c-classifications2/crb/classification-rule-set.md#task_86F216DFD2534FA181E64ABDF306782B) .
1. On the [!UICONTROL Classification Rule Builder], click the rule set name.
1. Assicurati che il set di regole sia associato a una suite di rapporti.
1. On the rule editor, click **[!UICONTROL Test Rule Set]**.

   ![Risultato passaggio](assets/classification_test_rule_set.png)

1. Type or paste test keys in the [!UICONTROL Sample Keys] field.

   Le chiavi campione includono:

   * Codici di tracciamento
   * Cercare parole chiave o frasi
   See [Regular Expressions in Classification Rules](../../../components/c-classifications2/crb/classification-quickstart-rules.md#concept_8A63F9BCF9484963962E14E6286D312D) for information about testing regular expressions.
1. Fai clic su **[!UICONTROL Run Test]**.

   Rules that match are displayed in the [!UICONTROL Results] table.
1. (Optional) Click **[!UICONTROL Activate]** to activate the rule, and to overwrite existing classifications.

   Per ulteriori informazioni sull'uso delle regole per sovrascrivere le classificazioni esistenti.

## Validate and Activate Classification Rules {#task_2B4FA41F1EE64F4AAC6170C5EFC066AC}

<!-- 

t_validate_rules.xml

 -->

Procedura che descrive come convalidare e attivare le regole di classificazione.

1. [Create un set](../../../components/c-classifications2/crb/classification-rule-set.md#task_86F216DFD2534FA181E64ABDF306782B) di regole di classificazione, quindi [aggiungete le regole](../../../components/c-classifications2/crb/classification-quickstart-rules.md#task_86F216DFD2534FA181E64ABDF306782B) di classificazione al set.
1. On the rule editor, click **[!UICONTROL Activate]**.

   ![](assets/overwrite_keys.png)

1. (Optional) To overwrite classifications, enable **[!UICONTROL Overwrite classifications for]** *`<selection>`*.

   Questa opzione consente di sovrascrivere le classificazioni esistenti per le chiavi interessate.

   See [Rules Page](../../../components/c-classifications2/crb/classification-rule-definitions.md#section_4A5BF384EEEE4994B6DC888339833529) for a definition of this option.
