---
description: Puoi scaricare progetti salvati e non, in formato PDF e CSV.
title: Scaricare file PDF o CSV
uuid: 8af5f3d7-5870-4ed6-8a9f-ef290a48ef5f
translation-type: tm+mt
source-git-commit: 08d564f7fb06b94c2010515ea4a1dcbb2e6e2815

---


# Scaricare file PDF o CSV

Puoi scaricare progetti salvati e non, in formato PDF e CSV.

Il nome del file PDF o CSV corrisponde al nome corrente del progetto. Per i progetti non salvati, i file scaricati includono le modifiche non salvate nel progetto. Ricorda che è impossibile pianificare progetti in PDF o CSV.

Nota bene:

* Nel formato CSV viene supportata anche la visualizzazione Abbandono.
* Quando si esegue il rendering di un progetto in PDF, questo conterrà solo ciò che si trova sulla pagina. Se un progetto contiene pannelli e visualizzazioni di dimensione personalizzata, dovrai impostarli per il ridimensionamento automatico (con il pulsante in alto a destra) in modo da evitare che alcuni contenuti vengano troncati.
* I PDF scaricati nel browser possono richiedere alcuni minuti per l’esportazione. Questo perché dobbiamo rieseguire l&#39;intero progetto sui nostri server prima di renderlo in formato PDF. È consigliabile non uscire dal progetto fino al download del PDF nel browser. Tuttavia, potete continuare a apportare modifiche al progetto mentre attendete.
* Sappiamo che se si dispone di progetti Workspace molto lunghi, i PDF vengono attualmente esportati come una sola pagina gigante, anziché come documento impaginato. Stiamo lavorando a un miglioramento dell’esportazione PDF Workspace che consente l’impaginazione.

1. Crea o apri un progetto.
1. Fai clic su **[!UICONTROL Project]** (Progetto) > **[!UICONTROL Download CSV (or Download PDF).]** (Scarica CSV (o Scarica PDF))

A partire dall’11 aprile 2019 sono state apportate diverse modifiche a **[!CSV download]** (e **[!CCopia negli Appunti]**) da Analysis Workspace, per rimuovere la formattazione dai dati esportati.
* Il separatore di migliaia non è più incluso. Il separatore decimale continua a essere incluso e si attiene al formato definito in **[!UICONTROL Components > Report Settings > Thousands Separator]** (Componenti > Impostazioni report > Separatore delle migliaia).
* Non vengono visualizzati simboli di valuta.
* Non vengono visualizzati simboli di percentuale.
* Le percentuali sono espresse in forma decimale. Ad esempio, 75% è rappresentato da 0,75.
* Il tempo viene visualizzato in secondi.
* Le tabelle di coorte mostrano solo valori non elaborati. Le percentuali sono rimosse.
* Se un numero non è valido, viene visualizzata una cella vuota.

>[!NNota:]
>
> I valori numerici che utilizzano una virgola come separatore decimale continuano a essere inclusi nel file CSV esportato.
