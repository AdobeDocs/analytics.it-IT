---
description: Scoprite come specificare la scadenza del coinvolgimento dei visitatori nei canali di marketing.
subtopic: Marketing channels
title: Scadenza canale di marketing
topic: Reports and analytics
uuid: 47f1ccaf-3ce7-494d-b456-956a3a3c6c9a
translation-type: tm+mt
source-git-commit: 46dae8ee28b202578f5ad0c2446b1fd63e5144cc
workflow-type: tm+mt
source-wordcount: '323'
ht-degree: 4%

---


# Scadenza canale di marketing

Scoprite come specificare la scadenza, o il periodo di coinvolgimento del visitatore, per i canali di marketing.

Il coinvolgimento del visitatore è il tempo che desiderate concedere affinché l&#39;attività precedente del visitatore sul sito venga attribuita al primo canale touch. L’impostazione predefinita per la scadenza è 30 giorni.

Se il visitatore utilizza il sito frequentemente, la finestra di coinvolgimento si espanderà con loro. Devono essere inattivi per 30 giorni affinché il periodo scada e i canali vengano reimpostati. Sia il primo che l’ultimo canale touch per un visitatore verranno reimpostati dopo 30 giorni di inattività in quel browser.

Esempio:

* Giorno 1: L&#39;utente accede al sito sul display. I canali Primo e Ultimo tocco verranno impostati su Display.
* Giorno 2: L&#39;utente viene al sito su Natural Search. Il primo tocco rimane Display e l&#39;ultimo tocco è impostato su Natural Search.
* Giorno 35: L&#39;utente non è stato sul sito in 33 giorni e torna utilizzando la scheda che aveva aperto nel browser. Presupponendo una finestra di coinvolgimento di 30 giorni, la finestra si sarebbe chiusa e i cookie di Marketing Channel sarebbero scaduti. Il primo canale touch e l’ultimo touch vengono reimpostati e impostati su Aggiornamento sessione, dal momento che l’utente proviene da un URL interno.

## Impostazioni di scadenza canale di marketing

Le impostazioni di scadenza sono le seguenti:

| Campo | Definizione |
|--- |--- |
| Giorni di inattività | Il numero di giorni che devono trascorrere prima della scadenza del primo contatto del visitatore. Il valore predefinito è 30. |
| Mai | Il periodo di coinvolgimento del visitatore non scade. |
| Ripristino canale | Scade tutti i periodi di coinvolgimento dei visitatori.  Se hai bisogno di ripristinare tutti i dati dei canali di marketing, puoi scadere tutti i periodi di coinvolgimento dei visitatori. Potrebbe essere necessario reimpostare i dati se le regole di elaborazione erano state precedentemente configurate in modo errato. Tutti i valori del primo e dell&#39;ultimo canale di tocco scadranno immediatamente e verranno reimpostati al ritorno dei visitatori. |

## Definizione della scadenza del canale di marketing {#define-expiration}

Specifica il periodo di coinvolgimento del visitatore.

1. Fai clic su **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
2. In [!UICONTROL Report Suite Manager], fai clic su **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Expiration]**.

   ![](assets/mchannel_expiration.png)

3. Configurate i campi del periodo di coinvolgimento dei visitatori.
4. Fai clic su **[!UICONTROL Save.]**

