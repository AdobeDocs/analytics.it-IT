---
title: Regole dei set di classificazione
description: Scopri come utilizzare le regole dei set di classificazione per definire regole per i dati di classificazione.
feature: Classifications
hide: true
hidefromtoc: true
source-git-commit: 6ae2bbd1ea268524f852fecda88e9d2e237d496a
workflow-type: tm+mt
source-wordcount: '1573'
ht-degree: 11%

---


# Regole dei set di classificazione

Utilizza le regole per supportare le classificazioni automatiche in scenari in cui la dimensione chiave cambia costantemente. L’aggiornamento delle classificazioni tramite il caricamento o l’automazione diventa un processo complicato o ritarda la classificazione corretta per i nuovi valori di dimensione. Ad esempio, campagne interne, codici di tracciamento o SKU di prodotto. La dimensione deve contenere valori che ti consentono di applicare una o più regole in modo da poter derivare i dati di classificazione dai valori.

Puoi definire le regole nel contesto di un set di classificazione. Questo contesto implica che le regole vengano applicate (se attivate) a tutte le combinazioni di suite di rapporti e dimensioni chiave sottoscritte al set di classificazione. Questa implementazione è leggermente diversa da come funziona il generatore di regole di classificazione legacy. Nel generatore di regole di classificazione, definisci separatamente una o più regole come parte di un set di regole, quindi associa il set di regole a una o più suite di rapporti. Nella nuova interfaccia, le regole all’interno del set di classificazione sono anche denominate set di regole. Tuttavia, i set di regole sono definiti all’interno della stessa interfaccia in cui puoi configurare altri attributi del set di classificazione.


Per definire un set di regole per un set di classificazione:

1. Seleziona **[!UICONTROL Components]** dalla barra dei menu superiore di Adobe Analytics, quindi seleziona **[!UICONTROL Classification sets]**.
1. In **[!UICONTROL Classification Sets]**, selezionare la scheda **[!UICONTROL Classification Sets]**.
1. Nel gestore **[!UICONTROL Classifications Sets]**, selezionare il set di classificazione per il quale si desidera definire le regole.
1. Nella finestra di dialogo **[!UICONTROL Classification Set: _nome set di classificazione_]**, seleziona la scheda **[!UICONTROL Rules]**.

   * Se accedi all&#39;interfaccia **[!UICONTROL Rules]** per la prima volta per un set di classificazione o decidi di continuare a utilizzare l&#39;interfaccia del generatore di regole legacy, viene visualizzata una finestra di dialogo che consente di selezionare come iniziare. Le opzioni sono:

      * **Esegui migrazione regole esistenti**. Importa le regole di classificazione correnti e continua a lavorare con queste regole nella nuova interfaccia. Le regole esistenti vengono mantenute e convertite nel nuovo formato.
         * Seleziona **[!UICONTROL Migrate rules]** (Avanti) per continuare.
         * Nella finestra di dialogo **[!UICONTROL Confirm migration]**, leggi le implicazioni della migrazione.
            * Selezionare **[!UICONTROL Migrate rules]** per confermare la migrazione. Al termine della migrazione, utilizzare l&#39;[interfaccia set di regole](#rule-set-interface) per creare nuove regole e modificare le regole di cui è stata eseguita la migrazione.
            * Seleziona **[!UICONTROL Cancel]** per annullare la migrazione

      * **Ricomincia**. Crea nuove regole di classificazione da zero utilizzando il nuovo generatore di regole. Seleziona questa opzione se desideri riprogettare la logica di classificazione o iniziare da capo con nuove regole di classificazione.
         * Seleziona **[!UICONTROL Create new rules]** (Avanti) per continuare.
         * Nella finestra di dialogo **[!UICONTROL Confirm start fresh]**, leggi le implicazioni di un nuovo inizio.
            * Selezionare **[!UICONTROL Start fresh]** per confermare un nuovo avvio ed eliminare eventuali regole esistenti. Utilizza l&#39;interfaccia [set di regole](#rule-set-interface) per creare nuove regole.
            * Seleziona **[!UICONTROL Cancel]** per annullare.


      * **Usa interfaccia legacy**. Continua a utilizzare la precedente interfaccia del generatore di regole. Puoi migrare alla nuova esperienza in qualsiasi momento quando sei pronto.
         * Seleziona **[!UICONTROL Go to legacy interface]** per continuare. Si è indirizzati all&#39;interfaccia legacy **[!UICONTROL Classification Rule Builder]**.

   * Se hai già eseguito la migrazione delle regole o ne hai create di nuove per un set di classificazione, finisci direttamente nell’interfaccia del set di regole.



## Interfaccia set di regole {#rule-set-interface}

>[!CONTEXTUALHELP]
>id="classificationsets_rules_samplekeys"
>title="Chiavi di esempio"
>abstract="Digita o incolla le chiavi di test per testare il set di regole. Ogni riga è un valore chiave separato. Selezionare **[!UICONTROL Test Ruleset]** per visualizzare una finestra di dialogo con i risultati."


Per creare o modificare le regole, utilizza l’interfaccia Set di regole.

![Interfaccia set regole](assets/rulesets-ui.png)

| | Nome | Descrizione |
|---|---|---|
| 1 | **[!UICONTROL Functions]** | Utilizza l&#39;area **[!UICONTROL Functions]** per selezionare e trascinare le funzioni nel generatore di set di regole. |
| 2 | **Generatore set di regole** | Puoi creare il set di regole utilizzando una o più regole. Una regola è l’implementazione di una funzione e sempre associata a una sola funzione. Una funzione può avere più operatori. Per creare una regola, devi trascinare una funzione nel generatore di set di regole. Il tipo di funzione definisce l’interfaccia della regola. <br/>Per ulteriori informazioni, vedere [Interfaccia regola](#rule-interface).<br/>È possibile inserire funzioni in qualsiasi luogo e le funzioni vengono eseguite in sequenza per determinare i valori finali per le classificazioni.<br/>Utilizzare **[!UICONTROL Collapse all]** per comprimere tutte le regole e **[!UICONTROL Expand all]** per espandere tutte le regole. |
| 3 | **[!UICONTROL Status]** | Mostra lo stato e la data dell’ultima modifica del set di regole. <br/>Selezionare **[!UICONTROL Activate]** per attivare il set di regole. <br/>Selezionare **[!UICONTROL Deactivate]** per disattivare il set di regole. |
| 4 | **[!UICONTROL Lookback]** | Specifica l’intervallo di lookback per il set di regole.<br/>Selezionare un&#39;opzione (da 1 a 6 mesi) dal menu a discesa.<br/>Selezionare **[!UICONTROL Perform lookback]** per eseguire un lookback utilizzando il periodo di lookback selezionato. |
| 5 | **[!UICONTROL Test options]** | Utilizza valori di dimensione chiave di esempio per testare le classificazioni: <ul><li>Aggiungere o incollare valori nell&#39;area di testo **[!UICONTROL Sample keys]**.<br/>Controllare **[!UICONTROL Remember sample keys]** per assicurarsi che le chiavi di esempio persistano in diversi utilizzi dell&#39;interfaccia del set di regole.</li><li>Seleziona **[!UICONTROL Test rule set]** per verificare il set di regole.</li></ul> |


## Interfaccia regola

Puoi definire ogni singola regola all’interno del set di regole nell’interfaccia Regola. L’interfaccia è costituita dai seguenti elementi:

![Interfaccia regola](assets/rule-ui.png)

| | Descrizione |
|---|---|
| 1 | Il nome della funzione selezionata e l&#39;input immesso per la funzione. |
| 2 | Input per la funzione selezionata. L&#39;input dipende dalla funzione selezionata. Ad esempio, per la funzione **[!UICONTROL Regular expression]**, l&#39;input è un&#39;espressione regolare. E per la funzione **[!UICONTROL Split]**, l&#39;input è un token. Immettere l&#39;input appropriato per la funzione specifica. Ad esempio, `^(.+)\:(.+)\:(.+)$` per un&#39;espressione regolare che identifica tre classificazioni in un codice campagna interno. |
| 3 | Ogni operazione imposta una classificazione specifica su un valore. <br/>Selezionare una classificazione dal menu a discesa **[!UICONTROL Set Classification]** e immettere un valore per **[!UICONTROL to]**. <br/>Utilizzare ![CrossSize400](/help/assets/icons/CrossSize400.svg) per eliminare un&#39;operazione dall&#39;elenco. |
| 4 | Selezionare ![Aggiungi](/help/assets/icons/Add.svg) **[!UICONTROL Add operation]** per aggiungere un&#39;operazione aggiuntiva alla funzione. |
| 5 | Selezionare ![ChevronDown](/help/assets/icons2/ChevronDown.svg) per comprimere la regola. Selezionare ![ChevronLeft](/help/assets/icons/ChevronLeft.svg) per espandere la regola.<br/>Selezionare ![CrossSize400](/help/assets/icons/CrossSize400.svg) per eliminare la regola. |

## Riferimento funzione

Per ciascuna funzione supportata, di seguito trovi i dettagli sui casi di utilizzo di input e di esempio richiesti.


### Inizia con...

Imposta una classificazione basata su un valore specifico a partire dal quale inizia la dimensione chiave.

+++ Dettagli 

#### Input richiesto

Immettere un valore per **[!UICONTROL Starts With]**. Ad esempio: `em`.

#### Caso d’uso

Definire una regola per assegnare `Email` come valore per la classificazione **[!UICONTROL Channel]** quando il valore per la dimensione chiave Internal Campaign inizia con `em` (ad esempio: `em:FY2025:Summer Sale`).

>[!BEGINTABS]

>[!TAB Regola]

![Regola - Inizia Con](assets/rule-startswith.png)

>[!TAB Risultati del test]

![Regola - Inizia Con I Risultati Del Test](assets/rule-startswith-test.png)

>[!ENDTABS]

+++



### Termina con...

Imposta una classificazione basata su un valore specifico con cui termina la dimensione chiave.

+++ Dettagli 

#### Input richiesto

Immettere un valore per **[!UICONTROL Ends With]**. Ad esempio: `2025`.

#### Caso d’uso

Definire una regola per assegnare `2025` come valore alla classificazione **[!UICONTROL Year]** quando il valore per la dimensione chiave Internal Campaign contiene `2025` (ad esempio: `em:Summer Sale:FY2025`).

>[!BEGINTABS]

>[!TAB Regola]

![Regola - Termina Con](assets/rule-endswith.png)

>[!TAB Risultati del test]

![Regola - Termina Con Risultati Test](assets/rule-endswith-test.png)

>[!ENDTABS]

+++


### Contiene...

Imposta una classificazione basata su un valore specifico contenuto nella dimensione chiave.

+++ Dettagli 

#### Input richiesto

Immettere un valore per **[!UICONTROL Contains]**. Ad esempio: `Winter`.

#### Caso d’uso

Definire una regola per assegnare `Winter Sale` come valore alla classificazione **[!UICONTROL Type]** quando il valore per la dimensione chiave Internal Campaign contiene `Winter` (ad esempio: `fb:Winter:FY2024`).


>[!BEGINTABS]

>[!TAB Regola]

![Regola - Contiene](assets/rule-contains.png)

>[!TAB Risultati del test]

![Regola - Contiene Risultati](assets/rule-contains-test.png)

>[!ENDTABS]

+++


### Corrisponde

Imposta una classificazione basata su un valore specifico che corrisponde al valore della dimensione chiave.

+++ Dettagli 

#### Input richiesto

Immettere un valore per **[!UICONTROL Matches]**. Ad esempio: `em:Summer:2025`.

#### Caso d’uso

Definire una regola per assegnare `Email` come valore alla classificazione **[!UICONTROL Channel]**, `Summer Sale` come valore alla classificazione **[!UICONTROL Type]** e `2025` alla classificazione **[!UICONTROL Year]**. Ma solo quando il valore della dimensione chiave Internal Campaign corrisponde a `em:Summer:2025`.


>[!BEGINTABS]

>[!TAB Regola]

![Regola - Corrisponde](assets/rule-matches.png)

>[!TAB Risultati del test]

![Regola - Corrisponde](assets/rule-matches-test.png)

>[!ENDTABS]

+++


### Espressione regolare

Imposta una o più classificazioni basate su un’espressione regolare applicata al valore della dimensione chiave.

+++ Dettagli 

#### Input richiesto

Immettere un valore per **[!UICONTROL Regular Expression]**. Ad esempio: `^(.+)\:(.+)\:FY(.+)$`.

#### Caso d’uso

Definire una regola per assegnare valori alle classificazioni **[!UICONTROL Channel]**, **[!UICONTROL Type]** e **[!UICONTROL Year]** applicando l&#39;espressione regolare `^(.+)\:(.+)\:FY(.+)$` e utilizzando i gruppi di corrispondenza (`$1`, `$2` e `$3`) ai valori per la dimensione chiave Internal Campaign.

>[!BEGINTABS]

>[!TAB Regola]

![Regola - Espressione regolare](assets/rule-regex.png)

>[!TAB Risultati del test]

![Regola - Risultati test espressione regolare](assets/rule-regex-test.png)

>[!ENDTABS]

+++


### Suddivisione

Divide il valore della dimensione chiave, basato su un token, in una o più classificazioni.

+++ Dettagli

#### Input richiesto

Immettere un valore per **[!UICONTROL Split]**. Ad esempio: `:`.

#### Caso d’uso

Definire una regola che divida i valori per la dimensione chiave Internal Campaign nelle classificazioni **[!UICONTROL Channel]**, **[!UICONTROL Type]** e **[!UICONTROL Year]** in base alle `:` **[!UICONTROL Token]**.

>[!BEGINTABS]

>[!TAB Regola]

![Regola - Divisione](assets/rule-split.png)

>[!TAB Risultati del test]

![Regola - Risultati test suddivisi](assets/rule-split-test.png)

>[!ENDTABS]

+++


#### Tabella riferimenti {#section_0211DCB1760042099CCD3ED7A665D716}

| Espressione regolare | Descrizione |
|---|---|
| `(?ms)` | Confrontare l&#39;intera espressione regolare con un input su più righe, consentendo al carattere jolly `.` di corrispondere a qualsiasi carattere di nuova riga |
| `(?i)` | Fai in modo che l’intera espressione regolare non faccia distinzione tra maiuscole e minuscole |
| `[abc]` | Un carattere singolo tra: a, b o c |
| `[^abc]` | Qualsiasi carattere singolo tranne: a, b o c |
| `[a-z]` | Qualsiasi carattere singolo nell’intervallo a-z |
| `[a-zA-Z]` | Qualsiasi carattere singolo nell’intervallo a-z o A-Z |
| `^` | Inizio riga (corrisponde all’inizio della riga) |
| `$` | Corrisponde alla fine della riga (o prima della nuova riga alla fine) |
| `\A` | Inizio della stringa |
| `\z` | Fine della stringa |
| `.` | Corrispondenza con qualsiasi carattere (tranne una nuova riga) |
| `\s` | Qualsiasi carattere spazio vuoto |
| `\S` | Qualsiasi carattere tranne gli spazi vuoti |
| `\d` | Qualsiasi cifra |
| `\D` | Qualsiasi carattere tranne le cifre |
| `\w` | Qualsiasi carattere alfanumerico (lettera, numero, carattere di sottolineatura) |
| `\W` | Qualsiasi carattere non alfanumerico |
| `\b` | Qualsiasi confine di parola |
| `(...)` | Acquisire tutti i caratteri racchiusi tra parentesi |
| `(a\b)` | a o b |
| `a?` | Zero o uno di a |
| `a*` | Zero o più di uno di a |
| `a+` | Uno o più di a |
| `a{3}` | Esattamente 3 di a |
| `a{3,}` | 3 o più di a |
| `a{3,6}` | Tra 3 e 6 di a |

+++


## Priorità delle regole

L’ultima regola determina il valore per la classificazione se:

* Un valore di dimensione chiave corrisponde a più regole.
* Il set di regole contiene regole con la stessa operazione **[!UICONTROL Set Classification]**.

È quindi consigliabile classificare l&#39;operazione **[!UICONTROL Set Classification]** più importante come parte dell&#39;ultima regola del set di regole.

Se si creano più regole che non condividono la stessa operazione **[!UICONTROL Set Classification]**, l&#39;ordine di elaborazione non ha importanza.


### Esempio

Si desidera classificare con la classificazione **[!UICONTROL Type]** il modo in cui gli utenti cercano un atleta utilizzando la stringa di ricerca come dimensione chiave. Ad esempio, utilizzando questo set di regole:

![Priorità regole](assets/rule-priority.png)

* Quando un utente cerca `Cowboys Fantasy Tony Romo`, `Romo` è classificato come **[!UICONTROL Type]**.
* Quando un utente cerca `Cowboys Fantasy Tony Romeo`, `Fantasy` è classificato come **[!UICONTROL Type]**.
* Quando un utente cerca `Cowboys vs. Broncos`, `Team` è classificato come **[!UICONTROL Type]**.

