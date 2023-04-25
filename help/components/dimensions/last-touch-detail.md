---
title: Dettaglio del canale di ultimo contatto
description: Dettagli del canale di marketing più recente entro la scadenza del coinvolgimento del visitatore.
feature: Dimensions
exl-id: def03267-f3e5-4772-a707-5678c45eba6d
source-git-commit: 78cfb1f3c4d45fc983982a8da11b66f2b2c9ecbc
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 3%

---

# Dettaglio del canale di ultimo contatto

La dimensione &quot;Dettaglio canale ultimo contatto&quot; riporta i dettagli relativi al canale di marketing più recente a cui un visitatore corrisponde durante il periodo di coinvolgimento del visitatore (30 giorni per impostazione predefinita). Questa dimensione è utile per comprendere cosa ha contribuito alla corrispondenza dell’hit con un canale di marketing. Ad esempio, se un visitatore è arrivato sul tuo sito e corrisponde al canale di marketing &quot;Ricerca a pagamento&quot;, puoi utilizzare il dettaglio del canale per vedere quale motore di ricerca è stato utilizzato o quale parola chiave ha cercato.

## Popolare questa dimensione con i dati

Questa dimensione copia i valori da altre variabili. La variabile utilizzata fa riferimento al valore del canale all’interno di ogni [Regola di elaborazione del canale di marketing](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-rules.md). Quando un hit corrisponde a una regola di elaborazione del canale di marketing, il [Canale di ultimo contatto](last-touch-channel.md) è impostata sul nome del canale e questa dimensione è impostata sul valore del canale impostato nella regola.

Se desideri impostare questa dimensione su un valore specifico, sono necessari i seguenti passaggi:

* Assicurati che l&#39;elemento dimensione desiderato si trovi in un attributo hit o in una variabile personalizzata.
* Imposta una regola di elaborazione del canale di marketing che contiene i criteri desiderati per l’hit.
* Seleziona il valore a discesa desiderato in [!UICONTROL Set the channel's value] nella regola di elaborazione del canale di marketing.
* L’hit del visitatore per il sito deve corrispondere ai criteri descritti nella regola di elaborazione del canale di marketing .

## Elementi dimensionali

Gli elementi Dimension dipendono dal valore del canale elencato nell’elenco a discesa per la regola di elaborazione del canale di marketing applicabile. Ad esempio, se imposti il valore del canale su &quot;URL pagina&quot;, gli elementi dimensionali includono gli URL della pagina sul sito. Se imposti il valore del canale su Dominio di riferimento, gli elementi dimensionali includono domini che i visitatori hanno fatto clic su per accedere al tuo sito. Questa dimensione aggrega tutti gli elementi dimensionali di dettaglio, indipendentemente dal canale in cui si trovano.

Adobe consiglia di impostare i valori di canale relativi al canale di marketing per informazioni dettagliate sui dettagli del canale.
