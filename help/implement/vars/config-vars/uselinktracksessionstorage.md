---
title: useLinkTrackSessionStorage
description: Archivia i dati di tracciamento dei collegamenti nell’archiviazione delle sessioni invece che in un cookie.
feature: Variables
exl-id: 3295195d-bfd6-4af9-9487-dc1ea6c3da23
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 0%

---

# useLinkTrackSessionStorage

Se la tua organizzazione utilizza il tracciamento dei collegamenti, AppMeasurement utilizza il `s_sq` per trasmettere informazioni tra gli hit. Alcune configurazioni del sito web sono in conflitto con questo cookie. Se desideri utilizzare l’archiviazione della sessione del browser per il tracciamento dei collegamenti e i dati di Activity Map invece di un cookie, abilita questa variabile.

L’utilizzo dell’archiviazione di sessione di un browser per il tracciamento dei collegamenti presenta diverse limitazioni:

* L&#39;archiviazione della sessione non funziona tra i protocolli. Ad esempio, hai una pagina servita su HTTP e la pagina successiva servita su HTTPS. AppMeasurement non può accedere ai dati di tracciamento dei collegamenti nell&#39;archiviazione delle sessioni a causa di differenze di protocollo.
* L’archiviazione della sessione non funziona tra i sottodomini. Ad esempio, un visitatore accede a `store.example.com`, quindi passa a `toys.example.com`. AppMeasurement non può accedere ai dati di tracciamento dei collegamenti nell&#39;archiviazione delle sessioni a causa di sottodomini diversi.

>[!TIP]
>
>L’implementazione più affidabile utilizzando l’archiviazione delle sessioni per il tracciamento dei collegamenti fornisce tutto il contenuto tramite HTTPS su un singolo sottodominio.

AppMeasurement rimuove i dati di tracciamento dei collegamenti di archiviazione sessione dopo l&#39;invio di un hit ad Adobe. Inoltre scade automaticamente quando la scheda del browser viene chiusa.

## Utilizzare l&#39;archiviazione delle sessioni di tracciamento dei collegamenti tramite SDK per web

L&#39;SDK per web non supporta questa funzionalità.

## Utilizzare l&#39;archiviazione delle sessioni di tracciamento dei collegamenti tramite l&#39;estensione Adobe Analytics

Nell’estensione Adobe Analytics non è presente un campo dedicato per utilizzare questa variabile. Utilizza l&#39;editor di codice personalizzato seguendo la sintassi AppMeasurement.

## s.useLinkTrackSessionStorage in AppMeasurement e nell&#39;editor di codice personalizzato dell&#39;estensione Analytics

La `s.useLinkTrackSessionStorage` è una variabile booleana che determina se AppMeasurement utilizza l&#39;archiviazione della sessione per i dati di tracciamento dei collegamenti invece che `s_sq` cookie. Il valore predefinito è `false`. Imposta questa variabile su `true` se desideri che AppMeasurement utilizzi l&#39;archiviazione sessione invece del `s_sq` cookie per il tracciamento dei collegamenti e Activity Map.

```js
s.useLinkTrackSessionStorage = true;
```
