---
title: useLinkTrackSessionStorage
description: Archivia i dati di tracciamento dei collegamenti nell’archiviazione delle sessioni invece che in un cookie.
exl-id: 3295195d-bfd6-4af9-9487-dc1ea6c3da23
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 0%

---

# useLinkTrackSessionStorage

Se la tua organizzazione utilizza il tracciamento dei collegamenti, AppMeasurement utilizza il cookie `s_sq` per trasmettere informazioni tra i risultati. Alcune configurazioni del sito web sono in conflitto con questo cookie. Se desideri utilizzare l’archiviazione della sessione del browser per il tracciamento dei collegamenti e i dati di Activity Map invece di un cookie, abilita questa variabile.

L’utilizzo dell’archiviazione di sessione di un browser per il tracciamento dei collegamenti presenta diverse limitazioni:

* L&#39;archiviazione della sessione non funziona tra i protocolli. Ad esempio, hai una pagina servita su HTTP e la pagina successiva servita su HTTPS. AppMeasurement non può accedere ai dati di tracciamento dei collegamenti nell&#39;archiviazione delle sessioni a causa di differenze di protocollo.
* L’archiviazione della sessione non funziona tra i sottodomini. Ad esempio, un visitatore passa a `store.example.com`, quindi passa a `toys.example.com`. AppMeasurement non può accedere ai dati di tracciamento dei collegamenti nell&#39;archiviazione delle sessioni a causa di sottodomini diversi.

>[!TIP]
>
>L’implementazione più affidabile utilizzando l’archiviazione delle sessioni per il tracciamento dei collegamenti fornisce tutto il contenuto tramite HTTPS su un singolo sottodominio.

AppMeasurement rimuove i dati di tracciamento dei collegamenti di archiviazione sessione dopo l&#39;invio di un hit ad Adobe. Inoltre scade automaticamente quando la scheda del browser viene chiusa.

## Utilizza l’archiviazione delle sessioni di tracciamento dei collegamenti tramite tag in Adobe Experience Platform

Nell’interfaccia utente di raccolta dati non è disponibile un campo dedicato per l’utilizzo di questa variabile. Utilizza l&#39;editor di codice personalizzato seguendo la sintassi AppMeasurement.

## s.useLinkTrackSessionStorage in AppMeasurement e nell&#39;editor di codice personalizzato

La variabile `s.useLinkTrackSessionStorage` è un valore booleano che determina se AppMeasurement utilizza l’archiviazione delle sessioni per i dati di tracciamento dei collegamenti invece del cookie `s_sq`. Il valore predefinito è `false`. Imposta questa variabile su `true` se desideri che AppMeasurement utilizzi l’archiviazione della sessione invece del cookie `s_sq` per il tracciamento dei collegamenti e Activity Map.

```js
s.useLinkTrackSessionStorage = true;
```
