---
description: Le regole di elaborazione del canale di marketing determinano se un hit visitatore soddisfa i criteri assegnati a un canale. Il processo di regole viene elaborato ogni hit che un visitatore effettua sul sito. Quando una regola non soddisfa i criteri di un canale, o se le regole non sono configurate correttamente, il sistema assegna l'hit a Nessun canale identificato.
seo-description: Le regole di elaborazione del canale di marketing determinano se un hit visitatore soddisfa i criteri assegnati a un canale. Il processo di regole viene elaborato ogni hit che un visitatore effettua sul sito. Quando una regola non soddisfa i criteri di un canale, o se le regole non sono configurate correttamente, il sistema assegna l'hit a Nessun canale identificato.
seo-title: Regole di elaborazione per i canali di marketing
solution: Analytics
subtopic: Canali di marketing
title: Regole di elaborazione per i canali di marketing
topic: Reports & Analytics
uuid: f 6394 f 4 b-a 244-48 e 9-9892-7 dfbfceb 5 fc 9
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Regole di elaborazione per i canali di marketing

Le regole di elaborazione del canale di marketing determinano se un hit visitatore soddisfa i criteri assegnati a un canale. Il processo di regole viene elaborato ogni hit che un visitatore effettua sul sito. Quando una regola non soddisfa i criteri di un canale, o se le regole non sono configurate correttamente, il sistema assegna l'hit a Nessun canale identificato.

Seguono importanti linee guida per la creazione di regole:

* Ordinate le regole nell'ordine in cui desiderate che vengano elaborate.
* Alla fine dell'elenco, includete una regola catch-all, ad esempio Altro. Questa regola identifica il traffico esterno, ma non il traffico interno.

   See [No Channel Identified](../../components/c-marketing-channels/c-faq.md#section_451E42994DA247A8A7B8559C715A5EE7).

>[!NOTE]
>
>Queste regole non influiscono sui rapporti al di fuori dei canali di marketing, ma influenzano la raccolta dei dati del canale di marketing. I dati raccolti con queste regole sono permanenti al 100% e le regole modificate dopo la raccolta dei dati non sono retroattive. It is strongly recommended to review and consider all circumstances before saving [!UICONTROL Marketing Channel Processing Rules] to mitigate data being collected in incorrect channels.

**Prerequisiti**

* Review the conceptual information in [Getting Started with Marketing Channels](../../components/c-marketing-channels/c-getting-started-mchannel.md#concept_0C28C1592F564E53BB467E6EBC168E8C) and [About Marketing Channel Reports](../../components/c-marketing-channels/c-overview.md#concept_77BE50D20BAA402CB292026436A39068).

* Create uno o più canali per potervi assegnare delle regole.

   See [Add marketing channels](../../components/c-marketing-channels/c-channels.md#task_98C9D3F5DBBC4B198E0A9ED4D3891E03).

