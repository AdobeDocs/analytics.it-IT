---
title: Derivazione dei dati interessati dagli eventi
description: Utilizzare le metriche calcolate per correggere i dati con tendenze interessati da un evento.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '263'
ht-degree: 4%

---


# Derivazione dei dati interessati dagli eventi

Se i dati [sono influenzati da un evento](overview.md), puoi utilizzare le metriche calcolate per derivare i valori con tendenze per la durata dell&#39;evento. Ad esempio, in presenza di un evento che ha causato un calo del 25% dei dati, puoi utilizzarlo come moltiplicatore in una metrica calcolata.

>[!NOTE]
>
>Questi passaggi consentono di comprendere meglio l&#39;impatto di un evento, sia dal punto di vista della segmentazione che del confronto delle date. Seguire [Confrontare le date interessate da un evento con gli intervalli](compare-dates.md) precedenti ed [Escludere date specifiche nell&#39;analisi](segments.md) prima di seguire questa pagina.

1. Crea due segmenti per &quot;giorni interessati&quot; e &quot;Escludi giorni interessati&quot;, come indicato in [Escludi date specifiche nell&#39;analisi](segments.md).
2. Passa a **[!UICONTROL Components]** > **[!UICONTROL Calculated metrics]**.
3. Fai clic su **[!UICONTROL Add]**.
4. Trascina entrambi i segmenti sopra nel quadro di definizione. Cambiare l&#39;operatore tra di essi in una `+` somma.
5. Aggiungi la metrica desiderata in entrambi i segmenti. Ad esempio, puoi usare la metrica &quot;Visite&quot;.

   ![Generatore di segmenti](assets/event_segment_builder.png)

6. Fai clic **[!UICONTROL Add]** in alto a destra del contenitore &quot;Giorni interessati&quot;, quindi fai clic su **[!UICONTROL Static number]**. Impostare il numero statico sulla percentuale di scostamento dei dati, come indicato in [Confronta date interessate da un evento con intervalli](compare-dates.md)precedenti. In questo esempio, l&#39;offset è pari al 25% o 1,25.

   ![Numero statico](assets/event_static_number.png)

7. Applica la metrica &quot;corretta&quot; affiancata in una tabella a forma libera con tendenze. Tutti i giorni al di fuori dell’evento riflettono il loro normale conteggio delle metriche, mentre tutti i giorni interessati utilizzano l’offset del moltiplicatore.

   ![Metrica corretta](assets/event_corrected.png)

8. Visualizzare i dati in una visualizzazione a linee per vedere l&#39;effetto della metrica corretta.

   ![Linea corretta](assets/event_line.png)
