---
title: Domande frequenti sulle classificazioni
description: Domande frequenti per l'utilizzo delle classificazioni.
translation-type: tm+mt
source-git-commit: 6778dd290424651dc959224daa0eef8ebd8196e5
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 0%

---


# Domande frequenti sulle classificazioni

Domande frequenti per l&#39;utilizzo delle classificazioni.

## Come si classifica l’elemento dimensione &quot;0&quot;?

I file di classificazione caricati con un valore chiave o un valore di classificazione pari a zero (`0`) generano un errore. Include tutti i valori che contengono solo zeri (`00`, `000`e così via). Esistono diversi metodi per risolvere il problema:

* **Implementare valori** alternativi: L&#39;utilizzo di un valore di testo diverso da `"0"` è il modo migliore e più semplice per risolvere il problema. Ad esempio, modifica `s.campaign = "0";` l’implementazione in `s.campaign = "Zero";`.

* **Usa regole** di elaborazione: Puoi modificare gli elementi dimensionali tra la raccolta di dati e la relativa memorizzazione in una suite di rapporti. Create la seguente regola di elaborazione:

   *Se[la dimensione]è uguale a`0`, sovrascrivere il valore della[dimensione]con il valore personalizzato`Zero`.*

* **Richiedi una regola** VISTA: Un consulente dei servizi tecnici imposta una regola lato server a un costo aggiuntivo. Contatta l&#39;Account Manager della tua organizzazione per richiedere una regola VISTA.

## Posso usare il caricatore per classificare gli elementi dimensionali che non esistono ancora?

Sì, *tuttavia in questo modo ogni elemento dimensione viene conteggiato come chiamata al server fatturabile.*

* Gli elementi Dimension già esistenti non comportano alcun costo aggiuntivo.
* L&#39;utilizzo del generatore di regole di classificazione non classifica gli elementi inesistenti e non comporta pertanto costi aggiuntivi.
