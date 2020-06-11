---
title: Primo dettaglio canale touch
description: Dettagli per il primo canale di marketing entro la scadenza del coinvolgimento del visitatore.
translation-type: tm+mt
source-git-commit: 87d0c7e20594e2e39f55284e8d50d425cc1cdacf
workflow-type: tm+mt
source-wordcount: '344'
ht-degree: 0%

---


# Primo dettaglio canale touch

La dimensione &quot;Primo dettaglio canale di contatto&quot; indica i dettagli sul primo canale di marketing con cui un visitatore corrisponde durante il periodo di coinvolgimento del visitatore (per impostazione predefinita, 30 giorni). Questa dimensione è importante per comprendere cosa ha contribuito all’hit che corrisponde a un canale di marketing. Ad esempio, se un visitatore è arrivato sul sito e ha la corrispondenza con il canale Marketing &#39;Ricerca a pagamento&#39;, potete utilizzare il dettaglio del canale per vedere quale motore di ricerca è stato utilizzato o quale parola chiave ha cercato.

## Compilare questa dimensione con i dati

Questa dimensione copia i valori da altre variabili. La variabile utilizzata fa riferimento al valore del canale all&#39;interno di ogni regola [di elaborazione del canale](/help/admin/admin/marketing-channels-admin.md)Marketing. Quando un hit corrisponde a una regola di elaborazione del canale di marketing, la dimensione dell’ [ultimo canale](last-touch-channel.md) di contatto è impostata sul nome del canale e questa dimensione è impostata sul valore del canale impostato nella regola.

Per impostare questa dimensione su un valore specifico, sono necessari i passaggi seguenti:

* Accertatevi che il valore della dimensione desiderata sia in un attributo hit o in una variabile personalizzata.
* Impostate una regola di elaborazione del canale di marketing che contenga i criteri desiderati per l’hit.
* Selezionate il valore a discesa desiderato all&#39;interno [!UICONTROL Set the channel's value] della regola di elaborazione del canale di marketing.
* L&#39;hit del visitatore sul sito deve corrispondere ai criteri indicati nella regola di elaborazione del canale di marketing _e deve essere_ il primo valore del canale di marketing a farlo nel periodo di coinvolgimento del visitatore.

Se un hit successivo corrisponde ai criteri in un canale Marketing diverso, questa dimensione non viene sovrascritta con il nuovo canale di marketing.

## Valori dimensione

I valori delle dimensioni dipendono dal menu a discesa del valore del canale. Ad esempio, se imposti il valore del canale su &#39;URL pagina&#39;, i valori delle dimensioni includono gli URL delle pagine sul sito. Se imposti il valore del canale su Dominio di riferimento, i valori delle dimensioni includono i domini ai quali i visitatori hanno fatto clic per accedere al sito. Questa dimensione aggrega tutti i valori di dimensione del dettaglio, indipendentemente dal canale in cui si trovano.

Adobe consiglia di impostare i valori dei canali relativi al canale di marketing per informazioni dettagliate sui dettagli dei canali.
