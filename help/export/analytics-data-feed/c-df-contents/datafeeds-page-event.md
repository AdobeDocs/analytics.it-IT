---
description: Tabella di ricerca per determinare il tipo di hit in base al valore page_event.
keywords: Feed dati;pagina;evento;page_event;post_page_event
title: Ricerca eventi pagina
feature: Data Feeds
exl-id: ef0467df-b94b-4cec-b312-96d8f42c23b0
source-git-commit: 4daa5c8bdbcb483f23a3b8f75dde9eeb48516db8
workflow-type: tm+mt
source-wordcount: '231'
ht-degree: 3%

---

# Ricerca eventi pagina

Tabella di ricerca per determinare il tipo di hit in base al valore page_event.

| Tipo di hit | Valore `page_event` | Valore `post_page_event` |
| --- | --- | --- |
| Visualizzazioni pagina | 0: tutte le chiamate di visualizzazione pagina e `trackState` chiamate dall&#39;SDK per dispositivi mobili | Stesso valore di `page_event` |
| Tracciamento dei collegamenti | 10: Collegamenti personalizzati e `trackAction` chiamate nell&#39;SDK per dispositivi mobili<br>11: Collegamenti di download<br>12: Collegamenti di uscita | 100: collegamenti personalizzati e chiamate `trackAction` nell&#39;SDK per dispositivi mobili<br>101: Collegamenti di download<br>102: collegamenti di uscita |
| Video su Milestone | 31: Inizio elemento multimediale<br>32: aggiornamenti elemento multimediale (nessuna altra elaborazione variabile)<br>33: aggiornamenti elemento multimediale (con altre variabili) | 76: Avvio file multimediale<br>77: aggiornamenti file multimediali (nessuna altra elaborazione variabile)<br>78: aggiornamenti file multimediali (con altre variabili) |
| Video Heartbeat | 50: Avvio del flusso multimediale (non Primetime)<br>51: Chiusura del flusso multimediale (non Primetime)<br>52: Scrubbing del flusso multimediale (non Primetime)<br>53: Mantenimento del flusso multimediale (non Primetime)<br>54: Avvio dell&#39;annuncio del flusso multimediale (non Primetime)<br>55: Chiusura dell&#39;annuncio del flusso multimediale (non Primetime)<br>56: Scrubbing dell&#39;annuncio del flusso multimediale (non Primetime)<br>60: Avvio del flusso multimediale Primetime<br>61: Chiusura del flusso multimediale di Primetime<br>62: scrubbing del flusso multimediale Primetime<br>63: il flusso multimediale Primetime resta attivo<br>64: inizio annuncio flusso multimediale Primetime<br>65: chiusura annuncio flusso multimediale Primetime<br>66: scrubbing annuncio flusso multimediale Primetime | Stesso valore di `page_event` |
| Sondaggio | 40: qualsiasi chiamata generata dal sondaggio | 80: qualsiasi chiamata generata dal sondaggio |
| Analytics for Target | 70: hit include i dati dell’attività di Target | Stesso valore di `page_event` |
