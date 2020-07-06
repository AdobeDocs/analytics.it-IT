---
title: useLinkTrackSessionStorage
description: Archivia i dati di tracciamento dei collegamenti nell'archivio delle sessioni invece di un cookie.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 0%

---


# useLinkTrackSessionStorage

Se l’organizzazione utilizza il tracciamento dei collegamenti, AppMeasurement utilizza il `s_sq` cookie per trasmettere informazioni tra hit. Alcune configurazioni del sito Web entrano in conflitto con questo cookie. Se desiderate utilizzare la memorizzazione delle sessioni del browser per il tracciamento dei collegamenti e i dati  Activity Map invece di un cookie, abilitate questa variabile.

L&#39;utilizzo dell&#39;archivio delle sessioni di un browser per il tracciamento dei collegamenti presenta diverse limitazioni:

* L&#39;archiviazione della sessione non funziona tra i protocolli. Ad esempio, è disponibile una pagina su HTTP e la pagina successiva su HTTPS. AppMeasurement non è in grado di accedere ai dati di tracciamento dei collegamenti nell&#39;archiviazione delle sessioni a causa delle differenze di protocollo.
* L&#39;archiviazione delle sessioni non funziona tra i sottodomini. Ad esempio, un visitatore passa a `store.example.com`, quindi passa a `toys.example.com`. AppMeasurement non può accedere ai dati di tracciamento dei collegamenti nell&#39;archiviazione delle sessioni a causa di sottodomini diversi.

>[!TIP]
>
>L’implementazione più affidabile mediante l’archiviazione delle sessioni per il tracciamento dei collegamenti distribuisce tutto il contenuto tramite HTTPS su un singolo sottodominio.

AppMeasurement rimuove i dati di tracciamento dei collegamenti dell&#39;archiviazione sessione dopo l&#39;invio di un hit ad Adobe. Inoltre scade automaticamente quando la scheda del browser viene chiusa.

## Utilizza l&#39;archiviazione delle sessioni di tracciamento dei collegamenti in  lancio Adobe Experience Platform

In Launch non è disponibile un campo dedicato per l’utilizzo di questa variabile. Utilizzate l&#39;editor di codice personalizzato, seguendo la sintassi AppMeasurement.

## s.useLinkTrackSessionStorage in AppMeasurement e Avvia editor di codice personalizzato

La `s.useLinkTrackSessionStorage` variabile è un valore booleano che determina se AppMeasurement utilizza lo spazio di archiviazione delle sessioni per i dati di tracciamento dei collegamenti invece del `s_sq` cookie. Its default value is `false`. Impostate questa variabile su `true` se desiderate che AppMeasurement utilizzi lo spazio di archiviazione delle sessioni invece del `s_sq` cookie per il tracciamento dei collegamenti e  Activity Map.

```js
s.useLinkTrackSessionStorage = true;
```
