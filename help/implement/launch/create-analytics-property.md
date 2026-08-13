---
title: Creare una proprietà Analytics nei tag
description: Crea uno spazio per personalizzare la modalità di raccolta dei dati, utilizzando i tag.
feature: Tags
exl-id: ffcd8e97-4d29-489e-bc2b-88805400dad5
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/2cZHjGRwvLZPL-jmGLOQpgSXr5Rib8nMeqFWj2cCKAA'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: df312454-73c4-43f6-a90e-18f5043f074c
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: a947d2d7f45d4155a61cbfe0f8110851cca32e60
workflow-type: tm+mt
source-wordcount: 492
ht-degree: 15%

---

# Creare una proprietà tag in Adobe Analytics

I tag in Adobe Experience Platform consentono di integrare le soluzioni CX Enterprise sul sito Web (incluso Analytics). Questa pagina illustra in modo specifico come un amministratore di tag può ottenere un’implementazione di base di Adobe Analytics configurata correttamente.

## Prerequisiti

[Crea una suite di rapporti](/help/admin/tools/manage-rs/new-rs/t-create-a-report-suite.md): crea un silo per i dati di Analytics da raccogliere.

## Creare una proprietà tag e installare estensioni vitali

Le proprietà sono contenitori generali utilizzati per gestire i tag. Le estensioni consentono di installare tag specifici per il prodotto e configurarli.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic su **[!UICONTROL New Property]**.
1. Assegna alla proprietà un nome, ad esempio il titolo del sito web, e immetti il dominio in cui intendi implementare Analytics. Fai clic su **[!UICONTROL Save]**.
1. Fai clic sulla nuova proprietà tag creata per immetterne le impostazioni.
1. Fare clic sulla scheda **[!UICONTROL Extensions]**, quindi su **[!UICONTROL Catalog]**.
1. Individua il servizio Experience Cloud ID, quindi fai clic su **[!UICONTROL Install]**.
1. Tutte le impostazioni, incluso l’ID organizzazione IMS, devono essere già compilate. Fai clic su **[!UICONTROL Save]**.
1. Nel catalogo delle estensioni, individuare Adobe Analytics e fare clic su **[!UICONTROL Install]**.

Per informazioni più dettagliate, consulta la documentazione completa per l&#39;estensione [Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/analytics/overview.html?lang=it).

## Creare elementi dati per Adobe Analytics

Gli elementi dati sono riferimenti a parti specifiche del sito per raccogliere valori di variabili.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà tag che intendi implementare sul sito.
1. Fare clic sulla scheda **[!UICONTROL Data Elements]**, quindi su **[!UICONTROL Add Data Element]**.
1. Attribuisci all’elemento dati le seguenti impostazioni:

   * Nome: nome della pagina
   * Estensione: Core
   * Tipo di elemento dati: variabile JavaScript
   * Nome variabile JavaScript: `window.document.title`

     >[!NOTE]
     >
     >Questo valore funge da esempio per iniziare. Se la tua organizzazione definisce un valore migliore per il nome della pagina, ad esempio un valore del livello dati, puoi immetterlo qui.
   * Pulisci testo selezionato
   * Durata archiviazione: nessuna
1. Fai clic su **[!UICONTROL Save]**.

## Creare regole per Adobe Analytics

Le regole mappano gli elementi dati ai valori delle variabili di Analytics e determinano quando tali valori vengono inviati ai server di Adobe.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà tag che intendi implementare sul sito.
1. Fare clic sulla scheda **[!UICONTROL Rules]**, quindi su **[!UICONTROL Add Rule]**. Denominarlo `Global Rule`.
1. Fai clic su **[!UICONTROL Add]** accanto agli eventi e immetti le seguenti impostazioni:
   * Estensione: Core
   * Tipo evento: libreria caricata (parte superiore della pagina)
   * Nome: Core - Library Loaded (Page Top)
1. Fai clic su **[!UICONTROL Keep Changes]**.
1. In **[!UICONTROL Actions]**, fare clic su **[!UICONTROL Add]** e immettere le impostazioni seguenti:
   * Estensione: Adobe Analytics
   * Tipo azione: Imposta variabili
   * Nome pagina: fare clic sull&#39;icona del contenitore e selezionare l&#39;elemento dati `Page Name`.
   * Campaign: parametro di query con valore `cid`
1. Fai clic su **[!UICONTROL Keep Changes]**.
1. Fai clic sul segno Più accanto alle azioni per aggiungere un’altra azione, quindi immetti le seguenti impostazioni:
   * Estensione: Adobe Analytics
   * Tipo azione: invia beacon
   * Nome: Adobe Analytics - Invia beacon
   * Tracciamento: s.t()
1. Fai clic su **[!UICONTROL Keep Changes]**.
1. Verificare che siano impostati l&#39;evento e due azioni, quindi fare clic su **[!UICONTROL Save]**.

## Passaggi successivi

[Implementa Analytics nell&#39;ambiente di sviluppo](deploy-dev.md): ottieni il codice Analytics funzionante in un ambiente di test.
