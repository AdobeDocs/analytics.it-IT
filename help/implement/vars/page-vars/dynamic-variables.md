---
title: Variabili dinamiche
description: Copia le variabili senza aumentare la lunghezza della richiesta di immagine.
exl-id: 41aab44d-01fd-45fe-892d-637d69488d98
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 1%

---

# Variabili dinamiche

Le variabili dinamiche consentono di copiare i valori da una variabile all’altra senza aumentare la lunghezza della richiesta di immagini. Sono utili quando acquisisci gli stessi dati in più variabili.

Nelle versioni precedenti di Analytics, la lunghezza della richiesta di immagine era importante per evitare il troncamento dei dati. I miglioramenti ad AppMeasurement consentono stringhe di query di richiesta di immagini molto più lunghe, pertanto le variabili dinamiche in genere non sono necessarie.

Le variabili dinamiche supportano i parametri delle stringhe query o le intestazioni HTTP in una richiesta di immagine. Per un elenco completo dei parametri disponibili a cui fare riferimento, consulta [parametri della query di raccolta dati](../../validate/query-parameters.md) . Per un elenco completo dei campi di richiesta HTTP a cui fare riferimento, consulta [Campi di richiesta standard](https://en.wikipedia.org/wiki/List_of_HTTP_header_fields#Request_fields) su Wikipedia .

Quando Adobe riconosce un prefisso di variabile dinamica, copia automaticamente la stringa di query o il valore di intestazione HTTP nella suite di rapporti. Questa azione viene eseguita prima di qualsiasi altra elaborazione, incluse le regole di elaborazione e le regole VISTA.

>[!TIP]
>
>Presta attenzione ai limiti massimi dei caratteri durante la copia delle variabili. Ad esempio, se copi `eVar1` in `prop1`, `prop1` può avere un valore troncato in quanto ha un limite di 100 byte (mentre `eVar1` ha un limite di 255 byte).

## Variabili dinamiche che utilizzano i tag in Adobe Experience Platform

È possibile utilizzare variabili dinamiche in qualsiasi campo di dimensione che accetta una stringa. Gli elementi di Dimension vengono generalmente impostati durante la configurazione dell&#39;estensione Analytics (variabili globali) o in base alle regole.

1. Accedi all&#39; [Interfaccia di raccolta dati](https://experience.adobe.com/data-collection) utilizzando le tue credenziali AdobeID.
2. Fai clic sulla proprietà desiderata.
3. Vai alla scheda [!UICONTROL Rules] , quindi fai clic sulla regola desiderata (o crea una regola).
4. In [!UICONTROL Actions], fai clic su un&#39;azione [!UICONTROL Adobe Analytics - Set Variables] esistente o fai clic sull&#39;icona &quot;+&quot;.
5. Imposta il menu a discesa [!UICONTROL Extension] su Adobe Analytics e [!UICONTROL Action Type] su [!UICONTROL Set Variables].
6. Individua l’elemento di dimensione desiderato.

Posiziona il prefisso della variabile dinamica nel campo di testo, seguito dal parametro della stringa di query o dall’intestazione HTTP a cui si desidera fare riferimento. Per impostazione predefinita, il prefisso della variabile dinamica è `D=`.

## Variabili dinamiche in AppMeasurement e nell’editor di codice personalizzato

Le variabili dinamiche sono stringhe di testo assegnate ad altre variabili. Il prefisso della variabile dinamica predefinito è `D=`. Le variabili dinamiche sono sensibili all’uso di maiuscole e minuscole.

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
>Le variabili dinamiche vengono visualizzate come stringhe durante il debug dell’implementazione. I valori vengono copiati lato server dai server di raccolta dati di Adobe.
