---
description: Combina i dati con e senza marca temporale in un’unica suite di rapporti.
title: Configurazione timestamp
feature: Admin Tools
uuid: 0fa63658-1cc2-4adc-8d51-a0662d0aa941
exl-id: 4d64225a-5eb8-4b7b-ba13-3cdc12dd6651
role: Admin
source-git-commit: 2d5348a4a6377313f5aab229214d97a02c826939
workflow-type: tm+mt
source-wordcount: '399'
ht-degree: 5%

---

# Configurazione timestamp

La pagina di amministrazione &#39;[!UICONTROL Timestamps configuration]&#39; consente di abilitare **[!UICONTROL Timestamps optional]** per una o più suite di rapporti. Questa impostazione consente di combinare dati con e senza marca temporale in un’unica suite di rapporti.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL General]** > **[!UICONTROL Timestamps optional]**

## Impostazione marca temporale corrente

Questa sezione mostra la configurazione corrente della marca temporale per la suite di rapporti selezionata. Può essere uno dei tre valori possibili:

* **Marca temporale non consentita (impostazione `visitorID` supportata)**
* **Marca temporale richiesta (impostazione `visitorID` non supportata)**
* **Marca temporale opzionale (impostazione `visitorID` supportata ma non negli hit con marca temporale)**

Sotto questo testo è presente una casella di controllo con etichetta **[!UICONTROL Convert selected report suites to Timestamps optional]**. Selezionando questa casella di controllo e selezionando **[!UICONTROL Save]**, abilita [!UICONTROL Timestamps optional] per le suite di rapporti selezionate.

## Marca temporale non consentita

Quando invii dati a una suite di rapporti utilizzando questa configurazione di marca temporale, questa è la data in cui i server di elaborazione di Adobe ricevono l’hit. Se si tenta di impostare la variabile [`timestamp`](/help/implement/vars/page-vars/timestamp.md), l&#39;hit viene eliminato definitivamente.

## Marca temporale richiesta

Quando invii dati a una suite di rapporti utilizzando questa configurazione di marca temporale, ogni hit deve includere la variabile [`timestamp`](/help/implement/vars/page-vars/timestamp.md). Se in un hit manca una variabile di implementazione `timestamp`, l&#39;hit viene eliminato definitivamente.

I dati della sessione abilitati per le marche temporali vengono conservati per un massimo di 92 giorni. In altre parole, una visita è &quot;tenuta aperta&quot; per 92 giorni, consentendo l’inclusione di eventuali hit aggiuntivi nella stessa visita/sessione. Anche se è possibile aggiungere dati a sessioni esistenti, Adobe consiglia di aggiungere hit in ordine per visitatore. Gli hit ricevuti fuori ordine per visitatore possono produrre risultati di reporting imprevisti, anche se molte di queste limitazioni sono attenuate dall’elaborazione al momento del reporting.

## Marca temporale opzionale

L&#39;impostazione &#39;[!UICONTROL Timestamps optional]&#39; consente di integrare e creare rapporti tra più suite di rapporti con o senza la variabile [`timestamp`](/help/implement/vars/page-vars/timestamp.md). I casi d&#39;uso ideali per [!UICONTROL Timestamps optional] includono:

* Combinare dati con e senza marca temporale nella stessa suite di rapporti globale
* Inviare dati con marca temporale da un’app mobile a una suite di rapporti globale
* Aggiornare le app per utilizzare il tracciamento offline senza dover creare una nuova suite di rapporti

Questa impostazione è abilitata per impostazione predefinita per tutte le nuove suite di rapporti, a meno che la nuova suite di rapporti non sia stata copiata da una suite di rapporti con un’altra impostazione di configurazione della marca temporale.

>[!WARNING]
>
>Se utilizzi [!UICONTROL Timestamps optional], non impostare [`visitorID`](/help/implement/vars/config-vars/visitorid.md) sui dati con marca temporale. Questa azione può causare dati fuori ordine e influire negativamente sui calcoli dei tempi (come il tempo trascorso), sull’attribuzione, sui conteggi di numero di visite/visite e sui rapporti sui percorsi.

Dopo aver abilitato [!UICONTROL Timestamps optional], non è possibile disabilitarlo in questa interfaccia. Nel caso improbabile che tu voglia tornare a un’altra impostazione di configurazione della marca temporale, contatta l’Assistenza clienti di Adobe.
