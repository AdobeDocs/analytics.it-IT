---
description: Aggiungi o abilita canali di marketing in Marketing Channel Manager. Per le suite di rapporti prive di canali di marketing, una configurazione automatica consente di creare diversi canali per voi, insieme alle relative regole. Potete modificare i canali predefiniti in base alle vostre esigenze o crearne di nuovi (fino a un totale di 25).
subtopic: Marketing channels
title: Gestire i canali di marketing
topic: Reports and analytics
uuid: 9d367bb6-a17b-49b8-9cd5-24fac35ae982
translation-type: tm+mt
source-git-commit: dd58453a0459bc200a00badf34d06c259ce9fb59

---


# Gestire i canali di marketing

Aggiungi o abilita canali di marketing in Marketing Channel Manager. Per le suite di rapporti prive di canali di marketing, una configurazione automatica consente di creare diversi canali per voi, insieme alle relative regole. Potete modificare i canali predefiniti in base alle vostre esigenze o crearne di nuovi (fino a un totale di 25).

Di seguito sono riportate alcune linee guida per la creazione di canali:

* Pianificate in anticipo creando un elenco di tutti i canali, in modo che tutti gli hit visitatore siano organizzati per categorie sul canale giusto.
* Includi sempre canali per le categorie di hit [interni](/help/components/c-marketing-channels/mc-faq/c-faq.md) e [diretti](/help/components/c-marketing-channels/mc-faq/c-faq.md) .

L&#39;aggiunta di canali alla [!UICONTROL Marketing Channels] pagina viene effettuata indipendentemente dalla creazione di regole nella pagina Regole [di elaborazione dei canali](/help/components/c-marketing-channels/mc-proc-rules/t-rules.md) di marketing. Le regole vengono associate ai canali al momento della creazione della regola.

## Aggiunta di canali di marketing {#add-mktg-channels}

Aggiungi canali di marketing in Marketing Channel Manager.

> [!NOTE] Non è possibile eliminare un canale. Se non si desidera utilizzare un canale, è possibile disattivarlo o rinominarlo e mantenerlo per un uso successivo.

1. Fai clic su **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. Sulla [!UICONTROL Report Suite Manager] pagina, seleziona una suite di rapporti.

   Se selezionate più suite di rapporti, selezionate un modello che copia le impostazioni dal modello alle suite di rapporti selezionate.

   See [Apply template report suite settings to multiple report suites](/help/components/c-marketing-channels/getting-started/t-template.md).

1. Fai clic su **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Manager]**.

   Se nella suite di rapporti non sono definiti canali, viene visualizzata la pagina Configurazione [](/help/components/c-marketing-channels/getting-started/c-channel-autosetup.md) automatica.

1. Sulla [!UICONTROL Marketing Channel Manager] pagina fare clic su **[!UICONTROL Add Channel]**.

   Questa opzione non è disponibile quando sono definiti 25 canali.

1. Fai clic su **[!UICONTROL Save.]**
1. Per configurare le regole per il canale, fai clic su **[!UICONTROL Marketing Channel Processing Rules]**.

   See [Create Marketing Channel processing rules](/help/components/c-marketing-channels/mc-proc-rules/t-rules.md).

## Marketing Channel Manager - Definizioni dell&#39;interfaccia {#mktg-channel-mgr}

Definizioni dei campi per la [!UICONTROL Marketing Channel Manager] pagina.

| Campo | Definizione |
|--- |--- |
| Abilitato | Abilita o disabilita questo canale di marketing. |
| Nome canale | Il nome descrittivo del canale di marketing. |
| Ignora ultimo canale di tocco | Consente di scegliere se ignorare un canale esistente persistente con il canale selezionato. Se selezionate questa casella di controllo, qualsiasi canale (inclusi Diretto e Interno) sovrascrive un canale dell’ultimo tocco esistente. Il risultato è che la conversione viene attribuita a un canale che potrebbe non meritare credito. Ad esempio, questa opzione può garantire che il canale Direct non riceva credito per la conversione se l&#39;utente era stato precedentemente acquisito tramite il canale di ricerca naturale. |
| Suddivisione canale | Consente di suddividere un canale per questo valore. Puoi aggiungere possibili analisi dettagliate dei canali (canali secondari) durante la creazione di classificazioni dei canali di [marketing](/help/components/c-marketing-channels/mc-classifications/classifictions-mchannel.md). |
| Type (Tipo) | Specifica in che modo l’utente è arrivato sul sito. Potete selezionare Online o Offline. Utilizza i canali online per i visitatori che passano attraverso un motore di ricerca o una campagna e-mail. I canali offline si applicano ai visitatori che hanno trovato il tuo sito tramite annunci pubblicitari di giornali o riviste. I canali offline in genere includono i dati importati tramite Origini dati di reporting. See [Data Sources](https://docs.adobe.com/content/help/en/analytics/import/data-sources/datasrc-home.html). See [Add Offline Data](/help/components/c-marketing-channels/getting-started/c-channel-autosetup.md). |
| Colore | Colore associato a questo canale di marketing. Questo colore rappresenta il canale nel rapporto Canale di marketing. |