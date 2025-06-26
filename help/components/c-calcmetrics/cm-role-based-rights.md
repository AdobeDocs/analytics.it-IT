---
description: I diritti relativi alle metriche calcolate differiscono tra utenti amministratori e non amministratori.
title: Diritti basati sul ruolo
feature: Calculated Metrics
exl-id: 018d9ef5-5a6f-4ebc-a241-c1291ba6b561
source-git-commit: d85e6990998e3c153ef969d8dc7f3a4835f683bf
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 11%

---

# Diritti basati sul ruolo

I diritti relativi alle metriche calcolate differiscono tra utenti amministratori e non amministratori.

|  | Creazione | Condividere | Visualizza/Gestisci | Approvazione | Applica |
|--- |--- |--- |--- |--- |--- |
| Utenti a livello di amministratore | Gli amministratori possono creare metriche calcolate e profili di prodotto in Admin Console per limitare i diritti degli utenti di creare metriche calcolate. | Possono condividere con l’azienda, con i gruppi di utenti e con i singoli utenti. | Report Builder: può visualizzare/modificare/eliminare/ecc. le proprie metriche calcolate e quelle condivise con essa. | Può approvare le metriche calcolate come canoniche. | Può applicare qualsiasi metrica calcolata in tutta l’organizzazione. |
| Utenti non amministratori | Per impostazione predefinita, gli utenti possono creare metriche calcolate. Tuttavia, questi diritti possono essere limitati dagli amministratori. | Possono condividere solo con singoli utenti | Possono visualizzare/modificare/eliminare/ecc. solo le proprie metriche calcolate. Per poter visualizzare metriche condivise, gli utenti che non sono amministratori devono avere accesso a tutti gli eventi dei componenti (le autorizzazioni in Admin Console vengono ancora applicate).  Se un dashboard o un report pianificato è condiviso con un utente non amministratore e la metrica non è condivisa con quest’ultimo, il report verrà eseguito con la metrica applicata (supponendo che disponga delle autorizzazioni necessarie per visualizzare gli eventi). Tuttavia, non potranno visualizzare la definizione o modificare la metrica. | Può utilizzare solo metriche calcolate approvate; non può contrassegnare come approvate. | Possono applicare le proprie metriche calcolate e i segmenti condivisi con loro. |
