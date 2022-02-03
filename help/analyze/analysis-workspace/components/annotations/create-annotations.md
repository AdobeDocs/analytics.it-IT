---
title: Creare annotazioni
description: Come creare annotazioni in Workspace.
role: User, Admin
source-git-commit: 89cbecf109a8fa9a9fac1f1ed8ad198ffdd398d3
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 1%

---


# Creare annotazioni

>[!NOTE]
>
>Questa funzione è attualmente in fase di test.

1. Per creare le annotazioni sono disponibili 4 modi per iniziare:

   * Vai a [!UICONTROL Analytics] > [!UICONTROL Components] > [!UICONTROL Annotation]. Viene visualizzata la pagina Gestione annotazioni. Fai clic su [!UICONTROL Create New Annotation] viene aperto il Generatore di annotazioni.

   * Fare clic con il pulsante destro del mouse su un punto di una tabella o di un grafico a linee. Viene aperto il Generatore di annotazioni.

   * In Workspace, vai a [!UICONTROL Components] > [!UICONTROL Create annotation]. Viene aperto il Generatore di annotazioni.

   * Utilizza questo tasto di scelta rapida per aprire il generatore di annotazioni:
      * (PC) `ctrl` `shift` + o
      * (Mac) `shift` + `command` + o

1. Inserisci gli elementi Builder .

   ![](assets/ann-builder.png)

   | Elemento | Descrizione |
   | --- | --- |
   | [!UICONTROL Title] | Denomina l’annotazione, ad esempio &quot;Memorial Day&quot; |
   | [!UICONTROL Description] | (Facoltativo) Fornisci una descrizione dell’annotazione, ad esempio &quot;Vacanza pubblica osservata negli Stati Uniti&quot;. |
   | [!UICONTROL Tags] | (Facoltativo) Organizza le annotazioni creando o applicando un tag . |
   | [!UICONTROL Applied date] | Seleziona l’intervallo di date o date che deve essere presente affinché l’annotazione sia visibile. |
   | [!UICONTROL Color] | Applica un colore all’annotazione. L’annotazione viene visualizzata nel progetto con il colore selezionato. Il colore può essere utilizzato per classificare le annotazioni, ad esempio festività pubbliche, eventi esterni, problemi di tracciamento, ecc. |
   | [!UICONTROL Scope] | (Facoltativo) Trascina le metriche che attivano l’annotazione. Trascina quindi eventuali dimensioni o segmenti che fungono da filtri (ad esempio, con cui sarà visibile l’annotazione). Se non si specifica un ambito, l’annotazione verrà applicata a tutti i dati.<ul><li>**[!UICONTROL Any of these metrics are present]**: Trascina fino a 10 metriche per attivare l’annotazione da visualizzare.</li><li>**[!UICONTROL With all of these filters]**: Trascina fino a 10 dimensioni o segmenti per filtrare quando viene visualizzata l’annotazione.</li></ul><p>Casi di utilizzo: Un eVar ha interrotto la raccolta dei dati per un intervallo di date specifico. Trascina l’eVar nella **[!UICONTROL Any of these metrics are present]** finestra di dialogo. Oppure [!UICONTROL Visits] la metrica non riporta dati; segui lo stesso processo. |
   | [!UICONTROL Apply to all report suites] | Per impostazione predefinita, l’annotazione si applica alla suite di rapporti di origine. Selezionando questa casella, puoi applicare l’annotazione a tutte le suite di rapporti dell’azienda. |
   | [!UICONTROL Apply to all projects] | Per impostazione predefinita, l’annotazione si applica al progetto corrente. Selezionando questa casella, puoi applicare l’annotazione a tutti i progetti di tua proprietà. Questa casella di controllo viene visualizzata solo quando si avvia il generatore di annotazioni dal manager di annotazione. |

1. Fai clic su [!UICONTROL Save].