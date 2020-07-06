---
description: Descrive il processo di distribuzione in tre fasi.
title: Distribuzione dell'integrazione
uuid: a3c0ef21-ed9a-44d7-bdce-19b3bd5b8b80
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 2%

---


# Distribuzione dell&#39;integrazione{#deploying-the-integration}

Descrive il processo di distribuzione in tre fasi.

La distribuzione di questa integrazione è un processo semplice che richiede le seguenti azioni:

## Completamento dell&#39;Integrazione guidata{#completing-the-integration-wizard}

Procedura per utilizzare la procedura guidata di integrazione.

Per attivare l&#39;integrazione, è necessario completare la procedura guidata di integrazione di Lyris all&#39;interno dell&#39;interfaccia Connettori dati.

1. Passa all&#39;area Connettori dati (precedentemente Genesis) in Adobe Experience Cloud.

   ![](assets/data_connectors.png)

1. In **[!UICONTROL Add Integration]**, sotto Lyris HQ, fare clic su **[!UICONTROL Activate]**.

   ![](assets/add_integration.png)

1. In **[!UICONTROL General Settings]**, scegliete la suite di rapporti desiderata e fornite un nome per l&#39;integrazione.
1. Compila tutte le informazioni relative al tuo account Lyris in **[!UICONTROL Custom Values]**.

   ![](assets/general_settings.png)

1. Scegliete le eVar ed eventi riservati appropriate dai menu a discesa.

   ![](assets/variable_mapping.png)

1. Puoi scegliere i tuoi segmenti in **[!UICONTROL Your Segments]** - oltre ai 3 segmenti partner automatizzati.
1. Questa integrazione potrebbe richiedere il download di alcuni punti dati al tuo account Lyris. È possibile scegliere di consentire l&#39;accesso a questa sezione **[!UICONTROL Access Request]**.
1. In **[!UICONTROL Data Collection]**, è possibile scegliere una soluzione automatizzata o manuale (plug-in JavaScript) per raccogliere i parametri della stringa di query dall&#39;URL della pagina di destinazione. Se scegli di disporre di una soluzione automatizzata, immetti il parametro della stringa di query per ID messaggio e ID destinatario. Per un plug-in JavaScript, contattate il vostro consulente Adobe.

   ![](assets/data_collection.png)

1. È possibile scegliere di generare automaticamente il dashboard di Lyris e i segnalibri.

   ![](assets/dashboard_generation.png)

1. Rivedete il riepilogo dell&#39;integrazione e fate clic su **[!UICONTROL Activate]**.

## Configurazione in Lyris EmailLabs{#configuration-within-the-lyris-emaillabs}

Passaggi che descrivono cosa configurare in Lyris al termine della procedura guidata.

1. Dopo aver completato la procedura guidata di integrazione, devi lavorare con il team Lyris Professional per completare l&#39;integrazione con il tuo account Lyris HQ e facilitare il test.
1. Aggiungi parametri stringa query URL: Verificare che la stringa di aggiunta dell&#39;URL sia correttamente inserita nelle aree delle impostazioni dell&#39;organizzazione dell&#39;interfaccia utente. Deve contenere l’ID a livello di campagna (hq_m) e l’ID a livello di destinatario (hq_v).

   Un esempio di ID stringa è:

   ```
   hq_lid=149&hq_m=96843&hq_l=23&hq_v=7703a51905
   ```

   >[!NOTE]
   >
   >Se state applicando lo strumento di analisi nativo di Lyris, *Click Tracks* tag tutte le variabili richieste che vengono aggiunte.

## Verifica dell&#39;integrazione{#verifying-the-integration}

Passaggi per verificare il successo dell&#39;integrazione tra Lyris/Adobe  Analytics.

Una volta completati tutti i passaggi di distribuzione, potete verificare che l&#39;integrazione trasferisca correttamente i dati.

>[!NOTE]
>
>Ci vogliono alcuni giorni perché lo scambio di dati abbia inizio. Assicurarsi di contattare Lyris dopo aver attivato l&#39;integrazione.

1. Passa alla tua integrazione Lyris all&#39;interno dei connettori dati. Sotto la **[!UICONTROL Support]** scheda > **[!UICONTROL Integration Activity Log]**, è possibile visualizzare eventi quali **[!UICONTROL Metric data imported successfully]** e/o **[!UICONTROL Classification data imported successfully]**:

   ![](assets/integration_info.png)

1. Ora puoi visualizzare i tuoi rapporti sui messaggi di Lyris con le metriche appropriate. In Adobe Experience Cloud, seleziona **[!UICONTROL Reports & Analytics]**.
1. Selezionate la suite di rapporti appropriata.
1. In **[!UICONTROL Custom Conversions]**, selezionate il **[!UICONTROL Message ID Reports]** pulsante e scegliete **[!UICONTROL Message ID/Message Name]**.

## Codice Plug-in parametro di stringa query{#query-string-param-plug-in-code}

Mostra il codice del plug-in Lyris da utilizzare con Adobe  Analytics.

>[!NOTE]
>
>Prima di utilizzare il codice riportato di seguito, accertati di aver riservato le eVar necessarie in Admin Tool di Adobe  Analytics. Una volta a conoscenza delle eVar che hai riservato, sostituisci eVarN con l’eVar pertinente. Ad esempio, eVar10.

```
/* 
  * Plugin: getQueryParam 2.3 
  */ 
s.getQueryParam=new Function("p","d","u","" 
+"var s=this,v='',i,t;d=d?d:'';u=u?u:(s.pageURL?s.pageURL:s.wd.locati" 
+"on);if(u=='f')u=s.gtfs().location;while(p){i=p.indexOf(',');i=i<0?p" 
+".length:i;t=s.p_gpv(p.substring(0,i),u+'');if(t){t=t.indexOf('#')>-" 
+"1?t.substring(0,t.indexOf('#')):t;}if(t)v+=v?d+t:t;p=p.substring(i=" 
+"=p.length?i:i+1)}return v"); 
s.p_gpv=new Function("k","u","" 
+"var s=this,v='',i=u.indexOf('?'),q;if(k&&i>-1){q=u.substring(i+1);v" 
+"=s.pt(q,'&','p_gvf',k)}return v"); 
s.p_gvf=new Function("t","k","" 
+"if(t){var s=this,i=t.indexOf('='),p=i<0?t:t.substring(0,i),v=i<0?'T" 
+"rue':t.substring(i+1);if(p.toLowerCase()==k.toLowerCase())return s." 
+"epa(v)}return ''"); 
 
/*in the s_doPlugins function - Replace N with actual eVar number*/ 
s.eVarN=s.getQueryParam("<insert Lyris QS Param>");  
//places query param value from Message ID in eVarN variable s.eVarN=s.getQueryParam("<insert Lyris QS Param>");  
//places query param value from Recepient ID in eVarN variable 
```
