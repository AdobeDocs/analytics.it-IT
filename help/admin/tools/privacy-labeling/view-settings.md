---
description: La finestra di dialogo Etichetta privacy per governance dei dati fornisce una panoramica delle etichette sulla privacy e degli spazi dei nomi di una suite di rapporti. Da qui è possibile esportare le impostazioni in un file .csv.
title: Visualizzazione/gestione delle etichette sulla privacy per la governance dei dati
feature: Data Governance
role: Admin
exl-id: 87b0be42-1098-4e72-8eb8-0c1bb56791f8
TQID: https://experienceleague.adobe.com/0muNPJ8HVoX6ro-bqp6I3dWiOrNGSHF9yBy-qRWLhZI
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adebid: eddd9b14-83bd-4ff4-9072-54a4a484abb7id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 783
ht-degree: 24%

---

# Visualizzazione/gestione delle etichette sulla privacy per la governance dei dati

La finestra di dialogo **[!UICONTROL Privacy Labeling for Data Governance]** fornisce una panoramica delle etichette per la privacy e degli spazi dei nomi di una suite di rapporti. Da qui è possibile esportare le impostazioni in un file .csv.

## Visualizza etichette privacy {#view-privacy}

1. Accedi a Adobe Experience Cloud.
2. Passa a **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL All admin]** > **[!UICONTROL Data configuration & collection]** > **[!UICONTROL Data Governance]**.

   >[!NOTE]
   >
   >Se questa voce di menu non viene visualizzata, devi essere aggiunto a un profilo di prodotto [in Admin Console](/help/admin/admin-console/permissions/product-profile.md) con autorizzazioni per questa funzionalità oppure puoi accedere a una suite di rapporti all&#39;interno di Admin Console.

3. In alto a destra, seleziona una suite di rapporti di cui desideri visualizzare o gestire le etichette sulla privacy.

   ![](assets/privacy_labeling.png)

| Impostazione | Descrizione |
| --- | --- |
| **[!UICONTROL Component Name]** | In questa colonna sono elencati tutti i componenti (dimensioni, metriche) che fanno parte di questa suite di rapporti. |
| **[!UICONTROL Identity]** | Le etichette di identità “I” vengono utilizzate per categorizzare i dati che possono identificare o contattare una persona specifica. [Ulteriori informazioni](/help/admin/tools/privacy-labeling/labels.md#data-privacy-identity-labels) |
| **[!UICONTROL Sensitivity]** | Le etichette per dati sensibili “S” vengono utilizzate per categorizzare i dati sensibili, come i dati geografici. In futuro saranno introdotte etichette aggiuntive per i dati sensibili per identificare altri tipi di informazioni sensibili. [Ulteriori informazioni](/help/admin/tools/privacy-labeling/labels.md#sensitive-data-labels) |
| **[!UICONTROL GDPR Access]** | Le etichette per la governance dei dati consentono agli utenti di classificare i dati che riflettono considerazioni relative alla privacy e condizioni contrattuali conformi alle normative e alle politiche aziendali. [Ulteriori informazioni](/help/admin/tools/privacy-labeling/labels.md#data-privacy-access-labels) |
| **[!UICONTROL GDPR Delete]** | L’etichetta Elimina è necessaria solo per i campi che contengono un valore che consentirebbe l’associazione di un hit all’interessato (ovvero che consentirebbe l’identificazione dell’interessato). [Ulteriori informazioni](/help/admin/tools/privacy-labeling/labels.md#data-privacy-delete-labels) |
| **[!UICONTROL Namespace]** | Quando si applica a una variabile un’etichetta ID-DEVICE o ID-PERSON, viene richiesto di fornire uno spazio dei nomi. Puoi utilizzare uno spazio dei nomi definito in precedenza o definirne uno nuovo. |
| **[!UICONTROL Category]** | Riferisce il tipo di componente, ad esempio Componente standard, Variabile di conversione e così via. |

{style="table-layout:auto"}

## Copiare le etichette di privacy in una suite di rapporti  {#copy-to-rs}

Se desideri applicare le stesse impostazioni di Privacy dei dati a più di una suite di rapporti, effettua le seguenti operazioni:

1. Seleziona la variabile da copiare. Tieni presente che puoi copiare le etichette solo per una variabile alla volta.
1. Fare clic su **[!UICONTROL Copy to Report Suite(s)]** nella parte inferiore della finestra di dialogo Governance dei dati.

   ![Copia nella suite di rapporti](assets/copy_to_reportsuite.png)

1. La schermata risultante mostra il nome della variabile, le etichette attualmente applicate su cui stai tentando di copiare, le suite di rapporti e i relativi ID e se le impostazioni nelle suite di rapporti di destinazione corrispondono.

   ![Copia dell&#39;etichetta nella suite di rapporti](assets/copy_to_rs.png)

   >[!IMPORTANT]
   >
   >Tieni presente che tutte le suite di rapporti selezionate devono essere mappate nell’organizzazione Experience Cloud.

   Quando copi le etichette per una variabile o per un set di variabili in una suite di rapporti diversa, la copia passa alla variabile nella posizione corrispondente nella suite di rapporti di destinazione. Per i componenti standard, le variabili elenco e gli eventi di successo, le etichette verranno copiate nella variabile con **lo stesso nome** nella suite di rapporti di destinazione.

   Tuttavia, per le variabili di conversione (eVar) e le dimensioni di traffico (prop), la copia viene inviata alla variabile con **lo stesso numero** nella suite di rapporti di destinazione. Ad esempio, eVar12 verrà copiata in eVar12 in tutte le suite di rapporti di destinazione. I nomi di queste variabili verranno ignorati durante la determinazione della destinazione della copia. Se la variabile corrispondente non è abilitata nella suite di rapporti di destinazione, la copia non riuscirà per tale variabile.

   Durante la copia delle etichette per le classificazioni definite per una variabile, le etichette verranno copiate in una classificazione nella variabile corrispondente nella suite di rapporti di destinazione (ad esempio da eVar7 a eVar7) che ha un nome identico alla classificazione da copiare. In caso contrario, la copia delle etichette di tale classificazione avrà esito negativo.

1. Seleziona la casella accanto a una o più suite di rapporti in cui le impostazioni corrispondono.
1. Fai clic su **[!UICONTROL Apply]**.

   Dopo l&#39;applicazione di un&#39;etichetta viene visualizzato un messaggio di stato. Il messaggio di stato includerà i nomi di tutte le variabili o classificazioni di destinazione e delle relative suite di rapporti per le quali la copia non è riuscita.

   >[!IMPORTANT]
   >
   >Controlla sempre le suite di rapporti di destinazione per assicurarti che le etichette siano state copiate correttamente. Questo è molto importante soprattutto per le variabili che hanno le etichette ID o DEL.

## Esporta in un file .csv {#export-csv}

Puoi scaricare un file CSV contenente tutte le definizioni delle etichette correnti per tutte le variabili per le suite di rapporti selezionate. Consigliamo al team legale di esaminare le scelte di etichettatura; questa opzione facilita la revisione. Invece di eseguire la revisione durante l’accesso all’interfaccia utente di governance dei dati, puoi condividere con loro il file .CSV.

1. Fai clic su **[!UICONTROL Export CSV]** in alto a destra per visualizzare questa finestra di dialogo:

   ![](assets/export_csv.png)

1. Seleziona una o più suite di rapporti per le quali desideri esportare tutte le impostazioni di governance dei dati.

## Modifica etichette privacy {#edit}

Consulta [Assegnare o modificare le etichette per la privacy della suite di rapporti](/help/admin/tools/privacy-labeling/labeling-overview.md).
