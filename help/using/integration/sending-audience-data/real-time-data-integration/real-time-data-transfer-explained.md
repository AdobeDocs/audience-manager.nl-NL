---
description: Een algemeen overzicht van hoe de Audience Manager gegevensoverdrachten in real time met een derdeinhoudsleverancier uitvoert.
seo-description: Een algemeen overzicht van hoe de Audience Manager gegevensoverdrachten in real time met een derdeinhoudsleverancier uitvoert.
seo-title: Real-Time Data Transfer Process beschreven
solution: Audience Manager
title: Real-Time Data Transfer Process beschreven
uuid: b68781b3-0b7a-442d-8e34-2db2474849a4
feature: Inbound Data Transfers
translation-type: tm+mt
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 0%

---


# Real-Time Data Transfer Process Descripted{#real-time-data-transfer-process-described}

Een algemeen overzicht van hoe de Audience Manager gegevensoverdrachten in real time met een derdeinhoudsleverancier uitvoert.

<!-- real-time-data-transfer-explained.xml -->

## Real-Time gegevensoverdrachten

In real time gegevensoverdrachten verzenden en ontvangen segment IDs als gebruikersbezoeken of voeren actie op uw plaats. Over het algemeen zijn synchrone gegevensoverdrachten handig wanneer u gebruikers meteen moet kwalificeren of segmenteren terwijl ze door uw voorraad navigeren.

## Stappen voor gegevensintegratie

Het integratieproces van gegevens in real time werkt als volgt:

1. Een gebruiker bezoekt de plaats van een klant die Audience Manager code bevat.
1. Audience Manager laadt een iframe en roept [!UICONTROL Data Collection Server] ( [!DNL DCS]) aan.
1. [!DNL DCS] roept de server van de derde (in echt - tijd) om te controleren of heeft de verkoper om het even welke segmentinformatie over de gebruiker.
1. De inhoudsleverancier keert segmentinformatie over die gebruiker aan Audience Manager terug.
1. Audience Manager ontvangt deze segmentinformatie en stelt het beschikbaar voor het richten en het bouwen van nieuwe eigenschappen en segmenten.

![](assets/rt_reduce70.png)