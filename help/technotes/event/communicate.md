---
title: Comunicazione dell’impatto agli utenti
description: Scopri modi efficaci per comunicare l’impatto di un evento nell’organizzazione.
exl-id: 9ba83f3f-2eea-44c2-80b2-a0a9111d51cf
source-git-commit: d198e8ef0ec8415a4a555d3c385823baad6104fe
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 2%

---

# Comunicazione dell’impatto dell’evento agli utenti

Se i dati [sono interessati da un evento](overview.md), è importante comunicare tale evento agli utenti della tua organizzazione.

* Sviluppa una liberatoria comune da utilizzare nelle comunicazioni per garantire la coerenza
* Fornisci comunicazioni continue agli utenti di Analytics e alle principali parti interessate durante e dopo l’evento
* Inserire un promemoria del calendario per le tappe successive, ad esempio il mese o l’anno successivo. Questa comunicazione in futuro aiuta a ricordare agli utenti che visualizzano i rapporti l’impatto nei rapporti mese-su-mese o anno-su-anno.

In Adobe Analytics, le sezioni seguenti mostrano diversi modi in cui puoi comunicare con gli utenti all’interno della tua organizzazione. Puoi anche utilizzare altri metodi al di fuori di Adobe Analytics, ad esempio e-mail, per comunicare con gli utenti.

## Comunicazione tramite descrizioni di pannelli o visualizzazioni

Se disponi di un progetto Workspace condiviso tra gli utenti dell’organizzazione, puoi comunicare l’impatto di un evento tramite le descrizioni dei pannelli o delle visualizzazioni. Fai clic con il pulsante destro del mouse su un pannello o un’intestazione di visualizzazione, quindi seleziona **[!UICONTROL Edit description]**.

![Descrizione del pannello](assets/panel_description.png)

## Comunicare attraverso le visualizzazioni di testo

Puoi anche comunicare l’impatto di un evento tramite visualizzazioni di testo dedicate. Consulta [Visualizzazioni di testo](/help/analyze/analysis-workspace/visualizations/text.md) nella guida utente Analisi.

![Visualizzazione testo](assets/text_visualization.png)

## Aggiungere eventi calendario personalizzati alle tendenze in Workspace

Per qualsiasi visualizzazione con tendenze in Workspace, puoi aggiungere in una serie che rappresenta l’intervallo di date interessato.

1. Crea una metrica calcolata con il segmento &quot;Giorni interessati&quot; seguendo [Escludi date specifiche nell&#39;analisi](segments.md).
1. Aggiungi la metrica desiderata all’area di lavoro della metrica calcolata.

   ![Metrica](assets/calcmetric_event.png)

1. Aggiungi un titolo e una descrizione per informare gli utenti dell’impatto. Puoi anche assegnare tag a questa metrica come annotazione del calendario, se necessario.

   ![Titolo e descrizione](assets/calcmetric_title_description.png)

1. In una tabella a forma libera, aggiungi la dimensione &quot;Giorno&quot;. Aggiungi &quot;Visite&quot; e la metrica calcolata come colonne affiancate.

   ![Tabella a forma libera](assets/calcmetric_freeform.png)

1. Fai clic sull’icona a forma di ruota dentata delle impostazioni della colonna per la metrica calcolata e abilita **[!UICONTROL Interpret zero as no value]**.

   ![Impostazioni metriche calcolate](assets/calcmetric_zero_no_value.png)

1. Aggiungi una visualizzazione Linee . I giorni interessati sono rappresentati con un colore diverso. Per ulteriori informazioni, gli utenti possono anche fare clic sull’icona &quot;Informazioni&quot; nella metrica calcolata.

   ![Icona Info](assets/calcmetric_infoicon.png)

## Utilizzare un evento calendario in Reports &amp; Analytics

Se utilizzi Reports &amp; Analytics, puoi utilizzare un [evento calendario](/help/components/t-calendar-event.md) per evidenziare i giorni interessati in qualsiasi rapporto con tendenze. Questo metodo non si applica ad Analysis Workspace.

1. Passa a **[!UICONTROL Components]** > **[!UICONTROL All components]** > **[!UICONTROL Calendar events]**.
2. Inserisci il titolo, l’intervallo di date e il testo della nota desiderati.
3. Fai clic su **[!UICONTROL Save]**.

![Evento calendario](assets/exclude_calendar_event.png)
