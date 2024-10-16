---
title: Cos’è l’hub di Report Builder in Adobe Analytics
description: Descrive i componenti dell’hub Report Builder
role: User
feature: Report Builder
type: Documentation
solution: Analytics
source-git-commit: eedabc6295f9b918e1e00b93993680e676c216c3
workflow-type: tm+mt
source-wordcount: '490'
ht-degree: 59%

---

# Hub Report Builder

Utilizza l’hub Report Builder per creare, aggiornare, eliminare e gestire i blocchi di dati.

L&#39;hub di Report Builder contiene i pulsanti Crea e Gestisci, l&#39;elenco COMANDI e i pannelli QUICK EDIT (MODIFICA RAPIDA).

<img src="./assets/hub51.png" alt="Hub Report Builder"/>


## Pulsanti Crea, Gestisci e Pianifica

Utilizza i pulsanti Crea, Gestisci e Pianifica per creare nuovi blocchi di dati, gestire quelli esistenti o pianificare blocchi di dati.

## Pannello COMANDI

Utilizza il pannello COMANDI per accedere ai comandi compatibili con le celle selezionate o con un’azione precedente.

### Comandi

| Comandi visualizzati | Quando è disponibile | Finalità |
|------|------------------|--------|
| Create data block (Crea blocco di dati) | Nella cartella di lavoro è selezionata una o più celle. | Utilizzato per creare un blocco di dati |
| Edit data block (Modifica blocco di dati) | La cella o l’intervallo di celle selezionato fa parte di un solo blocco di dati. | Utilizzato per modificare un blocco di dati |
| Refresh data block (Aggiorna blocco di dati) | La selezione contiene almeno un blocco di dati. Il comando aggiorna solo i blocchi di dati nella selezione. | Utilizzato per aggiornare uno o più blocchi di dati |
| Refresh all data blocks (Aggiorna tutti i blocchi di dati) | La cartella di lavoro contiene uno o più blocchi di dati. | Utilizzato per aggiornare tutti i blocchi di dati nella cartella di lavoro |
| Invia cartella di lavoro |   | Invia una cartella di lavoro in base a una pianificazione. |
| Copy data block (Copia blocco di dati) | La cella o l’intervallo di celle selezionato fa parte di uno o più blocchi di dati. | Utilizzato per copiare un blocco di dati |
| Delete data block (Elimina blocco di dati) | La cella o l’intervallo di celle selezionato fa parte di un solo blocco di dati. | Utilizzato per eliminare un blocco di dati |

## Pannello QUICK EDIT (MODIFICA RAPIDA)

Quando selezioni uno o più blocchi di dati in un foglio di calcolo, in Report Builder viene visualizzato il pannello QUICK EDIT (MODIFICA RAPIDA). Puoi utilizzarlo per modificare i parametri in un singolo blocco di dati o per modificare i parametri in più blocchi di dati contemporaneamente.

![Pannello Quick Edit (Modifica rapida) nel Report Builder](./assets/hub2.png)

Le modifiche apportate utilizzando le sezioni di Quick Edit (Modifica rapida) si applicano a tutti i blocchi di dati selezionati.

### di Report Suite Manager

I blocchi di dati estraggono dati da una suite di rapporti selezionata. Se più blocchi di dati sono selezionati in un foglio di lavoro e non estraggono dati dalla stessa suite di rapporti, il collegamento **Suite di rapporti** visualizza *Multiple*.

Quando modifichi la suite di rapporti, tutti i blocchi di dati nella selezione adottano la nuova suite di rapporti. I componenti nel blocco di dati vengono associati alla nuova suite di rapporti in base all&#39;ID, ad esempio, corrispondente a ```evars```). Se un componente non viene trovato in un blocco di dati, viene visualizzato un messaggio di avvertenza e il componente viene rimosso dal blocco di dati.

Per modificare la suite di rapporti, seleziona una nuova suite di rapporti dal menu a discesa.

![Hub di Report Builder che mostra il menu a discesa della suite di rapporti.](./assets/image16.png)

### Intervallo date

**[!UICONTROL Date range]** mostra l&#39;intervallo di date per i blocchi di dati selezionati. Se sono selezionati più blocchi di dati con più intervalli di date, il collegamento **[!UICONTROL Date range]** visualizza *Multiple*.

### Filtri

Il collegamento **Filtri** visualizza un elenco riepilogativo dei filtri utilizzati dai blocchi di dati selezionati. Se sono selezionati più blocchi di dati con più filtri applicati, il collegamento **Filtri** visualizza *Multipli*.
