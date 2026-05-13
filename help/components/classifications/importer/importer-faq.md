---
title: Domande frequenti sulle classificazioni
description: Domande frequenti sull’utilizzo delle classificazioni.
feature: Classifications
exl-id: e929d7cb-0bfd-46de-88d1-aea2b4b91911
TQID: https://experienceleague.adobe.com/pIwAdewnHA4AB9hyRDRkH6xXvyxx-BceWvDXMydX-ew
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 413
ht-degree: 82%

---

# Domande frequenti sull’importazione delle classificazioni

{{classification-importer-deprecation}}

Domande frequenti sull’utilizzo dell’importazione di classificazioni.

## Come si classifica l’elemento dimensionale “0”?

I file di classificazione caricati con un valore chiave o un valore di classificazione pari a zero (`0`) generano un errore. Sono inclusi tutti i valori che contengono solo zeri (`00`, `000` e così via). Esistono diversi metodi per risolvere questo problema:

* **Implementare valori alternativi**: l’utilizzo di un valore di testo diverso da `"0"` è il modo migliore e più semplice per risolvere il problema. Ad esempio, modifica `s.campaign = "0";` nell’implementazione in `s.campaign = "Zero";`.

* **Utilizzare regole di elaborazione**: puoi modificare gli elementi dimensionali tra la raccolta di dati e la relativa memorizzazione in una suite di rapporti. Creare la seguente regola di elaborazione:

  *Se la [dimensione] è uguale a `0`, sovrascrivi il valore di [dimensione] con il valore personalizzato `Zero`.*

* **Richiedere una regola VISTA**: un consulente di servizi tecnici imposta una regola lato server a un costo aggiuntivo. Contatta il team Adobe Account per richiedere una regola VISTA.

## È possibile utilizzare l’importazione di classificazioni per classificare elementi dimensionali non ancora esistenti?

Sì, *tuttavia in questo modo ogni elemento dimensionale viene conteggiato come chiamata al server che può essere addebitata.*

* Gli elementi dimensionali già esistenti non comportano costi aggiuntivi.
* L’utilizzo del generatore di regole di classificazione non classifica gli elementi inesistenti e non comporta pertanto costi aggiuntivi.

## Come si classificano i valori che contengono caratteri speciali?

L’utilizzo di spazi vuoti iniziali e finali nei dati di classificazione e nei dati hit non è supportato perché Adobe Analytics tronca automaticamente i caratteri vuoti.

In genere non è consigliabile utilizzare caratteri speciali come virgole o virgolette nei rapporti. Tuttavia, in alcuni casi è necessario utilizzarli. Se i valori dei rapporti contengono tali caratteri che desideri classificare, segui i seguenti passaggi:

1. Accedi ad Adobe Analytics e seleziona **[!UICONTROL Admin]** > **[!UICONTROL Classification importer]**.
2. Fai clic sulla scheda **[!UICONTROL Browser export]**.
3. Configura le impostazioni di esportazione e accertati che l’opzione “Quote output” NON sia selezionata.
4. Fai clic su **[!UICONTROL Export File]** e apri il file scaricato in un editor per fogli di calcolo.
5. Nella riga 1, individua la cella C1 contenente il valore `v:2.0`. Modifica il valore in `v:2.1` e applica le classificazioni desiderate alla cartella di lavoro.
6. Carica il file come faresti con una classificazione.

## Cosa sono le classificazioni numeriche 2?

Le classificazioni numeriche 2 consentono di classificare gli elementi dimensionali come metriche basate sul tempo. Sono state ritirate dall’interfaccia utente di Adobe Analytics a luglio 2019.

## Come posso eseguire l’escape dei dati in un file di classificazione?

Racchiudere il campo contenente caratteri speciali tra virgolette doppie (`"`). Un carattere virgolette doppie può essere visualizzato in una cella con escape sostituendola con due virgolette doppie (`" "`). Ad esempio:

```
My String "of data"
```

Con escape:

```
"My String ""of data"""
```
