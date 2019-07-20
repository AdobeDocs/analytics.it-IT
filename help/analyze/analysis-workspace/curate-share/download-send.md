---
description: Puoi scaricare progetti salvati e non, in formato PDF e CSV.
seo-description: Puoi scaricare progetti salvati e non, in formato PDF e CSV.
seo-title: Scaricare file PDF o CSV
title: Scaricare file PDF o CSV
uuid: 8 af 5 f 3 d 7-5870-4 ed 6-8 a 9 f-ef 290 a 48 ef 5 f
translation-type: tm+mt
source-git-commit: b9e57162fae605719d7d85aad52a29165cb63fe4

---


# Scaricare file PDF o CSV

Puoi scaricare progetti salvati e non, in formato PDF e CSV.

Il nome del file PDF o CSV corrisponde al nome corrente del progetto. Per i progetti non salvati, i file scaricati includono le modifiche non salvate nel progetto. Ricorda che è impossibile pianificare progetti in PDF o CSV.

>[!NOTE]
>
>È inoltre supportata la visualizzazione Abbandono in formato CSV.

>[!NOTE]
>
>Quando eseguiamo il rendering di un progetto in PDF, il rendering viene semplicemente eseguito sulla pagina. Se un progetto contiene pannelli e visualizzazioni di dimensione personalizzata, dovrai impostarli per il ridimensionamento automatico (con il pulsante in alto a destra) in modo da evitare che alcuni contenuti vengano troncati.

1. Crea o apri un progetto.
1. Click **[!UICONTROL Project]** &gt; **[!UICONTROL Download CSV (or Download PDF).]**

On April 11, 2019, several changes were made to **[!CSV downloads]** (and **[!Copy to Clipboard]**) from Analysis Workspace to remove formatting from exported data.
* Il separatore delle migliaia non è più incluso. (The decimal separator will continue to be included, and will adhere to the format defined under **[!UICONTROL Components > Report Settings > Thousands Separator]**).
* Non vengono visualizzati simboli di valuta.
* Non vengono visualizzati i simboli percentuali.
* Le percentuali sono in forma decimale; ad esempio, 75% è rappresentato da 0.75.
* L'ora viene visualizzata in secondi.
* Le tabelle coorte mostrano solo valori non elaborati; vengono rimosse.
* Se un numero non è valido, viene visualizzata una cella vuota.

>[!Note:]
>
> I valori numerici che utilizzano una virgola come separatore decimale continueranno a essere citati nel file CSV esportato.