---
title: Regole di elaborazione per i canali di marketing
description: Le regole di elaborazione del canale di marketing determinano se un hit di visitatore soddisfa i criteri assegnati a un canale. Le regole elaborano ogni hit che un visitatore fa sul sito. Quando una regola non soddisfa i criteri per un canale, o se le regole non sono configurate correttamente, il sistema assegna l'hit a Nessun canale identificato.
translation-type: tm+mt
source-git-commit: ea4d9e6c9396032fe323de594cb43eecbf97aa15

---


# Regole di elaborazione per i canali di marketing

Le regole di elaborazione del canale di marketing determinano se un hit di visitatore soddisfa i criteri assegnati a un canale. Le regole elaborano ogni hit che un visitatore fa sul sito. Quando una regola non soddisfa i criteri per un canale, o se le regole non sono configurate correttamente, il sistema assegna l&#39;hit a Nessun canale identificato.

Di seguito sono riportate importanti linee guida per la creazione di regole:

* Ordinare le regole nell&#39;ordine desiderato.
* Alla fine dell’elenco, includete una regola catch-all, ad esempio Altro. Questa regola identifica il traffico esterno ma non il traffico interno.

   Vedere [Nessun canale identificato.](/help/components/c-marketing-channels/mc-faq/c-faq.md#no-channel-identified)

> [!NOTE] Sebbene queste regole non influenzino i rapporti al di fuori dei canali di marketing, influiscono sulla raccolta dei dati dei canali di marketing. I dati raccolti con queste regole sono permanenti al 100% e le regole modificate dopo la raccolta dei dati non sono retroattive. È vivamente consigliato rivedere e considerare tutte le circostanze prima di salvare [!UICONTROL Marketing Channel Processing Rules] per attenuare la raccolta dei dati in canali non corretti.

## Prerequisiti

* Consultate le informazioni concettuali in [Guida introduttiva ai canali](/help/components/c-marketing-channels/getting-started/c-getting-started-mchannel.md)di marketing.
* Create uno o più canali in modo da poter assegnare loro le regole. Consultate [Aggiunta di canali di marketing.](/help/components/c-marketing-channels/mark-channel-mgr/c-channels.md)
