---
description: Methoden waarmee u programmatisch kunt werken met doelfuncties.
seo-description: Methoden waarmee u programmatisch kunt werken met doelfuncties.
seo-title: 'API-methoden voor bestemmingen '
solution: Audience Manager
title: 'API-methoden voor bestemmingen '
uuid: 048bcdb9-2b31-46f4-8b80-4ba25bf06640
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '101'
ht-degree: 15%

---


# API-methoden voor bestemmingen {#destination-api-methods}

Methoden waarmee u programmatisch kunt werken met doelfuncties.

<!-- c_destinations_api.xml -->

In Audience Manager, is een bestemming elk ander systeem (ad server, [!DNL DSP], en netwerk, uitwisseling, uw eigen eersteklas koekje, enz.) waarmee u data wilt delen.

## Doeltypen: URL en cookie {#destination-types}

Hiermee geeft u de variabelen weer die door de parameter `destinationType` worden gebruikt. Geef `push` of `ADS` op om met een [!UICONTROL URL] of [!UICONTROL cookie destination] te werken. U kunt geen [!UICONTROL server-to-server destinations] met de beschikbare bestemmings [!DNL API] methodes tot stand brengen.

<!-- r_destination_types.xml -->

| API-doeltype | UI-doeltype |
|---|---|
| `PUSH` | [!UICONTROL URL] |
| `ADS` | [!UICONTROL Cookie] |

>[!MORELIKETHIS]
>
>* [Hoe te om een Type van Bestemming te kiezen](../../../features/destinations/destinations.md)

