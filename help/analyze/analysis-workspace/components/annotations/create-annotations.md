---
title: Creare annotazioni
description: Come creare annotazioni in Workspace.
role: User, Admin
source-git-commit: 6b5fd4e25056d7efbf3119a4d55d2e0a7897965f
workflow-type: tm+mt
source-wordcount: '472'
ht-degree: 1%

---


# Creare annotazioni

>[!NOTE]
>
>Questa funzione è attualmente in fase di test.

1. Per creare le annotazioni sono disponibili 4 modi per iniziare:

   * Vai a [!UICONTROL Analytics] > [!UICONTROL Components] > [!UICONTROL Annotation]. Viene visualizzata la pagina Gestione annotazioni. Fai clic su [!UICONTROL Create New Annotation] viene aperto il Generatore di annotazioni.

   * Fare clic con il pulsante destro del mouse su un punto di una tabella o di un grafico a linee. Viene aperto il Generatore di annotazioni. Per impostazione predefinita, le annotazioni create in questo modo sono visibili solo nel progetto in cui sono state create. Ma puoi renderli disponibili a tutti i progetti.

   * In Workspace, vai a [!UICONTROL Components] > [!UICONTROL Create annotation]. Viene aperto il Generatore di annotazioni.

   * Utilizza questo tasto di scelta rapida per aprire il generatore di annotazioni:
      * (PC) `ctrl` `shift` + o
      * (Mac) `shift` + `command` + o

1. Inserisci gli elementi del generatore di annotazioni.

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
   | [!UICONTROL Apply to all projects] | Per impostazione predefinita, l’annotazione si applica al progetto corrente. Selezionando questa casella, puoi applicare l’annotazione a tutti i progetti di tua proprietà. Questa casella di controllo viene visualizzata solo quando si avvia il Generatore di annotazioni dal Generatore di annotazioni? |

1. Fai clic su [!UICONTROL Save].

## Creare annotazioni da un [!UICONTROL Line] grafico

1. Da all&#39;interno di un [!UICONTROL Line] grafico, scegliere un calo o un picco nel [!UICONTROL Line] grafico e fare clic con il pulsante destro del mouse. Una finestra a comparsa chiamata **[!UICONTROL Annotate selection]** appare.

   ![](assets/annotate-line.png)

1. Fai clic su **[!UICONTROL Annotate selection]**. Viene aperto il Generatore di annotazioni.

>[!NOTE]
>
>Osserva l’annotazione solo progetto. Per rendere l’annotazione disponibile per tutti i progetti, seleziona la casella .

1. Compila i dettagli indicati sopra. Tieni presente che le date e le metriche, ecc., sono già state compilate.

## Creare un’annotazione all’interno di una tabella a forma libera

1. Procedi come faresti per un grafico a linee, ma fai clic con il pulsante destro del mouse su una riga della tabella che deve essere annotata.

1. Select **[!UICONTROL Create annotation from selection]**.

   ![](assets/annotate-table.png)

1. Compila i dettagli indicati sopra. Tieni presente che le date e le metriche, ecc., sono già state compilate.

