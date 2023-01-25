---
description: La scheda Utilizzo suite di rapporti fornisce i dati di utilizzo del server per ogni suite di rapporti in tutte le società associate alla tua società di fatturazione che vi accedono, per il periodo di utilizzo corrente.
title: Visualizzazione dell’utilizzo della suite di rapporti
feature: Server Call Usage
exl-id: bedd4ed8-1c8b-45fd-a059-fed88e9fbe73
source-git-commit: a17297af84e1f5e7fe61f886eb3906c462229087
workflow-type: ht
source-wordcount: '418'
ht-degree: 100%

---

# Visualizzazione dell’utilizzo della suite di rapporti

La scheda Utilizzo suite di rapporti fornisce i dati di utilizzo del server per ogni suite di rapporti in tutte le società associate alla tua società di fatturazione che vi accedono, per il periodo di utilizzo corrente.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Server Call Usage]** > **[!UICONTROL Report Suite Usage]**

>[!IMPORTANT]
>
>Se una suite di rapporti non è collegata a un’organizzazione Experience Cloud, i relativi dati di utilizzo non vengono riportati in questa dashboard. Inoltre, un ID di fatturazione potrebbe essere associato a più organizzazioni Experience Cloud; non esiste sempre una relazione 1:1 tra un’organizzazione e un ID di fatturazione.

Dashboard di utilizzo della suite di rapporti

* Mostra l’utilizzo della chiamata al server nel periodo di utilizzo corrente (Tutte le chiamate, Primaria, Secondaria, Primaria da dispositivo mobile, Secondaria da dispositivo mobile) per ogni suite di rapporti nell’organizzazione Experience Cloud.
* Mostra la percentuale di utilizzo complessivo per categoria di chiamate al server.
* Viene aggiornato ogni giorno.
* È scaricabile.
* Consente di accedere all’interfaccia utente **[!UICONTROL Manage Alerts]**.

![](/help/admin/admin/c-server-call-usage/assets/report-suite-usage.png)

| Colonna | Definizione |
|--- |--- |
| Nome della suite di rapporti | Nome descrittivo della suite di rapporti |
| Tutte le chiamate (% del totale) | Tutte le chiamate al server effettuate nel periodo di utilizzo corrente. |
| Chiamate primarie (%) | Tutte le chiamate primarie al server (e la loro percentuale sul totale) effettuate nel periodo di utilizzo corrente. |
| Chiamate secondarie (%) | Tutte le chiamate secondarie al server (e la loro percentuale sul totale) effettuate nel periodo di utilizzo corrente. |
| Primaria da dispositivo mobile (%) | Tutte le chiamate primarie al server da dispositivo mobile (e la loro percentuale sul totale) effettuate nel periodo di utilizzo corrente. |
| Secondaria da dispositivo mobile (%) | Tutte le chiamate secondarie al server da dispositivo mobile (e la loro percentuale del totale) effettuate nel periodo di utilizzo corrente. |


## Download del rapporto di utilizzo {#section_D7345660B5E043CD8850954216509A3D}

Questa opzione consente di scaricare i dati di utilizzo correnti e i dati relativi ai periodi di utilizzo precedenti a quello corrente (a partire da gennaio 2015). Il rapporto viene scaricato come file .csv.

1. Seleziona almeno una suite di rapporti.
1. Fai clic su **[!UICONTROL Download Report]**.

   ![](/help/admin/admin/c-server-call-usage/assets/download_report.png)

| Elemento di rapporto | Descrizione |
|--- |--- |
| Nome del file | Nome codificato: rapporto di utilizzo `day and time of report creation.csv` |
| Suite di rapporti incluse | Tutte le suite di rapporti selezionate nella pagina Rapporto di utilizzo server sono incluse in questo elenco. |
| Tipi di chiamate inclusi | Specifica una combinazione di queste: Tutte Le Chiamate (predefinito), Primaria, Secondaria, Primaria da dispositivo mobile, Secondaria da dispositivo mobile. |
| Intervallo di tempo | Puoi scegliere il periodo di utilizzo corrente o specificare un intervallo personalizzato.  Per un intervallo personalizzato, specifica Inizio intervallo e Fine intervallo. <br>**Nota:** non è possibile scaricare i dati di utilizzo precedenti a gennaio 2015</br>. |

1. Fai clic su **[!UICONTROL Download]**.

Questa schermata riproduce l’aspetto del file .csv scaricato. Include una colonna per l’ID suite di rapporti. L’ID suite di rapporti specifica un ID univoco che può contenere solo caratteri alfanumerici. Questo ID non può essere modificato dopo la creazione di una suite di rapporti.

![](/help/admin/admin/c-server-call-usage/assets/download-usage.png)
