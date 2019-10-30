---
description: Come utilizzare le metriche nei report Marketing Channel.
seo-description: Come utilizzare le metriche nei report Marketing Channel.
seo-title: Metriche utilizzate nei rapporti sul canale di marketing
solution: Analytics
subtopic: Canali di marketing
title: Metriche utilizzate nei rapporti sul canale di marketing
topic: Reports and Analytics
uuid: be5bcb94-927e-4b5f-b201-3d54eb51e740
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Metriche utilizzate nei rapporti sul canale di marketing

Come utilizzare le metriche nei report Marketing Channel.

## Metriche utilizzate nei rapporti sul canale di marketing {#topic_F83F5D4C3E144967AD90D956F0E8A999}

Come utilizzare le metriche nei report Marketing Channel.

![](assets/metric_edit_icon.png)

Aggiungi (o modifica) metriche.

![](assets/add_column_icon.png)

Aggiungi una colonna al rapporto.

## Prima e ultima metrica di tocco {#concept_68D9A50204304BA58C1F8013451E7853}

Gli attributi "first-touch" e "last-touch" sono gli attributi del canale che consentono di vedere quanti nuovi impegni (o dati di metriche come visualizzazioni di prodotto, ricavi e ordini) derivano dall'attività di un visitatore nel canale.

Quando si verifica un evento di successo, Analytics esamina l'intera attività e la cronologia del visitatore (tornando alla scadenza [del coinvolgimento del](../../components/c-marketing-channels/visitor-engagement.md#topic_32ADFDB12D3A4F35843A4545AC97C49F)visitatore). Nota il primo canale che l'utente ha attraversato, così come il canale più recente. Successivamente, l'evento di successo viene accreditato a ogni canale appropriato.

<!-- 

<note>
  A first-touch value has a rolling expiration based on the frequency of a visitor returning to the site. This first-touch expiration resets whenever a visitor returns to the site. This effects reporting by causing first-touch values to persist longer than you might expect. For example, this can occur if an instance of an first-touch channel was created a year ago. Remove the values on the eVar in the admin console to reset.
</note>

 -->

**Esempio**

Supponiamo di configurare due canali di marketing: Ricerca a pagamento e campagna e-mail.

![](assets/paid_search.png)

La ricerca a pagamento è un annuncio per un prodotto. Raccoglie l'interesse di un visitatore e genera una visualizzazione di prodotto ma non genera un evento di conversione.

![](assets/email_campaign.png)

Un mese dopo viene eseguita una campagna e-mail per lo stesso prodotto. Si traduce in un acquisto di $100 (o altro evento di conversione desiderato).

Nel rapporto Canale di marketing, il risultato può essere visualizzato come segue:

![](assets/report-graphic.png)

Il canale di ricerca a pagamento viene accreditato a $100 come primo canale per i ricavi, con 1 ordine di primo tocco. Al canale della campagna e-mail viene accreditato $100 come ultimo canale di fatturato (l'ultimo canale toccato dall'utente prima dell'evento di conversione) e con 1 ultimo ordine di tocco. In altre parole, uno scopo principale della relazione è quello di vedere come la ripartizione delle entrate tra i primi canali di contatto differisca dalla suddivisione delle entrate tra gli ultimi canali di contatto.

Ogni istanza di evento di successo avrà esattamente un canale First Touch e un canale Last Touch. Questo significa che se aggiungi una colonna metrica specifica per un evento di successo, sarà sempre esattamente uguale al totale per lo stesso periodo di tempo. Questo totale corrisponderà anche esattamente al numero totale di eventi nel report appropriato [!UICONTROL Site Metrics] &gt; [!UICONTROL Custom Events] . Le metriche di eventi non di successo, come visite e visitatori, non corrispondono fino a 1 a 1, in quanto più canali possono essere attivati nella stessa visita.

> [!NOTE] Questo rapporto utilizza la versione con il primo o l'ultimo tocco di ogni metrica. Di conseguenza, i dati visualizzati in un [!UICONTROL Marketing Channel] report potrebbero non corrispondere ai dati mostrati in altri report.

## Metric definitions {#section_364D003D34D748B79503DFA4DD208EDB}

| Metrica | Definizione |
|--- |--- |
| Primo canale touch | Il primo canale di marketing per coinvolgere un visitatore. Tecnicamente, il primo canale touch è un eVar con allocazione originale. |
| Visitatore principale | Nel reporting sui canali, un visitatore di primo contatto è un Visitatore unico giornaliero originato da un canale. Il coinvolgimento del visitatore viene memorizzato per tutta la durata del periodo di coinvolgimento con il sito, che può durare molte visite. |
| Ultimo canale touch | Il canale di conversione, ovvero l'ultimo canale di marketing per coinvolgere il visitatore e ottenere una conversione. Solo un canale è impostato come primo canale touch. L'ultimo canale touch può cambiare con ogni visita di ritorno al sito. Ogni visita ha un canale di primo e ultimo tocco, ma il valore del canale di primo tocco non cambia mai con le visite successive. |

## Click-through {#reference_55E2254F02EF4E7EB0AD2838C948347A}

Un click-through è un'istanza sul canale dell'ultimo tocco. È una eVar con l'allocazione più recente.

Ad esempio, supponiamo che un visitatore venga sul sito Web una volta al giorno, con ogni visita proveniente da un canale di marketing diverso:

* Giorno 1: Ricerca a pagamento
* Giorno 2: Display
* Giorno 3: Ricerca naturale
* Giorno 4: Display
* Giorno 5: Ricerca a pagamento
* Giorno 6: Display
* Giorno 7: Ricerca naturale

Il report First-Touch Channel (Canale di primo contatto) mostrerebbe 1 nuovo coinvolgimento per la ricerca a pagamento. Ogni altro canale mostrava 0 nuovi impegni. Il rapporto Last-Touch Channel (Ultimo canale touch) mostra 2 click-through per la ricerca a pagamento; 3 per il display; e 2 per Ricerca naturale.

## Aggiunta di metriche a un report Marketing Channel {#task_D381139E00504666AB2402D553CFEA5B}

Aggiungi metriche al report Marketing Channel. Puoi aggiungere fino a quattro metriche a ciascuna colonna del rapporto e quante colonne desideri.

1. Apri il [!UICONTROL Marketing Channel Report].
1. Fate clic su Aggiungi metriche.

   ![](assets/metric_edit_icon.png)

1. In [!UICONTROL Available Metrics]questa sezione, trascina le metriche dalla [!UICONTROL Available Metrics] sezione alla [!UICONTROL Selected Metrics] sezione.

   ![Risultato passaggio](assets/metric_create.png)

1. Per creare metriche calcolate, scorri fino a [!UICONTROL Calculated Metrics], quindi fai clic su **[!UICONTROL Create]**.
1. Fai clic su **[!UICONTROL Save.]**
