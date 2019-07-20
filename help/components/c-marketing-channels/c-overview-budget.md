---
description: Scopri come assegnare costi e budget ai canali.
seo-description: Scopri come assegnare costi e budget ai canali.
seo-title: Costi e budget
solution: Analytics
subtopic: Canali di marketing
title: Costi e budget
topic: Reports & Analytics
uuid: 7 ba 0 e 968-e 565-4 d 4 c -8 fc 0-39 bf 25 d 3 e 5 b 1
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Costi e budget

Scopri come assegnare costi e budget ai canali.

## Costs and budgets {#topic_7CCFD3B54440433FBA0E4EE127F58B0C}

Scopri come assegnare costi e budget ai canali.

Costo rappresenta ciò che spendi sul canale. Budget rappresenta l'importo disponibile per la spesa.

Un modo utile per visualizzare il ROI è quello di creare una metrica calcolata che mostra i costi meno costosi. Oppure creane uno che mostri il costo totale insieme a una suddivisione del costo per nuovo coinvolgimento. For example, you can run a [!UICONTROL First-Touch Channel] report showing new engagements. Quindi aggiungi una metrica Costi touch che mostra i costi per nuovo coinvolgimento, creando una metrica calcolata.

See [Calculated metrics used Marketing Channel reports](../../components/c-marketing-channels/c-channel-calc-metrics.md#topic_4521D324A79E43EF99E69FCDE1E92F74).

Potete assegnare costi e budget solo ai canali. A tutti i costi viene fornito un intervallo di tempo per il reporting. Quando i costi sono associati direttamente a un canale, viene scelta una metrica di allocazione per mostrare il modo in cui i costi si suddividono tra le campagne all'interno di un canale.

Dopo aver aggiunto gli elementi costi e budget, potete esportare i dati della tabella in un file CSV. Potete anche importare un file CSV nella pagina Costi canale di marketing.

## Add cost and budget items {#task_9238A033994440748960DE21593E6388}

Aggiungi elementi costi e budget a canali di marketing.

1. Click **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]**.
1. On the [!UICONTROL Report Suite Manager] page, select a report suite.
1. Click **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Marketing Channels]** &gt; **[!UICONTROL Marketing Channel Costs]**.
1. On the [!UICONTROL Marketing Channel Costs] page, click **[!UICONTROL Add Cost Item]** or **[!UICONTROL Add Budget Item]**.
1. Fai clic su **[!UICONTROL Save.]**

   To continue adding cost items, click **[!UICONTROL Save and Add Another]**.

1. (Optional) To export or import CSV files, access the [!UICONTROL Marketing Channel Costs] page, click **[!UICONTROL Export File]** or **[!UICONTROL Import File]**, then follow the prompts.

## Marketing Channel costs - definitions {#reference_0B193210E10A4B6B84A385A781FD9515}

Definizioni dei campi per i costi dei canali di marketing o i budget.



| Campo | Definizione |
|--- |--- |
| Nome | Nome del costo o dell'elemento di budget. (Questo valore è il valore Chiave se si utilizza SAINT.) |
| Canale | Canale al quale associare questo importo. Specificate se il costo o il budget si applica a un canale First Touch o a un canale Ultimo tocco. Considerate un fattore costi per il primo tocco come nuovo livello di coinvolgimento. Un'ultima quantità di costi è per i clic. |
| Intervallo date | Tempo da utilizzare per questo importo. |
| Type (Tipo) | Il costo o il budget, a Rate o Una tantum. Il valore Rate specifica un costo continuo, ad esempio un importo per clic. Una tantum consente di specificare l'importo Distribuisci per. Ad esempio, se distribuite il costo per clic, alla filiale con il 60% dei clic totali viene attribuito il 60% del costo totale. Il valore Distribuito per valore è la metrica utilizzata per suddividere le classificazioni numeriche. |
| Esporta file | Consente di esportare i dati della tabella in un file CSV. |
| File di importazione | Consente di importare un file CSV nella pagina Costi canale di marketing. |
