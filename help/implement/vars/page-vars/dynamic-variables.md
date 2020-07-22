---
title: Variabili dinamiche
description: Copiare le variabili senza aumentare la lunghezza della richiesta di immagini.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '348'
ht-degree: 1%

---


# Variabili dinamiche

Le variabili dinamiche consentono di copiare i valori da una variabile all’altra senza aumentare la lunghezza delle richieste di immagini. Sono utili per acquisire gli stessi dati in più variabili.

Nelle versioni precedenti di  Analytics, la lunghezza della richiesta di immagini era importante per evitare il troncamento dei dati. I miglioramenti ad AppMeasurement consentono stringhe di query di richiesta immagine molto più lunghe, pertanto le variabili dinamiche in genere non sono necessarie.

Le variabili dinamiche supportano i parametri delle stringhe di query o le intestazioni HTTP in una richiesta di immagine. Per un elenco completo dei parametri disponibili a cui fare riferimento, vedere Parametri [query di raccolta](../../validate/query-parameters.md) dati. Consultate Campi [di richiesta](https://en.wikipedia.org/wiki/List_of_HTTP_header_fields#Request_fields) Standard su Wikipedia per un elenco completo dei campi di richiesta HTTP a cui fare riferimento.

Quando Adobe riconosce un prefisso di variabile dinamica, copia automaticamente la stringa di query o il valore di intestazione HTTP nella suite di rapporti. Questa azione viene eseguita prima di qualsiasi altra elaborazione, incluse le regole di elaborazione e le regole VISTA.

>[!TIP]
>
>Durante la copia delle variabili, tieni presente il limite massimo di caratteri. Ad esempio, se si copia `eVar1` in `prop1`, `prop1` è possibile che il valore venga troncato poiché presenta un limite di 100 byte (mentre `eVar1` ha un limite di 255 byte).

## Variabili dinamiche in  Adobe Experience Platform Launch

È possibile utilizzare variabili dinamiche in qualsiasi campo dimensione che accetta una stringa. Gli elementi dimensione vengono generalmente impostati durante la configurazione dell&#39;estensione Analytics  (variabili globali) o in base alle regole.

1. Accedete a [launch.adobe.com](https://launch.adobe.com) utilizzando le credenziali AdobeID.
2. Fate clic sulla proprietà desiderata.
3. Passate alla [!UICONTROL Rules] scheda, quindi fate clic sulla regola desiderata (o create una regola).
4. In [!UICONTROL Actions], fare clic su un&#39;azione esistente [!UICONTROL Adobe Analytics - Set Variables] o fare clic sull&#39;icona &quot;+&quot;.
5. Impostate il [!UICONTROL Extension] menu a discesa su Adobe  Analytics e [!UICONTROL Action Type] su [!UICONTROL Set Variables].
6. Individuate l’elemento di dimensione desiderato.

Inserite il prefisso della variabile dinamica nel campo di testo, seguito dal parametro della stringa di query o dall’intestazione HTTP a cui desiderate fare riferimento. Per impostazione predefinita, il prefisso della variabile dinamica è `D=`.

## Variabili dinamiche in AppMeasurement e Launch editor di codice personalizzato

Le variabili dinamiche sono stringhe di testo assegnate ad altre variabili. Il prefisso predefinito per la variabile dinamica è `D=`. Le variabili dinamiche fanno distinzione tra maiuscole e minuscole.

```js
// Copy eVar1 into eVar2. The query string parameter of eVar1 is v1.
s.eVar1 = "Example value";
s.eVar2 = "D=v1";

// Take the user agent string found in the image request HTTP header and place it in eVar1.
s.eVar1 = "D=User-Agent";

// Copy the page URL and place it in eVar1. The query string parameter of page URL is g.
s.eVar1 = "D=g";
```

>[!NOTE]
>
>Le variabili dinamiche vengono visualizzate come stringhe durante il debug dell&#39;implementazione. I valori vengono copiati sul lato server dai server di raccolta dati Adobe.
