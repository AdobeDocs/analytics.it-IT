---
description: Aggiungi o abilita canali di marketing in Marketing Channel Manager. Per le suite di rapporti che non hanno canali di marketing, una configurazione automatica ti consente di creare diversi canali, insieme alle relative regole. Puoi modificare i canali predefiniti in base alle tue esigenze, oppure crearne di personalizzati (fino a un totale di 25).
subtopic: Marketing channels
title: Gestire i canali di marketing
feature: Marketing Channels
exl-id: a768a4c2-f922-4d96-a9fb-78a1dfac04d8
source-git-commit: d173a6c6c9751a86f4218ec842da17da14f8485b
workflow-type: tm+mt
source-wordcount: '702'
ht-degree: 2%

---

# Gestire i canali di marketing

>[!NOTE]
>
> Per informazioni generali sui canali di marketing, consulta [Introduzione ai canali di marketing](/help/components/c-marketing-channels/c-getting-started-mchannel.md).
>
> Per massimizzare l’efficacia dei canali di marketing ai fini dell’attribuzione e del Customer Journey Analytics, abbiamo pubblicato alcuni [best practice riviste](/help/components/c-marketing-channels/mchannel-best-practices.md).

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Manager]**.

Aggiungi o abilita canali di marketing in Marketing Channel Manager. Per le suite di rapporti che non hanno canali di marketing, una configurazione automatica ti consente di creare diversi canali, insieme alle relative regole. Puoi modificare i canali predefiniti in base alle tue esigenze, oppure crearne di personalizzati (fino a un totale di 25).

Aggiunta di canali al [!UICONTROL Marketing Channels] la pagina viene eseguita indipendentemente dalla creazione di regole sulla [Regole di elaborazione per il canale di marketing](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-rules.md) pagina. Associate le regole ai canali durante la creazione della regola.

Di seguito sono riportate le linee guida per la creazione di canali:

* Pianifica in anticipo creando un elenco di tutti i canali, in modo che tutti gli hit dei visitatori vengano classificati nel canale giusto.
* Includi canali per le categorie di [Interno](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-rules.md) hit.
* Includi un canale &quot;Altre campagne&quot; onnicomprensivo, da posizionare dopo i canali a pagamento e prima dei canali organici.


## Prerequisiti {#prereqs}

* Impostare l’accesso alle dimensioni Canale di marketing.

  Consulta [Autorizzazioni dei canali di marketing](/help/components/c-marketing-channels/c-channel-report-access.md).

## Aggiungere canali di marketing {#add-mktg-channels}

Aggiungi canali di marketing in Marketing Channel Manager.

>[!NOTE]
>
>Impossibile eliminare un canale. Se non si desidera utilizzare un canale, è possibile disattivarlo o rinominarlo e conservarlo per un utilizzo successivo.

1. Fai clic su **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. Il giorno [!UICONTROL Report Suite Manager] , seleziona una suite di rapporti.

   Se selezioni più suite di rapporti, seleziona un modello che copia le impostazioni dal modello alle suite di rapporti selezionate.

   Consulta [Applicare le impostazioni suite di rapporti per più suite di rapporti](/help/components/c-marketing-channels/c-getting-started-mchannel.md).

1. Fai clic su **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Manager]**.

   Se nella suite di rapporti non sono definiti canali, il [Configurazione automatica](/help/components/c-marketing-channels/c-getting-started-mchannel.md) viene visualizzata la pagina.

1. Nella pagina [!UICONTROL Marketing Channel Manager] fai clic su **[!UICONTROL Add Channel]**.

   Questa opzione non è disponibile quando sono definiti 25 canali.

1. Fai clic su **[!UICONTROL Save.]**
1. Per configurare le regole per il canale, fai clic su **[!UICONTROL Marketing Channel Processing Rules]**.

   Consulta [Creare regole di elaborazione per il canale di marketing](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-rules.md).

## Applica impostazioni canale {#mktg-channel-mgr}

È possibile applicare diverse impostazioni a ciascun canale sulla [!UICONTROL Marketing Channel Manager] pagina.

| Campo | Definizione |
|--- |--- |
| Abilitata | Abilita o disabilita questo canale di marketing. |
| Nome canale | Il nome descrittivo del canale di marketing. |
| Ignora canale ultimo contatto | Consente di scegliere se escludere un canale di ultimo contatto persistente esistente dal canale selezionato. Se selezioni questa casella di controllo, qualsiasi canale (incluso Direct e Internal) ignora un canale di ultimo contatto esistente. Il risultato è che la conversione viene attribuita a un canale che potrebbe non meritare credito. Ad esempio, questa opzione può garantire che il canale diretto non riceva credito per la conversione se l’utente era stato precedentemente acquisito tramite il canale di ricerca naturale. |
| Suddivisione canale | Consente di suddividere un canale per questo valore. È possibile aggiungere possibili raggruppamenti dei canali (sottocanali) durante la creazione di [classificazioni dei canali di marketing](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/classifications-mchannel.md). |
| Tipo | Specifica la modalità di accesso dell&#39;utente al sito. È possibile selezionare Online o Offline. Utilizza i canali online per i visitatori che accedono a un motore di ricerca o a una campagna e-mail. I canali offline si applicano ai visitatori che hanno trovato il tuo sito tramite coupon di giornale o annunci pubblicitari sulle riviste. I canali offline in genere includono dati importati tramite Origini dati di reporting. Consulta [Origini dati](https://experienceleague.adobe.com/docs/analytics/import/data-sources/datasrc-home.html). Consulta [Aggiungi dati offline](/help/components/c-marketing-channels/c-getting-started-mchannel.md). |

### Sovrascrivi best practice

È consigliabile deselezionare l’opzione di esclusione dell’ultimo contatto per i canali Direct e Internal, in modo che non possano ottenere credito da altri canali di ultimo contatto persistenti (o l’uno dall’altro).

![](assets/int-channel2.png)

## Definire le regole del canale

Prima che i canali e i dati dei canali possano essere visualizzati nel rapporto, crea i canali e le regole sottostanti che elaborano i dati. Puoi anche specificare per quanto tempo desideri [periodo di coinvolgimento dei visitatori](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/visitor-engagement.md) per durare.

Adobe fornisce diversi canali predefiniti durante un [impostazione automatica](/help/components/c-marketing-channels/c-getting-started-mchannel.md) che puoi modificare in base alle tue esigenze. Inoltre, puoi modificare questa impostazione e definire regole personalizzate in [Regole di elaborazione per il canale di marketing](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-rules.md).

>[!NOTE]
>
>L’Adobe consiglia di impostare il rapporto in una suite di rapporti che puoi utilizzare come modello a scopo di test. Puoi utilizzare il modello per applicare set di canali e regole a livello globale a una o più suite di rapporti di produzione.
>
>Consulta [Applicare le impostazioni suite di rapporti per il modello a più suite di rapporti](/help/components/c-marketing-channels/c-getting-started-mchannel.md).
