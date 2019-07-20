---
description: Adobe offre alcune best practice per aggiornare il codice Analytics.
keywords: Implementazione di Analytics
seo-description: Adobe offre alcune best practice per aggiornare il codice Analytics.
seo-title: Sostituzione del codice di Analytics
solution: Analytics
subtopic: 'Risoluzione dei problemi   '
title: Sostituzione del codice di Analytics
topic: Sviluppatore e implementazione
uuid: d 3 ea 6585-199 f -4 dbe -9 ee 8-15 b 204689 f 2 f
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Sostituzione del codice di Analytics

Adobe offre alcune best practice per aggiornare il codice Analytics.

Frequently, customers use the Adobe [!UICONTROL Code Manager] to replace their code with the most recent version. Questa procedura è valida se si tengono presenti alcuni elementi.

## Using the Incorrect Data Collection Server ID {#section_1726CEB1ABEC408492569B06664410C8}

Occasionally, generic [!DNL s_code.js] files that have not been generated from Adobe Code Manager are sent to those implementing the code on your site. As a result, the incorrect data collection server ID (as shown in the [!UICONTROL s.dc] variable) for the account is used. It is best to generate new code directly from the [!UICONTROL Code Manager] for a specific report suite, rather than reusing code from a different report suite. This is the best way to make sure the [!UICONTROL s.dc] variable is populated correctly.

## Plug-ins {#section_53650E52D6A54A4795F95E491E7548D1}

Alcuni clienti implementano i plug-in per migliorare la loro esperienza Adobe. Quando sostituite il codice, non dimenticate di disporre dei plug-in come parte di tale codice. The code created in the [!UICONTROL Code Manager] does not have any plug-in code with it, so all plug-ins need to migrate manually to the newer code base. Crea una copia del codice esistente, qualora accada qualcosa e devi ripristinare il codice precedente.
