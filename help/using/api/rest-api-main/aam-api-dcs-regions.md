---
description: Methoden waarmee u programmatically van de Manager DCS van de Audience- gebieden een lijst kunt maken.
seo-description: Methoden waarmee u programmatically van de Manager DCS van de Audience- gebieden een lijst kunt maken.
seo-title: Methoden van DCS Region API
solution: Audience Manager
title: Methoden van DCS Region API
uuid: 00b70927-b3b7-46bb-8be1-37c6100ecf80
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Methoden van DCS Region API {#dcs-region-api-methods}

Methoden waarmee u programmatisch [!UICONTROL DCS] gebieden van de Manager van de Publiek kunt vermelden.

<!-- c_rest_api_regions.xml -->

Voor een lijst van gebieden en hun overeenkomstige gehelen, zie [DCS Gebied IDs, Locaties, en de Namen](../../api/dcs-intro/dcs-api-reference/dcs-regions.md)van de Gastheer.

## Een specifiek DCS-gebied weergeven {#list-specific-dcs-region}

Een `GET` methode om een bepaald [!UICONTROL DCS] gebied weer te geven.

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

Voor een lijst van gebieden en hun overeenkomstige gehelen, zie [DCS Gebied IDs, Locaties, en de Namen](../../api/dcs-intro/dcs-api-reference/dcs-regions.md)van de Gastheer.

## DCS-gebieden weergeven {#list-dcs-regions}

Een `GET` methode om [!UICONTROL DCS] gebieden weer te geven.

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

Voor een lijst van gebieden en hun overeenkomstige gehelen, zie [DCS Gebied IDs, Locaties, en de Namen](../../api/dcs-intro/dcs-api-reference/dcs-regions.md)van de Gastheer.
