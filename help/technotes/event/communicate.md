---
title: Comunicare l’impatto agli utenti
description: Scopri modi efficaci per comunicare l’impatto di un evento nella tua organizzazione.
exl-id: 9ba83f3f-2eea-44c2-80b2-a0a9111d51cf
feature: Curate and Share
source-git-commit: 29ab0cc535bd8f74b50428c11756bf8b446a23ab
workflow-type: tm+mt
source-wordcount: '339'
ht-degree: 0%

---

# Comunicazione dell’impatto dell’evento agli utenti

Se si dispone di dati [interessati da un evento](overview.md), è importante comunicare tale evento agli utenti dell&#39;organizzazione.

* Sviluppa una liberatoria comune che puoi utilizzare nelle comunicazioni per coerenza
* Fornisci comunicazioni continue agli utenti di Analytics e alle principali parti interessate durante e dopo l’evento
* Posiziona un promemoria del calendario per le fasi cardine successive, ad esempio il mese o l’anno successivo. Questa comunicazione nel futuro consente di ricordare agli utenti che visualizzano i rapporti l’impatto nei rapporti mese-su-mese o anno-su-anno.

In Adobe Analytics, le sezioni seguenti mostrano diversi modi di comunicare con gli utenti dell’organizzazione. Per comunicare con gli utenti, puoi inoltre utilizzare altri metodi al di fuori di Adobe Analytics, ad esempio e-mail.

## Comunicazione attraverso descrizioni di pannelli o visualizzazioni

Se un progetto Workspace è condiviso tra gli utenti dell’organizzazione, puoi comunicare l’impatto di un evento tramite descrizioni di pannelli o visualizzazioni. Fai clic con il pulsante destro del mouse su un pannello o su un&#39;intestazione di visualizzazione, quindi seleziona **[!UICONTROL Edit description]**.

![Descrizione pannello](assets/panel_description.png)

## Comunicazione tramite visualizzazioni di testo

Puoi anche comunicare l’impatto di un evento tramite visualizzazioni di testo dedicate. Vedi [Visualizzazioni di testo](/help/analyze/analysis-workspace/visualizations/text.md) nella guida utente Analizza.

![Visualizzazione testo](assets/text_visualization.png)

## Aggiungere eventi di calendario personalizzati alle tendenze in Workspace

Per qualsiasi visualizzazione con tendenze in Workspace, puoi aggiungere una serie che rappresenta l’intervallo di date interessato.

1. Creare una metrica calcolata con il segmento &#39;Giorni interessati&#39; seguendo [Escludi date specifiche nell&#39;analisi](segments.md).
1. Aggiungi la metrica desiderata all’area di lavoro della metrica calcolata.

   ![Metrica](assets/calcmetric_event.png)

1. Aggiungi un titolo e una descrizione per informare gli utenti dell’impatto. Puoi anche assegnare a questa metrica un tag come annotazione del calendario, se lo desideri.

   ![Titolo e descrizione](assets/calcmetric_title_description.png)

1. In una tabella a forma libera, aggiungi la dimensione &quot;Giorno&quot;. Aggiungi &quot;Visite&quot; e la metrica calcolata come colonne affiancate.

   ![Tabella a forma libera](assets/calcmetric_freeform.png)

1. Fare clic sull&#39;icona a forma di ingranaggio delle impostazioni di colonna per la metrica calcolata e abilitare **[!UICONTROL Interpret zero as no value]**.

   ![Impostazioni metriche calcolate](assets/calcmetric_zero_no_value.png)

1. Aggiungi una visualizzazione Linee. I giorni interessati sono rappresentati con un colore diverso. Per ulteriori informazioni, gli utenti possono anche fare clic sull’icona &quot;Info&quot; nella metrica calcolata.

   ![Icona informazioni](assets/calcmetric_infoicon.png)

