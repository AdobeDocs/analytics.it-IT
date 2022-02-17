---
description: Puoi importare (caricare) i dati delle classificazioni utilizzando il browser. Questo metodo limita il caricamento dei dati di classificazione a una singola suite di rapporti
title: Importazione browser
feature: Classifications
exl-id: 5bef1f6d-9b27-464d-8343-472f300a7437
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 86%

---

# Importazione browser

Puoi importare (caricare) i dati delle classificazioni utilizzando il browser. Questo metodo limita il caricamento dei dati di classificazione a una singola suite di rapporti

## Importazione browser {#concept_314FB3D5FD5A439B9CFEDE37A3337BA7}

Puoi importare (caricare) i dati delle classificazioni utilizzando il browser. Questo metodo limita il caricamento dei dati di classificazione a una singola suite di rapporti

**[!UICONTROL Admin]** > **[!UICONTROL Classification Importer]**

## Importazione di classificazioni dal browser - Descrizioni dei campi {#section_F628C47081DA4026A4D30E3D3454B1DA}

| Elemento | Descrizione |
| --- | --- |
| Seleziona suite di rapporti | La suite di rapporti in cui desideri importare i dati delle classificazioni. Il file di dati di importazione deve corrispondere al formato del set di dati nella suite di rapporti. |
| Set di dati da classificare | Il set di dati per la ricezione delle classificazioni. L’elenco a discesa include tutti i rapporti nelle suite di rapporti configurati per le classificazioni. |
| Seleziona il file da importare | Consente di sfogliare per individuare il file di dati di importazione da caricare.  Nota: la dimensione massima per il file da caricare è 1 MB. |
| Sovrascrivi i dati sui conflitti | Sovrascrive automaticamente i dati esistenti in conflitto con quelli importati.<br>**Importante**: Questa opzione non è disponibile per le suite di rapporti abilitate per la nuova architettura di classificazione. |
| Scarica automaticamente il file di classificazione al termine dell’importazione | Scarica automaticamente un file con valori delimitati da tabulazioni che rappresenta il set di dati con i nuovi dati di classificazione caricati. Adobe genera automaticamente questo file se l’importazione crea ID univoci o se si verificano errori.<br>**Importante**: Questa opzione non è disponibile per le suite di rapporti abilitate per la nuova architettura di classificazione. |


## Importare classificazioni tramite il browser {#task_D7D51CB6FB35437AB68599B1B23FEAC1}

1. Fai clic su **[!UICONTROL Admin]** > **[!UICONTROL Classification Importer]**.
1. Fai clic su **[!UICONTROL Import File]**.
1. Configura i campi **[!UICONTROL Browser Import]**.
1. Fai clic su **[!UICONTROL Import File]**.
1. Controlla la finestra di stato per l’elaborazione dei messaggi.
1. (Condizionale) Se hai selezionato **[!UICONTROL Automatically Download Classification File After Upload is Complete]**, specifica dove memorizzare il file risultante al termine dell’elaborazione. Questa opzione non è disponibile per le suite di rapporti abilitate per la nuova architettura di classificazione.

>Un’importazione corretta visualizza immediatamente le modifiche appropriate in un’esportazione. Tuttavia, le modifiche ai dati nei rapporti richiedono fino a quattro ore quando si utilizza un’importazione browser e fino a 24 ore quando si utilizza un’importazione FTP.
