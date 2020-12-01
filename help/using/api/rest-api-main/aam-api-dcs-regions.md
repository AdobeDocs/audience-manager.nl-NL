---
description: Methoden waarmee u DCS-gebieden van Audience Managers programmatisch kunt weergeven.
seo-description: Methoden waarmee u DCS-gebieden van Audience Managers programmatisch kunt weergeven.
seo-title: API-methoden voor DCS-regio’s
solution: Audience Manager
title: API-methoden voor DCS-regio’s
uuid: 00b70927-b3b7-46bb-8be1-37c6100ecf80
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 9%

---


# API-methoden voor DCS-regio’s {#dcs-region-api-methods}

Methoden waarmee u programmatisch Audience Manager [!DNL DCS] gebieden kunt vermelden.

<!-- c_rest_api_regions.xml -->

Voor een lijst van gebieden en hun overeenkomstige gehelen, zie [DCS Gebied IDs, Locaties, en de Namen van de Gastheer](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

## Een specifiek DCS-gebied {#list-specific-dcs-region} weergeven

Een methode `GET` om een specifiek [!DNL DCS] gebied te vermelden.

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

Voor een lijst van gebieden en hun overeenkomstige gehelen, zie [DCS Gebied IDs, Locaties, en de Namen van de Gastheer](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

## DCS-gebieden {#list-dcs-regions} weergeven

Een `GET` methode om [!DNL DCS] gebieden te vermelden.

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

Voor een lijst van gebieden en hun overeenkomstige gehelen, zie [DCS Gebied IDs, Locaties, en de Namen van de Gastheer](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).
