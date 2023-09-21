---
title: Dettaglio del canale di ultimo contatto
description: Dettagli del canale di marketing più recente entro la scadenza del coinvolgimento del visitatore.
feature: Dimensions
exl-id: def03267-f3e5-4772-a707-5678c45eba6d
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 3%

---

# Dettaglio del canale di ultimo contatto

&#39;Dettaglio del canale di ultimo contatto&#39; [dimensione](overview.md) segnala i dettagli relativi al canale di marketing più recente con cui un visitatore corrisponde durante il periodo di coinvolgimento del visitatore (30 giorni per impostazione predefinita). Questa dimensione è utile per comprendere cosa ha contribuito a far corrispondere l’hit a un canale di marketing. Ad esempio, se un visitatore è arrivato sul tuo sito e corrisponde al canale di marketing &quot;Ricerca a pagamento&quot;, puoi utilizzare i dettagli del canale per vedere quale motore di ricerca è stato utilizzato o quale parola chiave ha cercato.

## Popola questa dimensione con i dati

Questa dimensione copia i valori da altre variabili. La variabile utilizzata fa riferimento al valore del canale all’interno di ogni [Regola di elaborazione del canale di marketing](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-rules.md). Quando un hit corrisponde a una regola di elaborazione del canale di marketing, il [Canale ultimo contatto](last-touch-channel.md) la dimensione è impostata sul nome del canale e questa dimensione è impostata sul valore del canale impostato nella regola.

Per impostare questa dimensione su un valore specifico, sono necessari i seguenti passaggi:

* Assicurati che l’elemento di dimensione desiderato si trovi in un attributo hit o in una variabile personalizzata.
* Imposta una regola di elaborazione del canale di marketing contenente i criteri desiderati per l’hit.
* Seleziona il valore dell’elenco a discesa desiderato in [!UICONTROL Set the channel's value] nella regola di elaborazione del canale di marketing.
* L&#39;hit del visitatore per il sito deve corrispondere ai criteri descritti nella regola di elaborazione del canale di marketing.

## Elementi dimensionali

Gli elementi di Dimension dipendono dal valore del canale elencato nell’elenco a discesa per la regola di elaborazione del canale di marketing applicabile. Ad esempio, se imposti il valore del canale su &quot;URL della pagina&quot;, gli elementi dimensionali includono gli URL della pagina sul sito. Se imposti il valore del canale su Dominio di riferimento, gli elementi dimensione includono i domini su cui i visitatori hanno fatto clic per arrivare al sito. Questa dimensione aggrega tutti gli elementi dimensionali di dettaglio, indipendentemente dal canale in cui si trovano.

L’Adobe consiglia di impostare i valori del canale relativi al canale di marketing per ottenere informazioni approfondite sui dettagli del canale.
