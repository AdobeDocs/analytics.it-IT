---
title: eVar
description: Variabili personalizzate che puoi utilizzare nell’implementazione.
exl-id: f89457b2-4186-4276-8637-9992070e3a73
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '365'
ht-degree: 0%

---

# eVar

*Questa pagina di aiuto descrive come implementare le eVar. Per informazioni sul funzionamento delle eVar come dimensioni, consulta [eVar](/help/components/dimensions/evar.md) nella guida utente Componenti.*

Le eVar sono variabili personalizzate che puoi utilizzare come desideri. Se disponi di un [documento di progettazione della soluzione](/help/implement/prepare/solution-design.md), la maggior parte delle dimensioni specifiche della tua organizzazione vengono considerate eVar. Per impostazione predefinita, le eVar persistono oltre l’hit su cui sono impostate. Puoi personalizzarne la scadenza e l’allocazione in [Variabili di conversione](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) nelle impostazioni della suite di rapporti.

Il numero di eVar disponibili dipende dal contratto con l’Adobe. Sono disponibili fino a 250 eVar se il contratto con Adobe lo supporta.

## Configurare eVar nelle impostazioni della suite di rapporti

Prima di utilizzare le eVar nell’implementazione, assicurati di configurare ogni eVar nelle impostazioni della suite di rapporti. Consulta [Variabili di conversione](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) nella guida dell&#39;amministratore.

## eVar che utilizzano i tag in Adobe Experience Platform

Puoi impostare le eVar sia durante la configurazione dell’estensione Analytics (variabili globali) sia in base a regole.

1. Accedi all&#39; [Interfaccia di raccolta dati](https://experience.adobe.com/data-collection) utilizzando le tue credenziali AdobeID.
2. Fai clic sulla proprietà desiderata.
3. Vai alla scheda [!UICONTROL Rules] , quindi fai clic sulla regola desiderata (o crea una regola).
4. In [!UICONTROL Actions], fai clic su un&#39;azione [!UICONTROL Adobe Analytics - Set Variables] esistente o fai clic sull&#39;icona &quot;+&quot;.
5. Imposta il menu a discesa [!UICONTROL Extension] su Adobe Analytics e [!UICONTROL Action Type] su [!UICONTROL Set Variables].
6. Individua la sezione [!UICONTROL eVars] .

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
>Devi prima configurare le eVar su &quot;Contatore&quot; nell’Admin Console prima di utilizzare le eVar dei contatori. Consulta [Variabili di conversione](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) nella guida dell&#39;amministratore.
