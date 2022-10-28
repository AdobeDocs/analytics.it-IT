---
title: hier
description: Implementa le variabili gerarchiche in Adobe Analytics.
feature: Variables
exl-id: 72bdab8f-a001-4ada-b5e2-453a8e3f24a6
source-git-commit: f435453f655caef89460de42ebecf489b021dc47
workflow-type: tm+mt
source-wordcount: '340'
ht-degree: 3%

---

# hier

>[!IMPORTANT]
>
>Questa variabile è ritirata e non è una dimensione disponibile in Analysis Workspace. Adobe consiglia di utilizzare [eVar](evar.md) e classificazioni.

Le variabili gerarchiche sono variabili personalizzate che consentono di visualizzare la struttura di un sito. Adobe supporta fino a 5 variabili gerarchiche nell’implementazione.

Questa variabile è utile per i siti con più di tre livelli nella struttura del sito. Ad esempio, un sito multimediale può avere 4 livelli nella sezione Sport: `Sports`, `Local Sports`, `Baseball`e `Team name`. Se qualcuno visita la pagina di baseball, Sport, Sport locali e Baseball, tutti i livelli riflettono quella visita.

Prima di utilizzare le gerarchie nell’implementazione, assicurati di configurare ogni gerarchia nelle impostazioni della suite di rapporti.

## Gerarchie che utilizzano l’SDK per web

Le gerarchie sono [mappato per Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html?lang=it) nei campi XDM `_experience.analytics.customDimensions.hierarchies.hier1` a `_experience.analytics.customDimensions.hierarchies.hier5`.

## Gerarchie che utilizzano l&#39;estensione Adobe Analytics

Puoi impostare le gerarchie sia durante la configurazione dell&#39;estensione Analytics (variabili globali) sia in base alle regole.

1. Accedi a [Raccolta dati Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzo delle credenziali AdobeID.
2. Fai clic sulla proprietà tag desiderata.
3. Vai a [!UICONTROL Rules] , quindi fai clic sulla regola desiderata (o crea una regola).
4. Sotto [!UICONTROL Actions], fai clic su un [!UICONTROL Adobe Analytics - Set Variables] fare clic sull&#39;icona &quot;+&quot;.
5. Imposta la [!UICONTROL Extension] del menu a discesa Adobe Analytics e [!UICONTROL Action Type] a [!UICONTROL Set Variables].
6. Individua il [!UICONTROL Hierarchy] sezione .

È possibile impostare un valore gerarchico su una stringa statica o fare riferimento a un elemento dati. Puoi anche impostare il delimitatore desiderato. Assicurati che il delimitatore impostato qui corrisponda al delimitatore impostato nelle impostazioni della suite di rapporti.

## s.hier1 - s.hier5 in AppMeasurement e nell&#39;editor di codice personalizzato dell&#39;estensione Analytics

Ogni gerarchia è una stringa che contiene valori personalizzati specifici dell’organizzazione. La loro lunghezza massima è di 255 byte; i valori superiori a 255 byte vengono troncati automaticamente quando inviati ad Adobe.

Assicurati che nessuno dei nomi di sezione contenga il delimitatore. Ad esempio, se viene chiamata una delle sezioni `Coach Griffin, Jim`, scegli un delimitatore diverso da una virgola. Il limite totale della variabile è di 255 byte. I delimitatori possono essere costituiti da più caratteri, ad esempio `||` o `/|\`, che hanno meno probabilità di apparire nei valori delle variabili.

```js
s.hier1 = "Toys|Boys 6+|Legos|Super Block Tub";

s.hier3 = "Sports/Local Sports/Baseball";
```
