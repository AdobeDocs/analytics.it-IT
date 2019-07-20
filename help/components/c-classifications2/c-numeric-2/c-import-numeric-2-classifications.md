---
description: Il file di importazione ed esportazione include sei colonne per ciascuna classificazione numerica 2.
seo-description: Il file di importazione ed esportazione include sei colonne per ciascuna classificazione numerica 2.
seo-title: Importare classificazioni numeriche 2
solution: Analytics
subtopic: Classificazioni
title: Importare classificazioni numeriche 2
topic: Strumenti di amministrazione
uuid: 82 a 3034 c-e 002-4991-900 f -22 dd 45 d 54910
translation-type: tm+mt
source-git-commit: 49e149fe57d5d66b8eda22b1bdf60e7c6200761c

---


# Importare classificazioni numeriche 2

>[!IMPORTANT]
>
>La possibilità di importare le classificazioni Numeriche 2 e Abilitate per data è stata rimossa dal codebase. Questa modifica entrerà in vigore con la versione di manutenzione di luglio 2019. Se nel file di importazione sono presenti colonne numeriche o abilitate per data, tali celle verranno automaticamente ignorate e gli altri dati del file verranno importati come di consueto. Le classificazioni esistenti possono ancora essere esportate attraverso il flusso di lavoro di classificazione standard e continueranno a essere disponibili nei rapporti.

Il file di importazione ed esportazione include sei colonne per ciascuna classificazione numerica 2.

Le definizioni seguenti presuppongono che il nome di classificazione numerico 2 sia mycost.

**~ Mycost:** Un nome descrittivo per la riga.

**~ Mycost ^~id~:** ID per la modifica di una riga esistente. Quando si aggiunge una nuova riga, questa deve essere vuota. Un ID viene assegnato automaticamente quando si esporta da Gestione classificazione.

**~MyCost^~value~: **The value for the row. Se la colonna della frequenza è fissa, si tratta di un valore semplice distribuito nell'intero periodo. Se la colonna rate è un evento, questo è il moltiplicatore per quell'evento. Questa voce non deve contenere virgole.

**~ Mycost ^~period~:** Il periodo di tempo corrispondente alla riga. Deve includere una data iniziale e finale, separata da un trattino. Il trattino deve essere racchiuso negli spazi. La definizione deve essere formattata come segue:

AAAA/MM/GG - AAAA/MM/DD

**~ Mycost ^~rate~:** L'evento da moltiplicare per [!UICONTROL Value] la colonna. I valori validi sono:

* fixed - utilizzato per indicare che il valore è un valore semplice da distribuire nel periodo.
* revenue
* order
* unit
* scosta
* scansioni
* instance
* click
* checkout
* scadd
* scremove
* event 1
* event 2
* etc

**~ Mycost ^~hinge~:** L'evento da utilizzare per distribuire il valore durante una suddivisione. This value is often the same as [!UICONTROL ~MyCost^~rate~], unless you are using [!UICONTROL fixed]. The valid values for this column are identical to that of [!UICONTROL ~MyCost^~rate~], with the addition of [!UICONTROL none].
