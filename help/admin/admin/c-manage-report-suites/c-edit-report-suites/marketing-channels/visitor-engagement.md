---
description: Scopri come specificare la scadenza del coinvolgimento del visitatore nei canali di marketing.
subtopic: Marketing channels
title: Scadenza canale di marketing
feature: Marketing Channels
exl-id: a9df659b-3b6a-4bdb-bd77-f4490d2b7c79
source-git-commit: 6b216a9af4b5614203b0f34fa754985b12ff59ea
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 10%

---

# Scadenza canale di marketing

>[!NOTE]
>
> Per informazioni generali sui canali di marketing, vedi [Introduzione ai canali di marketing](/help/components/c-marketing-channels/c-getting-started-mchannel.md).
>
> Per massimizzare l’efficacia dei canali di marketing per Attribution IQ e Customer Journey Analytics, abbiamo pubblicato alcune [best practice](/help/components/c-marketing-channels/mchannel-best-practices.md).

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Expiration]**.

Scopri come specificare la scadenza, o il periodo di coinvolgimento del visitatore, per i canali di marketing.

Il coinvolgimento del visitatore è il tempo che vuoi dedicare affinché l’attività precedente del visitatore sul tuo sito sia attribuita al canale di primo contatto. L’impostazione predefinita della scadenza è 30 giorni.

Se il visitatore utilizza il sito frequentemente, la finestra di coinvolgimento si sposterà con loro. Devono essere inattivi per 30 giorni affinché il periodo scada e i canali vengano reimpostati. I canali di primo e ultimo contatto per un visitatore verranno reimpostati dopo 30 giorni di inattività in quel browser.

Esempio:

* Giorno 1: L&#39;utente accede al sito su Display. I canali di primo e ultimo contatto saranno impostati su Visualizzazione.
* Giorno 2: L&#39;utente viene al sito sulla ricerca naturale. Il primo contatto rimane Display e l’ultimo contatto è impostato su Ricerca naturale.
* Giorno 35: L&#39;utente non è stato sul sito in 33 giorni e torna utilizzando la scheda che aveva aperto nel loro browser. Supponendo che sia presente una finestra di coinvolgimento di 30 giorni, la finestra si sarebbe chiusa e i cookie del canale di marketing sarebbero scaduti. Il canale di primo contatto e ultimo contatto viene reimpostato su Aggiornamento sessione poiché l’utente proviene da un URL interno.

## Impostazioni di scadenza del canale di marketing

Le impostazioni di scadenza sono le seguenti:

| Campo | Definizione |
|--- |--- |
| Giorni di inattività | Il numero di giorni che devono trascorrere prima della scadenza del coinvolgimento di primo contatto di un visitatore. Il valore predefinito è 30. |
| Mai | Il periodo di coinvolgimento del visitatore non scade. |
| Ripristino del canale | Scade da tutti i periodi di coinvolgimento del visitatore.  Se devi reimpostare tutti i dati dei canali di marketing, puoi scadere tutti i periodi di coinvolgimento dei visitatori. Potrebbe essere necessario reimpostare i dati se le regole di elaborazione erano precedentemente configurate in modo errato. Tutti i valori del canale di primo e ultimo contatto scadranno immediatamente e verranno reimpostati quando i visitatori ritornano. |

## Definire la scadenza del canale di marketing {#define-expiration}

Specifica il periodo di coinvolgimento del visitatore.

1. Fai clic su **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
2. In [!UICONTROL Report Suite Manager], fai clic su **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Expiration]**.

   ![](assets/mchannel_expiration.png)

3. Configura i campi del periodo di coinvolgimento del visitatore.
4. Fai clic su **[!UICONTROL Save.]**
