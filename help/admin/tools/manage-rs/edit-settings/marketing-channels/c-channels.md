---
description: Aggiungi o abilita canali di marketing in Gestore del canale di marketing. Per le suite di rapporti che non hanno canali di marketing, una configurazione automatica ti consente di creare diversi canali, insieme alle relative regole. Puoi modificare i canali predefiniti in base alle tue esigenze, oppure crearne di personalizzati (fino a un totale di 25).
subtopic: Marketing channels
title: Gestire i canali di marketing
feature: Marketing Channels
exl-id: a768a4c2-f922-4d96-a9fb-78a1dfac04d8
role: Admin
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '701'
ht-degree: 100%

---

# Gestire i canali di marketing

>[!NOTE]
>
> Per informazioni generali sui canali di marketing, consulta [Introduzione ai canali di marketing](/help/components/c-marketing-channels/c-getting-started-mchannel.md).
>
> Per ottimizzare l’efficacia dei canali di marketing per la funzione Attribuzione e Customer Journey Analytics, abbiamo pubblicato alcune [best practice revisionate](/help/components/c-marketing-channels/mchannel-best-practices.md).

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Manager]**.

Aggiungi o abilita canali di marketing in Gestore del canale di marketing. Per le suite di rapporti che non hanno canali di marketing, una configurazione automatica ti consente di creare diversi canali, insieme alle relative regole. Puoi modificare i canali predefiniti in base alle tue esigenze, oppure crearne di personalizzati (fino a un totale di 25).

L’aggiunta di canali alla pagina [!UICONTROL Marketing Channels] viene eseguita indipendentemente dalla creazione di regole sulla pagina [Regole di elaborazione per il canale di marketing](/help/admin/tools/manage-rs/edit-settings/marketing-channels/c-rules.md). Associa le regole ai canali durante la creazione della regola.

Di seguito sono riportate le linee guida per la creazione di canali:

* Pianifica in anticipo creando un elenco di tutti i canali, in modo che tutti gli hit visitatore vengano classificati nel canale giusto.
* Includi canali per le categorie di hit [Interni](/help/admin/tools/manage-rs/edit-settings/marketing-channels/c-rules.md).
* Includi un canale onnicomprensivo “Altre campagne”, da posizionare dopo i canali a pagamento e prima dei canali organici.


## Prerequisiti {#prereqs}

* Impostare l’accesso alle dimensioni del Canale di marketing.

  Consulta [Autorizzazioni canali di marketing](/help/components/c-marketing-channels/c-channel-report-access.md).

## Aggiungere canali di marketing {#add-mktg-channels}

Aggiungi canali di marketing in Gestione canali di marketing.

>[!NOTE]
>
>Non puoi eliminare un canale. Se non desideri utilizzare un canale, è possibile disattivarlo o rinominarlo e conservarlo per un utilizzo successivo.

1. Fai clic su **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. Nella pagina [!UICONTROL Report Suite Manager], seleziona una suite di rapporti.

   Se selezioni più suite di rapporti, scegli un modello che copia le impostazioni dal modello alle suite di rapporti selezionate.

   Consulta [Applicare le impostazioni di un modello a più suite di rapporti](/help/components/c-marketing-channels/c-getting-started-mchannel.md).

1. Fai clic su **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Manager]**.

   Se nella suite di rapporti non sono definiti canali, compare la pagina [Configurazione automatica](/help/components/c-marketing-channels/c-getting-started-mchannel.md).

1. Nella pagina [!UICONTROL Marketing Channel Manager], fai clic su **[!UICONTROL Add Channel]**.

   Questa opzione non è disponibile quando sono definiti 25 canali.

1. Fai clic su **[!UICONTROL Save.]**
1. Per configurare le regole per il canale, fai clic su **[!UICONTROL Marketing Channel Processing Rules]**.

   Consulta [Creare regole di elaborazione per il canale di marketing](/help/admin/tools/manage-rs/edit-settings/marketing-channels/c-rules.md).

## Applica impostazioni canale {#mktg-channel-mgr}

Sulla pagina [!UICONTROL Marketing Channel Manager] sono disponibili diverse impostazioni che possono essere applicate a ciascun canale.

| Campo | Definizione |
|--- |--- |
| Abilitata | Abilita o disabilita questo canale di marketing. |
| Nome del canale | Nome descrittivo del canale di marketing. |
| Sovrascrivi canale ultimo contatto | Consente di scegliere se il canale selezionato può sovrascrivere un canale di ultimo contatto persistente ed esistente. Selezionando questa casella di controllo, qualsiasi canale (incluso Diretto e Interno) potrà sovrascrivere un canale di ultimo contatto esistente. Il risultato è che la conversione viene attribuita a un canale che potrebbe non meritare credito. Ad esempio, questa opzione può garantire che il canale Diretto non riceva credito per la conversione se l’utente era stato precedentemente acquisito tramite il canale di ricerca naturale. |
| Raggruppamento per canale | Ti consente di suddividere un canale per questo valore. È possibile aggiungere raggruppamenti per canali (sottocanali) durante la creazione di [classificazioni dei canali di marketing](/help/admin/tools/manage-rs/edit-settings/marketing-channels/classifications-mchannel.md). |
| Tipo | Specifica come l’utente è arrivato al sito. È possibile selezionare Online o Offline. Utilizza i canali Online per i visitatori che arrivano tramite motore di ricerca o campagna e-mail. I canali Offline si utilizzano per i visitatori che hanno trovato il sito tramite coupon su un giornale o annunci pubblicitari sulle riviste. I canali offline in genere includono dati importati tramite le Origini dati di reporting. Consulta [Origini dati](/help/import/data-sources/overview.md). Consulta [Aggiungi dati offline](/help/components/c-marketing-channels/c-getting-started-mchannel.md). |

### Best practice di sovrascrittura

È consigliabile deselezionare l’opzione di sovrascrittura dell’ultimo contatto per i canali Diretto e Interno, in modo che non possano ottenere credito da altri canali di ultimo contatto persistenti (o l’uno dall’altro).

![](assets/int-channel2.png)

## Definire le regole del canale

Prima che i canali e i dati dei canali possano essere visualizzati nel rapporto, crea i canali e le regole sottostanti che elaborano i dati. Puoi anche specificare per quanto tempo desideri che duri il [periodo di coinvolgimento dei visitatori](/help/admin/tools/manage-rs/edit-settings/marketing-channels/visitor-engagement.md).

Tramite una [configurazione automatica](/help/components/c-marketing-channels/c-getting-started-mchannel.md), Adobe fornisce diversi canali predefiniti che puoi modificare in base alle tue esigenze. Inoltre, puoi modificare questa impostazione e definire regole personalizzate all’interno di [Regole di elaborazione per il canale di marketing](/help/admin/tools/manage-rs/edit-settings/marketing-channels/c-rules.md).

>[!NOTE]
>
>Adobe consiglia di impostare il rapporto in una suite di rapporti che puoi utilizzare come modello a scopo di test. Puoi utilizzare il modello per applicare set di canali e regole a livello globale a una o più suite di rapporti di produzione.
>
>Consulta [Applicare le impostazioni di un modello di suite di rapporti a più suite di rapporti](/help/components/c-marketing-channels/c-getting-started-mchannel.md).
