---
title: eVar
description: Variabili personalizzate utilizzabili nell’implementazione.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 1%

---


# eVar

*Questa pagina della Guida descrive come implementare le eVar. Per informazioni sul funzionamento delle eVar come una dimensione, vedi[eVar](/help/components/dimensions/evar.md)nella guida utente Componenti.*

Le eVar sono variabili personalizzate che potete utilizzare come desiderate. Se si dispone di un documento [di progettazione di una](/help/implement/prepare/solution-design.md)soluzione, la maggior parte delle dimensioni specifiche per l&#39;organizzazione vengono visualizzate come eVar. Per impostazione predefinita, le eVar persistono oltre l’hit impostato. Puoi personalizzarne la scadenza e l’allocazione nelle variabili [di](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) conversione nelle impostazioni della suite di rapporti.

Il numero di eVar disponibili dipende dal contratto con Adobe. Se il contratto con Adobe lo supporta, sono disponibili fino a 250 eVar.

## Configurare le eVar nelle impostazioni della suite di rapporti

Prima di utilizzare le eVar nell&#39;implementazione, accertati di configurare ogni eVar nelle impostazioni della suite di rapporti. Consulta Variabili [di](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) conversione nella guida di amministrazione.

## eVar nel lancio  Adobe Experience Platform

Potete impostare le eVar sia durante la configurazione dell&#39;estensione Analytics  (variabili globali), sia in base a regole.

1. Accedete a [launch.adobe.com](https://launch.adobe.com) utilizzando le credenziali AdobeID.
2. Fate clic sulla proprietà desiderata.
3. Passate alla [!UICONTROL Rules] scheda, quindi fate clic sulla regola desiderata (o create una regola).
4. In [!UICONTROL Actions], fare clic su un&#39;azione esistente [!UICONTROL Adobe Analytics - Set Variables] o fare clic sull&#39;icona &quot;+&quot;.
5. Impostate il [!UICONTROL Extension] menu a discesa su Adobe  Analytics e [!UICONTROL Action Type] su [!UICONTROL Set Variables].
6. Individuare la [!UICONTROL eVars] sezione.

È possibile impostare un&#39;eVar su un valore o su un elemento dati. Potete anche copiare il valore da un’altra variabile  Analytics.

## s.eVar1 - s.eVar250 in AppMeasurement e Avvia editor di codice personalizzato

Ogni eVar è una stringa che contiene valori personalizzati specifici dell&#39;organizzazione. La loro lunghezza massima è di 255 byte; i valori superiori a 255 byte vengono troncati automaticamente quando inviati ad Adobe.

```js
s.eVar1 = "Example custom value";
```

## eVar contatore

I valori eVar in genere contengono un valore stringa. Tuttavia, puoi configurare le eVar in modo che contengano un contatore. Ad esempio, si desidera conteggiare il numero di ricerche interne effettuate prima di un acquisto. Anziché impostare un valore di testo, è necessario utilizzare la sintassi seguente:

```js
// Increment a counter eVar by 1
s.eVar1 = "+1";

// Increment a counter eVar by 12.49
s.eVar1 = "+12.49";
```

Se vengono date più di due posizioni decimali, il contatore eVar arrotonda a due posizioni decimali. Un contatore eVar non può contenere numeri negativi.

>[!IMPORTANT]
>
>Prima di utilizzare le eVar del contatore, è necessario configurare le eVar su Contatore nell&#39;Admin Console . Consulta Variabili [di](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) conversione nella guida di amministrazione.
