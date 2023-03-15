---
title: useLinkTrackSessionStorage
description: Memorizza i dati di tracciamento dei collegamenti nell’archiviazione della sessione invece di un cookie.
feature: Variables
exl-id: 3295195d-bfd6-4af9-9487-dc1ea6c3da23
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 8%

---

# useLinkTrackSessionStorage

Se la tua organizzazione utilizza il tracciamento dei collegamenti, AppMeasurement utilizza `s_sq` cookie per trasmettere informazioni tra gli hit. Alcune configurazioni del sito web sono in conflitto con questo cookie. Abilita questa variabile se desideri utilizzare l’archiviazione della sessione del browser per il tracciamento dei collegamenti e i dati Activity Map invece di un cookie.

L’utilizzo dell’archiviazione della sessione di un browser per il tracciamento dei collegamenti presenta diverse limitazioni:

* L&#39;archiviazione della sessione non funziona tra i protocolli. Ad esempio, una pagina viene trasmessa tramite HTTP e la pagina successiva tramite HTTPS. AppMeasurement: impossibile accedere ai dati di tracciamento dei collegamenti nell’archiviazione della sessione a causa di differenze di protocollo.
* L’archiviazione della sessione non funziona tra i sottodomini. Ad esempio, un visitatore passa a `store.example.com`, quindi passa a `toys.example.com`. AppMeasurement: impossibile accedere ai dati di tracciamento dei collegamenti nell’archiviazione della sessione a causa di sottodomini diversi.

>[!TIP]
>
>L’implementazione più affidabile che utilizza l’archiviazione di sessione per il tracciamento dei collegamenti trasmette tutti i contenuti tramite HTTPS su un singolo sottodominio.

AppMeasurement rimuove i dati di tracciamento dei collegamenti di archiviazione della sessione dopo l’invio di un hit all’Adobe. Scade inoltre automaticamente quando viene chiusa la scheda del browser.

## Utilizzare l’archiviazione della sessione di tracciamento dei collegamenti tramite Web SDK

L’SDK per web non supporta questa funzionalità.

## Utilizzare l’archiviazione della sessione di tracciamento dei collegamenti tramite l’estensione Adobe Analytics

Nell’estensione Adobe Analytics non è presente un campo dedicato per utilizzare questa variabile. Utilizza l’editor di codice personalizzato seguendo la sintassi di AppMeasurement.

## s.useLinkTrackSessionStorage in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

Il `s.useLinkTrackSessionStorage` è un valore booleano che determina se AppMeasurement utilizza l’archiviazione della sessione per i dati di tracciamento dei collegamenti invece del `s_sq` cookie. Il valore predefinito è `false`. Imposta questa variabile su `true` se desideri che AppMeasurement utilizzi l’archiviazione della sessione invece del `s_sq` cookie per il tracciamento dei collegamenti e Activity Map.

```js
s.useLinkTrackSessionStorage = true;
```
