---
title: Derivazione dei dati interessati dagli eventi
description: Utilizza le metriche calcolate per correggere i dati con tendenze interessati da un evento.
exl-id: 0fe70c8b-fa07-47e4-b6b3-b55eebad1fef
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: tm+mt
source-wordcount: '321'
ht-degree: 4%

---

# Derivazione dei dati interessati dagli eventi

Se si dispone di dati [interessato da un evento](overview.md), puoi utilizzare le metriche calcolate per derivare i valori stimati per la durata dell’evento. Ad esempio, se si è verificato un evento che ha causato un calo del 25% dei dati, puoi utilizzarlo come moltiplicatore in una metrica calcolata.

Questi passaggi funzionano meglio quando comprendi l’impatto di un evento, sia dal punto di vista della segmentazione che del confronto delle date. Assicurati di seguire [Confrontare le date interessate da un evento con intervalli precedenti](compare-dates.md) e [Escludere date specifiche nell’analisi](segments.md) prima di seguire questa pagina.

>[!NOTE]
>
>Questo approccio è una stima basata su una serie specifica di input e intervalli di date. Non sarà una soluzione completa per tutti i casi d’uso o per porzioni di dati. Inoltre, questo approccio richiede che l’intervallo di date interessato disponga di almeno 1 hit da cui calcolare.

Per creare una metrica calcolata stimata per il periodo di tempo interessato:

1. Crea due segmenti per &quot;Giorni interessati&quot; ed &quot;Escludi giorni interessati&quot;, come descritto in [Escludere date specifiche nell’analisi](segments.md).
2. Passa a **[!UICONTROL Components]** > **[!UICONTROL Calculated metrics]**.
3. Fai clic su **[!UICONTROL Add]** (Usa modello di attribuzione non predefinito).
4. Trascina entrambi i segmenti sopra elencati nell’area di lavoro di definizione. Cambia l’operatore tra le due in una `+` per riassumerli.
5. Aggiungi la metrica desiderata all’interno di entrambi i segmenti. Ad esempio, puoi utilizzare la metrica &quot;Visite&quot;.

   ![Generatore di segmenti](assets/event_segment_builder.png)

6. Clic **[!UICONTROL Add]** in alto a destra nel contenitore &quot;Giorni interessati&quot;, quindi fai clic su **[!UICONTROL Static number]**. Impostare il numero statico sulla percentuale di offset dei dati, come descritto in [Confrontare le date interessate da un evento con intervalli precedenti](compare-dates.md). In questo esempio, l&#39;offset è 25% o 1,25.

   ![Numero statico](assets/event_static_number.png)

7. Applica la metrica &quot;corretta&quot; una accanto all’altra in una tabella a forma libera con tendenze. Tutti i giorni al di fuori dell’evento riflettono il normale conteggio delle metriche, mentre tutti i giorni interessati utilizzano l’offset del moltiplicatore.

   ![Metrica corretta](assets/event_corrected.png)

8. Visualizza i dati in una visualizzazione a linee per vedere l’effetto della metrica corretta.

   ![Riga corretta](assets/event_line.png)
