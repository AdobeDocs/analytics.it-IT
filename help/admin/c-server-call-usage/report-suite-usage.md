---
description: La scheda Utilizzo suite di rapporti fornisce i dati di utilizzo del server per ogni suite di rapporti in tutte le società di accesso associate alla società Fatturazione, per il periodo di utilizzo corrente.
seo-description: La scheda Utilizzo suite di rapporti fornisce i dati di utilizzo del server per ogni suite di rapporti in tutte le società di accesso associate alla società Fatturazione, per il periodo di utilizzo corrente.
seo-title: Visualizzazione dell'utilizzo della suite di rapporti
title: Visualizzazione dell'utilizzo della suite di rapporti
uuid: c 609 ed 99-9 acc -4023-905 a -81 a 40 dd 07 a 79
translation-type: tm+mt
source-git-commit: a6aac17d93877ed2a6525484ba5aa4e741ca116a

---


# Visualizzazione dell'utilizzo della suite di rapporti

La scheda Utilizzo suite di rapporti fornisce i dati di utilizzo del server per ogni suite di rapporti in tutte le società di accesso associate alla società Fatturazione, per il periodo di utilizzo corrente.

**[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Server Call Usage]** &gt; **[!UICONTROL Report Suite Usage]**

>[!IMPORTANT]
>
>If a report suite is not [linked to an Experience Cloud Organization](https://marketing.adobe.com/resources/help/en_US/mcloud/report-suite-mapping.html), its usage data will not be reflected in this dashboard. Inoltre, un ID di fatturazione può essere associato a più organizzazioni Experience Cloud; non esiste sempre una relazione 1:1 tra un'organizzazione e un ID di fatturazione.

Dashboard Utilizzo suite di rapporti

* Mostra l'utilizzo delle chiamate server del periodo di utilizzo corrente (Tutte le chiamate, Primaria, Secondaria, Mobile primaria, Secondaria mobile) per ogni suite di rapporti nell'organizzazione Experience Cloud.
* Mostra la percentuale dell'utilizzo complessivo per categoria di chiamate server.
* Viene aggiornato ogni giorno.
* Scaricabile.
* Lets you access the **[!UICONTROL Manage Alerts]** UI.

![](assets/report-suite-usage.png)

| Colonna | Definizione |
|--- |--- |
| Nome suite di rapporti | Nome intuitivo della suite di rapporti |
| Tutte le chiamate (% di Totale) | Tutte le chiamate server registrate nel periodo di utilizzo corrente. |
| Chiamate principali (%) | Tutte le chiamate server principali (e la percentuale di totale) supportata nel periodo di utilizzo corrente. |
| Chiamate secondarie (%) | Tutte le chiamate server secondarie (e la percentuale di totale) sono state salvate nel periodo di utilizzo corrente. |
| Mobile principale (%) | Tutte le chiamate server principali mobili (e la percentuale di totale) sono state salvate nel periodo di utilizzo corrente. |
| Secondario mobile (%) | Tutte le chiamate server secondarie mobili (e la percentuale di totale) supportata nel periodo di utilizzo corrente. |


## Download Usage Report {#section_D7345660B5E043CD8850954216509A3D}

Questa opzione consente di scaricare i dati di utilizzo correnti e i dati dai periodi di tempo precedenti al periodo di utilizzo corrente (tornare al 2015 gennaio). Il rapporto viene scaricato come file. csv.

1. Seleziona almeno una suite di rapporti.
1. Fai clic su **[!UICONTROL Download Report]**.

   ![](assets/download_report.png)

| Elemento rapporto | Descrizione |
|--- |--- |
| Nome file | Hardcoded name: Usage Report `day and time of report creation.csv` |
| Suite di rapporti incluse | Tutte le suite di rapporti selezionate nella pagina Uso server di report sono incluse in questo elenco. |
| Tipi di chiamate inclusi | Specificate una combinazione di questi elementi: Tutte le chiamate (predefinito), primaria, secondaria, mobile primaria, mobile secondaria. |
| Intervallo di tempo | Puoi scegliere il periodo di utilizzo corrente o specificare un intervallo personalizzato. Per un intervallo personalizzato, specificate l'intervallo intervallo e Fine intervallo. <br>**Nota:** Non è possibile scaricare i dati di utilizzo prima del 2015 </br>gennaio. |

1. Fai clic su **[!UICONTROL Download]**.

Ecco una schermata di come si presenta il file. csv scaricato. Include una colonna per l'ID suite di rapporti. L'ID suite di rapporti specifica un ID univoco che può contenere solo caratteri alfanumerici. Questo ID non può essere modificato dopo la creazione di una suite di rapporti.

![](assets/download-usage.png)