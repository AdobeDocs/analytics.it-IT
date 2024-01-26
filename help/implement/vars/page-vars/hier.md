---
title: hier
description: Implementa le variabili gerarchiche in Adobe Analytics.
feature: Variables
exl-id: 72bdab8f-a001-4ada-b5e2-453a8e3f24a6
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 97%

---

# hier

>[!IMPORTANT]
>
>Questa variabile è ritirata e non è una dimensione disponibile in Analysis Workspace. Al suo posto, Adobe consiglia di utilizzare le [eVar](evar.md) e le classificazioni.

Le variabili gerarchiche sono variabili personalizzate che consentono di visualizzare la struttura di un sito. Adobe supporta fino a 5 variabili gerarchiche nell’implementazione.

Questa variabile è utile per i siti con più di tre livelli nella loro struttura. Ad esempio, un sito di contenuti multimediali può avere 4 livelli nella sezione Sport: `Sports`, `Local Sports`, `Baseball` e `Team name`. Se qualcuno visita la pagina Baseball, Sport, Sport locali e Baseball, tutti i livelli riflettono quella visita.

Prima di utilizzare le gerarchie nell’implementazione, assicurati di configurare ogni gerarchia nelle impostazioni della suite di rapporti.

## Impostare le gerarchie tramite Web SDK

Le gerarchie sono [mappate per Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html?lang=it) nei campi XDM da `_experience.analytics.customDimensions.hierarchies.hier1` a `_experience.analytics.customDimensions.hierarchies.hier5`.

## Impostare le gerarchie tramite l’estensione Adobe Analytics

Puoi impostare le gerarchie sia durante la configurazione dell’estensione Analytics (variabili globali) sia nelle regole.

1. Accedi a [Raccolta dati Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
2. Fai clic sulla proprietà del tag desiderata.
3. Vai alla scheda [!UICONTROL Rules], quindi fai clic sulla regola desiderata (o crea una regola).
4. Nella sezione [!UICONTROL Actions], fai clic su un’azione [!UICONTROL Adobe Analytics - Set Variables] esistente o fai clic sull’icona “+”.
5. Imposta il [!UICONTROL Extension] in Adobe Analytics e nella sezione [!UICONTROL Action Type] a [!UICONTROL Set Variables].
6. Individua la sezione [!UICONTROL Hierarchy].

È possibile impostare un valore gerarchico come stringa statica o fare riferimento a un elemento dati. Puoi anche impostare il delimitatore desiderato. Assicurati che il delimitatore impostato qui corrisponda al delimitatore impostato nelle impostazioni della suite di rapporti.

## s.hier1 - s.hier5 in AppMeasurement e nel‘’editor di codice personalizzato dell’estensione Analytics

Ogni gerarchia è una stringa che contiene valori personalizzati specifici dell’organizzazione. La loro lunghezza massima è di 255 byte; i valori superiori a 255 byte vengono troncati automaticamente quando sono inviati ad Adobe.

Assicurati che nessuno dei nomi di sezione contenga il delimitatore. Ad esempio, se una delle sezioni si chiama `Coach Griffin, Jim`, scegli un delimitatore diverso da una virgola. Il limite totale della variabile è di 255 byte. I delimitatori possono essere costituiti da più caratteri, ad esempio `||` o `/|\`, che hanno meno probabilità di apparire nei valori delle variabili.

```js
s.hier1 = "Toys|Boys 6+|Legos|Super Block Tub";

s.hier3 = "Sports/Local Sports/Baseball";
```
