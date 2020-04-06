---
title: eVar
description: Variabili personalizzate utilizzabili nell’implementazione.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# eVar

*Questa pagina della Guida descrive come implementare le eVar. Per informazioni sul funzionamento delle eVar come una dimensione, vedi[eVar](../../../components/c-variables/dimensionslist/reports-conversion.md)nella guida utente Componenti.*

Le eVar sono variabili personalizzate che potete utilizzare come desiderate.

>[!TIP] Nella maggior parte dei casi, Adobe consiglia di utilizzare le eVar sulle proprietà. Nelle versioni precedenti di Adobe Analytics, le proprietà e le eVar presentavano vantaggi e svantaggi l&#39;una per l&#39;altra. Tuttavia, Adobe ha migliorato le eVar dove soddisfano quasi tutti i casi di utilizzo per le prop.

Assicurati di registrare come utilizzi ogni eVar e la relativa logica nel documento [di progettazione della](../../prepare/solution-design.md)soluzione.

## Configurare le eVar nelle impostazioni della suite di rapporti

Prima di utilizzare le eVar nell&#39;implementazione, accertati di configurare ogni eVar nelle impostazioni della suite di rapporti. Consulta Variabili [di](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) conversione nella guida di amministrazione.

## eVar in Adobe Experience Platform Launch

Puoi impostare eVar sia durante la configurazione dell&#39;estensione Analytics (variabili globali), sia in base a regole.

1. Accedete a [launch.adobe.com](https://launch.adobe.com) utilizzando le credenziali AdobeID.
2. Fate clic sulla proprietà desiderata.
3. Passate alla [!UICONTROL Rules] scheda, quindi fate clic sulla regola desiderata (o create una regola).
4. In [!UICONTROL Actions], fare clic su un&#39;azione esistente [!UICONTROL Adobe Analytics - Set Variables] o fare clic sull&#39;icona &quot;+&quot;.
5. Impostate il [!UICONTROL Extension] menu a discesa su Adobe Analytics e [!UICONTROL Action Type] su [!UICONTROL Set Variables].
6. Individuare la [!UICONTROL eVars] sezione.

Puoi selezionare una eVar per impostare un valore o un elemento dati. Puoi anche copiare il valore da un’altra variabile di Analytics.

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

>[!IMPORTANT] Prima di utilizzare le eVar dei contatori, devi configurare le eVar su &#39;Contatore&#39; nell&#39;Admin Console. Consulta Variabili [di](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) conversione nella guida di amministrazione.

## Vantaggi esclusivi per proprietà o eVar

Nella versione corrente di Adobe Analytics, prop ed eVar sono entrambe variabili personalizzate con funzionalità simili. Tuttavia, le differenze sono diverse:

* I dati nelle proprietà sono disponibili nel reporting in pochi minuti. Le eVar possono richiedere fino a 30 minuti per essere visualizzate nel reporting.
* Le proprietà hanno un limite di 100 byte nei report. Le eVar hanno un limite di 255 byte.
* Le proprietà possono diventare proprietà elenco, che accettano più valori nello stesso hit. Le variabili elenco sono separate e sono disponibili solo tre variabili elenco.
* Per impostazione predefinita, le proprietà non persistono oltre l’hit impostato. Le eVar hanno una scadenza personalizzata, che consente di determinare quando un&#39;eVar non ottiene più credito per un evento successivo. Tuttavia, se utilizzate l&#39;elaborazione [del tempo del](../../../components/vrs/vrs-report-time-processing.md)rapporto, sia le prop che le eVar possono utilizzare un modello di attribuzione personalizzato.
