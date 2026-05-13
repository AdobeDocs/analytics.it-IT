---
description: I diritti relativi alle metriche calcolate differiscono tra utenti amministratori e non amministratori.
title: Diritti basati sul ruolo
feature: Calculated Metrics
exl-id: 018d9ef5-5a6f-4ebc-a241-c1291ba6b561
TQID: https://experienceleague.adobe.com/M2ZwpkhpvhavBOwrVsDxcEYsS9kAFGAcuCl5TSUzxXU
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f1f1a2d4-0976-4881-b091-c2bb8de7ffacid: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 244
ht-degree: 9%

---

# Diritti basati sul ruolo

I diritti relativi alle metriche calcolate differiscono tra utenti amministratori e non amministratori.

|  | Creazione | Condividere | Visualizza/Gestisci | Approvazione | Applica |
|--- |--- |--- |--- |--- |--- |
| Utenti a livello di amministratore | Gli amministratori possono creare metriche calcolate e profili di prodotto in Admin Console per limitare i diritti degli utenti di creare metriche calcolate. | Possono condividere con l’azienda, con i gruppi di utenti e con i singoli utenti. | Report Builder: può visualizzare/modificare/eliminare/ecc. le proprie metriche calcolate e quelle condivise con essa. | Può approvare le metriche calcolate come canoniche. | Può applicare qualsiasi metrica calcolata in tutta l’organizzazione. |
| Utenti non amministratori | Per impostazione predefinita, gli utenti possono creare metriche calcolate. Tuttavia, questi diritti possono essere limitati dagli amministratori. | Possono condividere solo con singoli utenti | Possono visualizzare/modificare/eliminare/ecc. solo le proprie metriche calcolate. Per poter visualizzare metriche condivise, gli utenti che non sono amministratori devono avere accesso a tutti gli eventi dei componenti (le autorizzazioni in Admin Console vengono ancora applicate).  Se un dashboard o un report pianificato è condiviso con un utente non amministratore e la metrica non è condivisa con quest’ultimo, il report verrà eseguito con la metrica applicata (supponendo che disponga delle autorizzazioni necessarie per visualizzare gli eventi). Tuttavia, non potranno visualizzare la definizione o modificare la metrica. | Può utilizzare solo metriche calcolate approvate; non può contrassegnare come approvate. | Possono applicare le proprie metriche calcolate e i segmenti condivisi con loro. |
