---
description: Scopri come assegnare importi di costo e budget ai canali.
seo-description: Scopri come assegnare importi di costo e budget ai canali.
seo-title: Costi e budget
solution: Analytics
subtopic: Canali di marketing
title: Costi e budget
topic: Reports and Analytics
uuid: 7ba0e968-e565-4d4c-8fc0-39bf25d3e5b1
translation-type: tm+mt
source-git-commit: 8c4c368a84ba5499d85f0b7512c99de47ddb14c2

---


# Costi e budget

Scopri come assegnare importi di costo e budget ai canali.

Il costo rappresenta ciò che si spende sul canale. Il budget rappresenta l'importo disponibile da spendere.

Un modo utile per visualizzare il ROI è creare una metrica calcolata che mostra le entrate meno i costi. Oppure creane uno che mostri il costo totale insieme a una suddivisione del costo per nuovo impegno. Ad esempio, potete eseguire un [!UICONTROL First-Touch Channel] rapporto che mostra i nuovi impegni. Quindi aggiungi una metrica Costo primo contatto che ti mostra il costo per il nuovo coinvolgimento, creando una metrica calcolata.

See [Calculated metrics used Marketing Channel reports](/help/components/c-marketing-channels/c-channel-calc-metrics.md).

È possibile assegnare costi e budget solo ai canali. A tutti i costi viene assegnato un intervallo di tempo al quale si applicano nella segnalazione. Quando i costi sono associati direttamente a un canale, viene scelta una metrica di allocazione per mostrare come i costi si suddividono tra le campagne all'interno di un canale.

Dopo aver aggiunto voci di costo e budget, potete esportare i dati della tabella in un file CSV. Potete anche importare un file CSV nella pagina Costi canale marketing.

## Aggiunta di voci di costo e budget {#add-cost-and-budget}

Aggiungi elementi di costo e budget a Marketing Channels.

1. Clic **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]**.
1. Sulla [!UICONTROL Report Suite Manager] pagina, seleziona una suite di rapporti.
1. Clic **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Marketing Channels]** &gt; **[!UICONTROL Marketing Channel Costs]**.
1. Sulla [!UICONTROL Marketing Channel Costs] pagina, fare clic su **[!UICONTROL Add Cost Item]** o **[!UICONTROL Add Budget Item]**.
1. Fai clic su **[!UICONTROL Save.]**

   Per continuare ad aggiungere elementi di costo, fate clic su **[!UICONTROL Save and Add Another]**.

1. (Facoltativo) Per esportare o importare file CSV, accedete alla [!UICONTROL Marketing Channel Costs] pagina, fate clic **[!UICONTROL Export File]** o **[!UICONTROL Import File]**, quindi seguite le istruzioni.

## Costi del canale di marketing - definizioni {#mktg-channel-costs}

Definizioni dei campi per i costi o i budget del canale di marketing.

| Campo | Definizione |
|--- |--- |
| Nome | Nome della voce di costo o budget. (Questo valore è il valore Key se si utilizza SAINT.) |
| Canale | Canale a cui si desidera associare l'importo. Specificate se il costo o il budget si applica a un canale First Touch o Last Touch. Considerate l'importo del costo del primo tocco come un nuovo impegno una tantum. Un costo dell'ultimo tocco è relativo ai click-through. |
| Intervallo date | Tempo da utilizzare per questo importo. |
| Type (Tipo) | Il tipo di costo o budget, un tasso o un costo una tantum. Il tasso specifica un costo continuo, ad esempio un importo per clic. Un costo una tantum consente di specificare un importo Distribuisci per. Ad esempio, se distribuite il costo per clic, alla filiale con il 60% dei clic totali viene assegnato il 60% del costo totale. Il valore Distribuito per è la metrica utilizzata per suddividere le classificazioni numeriche. |
| Esporta file | Consente di esportare i dati della tabella in un file CSV. |
| Importa file | Consente di importare un file CSV nella pagina Costi canale marketing. |
