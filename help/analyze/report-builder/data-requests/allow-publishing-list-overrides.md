---
description: Quando pianifichi un rapporto, puoi scegliere una lista di pubblicazione da utilizzare per la distribuzione.
title: Consenti sostituzioni elenco di pubblicazione
uuid: f2cc9878-ab54-4c6f-8a88-3f3b579955e3
feature: Report Builder
role: User, Admin
exl-id: a7bd6cdb-397a-45ba-88ff-c3b3c7062005
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 1%

---

# Consenti sostituzioni elenco di pubblicazione

Quando pianifichi un rapporto, puoi scegliere una lista di pubblicazione da utilizzare per la distribuzione.

Gli elenchi di pubblicazione sono configurati negli strumenti di amministrazione di Analytics.

Consulta [Publishing List Manager](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/publishing-list.html) in Analytics Reference.

Per abilitare questa funzione, passa alla finestra [!UICONTROL Request Wizard: Step 1] .

Se si abilita [!UICONTROL Allow Publishing List Override], la suite di rapporti assegnata a ciascun destinatario nell’elenco di pubblicazione sostituisce la suite di rapporti per questa richiesta. Inoltre, se la cartella di lavoro contiene più suite di rapporti, viene utilizzato l’ID suite di rapporti associato all’elenco di pubblicazione.

Questa opzione non è disponibile per le suite di rapporti selezionate dalle celle.

>[!NOTE]
>
>Se invii il rapporto pianificato a più elenchi di pubblicazione, il rapporto viene eseguito una volta per ogni elenco. Le suite di rapporti variabili vengono sostituite dalla suite di rapporti assegnata all’elenco di pubblicazione.
