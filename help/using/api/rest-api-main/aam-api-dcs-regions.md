---
description: Methoden waarmee u Audience Manager DCS-gebieden programmatisch kunt weergeven.
seo-description: Methods that let you programmatically list Audience Manager DCS regions.
seo-title: DCS Region API Methods
solution: Audience Manager
title: Methoden van DCS Region API
uuid: 00b70927-b3b7-46bb-8be1-37c6100ecf80
feature: API
exl-id: 3cd1700e-6914-46be-a0be-a870c472343e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '110'
ht-degree: 0%

---

# Methoden van DCS Region API {#dcs-region-api-methods}

Methoden waarmee u Audience Manager [!DNL DCS] -gebieden programmatisch kunt weergeven.

<!-- c_rest_api_regions.xml -->

Voor een lijst van gebieden en hun overeenkomstige gehelen, zie [ DCS Gebied IDs, Locaties, en de Namen van de Gastheer ](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

## Een specifiek DCS-gebied weergeven {#list-specific-dcs-region}

Een `GET` -methode om een specifiek [!DNL DCS] -gebied weer te geven.

<!-- r_rest_api_regions_list_specific.xml -->

### Verzoek

`GET /v1/dcs-regions/`*`<id>`*

### Samplereactie

```
{ 
    "regionId" : <id>, 
    "location" : "<location>",
    "host" : "<host>",
    "code" : "<code>",
    "status" : "ACTIVE" | "INACTIVE",
    "createTime" : long of milliseconds since epoch,
    "updateTime" : long of milliseconds since epoch,
    "crUID" : <userId who created>,
    "upUID" : <userId who updated>
  }
```

Retourneert `200 OK` indien gelukt.

Voor een lijst van gebieden en hun overeenkomstige gehelen, zie [ DCS Gebied IDs, Locaties, en de Namen van de Gastheer ](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

## DCS-gebieden weergeven {#list-dcs-regions}

Een `GET` -methode om [!DNL DCS] -gebieden weer te geven.

<!-- r_rest_api_regions_list.xml -->

### Verzoek

`GET /v1/dcs-regions/`

### Samplereactie

```
[
  { 
    "regionId" : <id>, 
    "location" : "<location>",
    "host" : "<host>",
    "code" : "<code> # APSE, USE, etc,
    "status" : "ACTIVE" | "INACTIVE",
    "createTime" : long of milliseconds since epoch,
    "updateTime" : long of milliseconds since epoch,
    "crUID" : <userId who created>,
    "upUID" : <userId who updated>
  },
  ...
]
```

Retourneert `200 OK` indien gelukt.

Voor een lijst van gebieden en hun overeenkomstige gehelen, zie [ DCS Gebied IDs, Locaties, en de Namen van de Gastheer ](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).
