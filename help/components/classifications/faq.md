---
title: Domande frequenti sulle classificazioni
description: Domande frequenti per l'utilizzo delle classificazioni.
translation-type: tm+mt
source-git-commit: 0870ace3fea8e3ef650d2de2960006a0d655cf9f
workflow-type: tm+mt
source-wordcount: '337'
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

## Posso utilizzare Importazione classificazioni per classificare gli elementi dimensione che non esistono ancora?

Sì, *tuttavia in questo modo ogni elemento dimensione viene conteggiato come chiamata al server fatturabile.*

* Gli elementi Dimension già esistenti non comportano alcun costo aggiuntivo.
* L&#39;utilizzo del generatore di regole di classificazione non classifica gli elementi inesistenti e non comporta pertanto costi aggiuntivi.

## Come si classificano i valori che contengono caratteri speciali?

In genere non è consigliabile utilizzare caratteri speciali come virgole o virgolette nei rapporti. Tuttavia, in alcuni casi il loro uso è necessario. Se i valori di reporting contengono caratteri che si sceglie di classificare, procedere come segue:

1. Accedete a  Adobe Analytics, quindi selezionate **[!UICONTROL Admin]** > **[!UICONTROL Classification importer]**.
2. Fai clic sulla scheda **[!UICONTROL Browser export]**.
3. Configurate le impostazioni di esportazione e accertatevi che l&#39;opzione &quot;Output quota&quot; NON sia selezionata.
4. Fate clic **[!UICONTROL Export File]** e aprite il file scaricato in un editor per fogli di calcolo.
5. Nella riga 1, individuare la cella C1 che contiene il valore `v:2.0`. Modificare il valore in `v:2.1` e applicare le classificazioni desiderate alla cartella di lavoro.
6. Caricate il file come qualsiasi altra classificazione.

## Cosa sono le classificazioni numeriche 2?

Le classificazioni numeriche 2 consentono di classificare gli elementi dimensionali come metriche basate sul tempo. Sono stati ritirati dall’interfaccia utente di Analytics nel luglio 2019.
