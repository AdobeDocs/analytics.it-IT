---
description: La scheda Uso suite di rapporti fornisce i dati di utilizzo del server per ogni suite di rapporti in tutte le società di accesso collegate alla società di fatturazione, per il periodo di utilizzo corrente.
seo-description: La scheda Uso suite di rapporti fornisce i dati di utilizzo del server per ogni suite di rapporti in tutte le società di accesso collegate alla società di fatturazione, per il periodo di utilizzo corrente.
seo-title: Visualizzazione dell'utilizzo della suite di rapporti
title: Visualizzazione dell'utilizzo della suite di rapporti
uuid: c609ed99-9acc-4023-905a-81a40dd07a79
translation-type: tm+mt
source-git-commit: 8c4c368a84ba5499d85f0b7512c99de47ddb14c2

---


# Visualizzazione dell'utilizzo della suite di rapporti

La scheda Uso suite di rapporti fornisce i dati di utilizzo del server per ogni suite di rapporti in tutte le società di accesso collegate alla società di fatturazione, per il periodo di utilizzo corrente.

**[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Server Call Usage]** &gt; **[!UICONTROL Report Suite Usage]**

>[!IMPORTANT]
>
>Se una suite di rapporti non è [collegata a un'organizzazione](https://marketing.adobe.com/resources/help/en_US/mcloud/report-suite-mapping.html)Experience Cloud, i relativi dati di utilizzo non saranno riportati in questo dashboard. Inoltre, un ID di fatturazione potrebbe essere associato a più organizzazioni Experience Cloud; non esiste sempre una relazione 1:1 tra un'organizzazione e un ID di fatturazione.

Pannello Utilizzo suite di rapporti

* Mostra l’utilizzo del periodo di utilizzo corrente delle chiamate server (Tutte le chiamate, Primarie, Secondarie, Primarie mobili e secondarie mobili) per ogni suite di rapporti nell’organizzazione Experience Cloud.
* Mostra la percentuale di utilizzo totale per categoria di chiamate server.
* Viene aggiornato ogni giorno.
* È scaricabile.
* Consente di accedere all’ **[!UICONTROL Manage Alerts]** interfaccia utente.

![](assets/report-suite-usage.png)

| Colonna | Definizione |
|--- |--- |
| Nome suite di rapporti | Nome descrittivo della suite di rapporti |
| Tutte le chiamate (% del totale) | Tutte le chiamate server effettuate nel periodo di utilizzo corrente. |
| Chiamate principali (%) | Tutte le chiamate server principali (e la loro percentuale del totale) effettuate nel periodo di utilizzo corrente. |
| Chiamate secondarie (%) | Tutte le chiamate server secondarie (e la loro percentuale del totale) effettuate nel periodo di utilizzo corrente. |
| Primaria mobile (%) | Tutte le chiamate al server primario mobile (e la loro percentuale del totale) effettuate nel periodo di utilizzo corrente. |
| Secondario mobile (%) | Tutte le chiamate al server secondario mobile (e la loro percentuale del totale) effettuate nel periodo di utilizzo corrente. |


## Download del rapporto sull'utilizzo {#section_D7345660B5E043CD8850954216509A3D}

Questa opzione consente di scaricare i dati di utilizzo correnti e i dati dai periodi di tempo precedenti al periodo di utilizzo corrente (da gennaio 2015). Il rapporto viene scaricato come file .csv.

1. Seleziona almeno una suite di rapporti.
1. Fai clic su **[!UICONTROL Download Report]**.

   ![](assets/download_report.png)

| Elemento report | Descrizione |
|--- |--- |
| Nome file | Nome hardcoded: Report di utilizzo `day and time of report creation.csv` |
| Suite di rapporti incluse | In questo elenco sono incluse tutte le suite di rapporti selezionate nella pagina Utilizzo server di report. |
| Tipi di chiamate inclusi | Specificate una combinazione di:  Tutte Le Chiamate (Predefinito), Primarie, Secondarie, Primarie Dispositivi Mobili, Secondarie Dispositivi Mobili. |
| Intervallo di tempo | Potete scegliere il periodo di utilizzo corrente o specificare un intervallo personalizzato.  Per un intervallo personalizzato, specificate i valori Inizio intervallo e Fine intervallo. <br>**** Nota: Non potete scaricare i dati di utilizzo prima di gennaio 2015 </br>. |

1. Fai clic su **[!UICONTROL Download]**.

Di seguito viene fornito uno screenshot dell'aspetto del file .csv scaricato. Include una colonna per l'ID suite di rapporti. L'ID suite di rapporti specifica un ID univoco che può contenere solo caratteri alfanumerici. Questo ID non può essere modificato dopo la creazione di una suite di rapporti.

![](assets/download-usage.png)
