---
description: Le regole di elaborazione del canale di marketing determinano se un hit di visitatore soddisfa i criteri assegnati a un canale. Le regole elaborano ogni hit che un visitatore fa sul sito. Quando una regola non soddisfa i criteri per un canale, o se le regole non sono configurate correttamente, il sistema assegna l'hit a Nessun canale identificato.
seo-description: Le regole di elaborazione del canale di marketing determinano se un hit di visitatore soddisfa i criteri assegnati a un canale. Le regole elaborano ogni hit che un visitatore fa sul sito. Quando una regola non soddisfa i criteri per un canale, o se le regole non sono configurate correttamente, il sistema assegna l'hit a Nessun canale identificato.
seo-title: Regole di elaborazione per i canali di marketing
solution: Analytics
subtopic: Canali di marketing
title: Regole di elaborazione per i canali di marketing
topic: Reports and Analytics
uuid: f6394f4b-a244-48e9-9892-7dfbfceb5fc9
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Regole di elaborazione per i canali di marketing

Le regole di elaborazione del canale di marketing determinano se un hit di visitatore soddisfa i criteri assegnati a un canale. Le regole elaborano ogni hit che un visitatore fa sul sito. Quando una regola non soddisfa i criteri per un canale, o se le regole non sono configurate correttamente, il sistema assegna l'hit a Nessun canale identificato.

Di seguito sono riportate importanti linee guida per la creazione di regole:

* Ordinare le regole nell'ordine desiderato.
* Alla fine dell’elenco, includete una regola catch-all, ad esempio Altro. Questa regola identifica il traffico esterno ma non il traffico interno.

   Consultate [Nessun canale identificato](../../components/c-marketing-channels/c-faq.md#section_451E42994DA247A8A7B8559C715A5EE7).

> [!NOTE] Sebbene queste regole non influenzino i rapporti al di fuori dei canali di marketing, influiscono sulla raccolta dei dati dei canali di marketing. I dati raccolti con queste regole sono permanenti al 100% e le regole modificate dopo la raccolta dei dati non sono retroattive. È vivamente consigliato rivedere e considerare tutte le circostanze prima di salvare [!UICONTROL Marketing Channel Processing Rules] per attenuare la raccolta dei dati in canali non corretti.

**Prerequisiti**

* Consultate le informazioni concettuali in [Guida introduttiva ai canali](../../components/c-marketing-channels/c-getting-started-mchannel.md#concept_0C28C1592F564E53BB467E6EBC168E8C) di marketing e [Informazioni sui rapporti](../../components/c-marketing-channels/c-overview.md#concept_77BE50D20BAA402CB292026436A39068)sui canali di marketing.

* Create uno o più canali in modo da poter assegnare loro le regole.

   Consultate [Aggiunta di canali](../../components/c-marketing-channels/c-channels.md#task_98C9D3F5DBBC4B198E0A9ED4D3891E03)di marketing.

