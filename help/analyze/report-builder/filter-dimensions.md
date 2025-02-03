---
title: Come filtrare le dimensioni nel Report Builder
description: Descrive come utilizzare le dimensioni filtro nel Report Builder
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: 43f48abf-951d-4fd1-afd4-58304ee5247b
source-git-commit: 06d762614969f3557c8ccf310af266742cde9738
workflow-type: tm+mt
source-wordcount: '970'
ht-degree: 64%

---

# Dimensioni filtro

Per impostazione predefinita, ogni elemento dimensione nella tabella restituisce i primi 10 elementi per tale dimensione.

Per modificare gli elementi dimensione restituiti per ogni dimensione:

1. Fare clic su **[!UICONTROL Manage]** e selezionare un blocco di dati dall&#39;elenco.

   ![Gestisci > Modifica blocco dati](./assets/manage-edit.png)

1. Fare clic su **[!UICONTROL Edit data block]** nel pannello COMANDI.

1. Fare clic su **[!UICONTROL Next]** per visualizzare la scheda Dimension.

1. Fare clic sull&#39;icona **...** accanto al nome di un componente nella tabella.

   ![Opzioni per l&#39;icona con i puntini di sospensione.](./assets/image27.png)

1. Selezionare **[!UICONTROL Filter dimension]** nel menu popup per visualizzare il riquadro **[!UICONTROL Filter dimension]**.

1. Seleziona **[!UICONTROL Most popular]** (Mostra origine dati) o **[!UICONTROL Specific]** (Blocca selezione).

   ![Opzione specifica selezionata nel riquadro Dimensione filtro.](./assets/image28.png)

1. Seleziona le opzioni appropriate in base al tipo di filtro scelto.

1. Fare clic su **[!UICONTROL Apply]** per aggiungere il filtro.

   In Report Builder viene visualizzata la conferma del filtro aggiunto.

Per visualizzare i filtri applicati, passa il cursore su una dimensione. Un’icona filtro a destra del nome di una dimensione indica che ci sono stati applicati dei filtri.

## Tipo di filtro

Esistono due modi per filtrare gli elementi dimensionali: Most popular (Più popolari) e Specific (Specifici).

## Most popular (Più popolari)

L&#39;opzione [!UICONTROL Most popular] consente di filtrare dinamicamente gli elementi dimensionali in base ai valori delle metriche. Il filtro [!UICONTROL Most popular] restituisce gli elementi dimensionali con classificazione più alta in base ai valori delle metriche. Per impostazione predefinita, sono elencati i primi 10 elementi dimensione, ordinati in base alla prima metrica aggiunta al blocco di dati.

![L&#39;opzione più comune.](./assets/image29.png)


### Opzioni Page (Pagina) e Rows (Righe)

Puoi utilizzare i campi **Page** (Pagina) e **Rows** (Righe) per suddividere i dati in pagine o gruppi sequenziali o pagine. Questo consente di inserire nel rapporto valori di riga diversi dai primi valori. Questa funzione è particolarmente utile per richiamare dati oltre il limite di 50.000 righe.

#### Valori predefiniti per pagina e righe

- Page = 1
- Rows = 10

Le impostazioni predefinite di Page (Pagina) e Rows (Righe) prevedono che ogni pagina contiene 10 righe di dati. La pagina 1 restituisce i primi 10 elementi, la pagina 2 restituisce i successivi 10 elementi e così via.

La tabella seguente riporta alcuni esempi di valori di pagina e riga e dell’output risultante.

| Pagina | Riga | Output |
|------|--------|----------------------|
| 1 | 10 | Primi 10 elementi |
| 2 | 10 | Elementi da 11 a 20 |
| 1 | 100 | Primi 100 elementi |
| 2 | 100 | Elementi da 101 a 200 |
| 2 | 50.000 | Elementi da 50.001 a 100.000 |

#### Valori minimi e massimi

- Pagina iniziale: Min = 1, Max: 50 milioni
- Numero di righe: Min = 1, Max: 50.000

### Includi “Nessun valore“

In Adobe Analytics, alcune dimensioni raccolgono una voce &quot;nessun valore&quot;. Con questo filtro puoi escludere tali valori dai rapporti. Ad esempio, puoi creare una classificazione “Nome prodotto” in base al codice SKU del prodotto. Se per uno SKU di prodotto non è stata impostata una classificazione Nome prodotto specifica, il valore Nome prodotto viene impostato su “No value” (Nessun valore).

L’opzione Includi “**Nessun valore**” è selezionata per impostazione predefinita. Per escludere le voci prive di valore, deseleziona questa opzione.

### Filtrare per criterio

Puoi filtrare gli elementi dimensione che soddisfano o meno tutti i criteri o qualsiasi criterio.

Per impostare i criteri da filtrare:

1. Seleziona un operatore dall’elenco a discesa.

   ![Elenco degli operatori.](./assets/image31.png)

1. Immetti un valore nel campo di ricerca.

1. Fare clic su **[!UICONTROL Add row]** per confermare la selezione e aggiungere un altro elemento di criteri.

1. Fai clic sull’icona Elimina per rimuovere un elemento di criteri.

   Puoi includere fino a 10 elementi di criteri.

### Modificare il filtro e l’ordinamento

Accanto alla metrica utilizzata per filtrare e ordinare il blocco di dati viene visualizzata una freccia. La direzione della freccia indica se la metrica è ordinata dal valore maggiore a quello minore o viceversa.

Per cambiare l’ordinamento, fai clic sulla freccia accanto alla metrica.

Per cambiare la metrica utilizzata per filtrare e ordinare il blocco di dati:

1. Passa il puntatore sul componente di metrica desiderato nel generatore di tabelle per visualizzare altre opzioni.

2. Fai clic sulla freccia della metrica desiderata.

   ![Generatore di tabelle e metriche.](./assets/image30.png)


## Filtri specifici

L’opzione Specific (Specifici) consente di creare un elenco di elementi dimensione per ogni dimensione. Utilizza il tipo di filtro **[!UICONTROL Specific]** per specificare gli elementi dimensionali esatti da includere nel filtro. Puoi selezionare gli elementi da un elenco o da un intervallo di celle.

![Opzioni specifiche ed elementi selezionati.](./assets/image32.png)

### From list (Da elenco)

1. Selezionare l&#39;opzione **[!UICONTROL From list]** per cercare e selezionare gli elementi dimensione.

   Quando selezioni l&#39;opzione **[!UICONTROL From list]**, l&#39;elenco viene compilato con gli elementi dimensione che hanno il maggior numero di eventi.

   ![Opzione From List ed elementi disponibili.](./assets/image33.png)

   L&#39;elenco **[!UICONTROL Available items]** è ordinato dagli elementi dimensione con il maggior numero di eventi a quelli con il minore numero.

1. Immettere un termine di ricerca nel campo **[!UICONTROL Add item]** per eseguire la ricerca nell&#39;elenco.

1. Per cercare un elemento non incluso negli ultimi 90 giorni di dati, fare clic su **[!UICONTROL Show items for the last 6 months]** per estendere la ricerca.

   ![Mostra elementi dell&#39;elenco degli ultimi 6 mesi.](./assets/image34.png)

   Dopo il caricamento dei dati degli ultimi 6 mesi, Report Builder aggiorna il collegamento a **[!UICONTROL Show items for last 18 months]**.

1. Seleziona un elemento dimensione.

   Gli elementi dimensione selezionati vengono aggiunti automaticamente all&#39;elenco **[!UICONTROL Selected items]**.

   ![](./assets/image35.png)

   Per rimuovere un elemento dall’elenco, fai clic sull’icona Elimina.

   Per spostare un elemento nell’elenco, trascinalo o fai clic su ... per visualizzare il menu di spostamento.

   ![Elenco degli elementi dimensione.](./assets/image36.png)

1. Fai clic su **[!UICONTROL Apply]**

   Report Builder aggiorna l’elenco in base al filtro specifico applicato.

### From range of cells (Da intervallo di celle)

Selezionare l&#39;opzione **[!UICONTROL From range of cells]** per scegliere un intervallo di celle contenente l&#39;elenco di elementi di dimensioni da associare.

![Opzione e campo From range of cells (Da intervallo di celle) per selezionare un intervallo di celle.](./assets/image37.png)

Quando selezioni un intervallo di celle, considera le seguenti restrizioni:

- L’intervallo deve avere almeno una cella.
- L’intervallo non può avere più di 50.000 celle.
- L’intervallo deve trovarsi in una singola riga o colonna ininterrotta.

La selezione può contenere celle vuote o con valori che non corrispondono a un elemento dimensione specifico.

### Nella scheda Dimensions (Dimensioni) del generatore di tabelle

Dalla scheda **[!UICONTROL Dimensions]**, fare clic sulla freccia accanto al nome di una dimensione per visualizzare l&#39;elenco degli elementi dimensione.

![Scheda Dimension e elenco delle dimensioni.](./assets/dimensions_chevron.png)

È possibile trascinare gli elementi su **[!UICONTROL Table]** oppure fare doppio clic sul nome di un elemento per aggiungerlo al generatore **[!UICONTROL Table]**.
