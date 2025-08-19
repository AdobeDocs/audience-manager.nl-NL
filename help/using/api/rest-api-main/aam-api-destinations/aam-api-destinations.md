---
description: Methoden waarmee u programmatisch kunt werken met doelfuncties.
seo-description: Methods that let you work programmatically with destination features.
seo-title: Destination API Methods
solution: Audience Manager
title: API-doelmethoden
uuid: 048bcdb9-2b31-46f4-8b80-4ba25bf06640
feature: API
exl-id: 38dea854-2b7b-417e-9d56-919b65807628
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 0%

---

# API-doelmethoden {#destination-api-methods}

Methoden waarmee u programmatisch kunt werken met doelfuncties.

<!-- c_destinations_api.xml -->

In Audience Manager is een doel elk ander systeem (advertentieserver, [!DNL DSP], netwerk, uitwisseling, uw eigen cookie van de eerste partij, enz.) waarmee u gegevens wilt delen.

## Doeltypen: URL en cookie {#destination-types}

Hier worden de variabelen weergegeven die door de parameter `destinationType` worden gebruikt. Geef `push` of `ADS` op om te werken met een [!UICONTROL URL] of [!UICONTROL cookie destination] . U kunt [!UICONTROL server-to-server destinations] niet maken met de beschikbare doelmethoden van [!DNL API] .

<!-- r_destination_types.xml -->

| API-doeltype | UI-doeltype |
|---|---|
| `PUSH` | [!UICONTROL URL] |
| `ADS` | [!UICONTROL Cookie] |

>[!MORELIKETHIS]
>
>* [ hoe te om een Type van Bestemming te kiezen ](../../../features/destinations/destinations.md)
