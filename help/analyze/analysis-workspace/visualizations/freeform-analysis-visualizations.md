---
description: Ulteriori informazioni sulle visualizzazioni e sulle impostazioni di visualizzazione in Analysis Workspace.
keywords: Analysis Workspace
seo-description: Ulteriori informazioni sulle visualizzazioni e sulle impostazioni di visualizzazione in Analysis Workspace.
seo-title: Panoramica visualizzazioni
solution: Analytics
title: Panoramica visualizzazioni
topic: Reports & Analytics
uuid: 318 dea 64-6277-4 ec 3-ad 48-4 dfcb 7 a 54555
translation-type: tm+mt
source-git-commit: f5f5b294f503911108e1693b7c6cd128bee659c6

---


# Panoramica visualizzazioni

Ulteriori informazioni sulle visualizzazioni e sulle impostazioni di visualizzazione in Analysis Workspace.

[Tipi di visualizzazione in Analysis Workspace su YouTube](https://www.youtube.com/watch?v=b1zLEywRa6w&index=39&list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS) (2:57)

## Visualizations panel {#section_DC07F032FBEF4046A40F7B95C28DA018}

Per visualizzare il pannello Visualizzazioni, fai clic su **[!UICONTROL Visualizations] (Visualizzazioni) nel pannello laterale.**

![Risultato passaggio](assets/visualizations.png)

Se usi già Adobe Analytics, la maggior parte dei tipi di visualizzazione (come ad area, a barre, a torta e a linee) ti sarà familiare. Tuttavia, Analysis Workspace consente di configurare le impostazioni di visualizzazione e offre molti tipi di visualizzazioni nuovi o unici, con funzionalità interattive.

## Visualization settings {#section_D3BB5042A92245D8BF6BCF072C66624B}

To access [!UICONTROL Visualization Settings], drag a visualization to the [!UICONTROL Freeform Panel], then click the [!UICONTROL Visualization Settings] gear icon.

>[!IMPORTANT]
>
>Le impostazioni visualizzate dipendono dalla visualizzazione. Alcune impostazioni non sono applicabili ad alcune visualizzazioni. Inoltre, alcune impostazioni avanzate sono disponibili **solo** per specifiche visualizzazioni, ad esempio le [impostazioni Istogramma](../../../analyze/analysis-workspace/visualizations/histogram.md#section_09D774C584864D4CA6B5672DC2927477).

![](assets/visualization_settings.png)

<table id="table_E0695243886046979EE609FAE5D6EA00"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Impostazione </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Percentuali </p> </td> 
   <td colname="col2"> <p>Visualizza i valori in percentuale. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Sovrapposizione 100% </p> </td> 
   <td colname="col2"> <p>Questa impostazione – applicata a visualizzazioni Superfici sovrapposte, Barre sovrapposte o Barre orizzontali sovrapposte – converte il grafico in una visualizzazione con sovrapposizione 100%. Esempio: </p> <p><img  src="assets/stacked_100_percent.png" placement="break" width="400px" id="image_1B60D53F7EB84571B1580BC3A1E603EE" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Visualizzazione legenda </p> </td> 
   <td colname="col2"> <p>Consente di nascondere il testo di dettagli del filtro per la visualizzazione Numero di riepilogo/Variazione di riepilogo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Limite massimo elementi </p> </td> 
   <td colname="col2"> <p>Consente di limitare il numero di elementi presentati in una visualizzazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ancoraggio asse Y su zero </p> </td> 
   <td colname="col2"> <p> Se tutti i valori rappresentati sul grafico sono uniformemente al di sopra dello zero, per impostazione predefinita la parte inferiore dell’asse y sarà NON-ZERO. Attivando questa opzione, l’asse y verrà forzata sullo zero (e il grafico verrà ridisegnato). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Normalizzazione </p> </td> 
   <td colname="col2"> <p>Forza le metriche ad adeguarsi alle proporzioni. See <a href="https://marketing.adobe.com/resources/help/en_US/reference/?f=normalization" format="https" scope="external"> Normalization</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Visualizza asse doppia </p> </td> 
   <td colname="col2"> <p>Applicabile solo in presenza di due metriche: è possibile avere un asse y a sinistra (per una metrica) e a destra (per l'altra metrica). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mostra anomalie </p> </td> 
   <td colname="col2"> <p>Ottimizza i grafici a linee e le tabelle a forma libera per la visualizzazione delle anomalie nei dati. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Create Visual icon {#section_9C11D9DEDC42413AA53E69A71A509DFC}

If you are not sure which visualization to pick, click the **[!UICONTROL Create Visual]** icon in any table row. Questa icona appare quando il mouse viene passato sulla riga di tabella. Facendo clic su di essa, Analysis Workspace cerca di fare una stima ragionata per individuare la visualizzazione più idonea ai tuoi dati. Ad esempio, selezionando fino a 3 segmenti, si crea un diagramma di Venn. Per più di 3 segmenti, crea un grafico a barre. Per altri tipi di dati, potrebbe creare un grafico a linee, ecc.

![](assets/create-visual.png)

## Right-click visualization/panel menu {#section_05B7914D4C9E443F97E2BFFDEC70240C}

Per accedere alle impostazioni contestuali disponibili per un grafico, fai clic con il pulsante destro del mouse accanto all’intestazione di una visualizzazione o di un pannello. Saranno disponibili tutte o alcune delle seguenti impostazioni:

![](assets/right-click_menu.png)

| Impostazione | Descrizione |
|--- |--- |
| Inserisci visualizzazione copiata/pannello copiato | Consente di incollare (inserire) l’elemento copiato in un’altra posizione all’interno del progetto o in un progetto completamente diverso. |
| Copia visualizzazione/pannello | Consente di fare clic con il pulsante destro del mouse e copiare una visualizzazione o un pannello. |
| Duplica visualizzazione/pannello | Crea una copia della visualizzazione corrente, che potrai quindi modificare. |
| Comprimi tutti i pannelli | Comprime tutti i pannelli del progetto. |
| Comprimi tutte le visualizzazioni nel pannello | Comprime tutte le visualizzazioni nel pannello di progetto corrente. |
| Espandi tutti i pannelli | Espande tutti i pannelli del progetto. |
| Espandi tutte le visualizzazioni nel pannello | Espande tutte le visualizzazioni nel pannello di progetto corrente. |
| Modifica descrizione | Aggiungi (o modifica) un testo descrittivo per la visualizzazione o il pannello. La descrizione viene visualizzata in Progetto &gt; Informazioni e impostazioni progetto . |
| Ottieni collegamento pannello | Consente di indirizzare un utente a uno specifico pannello in un progetto. |
| Ottieni collegamento visualizzazione | Consente di copiare e condividere il collegamento per far sì che altri utenti possano accedere direttamente a questa visualizzazione. Gli utenti dovranno effettuare l’accesso. |
| Ricomincia | (Per Flusso, Venn, Istogramma) Elimina la configurazione della visualizzazione corrente e apre un nuovo pannello dove la puoi riconfigurare. |

## Edit legend labels {#section_94F1988CB4B9434BA1D9C6034062C3DE}

È possibile modificare i nomi delle serie nelle legende delle visualizzazioni (Abbandono, Superfici, Superfici sovrapposte, Barre, Barre sovrapposte, Anello, Istogramma, Barre orizzontali, Barre orizzontali sovrapposte, Linee, Dispersione e Venn) per facilitare la lettura dei grafici.

La modifica della legenda **non** è disponibile per le visualizzazioni Mappa ad albero, Bullet, Variazione di riepilogo o Numero di riepilogo, Testo, Forma libera, Istogramma, Coorte o Flusso.

Ad esempio, per modificare un’etichetta di legenda in un grafico a linee:

1. Fai clic su una delle etichette della legenda.
1. Fai clic su **[!UICONTROL Edit Label]**.

   ![](assets/edit-label.png)

1. Inserisci il nuovo testo dell’etichetta.
1. Press **[!UICONTROL Enter]** to save.

Per approfondire, utilizza questo [collegamento a un video](https://www.youtube.com/watch?v=mry3vDrTml0&index=61&list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS) sull’argomento.
