---
title: Variabili dinamiche
description: Copia le variabili senza aumentare la lunghezza della richiesta dell'immagine.
feature: Variables
exl-id: 41aab44d-01fd-45fe-892d-637d69488d98
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '423'
ht-degree: 17%

---

# Variabili dinamiche

Le variabili dinamiche consentono di copiare i valori da una variabile all’altra senza aumentare la lunghezza della richiesta dell’immagine. Sono utili quando si acquisiscono gli stessi dati in più variabili.

Nelle versioni precedenti di Analytics, la lunghezza della richiesta di immagine era importante per evitare il troncamento dei dati. I miglioramenti apportati ad AppMeasurement consentono stringhe di query di richiesta di immagine molto più lunghe, pertanto le variabili dinamiche generalmente non sono necessarie.

Le variabili dinamiche supportano parametri di stringa di query o intestazioni HTTP in una richiesta di immagine. Consulta [parametri query della raccolta dati](../../validate/query-parameters.md) per un elenco completo dei parametri disponibili a cui fare riferimento. Consulta [Campi di richiesta standard](https://en.wikipedia.org/wiki/List_of_HTTP_header_fields#Request_fields) su Wikipedia per un elenco completo dei campi di richiesta HTTP disponibili come riferimento.

Quando Adobe riconosce un prefisso di variabile dinamica, copia automaticamente la stringa di query o il valore dell’intestazione HTTP nella suite di rapporti. Questa azione si verifica prima di qualsiasi altra elaborazione, incluse le regole di elaborazione e le regole VISTA.

>[!TIP]
>
>Presta attenzione ai limiti massimi dei caratteri durante la copia delle variabili. Ad esempio, se si copia `eVar1` a `prop1`, `prop1` può avere un valore troncato poiché ha un limite di 100 byte (mentre `eVar1` ha un limite di 255 byte).

## Variabili dinamiche tramite Web SDK

Utilizza la mappatura dello stream di dati per inviare dati a più variabili di Analytics da un singolo campo XDM.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic su **[!UICONTROL Datastreams]** nella barra a sinistra.
1. Fai clic sullo stream di dati desiderato.
1. Clic **[!UICONTROL Edit Mapping]** a destra.
1. Mappa il [!UICONTROL Source Field] al valore desiderato [!UICONTROL Target Field]. Un singolo campo di origine può essere mappato su qualsiasi numero di campi di destinazione.

## Variabili dinamiche tramite l’estensione Adobe Analytics

Puoi utilizzare le variabili dinamiche in qualsiasi campo dimensione che accetta una stringa. Gli elementi di Dimension vengono in genere impostati durante la configurazione dell’estensione Analytics (variabili globali) o nelle regole.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
2. Fai clic sulla proprietà del tag desiderata.
3. Vai alla scheda [!UICONTROL Rules], quindi fai clic sulla regola desiderata (o crea una regola).
4. Nella sezione [!UICONTROL Actions], fai clic su un’azione [!UICONTROL Adobe Analytics - Set Variables] esistente o fai clic sull’icona “+”.
5. Scegli Adobe Analytics nel menu a discesa [!UICONTROL Extension] e imposta [!UICONTROL Action Type] su [!UICONTROL Set Variables].
6. Individua l’elemento di dimensione desiderato.

Inserisci il prefisso della variabile dinamica nel campo di testo, seguito dal parametro della stringa di query o dall’intestazione HTTP a cui desideri fare riferimento. Per impostazione predefinita, il prefisso della variabile dinamica è `D=`.

## Variabili dinamiche in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

Le variabili dinamiche sono stringhe di testo assegnate ad altre variabili. Il prefisso predefinito della variabile dinamica è `D=`. Le variabili dinamiche fanno distinzione tra maiuscole e minuscole.

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
>Le variabili dinamiche vengono visualizzate come stringhe durante il debug dell’implementazione. I valori vengono copiati lato server dai server di raccolta dati Adobe.
