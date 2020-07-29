---
description: Il file di importazione ed esportazione include sei colonne per ogni classificazione numerica 2.
subtopic: Classifications
title: Importare classificazioni numeriche 2
topic: Admin tools
uuid: 82a3034c-e002-4991-900f-22dd45d54910
translation-type: tm+mt
source-git-commit: 6778dd290424651dc959224daa0eef8ebd8196e5
workflow-type: tm+mt
source-wordcount: '321'
ht-degree: 24%

---


# Importare classificazioni numeriche 2

>[!IMPORTANT]
>
>La possibilità di importare le classificazioni Numeriche 2 e Abilitate per data è stata rimossa dal codebase. Questa modifica entrerà in vigore con la versione di manutenzione di luglio 2019. Se nel file di importazione sono presenti colonne numeriche o abilitate per data, tali celle verranno automaticamente ignorate e gli altri dati del file verranno importati come di consueto. Le classificazioni esistenti possono ancora essere esportate attraverso il flusso di lavoro di classificazione standard e continueranno a essere disponibili nei rapporti.

Il file di importazione ed esportazione include sei colonne per ogni classificazione numerica 2.

Le seguenti definizioni presuppongono che il nome di classificazione numerico 2 sia MyCost.

**~MyCost:** Un nome descrittivo per la riga.

**~MyCost^~id~:** ID per la modifica di una riga esistente. Quando si aggiunge una nuova riga, questa deve essere vuota. Un ID viene assegnato automaticamente quando si esporta da Gestione classificazione.

**~MioCosto^~valore~:** Il valore della riga. Se la colonna del tasso è fissa, si tratta di un valore piatto distribuito sull&#39;intero periodo. Se la colonna della tariffa è un evento, questo è il moltiplicatore per tale evento. Questa voce non deve contenere virgole.

**~MioCosto^~periodo~:** Periodo di tempo a cui corrisponde questa riga. Deve includere una data di inizio e una data di fine, separata da un trattino. Il trattino deve essere racchiuso in spazi. La definizione deve essere formattata come segue:

AAAA/MM/GG - AAAA/MM/GG

**~MyCost^~rate~:** L’evento da moltiplicare per la [!UICONTROL Value] colonna. I valori validi sono:

* fisso: utilizzato per indicare che il valore è un valore fisso da distribuire nel periodo.
* ricavo
* order
* unit
* scopa
* scansioni
* instance
* click
* estrazione
* scadd
* scremove
* Evento 1
* event 2
* etc

**~MyCost^~hinge~:** Evento da utilizzare per distribuire il valore durante una suddivisione. Questo valore è spesso uguale a [!UICONTROL ~MyCost^~rate~], a meno che non si utilizzi [!UICONTROL fixed]. I valori validi per questa colonna sono identici a quelli della [!UICONTROL ~MyCost^~tariffa~], con l&#39;aggiunta di [!UICONTROL none].
