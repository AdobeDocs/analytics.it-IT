---
title: Dettaglio del canale di primo contatto
description: Dettagli del primo canale di marketing entro la scadenza del coinvolgimento del visitatore.
feature: Dimensions
exl-id: a155182d-7bc0-4c7d-9de7-680bfe2d6432
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 14%

---

# Dettaglio del canale di primo contatto

La &#39;Dettaglio canale di primo contatto&#39; [dimensione](overview.md) segnala i dettagli relativi al primo canale di marketing con cui un visitatore corrisponde durante il periodo di coinvolgimento del visitatore (30 giorni per impostazione predefinita). Questa dimensione è utile per comprendere cosa ha contribuito a far corrispondere l’hit a un canale di marketing. Ad esempio, se un visitatore è arrivato sul tuo sito e corrisponde al canale di marketing “Ricerca a pagamento”, puoi utilizzare i dettagli del canale per visualizzare quale motore di ricerca è stato utilizzato o quale parola chiave ha cercato.

## Popolare questa dimensione con i dati

Questa dimensione copia i valori da altre variabili. La variabile utilizzata fa riferimento al valore del canale in ogni [regola di elaborazione del canale di marketing](/help/admin/tools/manage-rs/edit-settings/marketing-channels/c-rules.md). Quando un hit corrisponde a una regola di elaborazione del canale di marketing, la dimensione [Canale di ultimo contatto](last-touch-channel.md) è impostata sul nome del canale e questa dimensione è impostata sul valore del canale impostato nella regola.

Per impostare questa dimensione su un valore specifico, sono necessari i seguenti passaggi:

* Assicurati che l’elemento di dimensione desiderato si trovi in un attributo hit o in una variabile personalizzata.
* Imposta una regola di elaborazione del canale di marketing contenente i criteri desiderati per l’hit.
* Selezionare il valore dell&#39;elenco a discesa desiderato in [!UICONTROL Set the channel's value] all&#39;interno della regola di elaborazione del canale di marketing.
* L&#39;hit del visitatore per il sito deve corrispondere ai criteri descritti nella regola di elaborazione del canale di marketing _e_ deve essere il primo valore del canale di marketing a farlo nel periodo di coinvolgimento del visitatore.

Se un hit successivo corrisponde ai criteri di un canale di marketing diverso, questa dimensione non viene sovrascritta con il nuovo canale di marketing.

## Elementi dimensionali

Gli elementi Dimension dipendono dal valore del canale elencato nell’elenco a discesa per la regola di elaborazione del canale di marketing applicabile. Ad esempio, se imposti il valore del canale su &quot;URL della pagina&quot;, gli elementi dimensionali includono gli URL della pagina sul sito. Se imposti il valore del canale su Dominio di riferimento, gli elementi dimensione includono i domini su cui i visitatori hanno fatto clic per arrivare al sito. Questa dimensione aggrega tutti gli elementi dimensionali di dettaglio, indipendentemente dal canale in cui si trovano.

Adobe consiglia di impostare i valori dei canali relativi al canale di marketing per insight in base ai dettagli del canale.
