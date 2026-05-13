---
description: Puoi importare (caricare) i dati delle classificazioni utilizzando il browser. Questo metodo limita il caricamento dei dati di classificazione a una singola suite di rapporti
title: Importazione browser
feature: Classifications
exl-id: 5bef1f6d-9b27-464d-8343-472f300a7437
TQID: https://experienceleague.adobe.com/iFVW-d9C12dj6TXnUlA3-zVF0oBAWpJwg1JK8LqzF-s
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 334
ht-degree: 65%

---

# Importazione browser (legacy)

{{classification-importer-deprecation}}

Puoi importare (caricare) i dati delle classificazioni utilizzando il browser. Questo metodo limita il caricamento dei dati di classificazione a una singola suite di rapporti

## Importazione browser {#concept_314FB3D5FD5A439B9CFEDE37A3337BA7}

Puoi importare (caricare) i dati delle classificazioni utilizzando il browser. Questo metodo limita il caricamento dei dati di classificazione a una singola suite di rapporti

**[!UICONTROL Admin]** > **[!UICONTROL Classification Importer]**

## Importazione di classificazioni dal browser - Descrizione dei campi {#section_F628C47081DA4026A4D30E3D3454B1DA}

| Elemento | Descrizione |
| --- | --- |
| Seleziona suite di rapporti | La suite di rapporti in cui desideri importare i dati delle classificazioni. Il file di dati di importazione deve corrispondere al formato del set di dati nella suite di rapporti. |
| Set di dati da classificare | Il set di dati per la ricezione delle classificazioni. L’elenco a discesa include tutti i rapporti nelle suite di rapporti configurati per le classificazioni. |
| Seleziona il file da importare | Consente di sfogliare per individuare il file di dati di importazione da caricare.  Nota: la dimensione massima per il file da caricare è 1 MB. |
| Sovrascrivi i dati sui conflitti | Sovrascrive automaticamente i dati esistenti in conflitto con i dati importati.<br>**Importante**: questa opzione non è disponibile per le suite di rapporti abilitate per la nuova architettura di classificazione. |
| Scarica automaticamente il file di classificazione al termine dell’importazione | Scarica automaticamente un file con valori delimitati da tabulazioni che rappresenta il set di dati con i nuovi dati di classificazione caricati. Adobe genera automaticamente questo file se l&#39;importazione crea ID univoci o se si verificano errori.<br>**Importante**: questa opzione non è disponibile per le suite di rapporti abilitate per la nuova architettura di classificazione. |


## Importare classificazioni tramite il browser {#task_D7D51CB6FB35437AB68599B1B23FEAC1}

1. Fai clic su **[!UICONTROL Admin]** > **[!UICONTROL Classification Importer]**.
1. Fai clic su **[!UICONTROL Import File]**.
1. Configura i campi **[!UICONTROL Browser Import]**.
1. Fai clic su **[!UICONTROL Import File]**.
1. Controlla la finestra di stato per l’elaborazione dei messaggi.
1. (Condizionale) Se hai selezionato **[!UICONTROL Automatically Download Classification File After Upload is Complete]**, specifica dove memorizzare il file risultante al termine dell&#39;elaborazione. Questa opzione non è disponibile per le suite di rapporti abilitate per la nuova architettura di classificazione.

>Un’importazione corretta visualizza immediatamente le modifiche appropriate in un’esportazione. Tuttavia, le modifiche ai dati nei rapporti richiedono fino a quattro ore quando si utilizza un’importazione browser e fino a 24 ore quando si utilizza un’importazione FTP.
