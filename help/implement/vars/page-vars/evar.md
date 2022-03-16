---
title: Variabili eVar
description: Variabili personalizzate che puoi utilizzare nell’implementazione.
feature: Variables
exl-id: f89457b2-4186-4276-8637-9992070e3a73
source-git-commit: 10ff98f7ca4697afe5c2dae66be415c0d68c4aac
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 0%

---

# eVar

*Questa pagina di aiuto descrive come implementare le eVar. Per informazioni sul funzionamento delle eVar come dimensioni, consulta [eVar](/help/components/dimensions/evar.md) nella guida utente Componenti .*

Le eVar sono variabili personalizzate che puoi utilizzare come desideri. Se hai [documento di progettazione della soluzione](/help/implement/prepare/solution-design.md), la maggior parte delle dimensioni specifiche dell’organizzazione vengono visualizzate come eVar. Per impostazione predefinita, le eVar persistono oltre l’hit su cui sono impostate. Puoi personalizzarne la scadenza e l’allocazione in [Variabili di conversione](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) nelle impostazioni della suite di rapporti.

Il numero di eVar disponibili dipende dal contratto con l’Adobe. Sono disponibili fino a 250 eVar se il contratto con Adobe lo supporta.

## Configurare eVar nelle impostazioni della suite di rapporti

Prima di utilizzare le eVar nell’implementazione, assicurati di configurare ogni eVar nelle impostazioni della suite di rapporti. Vedi [Variabili di conversione](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) nella guida Amministratore.

## eVar che utilizzano i tag in Adobe Experience Platform

Puoi impostare le eVar sia durante la configurazione dell’estensione Analytics (variabili globali) sia in base a regole.

1. Accedi a [Interfaccia utente per la raccolta dati](https://experience.adobe.com/data-collection) utilizzo delle credenziali AdobeID.
2. Fai clic sulla proprietà desiderata.
3. Vai a [!UICONTROL Rules] , quindi fai clic sulla regola desiderata (o crea una regola).
4. Sotto [!UICONTROL Actions], fai clic su un [!UICONTROL Adobe Analytics - Set Variables] fare clic sull&#39;icona &quot;+&quot;.
5. Imposta la [!UICONTROL Extension] del menu a discesa Adobe Analytics e [!UICONTROL Action Type] a [!UICONTROL Set Variables].
6. Individua il [!UICONTROL eVars] sezione .

Puoi impostare un eVar su un valore o su un elemento dati. Puoi anche copiare il valore da un’altra variabile di Analytics.

## s.eVar1 - s.eVar250 in AppMeasurement e nell&#39;editor di codice personalizzato

Ogni eVar è una stringa che contiene valori personalizzati specifici dell&#39;organizzazione. La loro lunghezza massima è di 255 byte; i valori superiori a 255 byte vengono troncati automaticamente quando inviati ad Adobe.

```js
s.eVar1 = "Example custom value";
```

## eVar contatore

I valori di eVar generalmente contengono un valore stringa. Tuttavia, puoi configurare le eVar in modo che contengano un contatore. Ad esempio, puoi contare il numero di ricerche interne effettuate prima di un acquisto. Invece di impostare un valore di testo, è necessario utilizzare la sintassi seguente:

```js
// Increment a counter eVar by 1
s.eVar1 = "+1";

// Increment a counter eVar by 12.49
s.eVar1 = "+12.49";
```

Se vengono fornite più di due posizioni decimali, il contatore eVar arrotonda a due posizioni decimali. Un contatore di eVar non può contenere numeri negativi.

>[!IMPORTANT]
>
>Devi prima configurare le eVar su &quot;Contatore&quot; nell’Admin Console prima di utilizzare le eVar dei contatori. Vedi [Variabili di conversione](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) nella guida Amministratore.
