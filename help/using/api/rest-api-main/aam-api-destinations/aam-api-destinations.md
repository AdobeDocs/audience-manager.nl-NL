---
description: Methoden waarmee u programmatisch kunt werken met doelfuncties.
seo-description: Methoden waarmee u programmatisch kunt werken met doelfuncties.
seo-title: API-doelmethoden
solution: Audience Manager
title: API-doelmethoden
uuid: 048bcdb9-2b31-46f4-8b80-4ba25bf06640
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '101'
ht-degree: 0%

---


# API-doelmethoden {#destination-api-methods}

Methoden waarmee u programmatisch kunt werken met doelfuncties.

<!-- c_destinations_api.xml -->

In Audience Manager, is een bestemming om het even welk ander systeem (ad server, [!DNL DSP], en netwerk, uitwisseling, uw eigen eerstepartijkoekje, enz.) waarmee u gegevens wilt delen.

## Doeltypen: URL en cookie {#destination-types}

Hier worden de variabelen weergegeven die door de `destinationType` parameter worden gebruikt. Geef op `push` of `ADS` om met een [!UICONTROL URL] of [!UICONTROL cookie destination]. U kunt niet maken [!UICONTROL server-to-server destinations] met de beschikbare [!DNL API] doelmethoden.

<!-- r_destination_types.xml -->

| API-doeltype | UI-doeltype |
|---|---|
| `PUSH` | [!UICONTROL URL] |
| `ADS` | [!UICONTROL Cookie] |

>[!MORELIKETHIS]
>
>* [Hoe te om een Type van Bestemming te kiezen](../../../features/destinations/destinations.md)

