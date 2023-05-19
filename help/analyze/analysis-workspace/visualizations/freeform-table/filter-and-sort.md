---
description: Documentazione che descrive come filtrare e ordinare le tabelle in Analysis Workspace.
title: Filtrare e ordinare tabelle
feature: Freeform Tables
role: User, Admin
exl-id: 15fea9e2-f8d8-4489-9a44-e74a351b8f36
source-git-commit: 9899b5e0fbdfd5264be9d414477caad38d4550ae
workflow-type: tm+mt
source-wordcount: '823'
ht-degree: 70%

---

# Filtrare e ordinare tabelle

Le tabelle a forma libera in Analysis Workspace sono la base dell’analisi interattiva dei dati. In quanto tali, possono contenere migliaia di righe di informazioni. Filtrare e ordinare i dati può essere fondamentale per far emergere in modo efficace le informazioni più importanti.

## Filtrare le tabelle

I filtri in Analysis Workspace ti aiutano a far emergere le informazioni più importanti.

>[!NOTE]
>
> Solo gli elementi dimensionali dinamici possono essere filtrati come descritto in questa sezione. Gli elementi dimensionali statici non possono essere filtrati. Per ulteriori informazioni, consulta [Elementi dimensionali dinamici e statici nelle tabelle a forma libera](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md).

### Escludere rapidamente righe specifiche da una tabella

È possibile escludere rapidamente righe specifiche dalla tabella senza dover aprire la finestra di dialogo Filtro.

>[!NOTE]
>
>Quando escludi le righe come descritto in questa sezione, [!UICONTROL **Escludere sempre gli elementi**] la regola viene applicata automaticamente nella finestra di dialogo del filtro avanzato. Per visualizzare la regola applicata, seleziona l’icona Filtro , quindi [**[!UICONTROL Show advanced]**](#apply-a-simple-or-advanced-filter-to-a-table).)

Per escludere rapidamente righe specifiche da una tabella a forma libera:

1. Passa il puntatore del mouse sulla riga da escludere, quindi seleziona l’icona x .

   Tenete premuto il tasto Maiusc per selezionare una riga di intervallo oppure tenete premuto il tasto Comando (su Mac) o il tasto Ctrl (su Windows) per selezionare più righe.

### Applicare un filtro semplice o avanzato a una tabella

Per filtrare i dati nelle tabelle a forma libera:

1. Passa il puntatore del mouse sulla colonna contenente i dati da filtrare. <!--only some types of columns show the filter... Which? Just Dimensions?-->

1. Seleziona l’icona **Filtro** quando viene visualizzata.

   ![Icona del filtro in una tabella](assets/table-filter-icon.png)

   Sono disponibili le seguenti opzioni:

   | Opzione | Funzione |
   |---------|----------|
   | [!UICONTROL **Ricerca di parole o frasi**] | Specificare una parola o una frase per la quale si desidera filtrare. Vengono visualizzate solo le righe contenenti la parola o la frase esatta specificata. |
   | [!UICONTROL **Includi non specificato (nessuno)**] | Selezionare questa opzione per visualizzare nella tabella i dati che non rientrano in alcuna delle dimensioni disponibili. <!--what is this?--> |

1. (Facoltativo) Per filtrare in base a criteri diversi o a più criteri, seleziona [!UICONTROL **Mostra avanzate**].

   Sono disponibili le seguenti opzioni di filtro avanzate:

   | Opzione | Funzione |
   |---------|----------|
   | [!UICONTROL **Includi non specificato (nessuno)**] | Selezionare questa opzione per visualizzare nella tabella i dati che non rientrano in alcuna delle dimensioni disponibili. <!--what is this?--> |
   | [!UICONTROL **Corrispondenza**] | <p>Scegli [!UICONTROL **Se sono soddisfatti tutti i criteri**] per mostrare solo i dati che soddisfano tutti i criteri specificati. In genere, questa opzione genera dati più precisi.</p> <p>Scegli [!UICONTROL **Se sono soddisfatti i criteri**] per mostrare i dati che soddisfano tutti i criteri di filtro specificati. Di solito, questa opzione genera dati meno precisi.</p> |
   | [!UICONTROL **Criteri**] | <p>Seleziona tra le opzioni filtro seguenti:</p><p>(Seleziona [!UICONTROL **Aggiungi riga**] per aggiungere più criteri di filtro. L’opzione selezionata nella sezione [!UICONTROL **Corrispondenza**] determina se tutti i criteri aggiunti devono essere soddisfatti o meno.)</p><ul><li><p>[!UICONTROL **Contiene la frase**]: nei risultati filtrati vengono inclusi solo i dati che contengono la frase esatta specificata. Le parole devono essere nell’ordine specificato nel [!UICONTROL **campo Cerca parola o frase**].<p>Questa è l’impostazione predefinita quando si esegue una ricerca semplice.</p></p></li><li><p>[!UICONTROL **Contiene qualsiasi termine**]: nei risultati filtrati sono inclusi solo i dati contenenti una o più parole della frase specificata. </p></li><li><p>[!UICONTROL **Contiene tutti i termini**]: nei risultati filtrati sono inclusi solo i dati che contengono tutte le parole della frase specificata. Le parole non devono necessariamente essere nell&#39;ordine specificato nel [!UICONTROL **campo Cerca parola o frase**].</p></li><li><p>[!UICONTROL **Non contiene alcun termine**]: nei risultati filtrati sono inclusi solo i dati che non contengono le parole della frase specificata. </p></li><li><p>[!UICONTROL **Non contiene la frase**]: nei risultati filtrati sono inclusi solo i dati che non contengono la frase esatta specificata. Le parole devono essere nell’ordine specificato nel [!UICONTROL **campo Cerca parola o frase**].</p></li><li><p>[!UICONTROL **È uguale a**]: nei risultati filtrati vengono inclusi solo i dati che corrispondono esattamente alla frase specificata. </p></li><li><p>[!UICONTROL **Non è uguale a**]: nei risultati filtrati vengono inclusi solo i dati che non corrispondono esattamente alla frase specificata. </p></li><li><p>[!UICONTROL **Inizia con**]: nei risultati filtrati sono inclusi solo i dati che iniziano con la parola o la frase esatta specificata. </p></li><li><p>[!UICONTROL **Termina con**]: nei risultati filtrati sono inclusi solo i dati che terminano con la parola o la frase esatta specificata. </p></li></ul> |
   | [!UICONTROL **Escludi sempre gli elementi**] | Specifica il nome degli elementi da escludere dai dati filtrati. |

1. Seleziona [!UICONTROL **Applica**] per filtrare i dati.

   L’icona **Filtro** ![Tabella con icona del filtro blu](assets/table-filter-blue-icon.png) diventa blu quando un filtro viene applicato alla tabella.

## Ordinare le tabelle

Puoi ordinare i dati di una tabella a forma libera in base a qualsiasi colonna di Analysis Workspace che sia una metrica.

Icona con freccia giù ![Colonna tabella ordinata con icona con freccia giù](assets/table-sort-arrow-icon.png) è visibile nell’intestazione della colonna in base alla quale i dati vengono ordinati.

Per ordinare i dati di una tabella a forma libera in base a una particolare colonna:

1. Passa il puntatore del mouse sul titolo della colonna in base al quale vuoi ordinare i dati.

1. Seleziona l’icona a forma di freccia giù quando viene visualizzata.

   ![Icona a freccia in giù, colonna della tabella ordinata](assets/table-sort.png)

   I dati della tabella sono ordinati in base alla colonna selezionata.
