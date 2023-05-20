---
description: Methoden waarmee u programmatisch kunt werken met doelfuncties.
seo-description: Methods that let you work programmatically with destination features.
seo-title: Destination API Methods
solution: Audience Manager
title: API-methoden voor bestemmingen
uuid: 048bcdb9-2b31-46f4-8b80-4ba25bf06640
feature: API
exl-id: 38dea854-2b7b-417e-9d56-919b65807628
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 14%

---

# API-methoden voor bestemmingen  {#destination-api-methods}

Methoden waarmee u programmatisch kunt werken met doelfuncties.

<!-- c_destinations_api.xml -->

In Audience Manager, is een bestemming een ander systeem (en server, [!DNL DSP], ad netwerk, exchange, uw eigen cookie van de eerste partij, enz.) waarmee u data wilt delen.

## Doeltypen: URL en cookie {#destination-types}

Hier worden de variabelen weergegeven die door de `destinationType` parameter. Opgeven `push` of `ADS` om te werken met een [!UICONTROL URL] of [!UICONTROL cookie destination]. U kunt niet maken [!UICONTROL server-to-server destinations] met de beschikbare bestemming [!DNL API] methoden.

<!-- r_destination_types.xml -->

| API-doeltype | UI-doeltype |
|---|---|
| `PUSH` | [!UICONTROL URL] |
| `ADS` | [!UICONTROL Cookie] |

>[!MORELIKETHIS]
>
>* [Hoe te om een Type van Bestemming te kiezen](../../../features/destinations/destinations.md)

