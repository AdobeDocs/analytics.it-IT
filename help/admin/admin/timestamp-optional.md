---
description: Combina sia i dati con marca temporale che quelli privi di marca in una singola suite di rapporti.
seo-description: Combina sia i dati con marca temporale che quelli privi di marca in una singola suite di rapporti.
seo-title: Marca temporale opzionale
solution: Analytics
title: Marca temporale opzionale
topic: Strumenti di amministrazione
uuid: 0 fa 63658-1 cc 2-4 adc -8 d 51-a 0662 d 0 aa 941
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Marca temporale opzionale

Combina sia i dati con marca temporale che quelli privi di marca in una singola suite di rapporti.

Marca temporale opzionale:

* Inserite sia i dati con marca temporale sia quelli privi di marca nella stessa suite per report globale.
* Inviate dati con marca temporale da un app per dispositivo mobile a una suite per report globale.
* Aggiornate le app per poter utilizzare il monitoraggio offline senza dover creare per una suite per report.

See [Using Timestamps Optional](https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=timestamps-overview) for best practices when using timestamps in your report suite.

>[!IMPORTANT]
>
>If you are using Timestamps Optional, then do not set [s.visitorID](https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=visid_custom) on data that is already timestamped. Questo può portare a dati out-of-order e influenzare in modo negativo i calcoli temporale (ad esempio i valori passati), l'attribuzione (persistenza evar), il numero di visite/visite e i rapporti sui percorsi.

>[!NOTE]
>
>I dati delle sessioni abilitati per marca temporale vengono conservati per un massimo di 92 giorni.

## New Report Suites {#section_095A7CFBD280494593B9BEC1592B73A6}

* Se viene creata da un modello, una nuova suite di rapporti è impostata su Marca temporale opzionale.

   (You can create a new report suite from a template at **Admin &gt; Report Suites &gt; Create New &gt; Report Suite**.)
* Se copiata da una suite di rapporti esistente, la nuova suite di rapporti eredita l'impostazione temporale dall'originale, incluso:

   * **Marche temporali non consentite** (impostazione s. visitorid supportata)
   * **Marca temporale richiesta** (impostazione s. visitorid non supportata)
   * **Marca temporale opzionale** (impostazione s. visitorid supportata ma non sugli hit con marca temporale)

## To change existing report suites to Timestamps Optional {#section_40BCD3B4639241DEA716F7640ED33E72}

1. Go to **Admin &gt; Report Suites &gt; Edit Settings &gt; General &gt; Timestamp Configuration**.
1. Select the **Convert selected report suites to Timestamps Optional** box.

   In questo modo la suite di rapporti viene modificata in Marca temporale opzionale.

>[!NOTE]
>
>If a report suite was set to **Timestamps Optional**, to change this to any other setting, please contact Adobe Client Care.

