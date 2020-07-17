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

Methoden waarmee u programmatisch [!DNL DCS] gebieden van Audience Managers kunt weergeven.

<!-- c_rest_api_regions.xml -->

Voor een lijst van gebieden en hun overeenkomstige gehelen, zie [DCS Gebied IDs, Locaties, en de Namen](../../api/dcs-intro/dcs-api-reference/dcs-regions.md)van de Gastheer.

## Een specifiek DCS-gebied weergeven {#list-specific-dcs-region}

Een `GET` methode om een bepaald [!DNL DCS] gebied weer te geven.

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

Een `GET` methode om [!DNL DCS] gebieden weer te geven.

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
