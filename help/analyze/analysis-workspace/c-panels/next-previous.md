---
description: Pannello che mostra gli elementi dimensionali precedenti o successivi per una dimensione specifica.
title: Pannello elemento successivo o precedente
feature: Panels
role: User, Admin
exl-id: 9f2f8134-2a38-42bb-b195-5e5601d33c4e
source-git-commit: d173a6c6c9751a86f4218ec842da17da14f8485b
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 5%

---

# Pannello elemento successivo o precedente

Questo pannello contiene una serie di tabelle e visualizzazioni per identificare facilmente l’elemento dimensione successivo o precedente per una dimensione specifica. Ad esempio, puoi scoprire a quali pagine i clienti accedono più spesso dopo aver visitato la home page.

## Accedere al pannello

Puoi accedere al pannello da [!UICONTROL Reports] o da [!UICONTROL Workspace].

| Punto di accesso | Descrizione |
| --- | --- |
| [!UICONTROL Reports] | <ul><li>Il pannello è già stato rilasciato in un progetto.</li><li>La barra a sinistra è compressa.</li><li>Se hai selezionato [!UICONTROL Next page], sono già state applicate le impostazioni predefinite, ad esempio [!UICONTROL Page] per [!UICONTROL Dimension], e la pagina superiore come [!UICONTROL Dimension Item], [!UICONTROL Next] per [!UICONTROL Direction] e [!UICONTROL Visit] per [!UICONTROL Container]. Puoi modificare tutte queste impostazioni.</li></ul>![Pannello precedente/successivo](assets/next-previous.png) |
| Workspace | Crea un nuovo progetto e seleziona l’icona Pannello nella barra a sinistra. Trascinare quindi il pannello [!UICONTROL Next or previous item] sopra la tabella a forma libera. Si noti che i campi [!UICONTROL Dimension] e [!UICONTROL Dimension Item] sono vuoti. Seleziona una dimensione dall’elenco a discesa. [!UICONTROL Dimension items] sono compilati in base a [!UICONTROL dimension] scelto. Viene aggiunto l’elemento della dimensione superiore, ma puoi selezionare un elemento diverso. Le impostazioni predefinite sono Successivo e Visitatore. Di nuovo, puoi modificare anche questi.<p>![Pannello precedente/successivo](assets/next-previous2.png) |

{style="table-layout:auto"}

## Input del pannello {#Input}

È possibile configurare il pannello del pannello [!UICONTROL Next or previous item] utilizzando le seguenti impostazioni di input:

| Impostazione | Descrizione |
| --- | --- |
| Zona di rilascio del segmento (o di un altro componente) | Puoi trascinare segmenti o altri componenti per filtrare ulteriormente i risultati del pannello. |
| Dimensione | La dimensione per la quale desideri esplorare gli elementi successivi o precedenti. |
| Elemento Dimension | L&#39;oggetto specifico al centro della richiesta successiva/precedente. |
| Direzione | Specificare se si sta cercando l&#39;elemento di dimensione [!UICONTROL Next] o [!UICONTROL Previous]. |
| Contenitore | [!UICONTROL Visit] o [!UICONTROL Visitor] (impostazione predefinita) determinano l&#39;ambito della richiesta di informazioni. |

{style="table-layout:auto"}

Fare clic su **[!UICONTROL Build]** per creare il pannello.

## Output del pannello {#output}

Il pannello [!UICONTROL Next or previous item] restituisce un set completo di dati e visualizzazioni per consentirti di comprendere meglio le occorrenze che seguono o precedono specifici elementi dimensionali.

![Output pannello precedente/successivo](assets/next-previous-output.png)

![Output pannello precedente/successivo](assets/next-previous-output2.png)

| Visualizzazione | Descrizione |
| --- | --- |
| Barre orizzontali | Elenca gli elementi successivi (o precedenti) in base all’elemento dimensione scelto. Passando il puntatore del mouse su una singola barra viene evidenziato l’elemento corrispondente nella tabella a forma libera. |
| Numero di riepilogo | Numero di riepilogo di alto livello di tutte le occorrenze successive o precedenti degli elementi dimensione per il mese corrente (finora). |
| Tabella a forma libera | Elenca gli elementi successivi (o precedenti) in base all’elemento dimensione scelto, in formato tabella. Ad esempio, si trattava delle pagine più popolari (per occorrenze) a cui gli utenti accedevano dopo (o prima) la pagina Home o l’area di lavoro. |

{style="table-layout:auto"}
