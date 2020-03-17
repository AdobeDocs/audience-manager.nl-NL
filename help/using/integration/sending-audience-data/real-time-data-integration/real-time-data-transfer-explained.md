---
description: Een algemeen overzicht van hoe de Manager van het Publiek gegevensoverdrachten in real time met een derdeinhoudsleverancier uitvoert.
seo-description: Een algemeen overzicht van hoe de Manager van het Publiek gegevensoverdrachten in real time met een derdeinhoudsleverancier uitvoert.
seo-title: Real-Time Data Transfer Process beschreven
solution: Audience Manager
title: Real-Time Data Transfer Process beschreven
uuid: b68781b3-0b7a-442d-8e34-2db2474849a4
translation-type: tm+mt
source-git-commit: ea95df8531c00c183f22b09a4a78fc6b35ee279d

---


# Real-Time Data Transfer Process beschreven{#real-time-data-transfer-process-described}

Een algemeen overzicht van hoe de Manager van het Publiek gegevensoverdrachten in real time met een derdeinhoudsleverancier uitvoert.

<!-- real-time-data-transfer-explained.xml -->

## Real-Time gegevensoverdrachten

In real time gegevensoverdrachten verzenden en ontvangen segment IDs als gebruikersbezoeken of voeren actie op uw plaats. Over het algemeen zijn synchrone gegevensoverdrachten handig wanneer u gebruikers meteen moet kwalificeren of segmenteren terwijl ze door uw voorraad navigeren.

## Stappen voor gegevensintegratie

Het integratieproces van gegevens in real time werkt als volgt:

1. Een gebruiker bezoekt de plaats van een klant die de code van de Manager van de Publiek bevat.
1. Audience Manager laadt een iframe en roept onze [!UICONTROL Data Collection Server] ( [!UICONTROL DCS]) aan.
1. De [!UICONTROL DCS] vraag de derdenserver (in echt - tijd) om te controleren of heeft de verkoper om het even welke segmentinformatie over de gebruiker.
1. De inhoudsleverancier keert segmentinformatie over die gebruiker aan de Manager van het Publiek terug.
1. De Manager van het publiek ontvangt deze segmentinformatie en stelt het beschikbaar voor het richten en het bouwen van nieuwe eigenschappen en segmenten.

![](assets/rt_reduce70.png)