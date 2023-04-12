---
title: Domande frequenti sulle classificazioni
description: Domande frequenti sull’utilizzo delle classificazioni.
feature: Classifications
exl-id: e929d7cb-0bfd-46de-88d1-aea2b4b91911
source-git-commit: 34ba0e09cd909951a777b0ad3da080958633f97e
workflow-type: tm+mt
source-wordcount: '365'
ht-degree: 78%

---

# Domande frequenti sulle classificazioni

Domande frequenti sull’utilizzo delle classificazioni.

## Come si classifica l’elemento dimensionale “0”?

I file di classificazione caricati con un valore chiave o un valore di classificazione pari a zero (`0`) generano un errore. Sono inclusi tutti i valori che contengono solo zeri (`00`, `000` e così via). Esistono diversi metodi per risolvere questo problema:

* **Implementare valori alternativi**: l’utilizzo di un valore di testo diverso da `"0"` è il modo migliore e più semplice per risolvere il problema. Ad esempio, modifica `s.campaign = "0";` nell’implementazione in `s.campaign = "Zero";`.

* **Utilizzare regole di elaborazione**: puoi modificare gli elementi dimensionali tra la raccolta di dati e la relativa memorizzazione in una suite di rapporti. Creare la seguente regola di elaborazione:

   *Se la [dimensione] è uguale a `0`, sovrascrivi il valore di [dimensione] con il valore personalizzato `Zero`.*

* **Richiedere una regola VISTA**: un consulente di servizi tecnici imposta una regola lato server a un costo aggiuntivo. Contatta il team dell’account di Adobe per richiedere una regola VISTA.

## È possibile utilizzare l’importazione di classificazioni per classificare elementi dimensionali non ancora esistenti?

Sì, *tuttavia in questo modo ogni elemento dimensionale viene conteggiato come chiamata al server che può essere addebitata.*

* Gli elementi dimensionali già esistenti non comportano costi aggiuntivi.
* L’utilizzo del generatore di regole di classificazione non classifica gli elementi inesistenti e non comporta pertanto costi aggiuntivi.

## Come si classificano i valori che contengono caratteri speciali?

L’utilizzo di spazi vuoti iniziali e finali nei dati di classificazione e nei dati di hit non è supportato perché Adobe Analytics troncherà i caratteri vuoti da questi dati.

In genere non è consigliabile utilizzare caratteri speciali come virgole o virgolette nei rapporti. Tuttavia, in alcuni casi è necessario utilizzarli. Se i valori dei rapporti contengono tali caratteri che scegli di classificare, procedi come segue:

1. Accedi ad Adobe Analytics e seleziona **[!UICONTROL Admin]** > **[!UICONTROL Classification importer]**.
2. Fai clic sulla scheda **[!UICONTROL Browser export]**.
3. Configura le impostazioni di esportazione e accertati che l’opzione “Quote output” NON sia selezionata.
4. Fai clic su **[!UICONTROL Export File]** e apri il file scaricato in un editor per fogli di calcolo.
5. Nella riga 1, individua la cella C1 contenente il valore `v:2.0`. Modifica il valore in `v:2.1` e applica le classificazioni desiderate alla cartella di lavoro.
6. Carica il file come faresti con una classificazione.

## Cosa sono le classificazioni numeriche 2?

Le classificazioni numeriche 2 consentono di classificare gli elementi dimensionali come metriche basate sul tempo. Sono stati ritirati dall’interfaccia utente di Adobe Analytics a luglio 2019.
