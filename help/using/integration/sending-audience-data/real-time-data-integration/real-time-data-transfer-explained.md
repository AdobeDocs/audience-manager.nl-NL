---
description: Een algemeen overzicht van hoe Audience Manager realtime gegevensoverdracht uitvoert met een externe contentprovider.
seo-description: A general overview of how Audience Manager performs real-time data transfers with a third-party content provider.
seo-title: Real-Time Data Transfer Process Described
solution: Audience Manager
title: Real-Time Data Transfer Process beschreven
uuid: b68781b3-0b7a-442d-8e34-2db2474849a4
feature: Inbound Data Transfers
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 0%

---


# Real-Time Data Transfer Process beschreven{#real-time-data-transfer-process-described}

Een algemeen overzicht van hoe Audience Manager realtime gegevensoverdracht uitvoert met een externe contentprovider.

<!-- real-time-data-transfer-explained.xml -->

## Real-Time gegevensoverdrachten

In real time gegevensoverdrachten verzenden en ontvangen segment IDs als gebruikersbezoeken of voeren actie op uw plaats. Over het algemeen zijn synchrone gegevensoverdrachten handig wanneer u gebruikers meteen moet kwalificeren of segmenteren terwijl ze door uw voorraad navigeren.

## Stappen voor gegevensintegratie

Het proces van de gegevensintegratie in real time werkt als volgt:

1. Een gebruiker bezoekt de site van een klant die Audience Manager-code bevat.
1. Audience Manager laadt een iframe en roept het [!UICONTROL Data Collection Server] ( [!DNL DCS] ) aan.
1. [!DNL DCS] roept de server van de derde (in echt - tijd) om te controleren of de verkoper om het even welke segmentinformatie over de gebruiker heeft.
1. De inhoudsprovider retourneert gesegmenteerde informatie over die gebruiker naar Audience Manager.
1. Audience Manager ontvangt deze segmentinformatie en stelt deze beschikbaar voor het richten en het bouwen van nieuwe eigenschappen en segmenten.

![](assets/rt_reduce70.png)