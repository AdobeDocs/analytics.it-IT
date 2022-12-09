---
title: eVar (variabile)
description: Variabili personalizzate che puoi utilizzare nell’implementazione.
feature: Variables
exl-id: f89457b2-4186-4276-8637-9992070e3a73
source-git-commit: 84a4d38a65769f028bac4aa5817cb4002c4b1f97
workflow-type: tm+mt
source-wordcount: '394'
ht-degree: 100%

---

# eVar 

*Questa pagina di aiuto descrive come implementare le eVar. Per informazioni sul funzionamento delle eVar come dimensione, consulta [eVar](/help/components/dimensions/evar.md) nella guida utente Componenti.*

Le eVar sono variabili personalizzate che puoi utilizzare come desideri. Se hai un [documento di progettazione della soluzione](/help/implement/prepare/solution-design.md), la maggior parte delle dimensioni specifiche dell’organizzazione saranno delle eVar. Per impostazione predefinita, le eVar persistono oltre l’hit su cui sono impostate. Puoi personalizzarne la scadenza e l’allocazione in [Variabili di conversione](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/conversion-var-admin.md) nelle impostazioni della suite di rapporti.

Il numero di eVar disponibili dipende dal contratto con Adobe. Se il contratto con Adobe lo supporta, sono disponibili fino a 250 eVar.

## Impostare le eVar nelle impostazioni della suite di rapporti

Prima di utilizzare le eVar nell’implementazione, accertati di configurarle nelle impostazioni della suite di rapporti. Vedi [Variabili di conversione](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/conversion-var-admin.md) nella guida per l’amministratore.

## eVar tramite Web SDK

Le eVar sono [mappate per Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html?lang=it) nei campi XDM da `_experience.analytics.customDimensions.eVars.eVar1` a `_experience.analytics.customDimensions.eVars.eVar250`.

## eVar tramite l’estensione di Adobe Analytics

Puoi impostare le eVar sia durante la configurazione dell’estensione Analytics (variabili globali) sia nelle regole.

1. Accedi a [Raccolta dati Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
2. Fai clic sulla proprietà del tag desiderata.
3. Vai alla scheda [!UICONTROL Rules], quindi fai clic sulla regola desiderata (o crea una regola).
4. Nella sezione [!UICONTROL Actions], fai clic su un’azione [!UICONTROL Adobe Analytics - Set Variables] esistente o fai clic sull’icona “+”.
5. Scegli Adobe Analytics nel menu a discesa [!UICONTROL Extension] e imposta [!UICONTROL Action Type] su [!UICONTROL Set Variables].
6. Individua la sezione [!UICONTROL eVars].

Puoi impostare un’eVar su un valore o su un elemento dati. Puoi anche copiare il valore da un’altra variabile di Analytics.

## s.eVar1 - s.eVar250 in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

Ogni eVar è una stringa che contiene valori personalizzati specifici dell’organizzazione. La loro lunghezza massima è di 255 byte; i valori superiori a 255 byte vengono troncati automaticamente quando sono inviati ad Adobe.

```js
s.eVar1 = "Example custom value";
```

## Utilizzare le eVar come contatore

I valori di eVar in genere contengono un valore stringa. Tuttavia, puoi configurare le eVar in modo che contengano un contatore. Ad esempio, puoi contare il numero di ricerche interne effettuate prima di un acquisto. Invece di impostare un valore di testo, puoi utilizzare la sintassi seguente:

```js
// Increment a counter eVar by 1
s.eVar1 = "+1";

// Increment a counter eVar by 12.49
s.eVar1 = "+12.49";
```

Se vengono fornite più di due posizioni decimali, il contatore eVar arrotonda a due posizioni decimali. Una eVar di tipo contatore non può contenere numeri negativi.

>[!IMPORTANT]
>
>Prima di utilizzare le eVar come contatore, devi configurarle come “Contatore” in Admin Console. Vedi [Variabili di conversione](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/conversion-var-admin.md) nella guida per l’amministratore.
