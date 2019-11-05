---
description: Puoi scaricare progetti salvati e non, in formato PDF e CSV.
seo-description: Puoi scaricare progetti salvati e non, in formato PDF e CSV.
seo-title: Scaricare file PDF o CSV
title: Scaricare file PDF o CSV
uuid: 8af5f3d7-5870-4ed6-8a9f-ef290a48ef5f
translation-type: tm+mt
source-git-commit: 57fe1f6d613b9f54a5191ac8684d36bccfebf4e5

---


# Scaricare file PDF o CSV

Puoi scaricare progetti salvati e non, in formato PDF e CSV.

Il nome del file PDF o CSV corrisponde al nome corrente del progetto. Per i progetti non salvati, i file scaricati includono le modifiche non salvate nel progetto. Ricorda che è impossibile pianificare progetti in PDF o CSV.

> [!NOTE] È inoltre supportata la visualizzazione Abbandono in formato CSV.

> [!NOTE] Quando eseguiamo il rendering di un progetto in PDF, eseguiamo semplicemente il rendering di ciò che si trova sulla pagina. Se un progetto contiene pannelli e visualizzazioni di dimensione personalizzata, dovrai impostarli per il ridimensionamento automatico (con il pulsante in alto a destra) in modo da evitare che alcuni contenuti vengano troncati.

1. Crea o apri un progetto.
1. Fai clic su **[!UICONTROL Project]** &gt; **[!UICONTROL Download CSV (or Download PDF).]**

On April 11, 2019, several changes were made to **[!CSV downloads]** (and **[!Copy to Clipboard]**) from Analysis Workspace to remove formatting from exported data.
* Il separatore di migliaia non è più incluso. (The decimal separator will continue to be included, and will adhere to the format defined under **[!UICONTROL Components > Report Settings > Thousands Separator]**).
* Non vengono visualizzati simboli di valuta.
* Non vengono visualizzati simboli di percentuale.
* Le percentuali sono espresse in forma decimale; Ad esempio, il 75% è rappresentato da 0,75.
* Il tempo viene visualizzato in secondi.
* Le tabelle di coorte mostrano solo valori non elaborati; le percentuali vengono rimosse.
* Se un numero non è valido, viene visualizzata una cella vuota.

>[!NNota:]
>
> I valori numerici che utilizzano una virgola come separatore decimale continueranno a essere citati nel CSV esportato.
