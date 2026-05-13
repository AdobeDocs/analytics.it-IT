---
description: Scopri in che modo un flusso interdimensionale consente di esaminare i percorsi seguiti dagli utenti attraverso varie dimensioni.
title: Flussi interdimensionali
uuid: 51d08531-1c56-46c7-b505-bd8d5e6aa6c1
feature: Visualizations
role: User, Admin
exl-id: f84917a4-2c07-48fb-9af3-d96c537da65c
TQID: https://experienceleague.adobe.com/9OjAFYHo5uhcfbQQOB46jfG1R2wIQCBHXEr842EcZQ0
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2: id: dcae653e-62c6-4cc8-84e6-ee110b848296
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 317
ht-degree: 5%

---

# Flussi interdimensionali

Un flusso interdimensionale ti consente di esaminare i percorsi seguiti dai clienti attraverso varie dimensioni.

<!-- 

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Inter-dimensional flows](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/analyzing-customer-journeys/text-wrapping-and-multi-dimensional-flow){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

-->

Questo articolo mostra come utilizzare questo flusso per due casi d’uso: interazioni ed eventi delle app mobili e come le campagne guidano le visite web.

## Interazioni ed eventi delle app mobili

La dimensione [!UICONTROL Screen Name] viene utilizzata in questo flusso di esempio per vedere come gli utenti utilizzano le varie schermate (scene) nell&#39;app. La schermata superiore restituita è **[!UICONTROL luma: content: ios: en: home]**, che è la home page dell&#39;app:

![Un flusso che mostra l&#39;elemento aggiunto.](assets/flowapp.png)

Per esplorare l&#39;interazione tra schermate e tipi di evento (come aggiungi al carrello, acquisti e altri) in questa app, trascina e rilascia la dimensione **[!UICONTROL Event Types]**:

* Per sostituire la dimensione, esegui le operazioni riportate di seguito.

  ![Flusso che mostra la dimensione Pagina trascinata in più aree.](assets/flowapp-replace.png)

* Al di fuori della visualizzazione del flusso corrente, per aggiungere la dimensione:

  ![Flusso che mostra la dimensione Pagina trascinata nello spazio vuoto alla fine.](assets/flowapp-add.png)

La visualizzazione di flusso seguente mostra il risultato dell&#39;aggiunta della dimensione **[!UICONTROL Event Types]**. La visualizzazione fornisce informazioni su come gli utenti dell’app mobile si spostano attraverso le varie schermate dell’app prima di aggiungere prodotti al carrello, chiudere l’applicazione, visualizzare un’offerta e altro ancora.

![Un fLow che mostra i risultati della dimensione Pagina nella parte superiore dell&#39;elenco.](assets/flowapp-result.png)

## Come le campagne guidano le visite web

Desideri analizzare quali campagne sono all’origine delle visite al sito web. Si crea una visualizzazione di flusso con **[!UICONTROL Campaign Name]** come dimensione

![Dimensione nome campagna Web flusso](assets/flowweb.png)

L&#39;ultima dimensione **[!UICONTROL Campaign Name]** viene sostituita con la dimensione **[!UICONTROL Formatted Page Name]** e viene aggiunta un&#39;altra dimensione **[!UICONTROL Formatted Page Name]** alla fine della visualizzazione del flusso.

![Nome campagna Web di flusso e dimensione pagina Web](assets/flowweb-replace.png)

Puoi passare il cursore del mouse su uno dei flussi per visualizzare ulteriori dettagli. Ad esempio, quali campagne hanno generato un’estrazione dal carrello.

![Passaggio del mouse sul nome della campagna Web e sulla dimensione della pagina Web](assets/flowweb-hover.png)
