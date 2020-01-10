---
description: Puoi scaricare progetti salvati e non, in formato PDF e CSV.
title: Scaricare file PDF o CSV
uuid: 8af5f3d7-5870-4ed6-8a9f-ef290a48ef5f
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Scaricare file PDF o CSV

Puoi scaricare progetti salvati e non, in formato PDF e CSV.

Il nome del file PDF o CSV corrisponde al nome corrente del progetto. Per i progetti non salvati, i file scaricati includono le modifiche non salvate nel progetto. Ricorda che è impossibile pianificare progetti in PDF o CSV.

> [!NOTE] Nel formato CSV viene supportata anche la visualizzazione Abbandono.

> [!NOTE] Quando si esegue il rendering di un progetto in PDF, questo conterrà solo ciò che si trova sulla pagina. Se un progetto contiene pannelli e visualizzazioni di dimensione personalizzata, dovrai impostarli per il ridimensionamento automatico (con il pulsante in alto a destra) in modo da evitare che alcuni contenuti vengano troncati.

1. Crea o apri un progetto.
1. Fai clic su **[!UICONTROL Project]** &gt; **[!UICONTROL Download CSV (or Download PDF).]** (Progetto &gt; Scarica CVS (o Scarica PDF)).

A partire dall’11 aprile 2019 sono state apportate diverse modifiche a **[!CSV download]** (e **[!CCopia negli Appunti]**) da Analysis Workspace, per rimuovere la formattazione dai dati esportati.
* Il separatore di migliaia non è più incluso. Il separatore decimale continua a essere incluso e si attiene al formato definito in **[!UICONTROL Components > Report Settings > Thousands Separator]** (Componenti &gt; Impostazioni report &gt; Separatore delle migliaia).
* Non vengono visualizzati simboli di valuta.
* Non vengono visualizzati simboli di percentuale.
* Le percentuali sono espresse in forma decimale. Ad esempio, 75% è rappresentato da 0,75.
* Il tempo viene visualizzato in secondi.
* Le tabelle di coorte mostrano solo valori non elaborati. Le percentuali sono rimosse.
* Se un numero non è valido, viene visualizzata una cella vuota.

>[!NNota:]
>
> I valori numerici che utilizzano una virgola come separatore decimale continuano a essere inclusi nel file CSV esportato.
