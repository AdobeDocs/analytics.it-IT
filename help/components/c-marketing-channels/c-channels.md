---
description: Aggiungi o abilita canali di marketing in Marketing Channel Manager. Per le suite di rapporti prive di canali di marketing, una configurazione automatica consente di creare diversi canali per voi, insieme alle relative regole. Potete modificare i canali predefiniti in base alle vostre esigenze o crearne di nuovi (fino a un totale di 25).
subtopic: Marketing channels
title: Gestire i canali di marketing
topic: Reports and analytics
uuid: 9d367bb6-a17b-49b8-9cd5-24fac35ae982
translation-type: tm+mt
source-git-commit: c10a12781a8fe52b7b897cd337dc686aa0bbb240

---


# Gestire i canali di marketing

Aggiungi o abilita canali di marketing in Marketing Channel Manager. Per le suite di rapporti prive di canali di marketing, una configurazione automatica consente di creare diversi canali per voi, insieme alle relative regole. Potete modificare i canali predefiniti in base alle vostre esigenze o crearne di nuovi (fino a un totale di 25).

Di seguito sono riportate alcune linee guida per la creazione di canali:

* Pianificate in anticipo creando un elenco di tutti i canali, in modo che tutti gli hit visitatore siano organizzati per categorie sul canale giusto.
* Includi sempre canali per le categorie di hit [interni](/help/components/c-marketing-channels/c-faq.md) e [diretti](/help/components/c-marketing-channels/c-faq.md) .

L&#39;aggiunta di canali alla [!UICONTROL Marketing Channels] pagina viene effettuata indipendentemente dalla creazione di regole nella pagina Regole [di elaborazione dei canali](/help/components/c-marketing-channels/c-rules.md) di marketing. Le regole vengono associate ai canali al momento della creazione della regola.

## Aggiunta di canali di marketing {#add-mktg-channels}

Aggiungi canali di marketing in Marketing Channel Manager.

> [!NOTE] Non è possibile eliminare un canale. Se non si desidera utilizzare un canale, è possibile disattivarlo o rinominarlo e mantenerlo per un uso successivo.

1. Fai clic su **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. Sulla [!UICONTROL Report Suite Manager] pagina, seleziona una suite di rapporti.

   Se selezionate più suite di rapporti, selezionate un modello che copia le impostazioni dal modello alle suite di rapporti selezionate.

   See [Apply template report suite settings to multiple report suites](/help/components/c-marketing-channels/c-getting-started-mchannel.md).

1. Fai clic su **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Manager]**.

   Se nella suite di rapporti non sono definiti canali, viene visualizzata la pagina Configurazione [](/help/components/c-marketing-channels/c-getting-started-mchannel.md) automatica.

1. Sulla [!UICONTROL Marketing Channel Manager] pagina fare clic su **[!UICONTROL Add Channel]**.

   Questa opzione non è disponibile quando sono definiti 25 canali.

1. Fai clic su **[!UICONTROL Save.]**
1. Per configurare le regole per il canale, fai clic su **[!UICONTROL Marketing Channel Processing Rules]**.

   See [Create Marketing Channel processing rules](/help/components/c-marketing-channels/c-rules.md).

## Marketing Channel Manager - Definizioni dell&#39;interfaccia {#mktg-channel-mgr}

Definizioni dei campi per la [!UICONTROL Marketing Channel Manager] pagina.

| Campo | Definizione |
|--- |--- |
| Abilitato | Abilita o disabilita questo canale di marketing. |
| Nome canale | Il nome descrittivo del canale di marketing. |
| Ignora ultimo canale di tocco | Consente di scegliere se ignorare un canale esistente persistente con il canale selezionato. Se selezionate questa casella di controllo, qualsiasi canale (inclusi Diretto e Interno) sovrascrive un canale dell’ultimo tocco esistente. Il risultato è che la conversione viene attribuita a un canale che potrebbe non meritare credito. Ad esempio, questa opzione può garantire che il canale Direct non riceva credito per la conversione se l&#39;utente era stato precedentemente acquisito tramite il canale di ricerca naturale. |
| Suddivisione canale | Consente di suddividere un canale per questo valore. Puoi aggiungere possibili analisi dettagliate dei canali (canali secondari) durante la creazione di classificazioni dei canali di [marketing](/help/components/c-marketing-channels/classifictions-mchannel.md). |
| Type (Tipo) | Specifica in che modo l’utente è arrivato sul sito. Potete selezionare Online o Offline. Utilizza i canali online per i visitatori che passano attraverso un motore di ricerca o una campagna e-mail. I canali offline si applicano ai visitatori che hanno trovato il tuo sito tramite annunci pubblicitari di giornali o riviste. I canali offline in genere includono i dati importati tramite Origini dati di reporting. See [Data Sources](https://docs.adobe.com/content/help/en/analytics/import/data-sources/datasrc-home.html). See [Add Offline Data](/help/components/c-marketing-channels/c-getting-started-mchannel.md). |
| Colore | Colore associato a questo canale di marketing. Questo colore rappresenta il canale nel rapporto Canale di marketing. |

## Definizione dei canali

Prima che i canali e i dati dei canali possano essere visualizzati nel rapporto, crea i canali e le regole sottostanti che elaborano i dati. Potete anche creare importi di costo e budget per i canali associati e specificare per quanto tempo il periodo di coinvolgimento del visitatore deve durare. Esegui le attività di configurazione dei rapporti in Strumenti di amministrazione.

Considerate un canale come un contenitore per le visite. Le regole assegnano visite al contenitore appropriato.

![](assets/buckets_2.png)

Adobe fornisce diversi canali predefiniti durante una configurazione [](/help/components/c-marketing-channels/c-getting-started-mchannel.md) automatica che potete modificare in base alle vostre esigenze.

>[!NOTE]
>
>Adobe consiglia di impostare il rapporto in una suite di rapporti da utilizzare come modello a scopo di test. Potete utilizzare il modello per applicare canali e set di regole a livello globale a una o più suite di rapporti di produzione.
>
>See [Apply Template Report Suite Settings to Multiple Report Suites](/help/components/c-marketing-channels/c-getting-started-mchannel.md).

### Prerequisiti {#prereqs}

Se necessario, contattate l&#39;Assistenza clienti per assistenza su questi prerequisiti:

* Nella console di amministrazione (Impostazioni account generali), abilita l’opzione **[!UICONTROL Conversion Level]** (e-commerce) per la suite di rapporti.

   Consulta Impostazioni [account](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/general-acct-settings-admin.html) generali nell&#39;Aiuto di Analytics per ulteriori informazioni.

* Configurate l&#39;accesso alle dimensioni del canale di marketing.

   Consultate Autorizzazioni per i canali [di marketing](/help/components/c-marketing-channels/c-channel-report-access.md).

* Verifica che il tuo account manager sia abilitato **[!UICONTROL Channel Reports]** per la suite di rapporti.

### Note importanti sull&#39;elaborazione {#important-proc-rules}

* Il sistema elabora le regole nell&#39;ordine specificato e quando viene soddisfatta una regola, il sistema interrompe l&#39;elaborazione delle regole rimanenti.
* Le regole possono accedere alle variabili che VISTA ha impostato, ma non ai dati che VISTA ha eliminato.
* I canali memorizzano solo le metriche di conversione. Le metriche del traffico non sono disponibili.
* Due canali di marketing non ricevono mai crediti per lo stesso evento (ad esempio acquisti o clic). In questo modo, i canali di marketing sono diversi dalle eVar (due eVar potrebbero ricevere credito per lo stesso evento).
* Il rapporto può elaborare fino a 25 canali alla volta.

